---
title: 'Excluindo elementos de esquema do documento XML resultante usando sql: mapped (SQLXML 4.0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- annotated XSD schemas, excluding schema elements
- mapped annotation
- table mapping [SQLXML], excluding schema elements
- sql:mapped
- excluding schema elements
- element mapping [SQLXML], excluding schema elements
- column mapping [SQLXML]
- XSD schemas [SQLXML], excluding schema elements
- attribute mapping [SQLXML], excluding schema elements
- table/view mapping [SQLXML], excluding schema elements
ms.assetid: 7d2649dd-0038-4a2c-b16d-f80f7c306966
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 865a9af892f948e77aa593d3713766e7860349b0
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66013859"
---
# <a name="excluding-schema-elements-from-the-resulting-xml-document-using-sqlmapped-sqlxml-40"></a>Excluindo elementos de esquema do documento XML resultante usando sql:mapped (SQLXML 4.0)
  Todo elemento e atributo no esquema XSD é mapeado para uma tabela/exibição e uma coluna do banco de dados devido ao mapeamento padrão. Se desejar criar um elemento no esquema XSD que não é mapeado para nenhuma tabela (exibição) ou coluna do banco de dados e que não aparece no XML, é possível especificar a anotação `sql:mapped`.  
  
 A anotação `sql:mapped` é especialmente útil quando o esquema não pode ser modificado ou quando o esquema é usado para validar XML de outras fontes e ainda contém dados que não estão armazenados em seu banco de dados. A anotação `sql:mapped` difere de `sql:is-constant` pois os elementos e atributos não mapeados não são exibidos no documento XML.  
  
 A anotação `sql:mapped` usa um valor Booliano (0 = false, 1 = true). Os valores aceitáveis são 0, 1, true e false.  
  
## <a name="examples"></a>Exemplos  
 Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos. Para obter mais informações, consulte [requisitos para executar exemplos do SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).  
  
### <a name="a-specifying-the-sqlmapped-annotation"></a>A. Especificando a anotação sql:mapped  
 Suponha que você tenha um esquema XSD de alguma outra origem. Esse esquema XSD consiste em uma  **\<Person. Contact >** elemento com **ContactID**, **FirstName**, **LastName**, e **HomeAddress** atributos.  
  
 Mapear esse esquema XSD para a tabela Person. Contact no banco de dados AdventureWorks `sql:mapped` for especificado em de **HomeAddress** atributo porque a tabela Employees não armazena os endereços residenciais dos funcionários. Como resultado, este atributo não é mapeado para o banco de dados e não é retornado no documento XML resultante quando uma consulta XPath é especificada com relação ao esquema de mapeamento.  
  
 O mapeamento padrão é executado para o restante do esquema. O  **\<Person. Contact >** elemento é mapeado para a tabela Person. Contact e todos os atributos são mapeados para as colunas com o mesmo nome na tabela Person. Contact.  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:attribute name="ContactID"   type="xsd:string"/>  
      <xsd:attribute name="FirstName"    type="xsd:string" />  
      <xsd:attribute name="LastName"     type="xsd:string" />  
      <xsd:attribute name="HomeAddress" type="xsd:string"   
                     sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a>Para testar uma consulta XPath de exemplo com relação ao esquema  
  
1.  Copie o código de esquema acima e cole-o em um arquivo de texto. Salve o arquivo como sql-mapped.xml.  
  
2.  Copie o modelo a seguir e cole-o em um arquivo de texto. Salve o arquivo como sql-mappedT.xml no mesmo diretório em que você salvou sql-mapped.xml.  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-mapped.xml">  
            /Person.Contact[@ContactID < 10]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     O caminho do diretório especificado para o esquema de mapeamento (MySchema.xml) é relativo ao diretório onde o modelo foi salvo. Também é possível especificar um caminho absoluto, por exemplo:  
  
    ```  
    mapping-schema="C:\MyDir\sql-mapped.xml"  
    ```  
  
3.  Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.  
  
     Para obter mais informações, consulte [usando o ADO para executar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).  
  
 Este é o conjunto de resultados:  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel" />   
  <Person.Contact ContactID="3" FirstName="Kim" LastName="Abercrombie" />   
  <Person.Contact ContactID="4" FirstName="Humberto" LastName="Acevedo" />   
  <Person.Contact ContactID="5" FirstName="Pilar" LastName="Ackerman" />   
  <Person.Contact ContactID="6" FirstName="Frances" LastName="Adams" />   
  <Person.Contact ContactID="7" FirstName="Margaret" LastName="Smith" />   
  <Person.Contact ContactID="8" FirstName="Carla" LastName="Adams" />   
  <Person.Contact ContactID="9" FirstName="Jay" LastName="Adams" />   
</ROOT>  
```  
  
 Observe que ContactID, FirstName e LastName estão presentes, mas HomeAddress não está, pois o esquema de mapeamento especificou 0 para o atributo `sql:mapped`.  
  
## <a name="see-also"></a>Consulte também  
 [Mapeamento padrão dos atributos e elementos XSD para tabelas e colunas &#40;SQLXML 4.0&#41;](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
  
  
