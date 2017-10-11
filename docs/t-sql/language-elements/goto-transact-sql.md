---
title: GOTO (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- GOTO
- GOTO_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- skipping statements
- Transact-SQL statements, skipping
- labels [SQL Server]
- statements [SQL Server], skipping
- GOTO statement
ms.assetid: 589b6f8e-dc80-416f-9e74-48bed5337f58
caps.latest.revision: 33
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4c5614843f961d1ff3188ba1f3caa589d77c4735
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="goto-transact-sql"></a>GOTO (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Altera o fluxo de execução para um rótulo. A instrução ou as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] que seguem GOTO são ignoradas e o processamento continua no rótulo. As instruções GOTO e os rótulos podem ser usados em qualquer lugar em um procedimento, lote ou bloco de instruções. As instruções GOTO podem ser aninhadas.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Define the label:   
label:   
Alter the execution:  
GOTO label   
```  
  
## <a name="arguments"></a>Argumentos  
 *rótulo*  
 É o ponto após o qual o processamento inicia se o destino de um GOTO for esse rótulo. Os rótulos devem seguir as regras para [identificadores](../../relational-databases/databases/database-identifiers.md). Um rótulo pode ser usado como um método de comentário se GOTO for usado.  
  
## <a name="remarks"></a>Comentários  
 GOTO pode existir em instruções de controle de fluxo condicional, blocos de instruções ou procedimentos, mas não pode ir para um rótulo fora do lote. A ramificação de GOTO pode ir para um rótulo definido antes ou depois de GOTO.  
  
## <a name="permissions"></a>Permissões  
 As permissões de GOTO são padronizadas para qualquer usuário válido.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir mostra como usar `GOTO` como um mecanismo de ramificação.  
  
```  
DECLARE @Counter int;  
SET @Counter = 1;  
WHILE @Counter < 10  
BEGIN   
    SELECT @Counter  
    SET @Counter = @Counter + 1  
    IF @Counter = 4 GOTO Branch_One --Jumps to the first branch.  
    IF @Counter = 5 GOTO Branch_Two  --This will never execute.  
END  
Branch_One:  
    SELECT 'Jumping To Branch One.'  
    GOTO Branch_Three; --This will prevent Branch_Two from executing.  
Branch_Two:  
    SELECT 'Jumping To Branch Two.'  
Branch_Three:  
    SELECT 'Jumping To Branch Three.';  
```  
  
## <a name="see-also"></a>Consulte também  
 [Linguagem de controle de fluxo &#40; Transact-SQL &#41;](~/t-sql/language-elements/control-of-flow.md)   
 [BEGIN... FINAL &#40; Transact-SQL &#41;](../../t-sql/language-elements/begin-end-transact-sql.md)   
 [QUEBRA &#40; Transact-SQL &#41;](../../t-sql/language-elements/break-transact-sql.md)   
 [Continuar &#40; Transact-SQL &#41;](../../t-sql/language-elements/continue-transact-sql.md)   
 [IF... OUTRA &#40; Transact-SQL &#41;](../../t-sql/language-elements/if-else-transact-sql.md)   
 [WAITFOR &#40; Transact-SQL &#41;](../../t-sql/language-elements/waitfor-transact-sql.md)   
 [WHILE &#40;Transact-SQL&#41;](../../t-sql/language-elements/while-transact-sql.md)  
  
  
