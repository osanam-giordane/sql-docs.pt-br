---
title: MSSQLSERVER_10502 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10502 (Database Engine error)
ms.assetid: 26d9b64d-4299-4b55-92d0-0a32a3688c0a
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 42b4a39678e4b85e581bca7e1b9e085c6f4620f2
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "62870668"
---
# <a name="mssqlserver10502"></a>MSSQLSERVER_10502
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|10502|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|PG_DUP_FOUND|  
|Texto da mensagem|Não é possível criar o guia de plano '%.*ls' porque a instrução especificada por @stmt e @module_or_batch ou por @plan_handle e @statement_start_offset, corresponde ao guia de plano '%.\*ls' existente no banco de dados. Descarte o guia de plano existente antes de criar o novo.|  
  
## <a name="explanation"></a>Explicação  
 Há um guia de plano relativo à instrução especificada.  
  
## <a name="user-action"></a>Ação do usuário  
 Descarte o guia de plano existente antes de criar o novo.  
  
## <a name="see-also"></a>Consulte também  
 [Guias de plano](../performance/plan-guides.md)   
 [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)   
 [sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
