---
title: sp_cdc_help_jobs (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cdc_help_jobs
- sys.sp_cdc_help_jobs_TSQL
- sp_cdc_help_jobs_TSQL
- sys.sp_cdc_help_jobs
dev_langs:
- TSQL
helpviewer_keywords:
- sp_cdc_help_jobs
ms.assetid: 9399b4bc-8293-408f-b3cb-f904e0657fb5
author: rothja
ms.author: jroth
ms.openlocfilehash: 9820476ecdee25551d09c8206595b637421b9efd
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68083720"
---
# <a name="sysspcdchelpjobs-transact-sql"></a>sys.sp_cdc_help_jobs (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Reporta informações sobre todos os trabalhos de captura e limpeza do Change Data Capture no banco de dados atual.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sys.sp_cdc_help_jobs  
```  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**job_id**|**uniqueidentifier**|A ID do trabalho.|  
|**job_type**|**nvarchar(20)**|O tipo de trabalho.|  
|**maxtrans**|**int**|O número máximo de transações a serem processadas em cada ciclo de verificação.<br /><br /> **maxtrans** é válido somente para trabalhos de captura.|  
|**maxscans**|**int**|O número máximo de ciclos de exame a executar para extrair todas as linhas do log.<br /><br /> **maxscans** é válido somente para trabalhos de captura.|  
|**contínua**|**bit**|Um sinalizador que indica se o trabalho de captura deve ser executado continuamente (1) ou de uma só vez (0). Para obter mais informações, consulte [sys. sp_cdc_add_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-add-job-transact-sql.md).<br /><br /> **contínua** é válido somente para trabalhos de captura.|  
|**pollinginterval**|**bigint**|O número de segundos entre ciclos de exame de log.<br /><br /> **pollinginterval** é válido somente para trabalhos de captura.|  
|**retention**|**bigint**|O número de minutos que as linhas de alteração serão retidas em tabelas de alteração.<br /><br /> **retenção** é válido somente para trabalhos de limpeza.|  
|**threshold**|**bigint**|O número máximo de entradas de exclusão que podem ser excluídas usando uma única instrução na limpeza.|  
  
## <a name="permissions"></a>Permissões  
 Requer associação na **db_owner** função fixa de banco de dados.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir retorna informações sobre os trabalhos de captura e de limpeza definidos para o banco de dados `AdventureWorks2012`.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sys.sp_cdc_help_jobs;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [dbo.cdc_jobs &#40;Transact-SQL&#41;](../../relational-databases/system-tables/dbo-cdc-jobs-transact-sql.md)   
 [sys.sp_cdc_add_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-add-job-transact-sql.md)  
  
  
