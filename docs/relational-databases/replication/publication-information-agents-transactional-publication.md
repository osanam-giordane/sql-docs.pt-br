---
title: "Informações da publicação, agentes (publicação transacional) | Microsoft Docs"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.monitor.publicationinfo.downlevelagents.tran.f1
ms.assetid: 38ef2f54-53bb-4053-876d-86f8f06a4519
caps.latest.revision: 23
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: a1e666793719f1a277fffe23d02d4a6630585f61
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="publication-information-agents-transactional-publication"></a>Informações da Publicação, Agentes (publicação transacional)
  A guia **Agentes** exibe informações resumidas sobre os agentes para a publicação selecionada. Informações sobre o Snapshot Agent e Log Reader Agent são exibida para todas as publicações transacionais. Informações sobre o Queue Reader Agent são exibidas para essas publicações transacionais que estão habilitadas para assinaturas de atualização enfileirada.  
  
## <a name="options"></a>Opções  
 Para obter informações mais detalhadas e tarefas relacionadas a um agente, clique com o botão direito do mouse na linha desse agente e clique em uma opção no menu de atalho. Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:  
  
-   **Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .  
  
-   **Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .  
  
-   **Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .  
  
-   **Limpar Filtro**: limpe as configurações de filtro da grade.  
  
 As configurações de filtro são específicas de cada grade. A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.  
  
 **Status**  
 O status de cada agente de replicação associado à publicação. A seguinte lista mostra os possíveis valores de status:  
  
-   Erro  
  
-   Tentando novamente comandos com falha  
  
-   Não está sendo executado  
  
-   Executando  
  
-   Concluído  
  
 **Agente**  
 O nome de cada agente de replicação associado à publicação. O Distribution Agent é associado com assinaturas para essa publicação. Para obter mais informações, consulte [View Information and Perform Tasks for the Agents Associated With a Subscription &#40;Replication Monitor&#41;](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-subscription-agents.md) [Exibir informações e executar tarefas para os agentes associados a uma assinatura (Replication Monitor)].  
  
 **Última Hora de Início**  
 A última vez que o agente foi iniciado.  
  
 **Duration**  
 O tempo durante o qual o agente foi executado. O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total, se o agente foi executado anteriormente.  
  
 **Última Ação**  
 A última ação executada durante a execução mais recente do agente.  
  
## <a name="see-also"></a>Consulte também  
 [Iniciar o Replication Monitor](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [Exibir informações e executar tarefas para uma publicação &#40;Replication Monitor&#41;](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-a-publication-replication-monitor.md)   
 [Exibir informações e executar tarefas para os agentes associados a uma publicação &#40;Replication Monitor&#41;](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-publication-agents.md)   
 [Monitorando a Replicação](../../relational-databases/replication/monitor/monitoring-replication-overview.md)  
  
  