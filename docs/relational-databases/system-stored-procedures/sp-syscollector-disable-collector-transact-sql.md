---
title: sp_syscollector_disable_collector (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_syscollector_disable_collector_TSQL
- sp_syscollector_disable_collector
dev_langs:
- TSQL
helpviewer_keywords:
- data collector [SQL Server], stored procedures
- sp_syscollector_disable_collector
ms.assetid: 9ef4c85d-cca6-452d-94be-2be6f616c3d8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2d5ae3f6f130852611c57eebaffc452ae1424fd2
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68000847"
---
# <a name="spsyscollectordisablecollector-transact-sql"></a>sp_syscollector_disable_collector (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Desabilita o coletor de dados. Como há apenas um coletor de dados por servidor, nenhum parâmetro é necessário.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
dbo.sp_syscollector_disable_collector   
```  
  
## <a name="arguments"></a>Argumentos  
 Nenhum  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Comentários  
 Assume o coletor de dados no servidor como padrão.  
  
## <a name="permissions"></a>Permissões  
 É necessária a associação na função de banco de dados fixa **dc_admin** ou **dc_operator** (com a permissão EXECUTE) para executar esse procedimento.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir desabilita o coletor de dados.  
  
```  
EXEC dbo.sp_syscollector_disable_collector;  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Coleta de Dados](../../relational-databases/data-collection/data-collection.md)  
  
  
