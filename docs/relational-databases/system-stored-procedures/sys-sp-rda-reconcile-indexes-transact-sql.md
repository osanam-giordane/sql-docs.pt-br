---
title: sys.sp_rda_reconcile_indexes (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: language-reference
f1_keywords:
- sp_rda_reconcile_indexes
- sp_rda_reconcile_indexes_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_rda_reconcile_indexes stored procedure
ms.assetid: 96b31ab9-bf84-46d6-9990-81f5c51f885a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0e439a04e55816f25cae318a8451452bf09dee0b
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67905041"
---
# <a name="syssprdareconcileindexes-transact-sql"></a>sys.sp_rda_reconcile_indexes (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Enfileira uma tarefa de esquema para reconciliar índices na tabela remota. Depois que essa tarefa for concluída com êxito, a tabela remota tem os mesmos índices que existem na tabela local habilitada para Stretch.  
  
 Se não houver outra tarefa em fila para reconciliar índices quando você chama **sp_rda_reconcile_indexes**, esse procedimento armazenado não enfileira uma tarefa duplicada.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_rda_reconcile_indexes [@objname = ] 'objname'  
  
```  
  
## <a name="arguments"></a>Argumentos  
 [@objname = ] *'objname'*  
 É o nome qualificado ou não qualificadas da tabela habilitados para Stretch para a qual você deseja reconciliar índices. As aspas são necessárias apenas se você especificar um objeto qualificado.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou > 0 (falha)  
  
## <a name="see-also"></a>Consulte também  
 [Stretch Database](../../sql-server/stretch-database/stretch-database.md)  
  
  
