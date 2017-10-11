---
title: KEY_GUID (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Key_GUID_TSQL
- Key_GUID
dev_langs:
- TSQL
helpviewer_keywords:
- symmetric keys [SQL Server], GUIDs
- KEY_GUID function
- GUIDs [SQL Server]
ms.assetid: 9246c7b2-7098-42c4-a222-cbf30267c46a
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3e167366e86cf10403abc6cafa894ad964c60733
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="keyguid-transact-sql"></a>KEY_GUID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna o GUID de uma chave simétrica no banco de dados.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Key_GUID( 'Key_Name' )  
```  
  
## <a name="arguments"></a>Argumentos  
 **'** *Key_Name* **'**  
 Nome de uma chave simétrica no banco de dados.  
  
## <a name="return-types"></a>Tipos de retorno  
 **uniqueidentifier**  
  
## <a name="remarks"></a>Comentários  
 Se um valor de identidade for especificado quando a chave é criada, seu GUID será um hash MD5 desse valor de identidade. Se nenhum valor de identidade for especificado, o servidor irá gerar o GUID.  
  
 Se a chave for uma chave temporária, o nome da chave deverá iniciar com um sinal de cerquilha (#).  
  
## <a name="permissions"></a>Permissões  
 Como as chaves temporárias estão disponíveis somente na sessão em que foram criadas, nenhuma permissão é necessária para acessá-las. Para acessar uma chave que não é temporária, o chamador requer algumas permissões na chave e não deve ter a permissão VIEW negada na chave.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir retorna o GUID de uma chave simétrica chamada `ABerglundKey1`.  
  
```  
SELECT Key_GUID('ABerglundKey1');  
```  
  
## <a name="see-also"></a>Consulte também  
 [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [symmetric_keys &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql.md)   
 [key_encryptions &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-key-encryptions-transact-sql.md)  
  
  