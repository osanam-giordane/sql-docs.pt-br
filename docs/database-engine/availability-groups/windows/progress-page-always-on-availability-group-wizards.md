---
title: "Página Progresso (Assistentes do Grupo de Disponibilidade AlwaysOn) | Microsoft Docs"
ms.custom: 
ms.date: 05/17/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-high-availability
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.failoverwizard.progress.f1
- sql13.swb.adddatabasewizard.progress.f1
- sql13.swb.addreplicawizard.progress.f1
- sql13.swb.newagwizard.progress.f1
ms.assetid: bd3b0306-8384-4120-a1c9-03825f0ae26a
caps.latest.revision: 13
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 78fd0315e1f58eef1dbc5d8c41f6254817879d8c
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="progress-page-always-on-availability-group-wizards"></a>Página Progresso (Assistentes do Grupo de Disponibilidade AlwaysOn)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Use esta caixa de diálogo para exibir o progresso de um assistente do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] que você está executando no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]. A barra de progresso indica o progresso relativo das etapas que o assistente está executando.  
  
## <a name="uielement-list"></a>Lista de elementos de interface do usuário  
 **Mais detalhes**  
 Clique na seta para baixo para exibir uma grade de progresso que lista todas as etapas concluídas, em ordem, seguidas pela operação em andamento no momento. A grade contém as seguintes colunas:  
  
 **Nome**  
 Exibe uma frase que descreve uma etapa específica.  
  
 **Status**  
 Indica o resultado das etapas concluídas e o percentual de conclusão da etapa atual, da seguinte maneira:  
  
|Resultado|Descrição|  
|------------|-----------------|  
|**Erro**|Indica que a operação desta etapa experimentou um erro. Clique no link para exibir uma caixa de diálogo de mensagem que descreve o erro.|  
|**Em andamento (** *percentual concluído* **)**|Indica que a operação está ocorrendo agora e estima o percentual desta etapa que foi concluída.|  
|**Success**|Indica que a operação desta etapa foi concluída com êxito.|  
  
 **Menos Detalhes**  
 Clique para ocultar a grade de progresso.  
  
 **Cancelar**  
 Clique para ignorar todas as operações restantes e sair do assistente.  
  
##  <a name="RelatedTasks"></a> Tarefas relacionadas  
  
-   [Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [Usar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/availability-group-add-database-to-group-wizard.md)  
  
-   [Usar o Assistente de Grupo de Disponibilidade de Failover &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)  
  
  
