---
title: Atualizar dados no Replication Monitor | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- refreshing data
ms.assetid: e9582244-7d00-45f4-be16-020a65c76a5e
caps.latest.revision: 17
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 7b58ebcc0ce0f46fd2818ae87f8093da1c3bb086
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="refresh-data-in-replication-monitor"></a>Atualizar dados no Replication Monitor
  No Replication Monitor, a janela principal e a janela de detalhes (as janelas abertas na janela principal) podem ser atualizadas automaticamente e manualmente. Para atualizar uma janela manualmente, pressione F5. Por padrão, a janela principal é atualizada a cada cinco segundos automaticamente; a taxa pode ser personalizada para cada Publicador.  
  
 Os dados exibidos no Replication Monitor são consultados por meio de um cache; para obter informações sobre a relação entre o cache e a atualização do Replication Monitor, consulte [Cache, atualização e desempenho do Replication Monitor](../../../relational-databases/replication/monitor/caching-refresh-and-replication-monitor-performance.md). Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](../../../relational-databases/replication/monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).  
  
### <a name="to-set-refresh-options-for-replication-monitor"></a>Para definir as opções de atualização para o Replication Monitor  
  
1.  Clique com o botão direito do mouse no Publicador do painel esquerdo do Replication Monitor e clique em **Configurações do Publicador**.  
  
2.  Na caixa de diálogo **Configurações do Publicador** , defina as opções **Atualização automática** e **Taxa de atualização** . As configurações de **Atualização automática** afetam a janela principal do Replication Monitor. As configurações de **Taxa de atualização** também afetam todos os detalhes definidos para atualizarem automaticamente (alterações na configuração afetam apenas as janelas de detalhes abertas depois da alteração).  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-specify-that-a-detail-window-should-automatically-refresh"></a>Para especificar que uma janela de detalhe deverá atualizar automaticamente  
  
1.  Abra uma janela de detalhe no Replication Monitor. Por exemplo:  
  
    1.  Expanda um Grupo do publicador no painel esquerdo, expanda um Publicador e clique em uma publicação.  
  
    2.  Clique na guia **Todas as Assinaturas** .  
  
    3.  Clique com o botão direito do mouse em uma assinatura e clique em **Exibir Detalhes**.  
  
2.  Na janela de detalhes **Assinatura \<SubscriptionName>**, clique em **Ação** e, em seguida, em **Atualização Automática**. A taxa de atualização é determinada pela configuração em **Taxa de atualização** , na caixa de diálogo **Configurações do Publicador** .  
  
## <a name="see-also"></a>Consulte também  
 [Monitorando a Replicação](../../../relational-databases/replication/monitor/monitoring-replication-overview.md)  
  
  