---
title: IS_OBJECTSIGNED (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/10/2016
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- IS_OBJECTSIGNED
- IS_OBJECTSIGNED_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- IS_OBJECTSIGNED function
ms.assetid: afbc4f7f-8266-4ee6-9802-14a2dbe69ef6
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e346fb803e18d9a43afe15984166985ff0a3e408
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="isobjectsigned-transact-sql"></a>IS_OBJECTSIGNED (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Indica se um objeto foi assinado por um determinado certificado ou chave assimétrica.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
IS_OBJECTSIGNED (   
'OBJECT', @object_id, @class, @thumbprint  
  )   
```  
  
## <a name="arguments"></a>Argumentos  
 **'OBJECT'**  
 O tipo de classe do protegível.  
  
 *@object_id*  
 O object_id do objeto que está sendo testado. *@object_id*é o tipo **int**.  
  
 *@class*  
 A classe do objeto:  
  
-   'certificado'  
  
-   'chave assimétrica'  
  
 *@class*é **sysname**.  
  
 *@thumbprint*  
 A impressão digital SHA do objeto. *@thumbprint*é o tipo **varbinary(32)**.  
  
## <a name="returned-types"></a>Tipos retornados  
 **int**  
  
## <a name="remarks"></a>Comentários  
 IS_OBJECTSIGNED retorna os seguintes valores:  
  
|Valor de retorno|Description|  
|------------------|-----------------|  
|NULL|O objeto não está assinado ou o objeto não é válido.|  
|0|O objeto foi assinado, mas a assinatura não é válida.|  
|1|O objeto foi assinado.|  
  
## <a name="permissions"></a>Permissões  
 Requer VIEW DEFINITION no certificado ou na chave assimétrica.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-displaying-extended-properties-on-a-database"></a>A. Exibindo propriedades estendidas em um banco de dados  
 O exemplo a seguir testa se a tabela spt_fallback_db do **mestre** banco de dados é assinado pelo certificado autenticado de esquema.  
  
```  
USE master;  
-- Declare a variable to hold a thumbprint and an object name  
DECLARE @thumbprint varbinary(20), @objectname sysname;  
  
-- Populate the thumbprint variable with the thumbprint of   
-- the master database schema signing certificate  
SELECT @thumbprint = thumbprint   
FROM sys.certificates   
WHERE name LIKE '%SchemaSigningCertificate%';  
  
-- Populate the object name variable with a table name in master  
SELECT @objectname = 'spt_fallback_db';  
  
-- Query to see if the table is signed by the thumbprint  
SELECT @objectname AS [object name],  
IS_OBJECTSIGNED(  
'OBJECT', OBJECT_ID(@objectname), 'certificate', @thumbprint  
) AS [Is the object signed?] ;  
```  
  
## <a name="see-also"></a>Consulte também  
 [fn_check_object_signatures &#40; Transact-SQL &#41;](../../relational-databases/system-functions/sys-fn-check-object-signatures-transact-sql.md)  
  
  
