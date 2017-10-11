---
title: PWDENCRYPT (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- PWDENCRYPT
- PWDENCRYPT_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- PWDENCRYPT function [Transact-SQL]
ms.assetid: 333e9a43-1099-4b9b-b941-4b0b016f47f3
caps.latest.revision: 9
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: dcae01f4b56e022f3b5966acd33877c851d9ae05
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="pwdencrypt-transact-sql"></a>PWDENCRYPT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna o hash de senha do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do valor de entrada que usa a versão atual do algoritmo de hash de senha.  
  
 PWDENCRYPT é uma função mais antiga e talvez não tenha suporte em uma versão futura do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Use [HASHBYTES](../../t-sql/functions/hashbytes-transact-sql.md) em vez disso. HASHBYTES fornece mais algoritmos de hash.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
PWDENCRYPT ( 'password' )  
```  
  
## <a name="arguments"></a>Argumentos  
 *senha*  
 É a senha a ser criptografada. *senha* é **sysname**.  
  
## <a name="return-types"></a>Tipos de retorno  
 **varbinary(128)**  
  
## <a name="permissions"></a>Permissões  
 PWDENCRYPT está disponível para o público.  
  
## <a name="see-also"></a>Consulte também  
 [Funções de segurança &#40;Transact-SQL&#41;](../../t-sql/functions/security-functions-transact-sql.md)   
 [PWDCOMPARE &#40; Transact-SQL &#41;](../../t-sql/functions/pwdcompare-transact-sql.md)  
  
  