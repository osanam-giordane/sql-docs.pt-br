---
title: Especificando operadores aritméticos em consultas XPath (SQLXML 4.0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- arithmetic operators
- XPath operators [SQLXML]
- XPath queries [SQLXML], arithmetic operators
- operators [SQLXML]
ms.assetid: fdfbc87d-759f-4abc-acf5-a21de01f78d3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2ca89efb197083b095ee7b1db18d3114525084a5
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66012473"
---
# <a name="specifying-arithmetic-operators-in-xpath-queries-sqlxml-40"></a>Especificando operadores aritméticos em consultas XPath (SQLXML 4.0)
  O exemplo a seguir mostra como são especificados operadores aritméticos em consultas XPath. A consulta XPath deste exemplo é especificada com relação ao esquema de mapeamento contido em SampleSchema1.xml. Para obter informações sobre esse esquema de exemplo, consulte [anotado de exemplo de esquema XSD para exemplos de XPath &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-specify-the--arithmetic-operator"></a>A. Especifique o operador aritmético *.  
 Essa consulta XPath retorna  **\<OrderDetail >** elementos que satisfazem o predicado especificado:  
  
```  
/child::OrderDetail[@UnitPrice * @Quantity = 12.350]  
```  
  
 Na consulta, `child` é o eixo e `OrderDetail` é o teste de nó (TRUE se **OrderDetail** é um  **\<nó de elemento >** , porque o  **\< elemento >** nó é o nó principal para o `child` eixo). Para todos os  **\<OrderDetail >** nós de elemento, o teste no predicado é aplicado, e somente os nós que satisfazem a condição são retornados.  
  
> [!NOTE]  
>  Os números em XPath são números de pontos flutuantes de precisão dupla e a comparação de números de pontos flutuantes como no exemplo provoca arredondamento.  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a>Para testar a consulta XPath com relação ao esquema de mapeamento  
  
1.  Cópia de [exemplos de código de esquema](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto. Salve o arquivo como SampleSchema1.xml.  
  
2.  Crie o modelo a seguir (ArithmeticOperatorAe.xml) e salve-o no diretório em que SampleSchema1.xml foi salvo.  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /OrderDetail[@UnitPrice * @OrderQty = 12.350]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo. Também é possível especificar um caminho absoluto, por exemplo:  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.  
  
     Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4.0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).  
  
```  
Here is the partial result set of the template execution:    
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-710" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
   ...  
</ROOT>  
```  
  
  
