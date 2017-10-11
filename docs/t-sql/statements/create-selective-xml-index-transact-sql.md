---
title: "Criar índice XML SELETIVO (Transact-SQL) | Microsoft Docs"
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
ms.assetid: 1d769f62-f646-4057-b93a-bf5f90e935ed
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 29a2a6eaec3ebbbafef0fcead331835921c7da44
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="create-selective-xml-index-transact-sql"></a>CREATE SELECTIVE XML INDEX (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Cria um novo índice XML seletivo na tabela especificada e na coluna XML. Os índices XML seletivos melhoram o desempenho da indexação e consulta XML indexando somente o subconjunto de nós normalmente consultado. Também é possível criar índices XML seletivos secundários. Para obter informações, consulte [Create, Alter e Drop índices XML seletivos secundários](../../relational-databases/xml/create-alter-and-drop-secondary-selective-xml-indexes.md).  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
CREATE SELECTIVE XML INDEX index_name  
    ON <table_object> (xml_column_name)  
    [WITH XMLNAMESPACES (<xmlnamespace_list>)]  
    FOR (<promoted_node_path_list>)  
    [WITH (<index_options>)]  
  
<table_object> ::=  
 { [database_name. [schema_name ] . | schema_name. ] table_name }  
  
<promoted_node_path_list> ::=   
<named_promoted_node_path_item> [, <promoted_node_path_list>]  
  
<named_promoted_node_path_item> ::=   
<path_name> = <promoted_node_path_item>  
  
<promoted_node_path_item>::=  
<xquery_node_path_item> | <sql_values_node_path_item>  
  
<xquery_node_path_item> ::=   
<node_path> [AS XQUERY <xsd_type_or_node_hint>] [SINGLETON]  
  
<xsd_type_or_node_hint> ::=   
[<xsd_type>] [MAXLENGTH(x)] | node()  
  
<sql_values_node_path_item> ::=  
<node_path> AS SQL <sql_type> [SINGLETON]  
  
<node_path> ::=   
character_string_literal  
  
<xsd_type> ::=   
character_string_literal  
  
<sql_type> ::=   
identifier  
  
<path_name> ::=   
identifier  
  
<xmlnamespace_list> ::=   
<xmlnamespace_item> [, <xmlnamespace_list>]  
  
<xmlnamespace_item> ::=   
<xmlnamespace_uri> AS <xmlnamespace_prefix>  
  
<xml_namespace_uri> ::=   
character_string_literal  
  
<xml_namespace_prefix> ::=   
identifier  
  
<index_options> ::=   
(   
  | PAD_INDEX  = { ON | OFF }  
  | FILLFACTOR = fillfactor  
  | SORT_IN_TEMPDB = { ON | OFF }  
  | IGNORE_DUP_KEY = OFF  
  | DROP_EXISTING = { ON | OFF }  
  | ONLINE = OFF  
  | ALLOW_ROW_LOCKS = { ON | OFF }  
  | ALLOW_PAGE_LOCKS = { ON | OFF }  
  | MAXDOP = max_degree_of_parallelism  
)  
```  
  
##  <a name="Arguments"></a> Argumentos  
 *index_name*  
 Nome do novo índice a ser criado. Os nomes de índice devem ser exclusivos dentro de uma tabela, mas não precisam ser exclusivos dentro de um banco de dados. Os nomes de índice devem seguir as regras de [identificadores](../../relational-databases/databases/database-identifiers.md).  
  
 *\<table_object >* é a tabela que contém a coluna XML para indexação. Use um destes formatos:  
  
-   `database_name.schema_name.table_name`  
  
-   `database_name..table_name`  
  
-   `schema_name.table_name`  
  
-   `table_name`  
  
 *xml_column_name*  
 Nome da coluna XML que contém os caminhos a serem indexados.  
  
 [WITH XMLNAMESPACES **(**\<xmlnamespace_list >**)**] é a lista de namespaces usados pelos caminhos a serem indexados. Para obter informações sobre a sintaxe da cláusula WITH XMLNAMESPACES, consulte [WITH XMLNAMESPACES &#40; Transact-SQL &#41; ](../../t-sql/xml/with-xmlnamespaces.md).  
  
 PARA **(**\<promoted_node_path_list >**)** é a lista de caminhos a serem indexados com dicas de otimização opcionais. Para obter informações sobre os caminhos e as dicas de otimização que você pode especificar na instrução CREATE ou ALTER, consulte [especificar caminhos e dicas de otimização para índices XML seletivos](../../relational-databases/xml/specify-paths-and-optimization-hints-for-selective-xml-indexes.md).  
  
 COM  *\<index_options >* para obter informações sobre as opções de índice, consulte [CREATE XML INDEX &#40; Índices XML seletivos &#41; ](../../t-sql/statements/create-xml-index-selective-xml-indexes.md).  
  
## <a name="best-practices"></a>Práticas recomendadas  
 Na maioria das vezes, crie um índice XML seletivo, em vez de um índice XML comum, para obter melhor desempenho e um armazenamento mais eficiente. Entretanto, um índice XML seletivo não é recomendado quando uma das seguintes condições é verdadeira:  
  
-   É necessário mapear um grande número de caminhos do nó.  
  
-   É necessário dar suporte a consultas de elementos desconhecidos ou elementos em um local desconhecido.  
  
## <a name="limitations-and-restrictions"></a>Limitações e restrições  
 Para obter informações sobre limitações e restrições, consulte [índices XML seletivos &#40; SXI &#41; ](../../relational-databases/xml/selective-xml-indexes-sxi.md).  
  
## <a name="security"></a>Segurança  
  
### <a name="permissions"></a>Permissões  
 Requer a permissão ALTER na tabela ou exibição. O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir mostra a sintaxe para criar um índice XML seletivo. Ele também mostra variações da sintaxe para descrever os caminhos a serem indexados, com dicas de otimização opcionais.  
  
```  
CREATE TABLE Tbl ( id INT PRIMARY KEY, xmlcol XML );  
GO  
CREATE SELECTIVE XML INDEX sxi_index  
ON Tbl(xmlcol)  
FOR(  
    pathab   = '/a/b' as XQUERY 'node()',  
    pathabc  = '/a/b/c' as XQUERY 'xs:double',   
    pathdtext = '/a/b/d/text()' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON,  
    pathabe = '/a/b/e' as SQL NVARCHAR(100)  
);  
```  
  
 O exemplo a seguir inclui uma cláusula WITH XMLNAMESPACES.  
  
```  
CREATE SELECTIVE XML INDEX on T1(C1)  
WITH XMLNAMESPACES ('http://www.tempuri.org/' as myns)  
FOR ( path1 = '/myns:book/myns:author/text()' );  
```  
  
## <a name="see-also"></a>Consulte também  
 [Índices XML Seletivos &#40;SXI&#41;](../../relational-databases/xml/selective-xml-indexes-sxi.md)   
 [Criar, alterar e remover índices XML seletivos](../../relational-databases/xml/create-alter-and-drop-selective-xml-indexes.md)   
 [Especificar caminhos e dicas de otimização para índices XML seletivos](../../relational-databases/xml/specify-paths-and-optimization-hints-for-selective-xml-indexes.md)  
  
  

