---
title: "REVOGAR permissões de coleção de esquema XML (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- REVOKE statement, XML schema collections
- XML schema collections [SQL Server], permissions
- schema collections [SQL Server], permissions
ms.assetid: 8ca0973c-30b2-4633-a165-c09b13cc81ae
caps.latest.revision: 22
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a4d7d530e89bdd3dcb320c4a08c340071b7faba3
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="revoke-xml-schema-collection-permissions-transact-sql"></a>Permissões de coleção de esquema REVOKE XML (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-pdw_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-pdw-md.md)]

  Revoga permissões concedidas ou negadas em uma coleção de esquemas XML.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
REVOKE [ GRANT OPTION FOR ] permission [ ,...n ] ON   
    XML SCHEMA COLLECTION :: [ schema_name . ]  
    XML_schema_collection_name  
    { TO | FROM } <database_principal> [ ,...n ]  
        [ CASCADE ]  
    [ AS <database_principal> ]   
  
<database_principal> ::=   
        Database_user   
    | Database_role   
    | Application_role   
    | Database_user_mapped_to_Windows_User   
    | Database_user_mapped_to_Windows_Group   
    | Database_user_mapped_to_certificate   
    | Database_user_mapped_to_asymmetric_key   
    | Database_user_with_no_login   
```  
  
## <a name="arguments"></a>Argumentos  
 *permissão*  
 Especifica uma permissão que pode ser revogada em uma coleção de esquemas XML. Para obter uma lista de permissões, consulte a seção Comentários mais adiante neste tópico.  
  
 COLEÇÃO de ESQUEMAS XML ON:: [ *schema_name***.** ] *XML_schema_collection_name*  
 Especifica a coleção de esquema XML na qual a permissão está sendo revogada. O qualificador de escopo (::) é necessário. Se *schema_name* não for especificado, o esquema padrão será usado. Se *schema_name* for especificado, o qualificador de escopo de esquema (.) é necessário.  
  
 GRANT OPTION  
 Indica que o direito de conceder a permissão especificada a outros principais será revogado. A permissão em si não será revogada.  
  
> [!IMPORTANT]  
>  Se a entidade de segurança tiver a permissão especificada sem a opção GRANT, a própria permissão será revogada.  
  
 CASCADE  
 Indica que a permissão que está sendo revogada também é revogada de outros principais aos quais ela foi concedida ou negada por esse principal.  
  
> [!CAUTION]  
>  A revogação em cascata de uma permissão WITH GRANT OPTION concedida revogará as opções GRANT e DENY dessa permissão.  
  
 {PARA | FROM} \< *database_principal*>  
 Especifica a entidade a partir da qual a permissão está sendo revogada.  
  
 AS \<database_principal > especifica uma entidade da qual o principal que executa esta consulta deriva seu direito de revogar a permissão.  
  
 *Database_user*  
 Especifica um usuário do banco de dados.  
  
 *Database_role*  
 Especifica uma função de banco de dados.  
  
 *Application_role*  
 Especifica uma função de aplicativo.  
  
 *Database_user_mapped_to_Windows_User*  
 Especifica um usuário do banco de dados mapeado para um usuário do Windows.  
  
 *Database_user_mapped_to_Windows_Group*  
 Especifica um usuário do banco de dados mapeado para um grupo do Windows.  
  
 *Database_user_mapped_to_certificate*  
 Especifica um usuário do banco de dados mapeado para um certificado.  
  
 *Database_user_mapped_to_asymmetric_key*  
 Especifica um usuário do banco de dados mapeado para uma chave assimétrica.  
  
 *Database_user_with_no_login*  
 Especifica um usuário do banco de dados sem nenhuma entidade de segurança correspondente no nível de servidor.  
  
## <a name="remarks"></a>Comentários  
 Informações sobre coleções de esquema XML são visíveis no [xml_schema_collections](../../relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql.md) exibição do catálogo.  
  
 A instrução falhará se CASCADE não for especificado ao revogar uma permissão de um principal ao qual ela foi concedida com GRANT OPTION especificado.  
  
 Uma coleção de esquema XML é um protegível em nível de esquema contido pelo esquema pai na hierarquia de permissões. As permissões mais específicas e limitadas que podem ser revogadas em uma coleção de esquema XML são listadas na tabela a seguir, junto com as permissões mais gerais que as incluem implicitamente.  
  
|Permissão de coleção de esquema XML|Indicado pela permissão de coleção de esquema XML|Implícito na permissão de esquema|  
|--------------------------------------|-------------------------------------------------|----------------------------------|  
|ALTER|CONTROL|ALTER|  
|CONTROL|CONTROL|CONTROL|  
|Execute|CONTROL|Execute|  
|REFERENCES|CONTROL|REFERENCES|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão CONTROL na coleção de esquema XML. Se você usar a opção AS, o principal especificado deve ser proprietário de uma coleção de esquema XML.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir revoga permissão `EXECUTE` na coleção de esquema XML `Invoices4` do usuário `Wanida`. A coleção de esquemas XML `Invoices4` está localizada dentro do esquema `Sales` do banco de dados `AdventureWorks2012`.  
  
 ```
 USE AdventureWorks2012;  
 REVOKE EXECUTE ON XML SCHEMA COLLECTION::Sales.Invoices4 FROM Wanida;  
 GO
 ```  
  
## <a name="see-also"></a>Consulte também  
 [CONCEDER permissões de coleção de esquemas XML &#40; Transact-SQL &#41;](../../t-sql/statements/grant-xml-schema-collection-permissions-transact-sql.md)   
 [Negar permissões de coleção de esquemas XML &#40; Transact-SQL &#41;](../../t-sql/statements/deny-xml-schema-collection-permissions-transact-sql.md)   
 [xml_schema_collections &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql.md)   
 [Criar COLEÇÃO de ESQUEMAS XML &#40; Transact-SQL &#41;](../../t-sql/statements/create-xml-schema-collection-transact-sql.md)   
 [Permissões &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [Entidades &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)  
  
  

