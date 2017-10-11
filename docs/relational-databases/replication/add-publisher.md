---
title: Adicionar publicador | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.monitor.addpublisher.f1
helpviewer_keywords:
- Add Publisher dialog box
ms.assetid: 4b57e298-655f-42c2-82bc-25cdad94a194
caps.latest.revision: 23
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 86d2654bba26b7bcd1a5c758b8d609d6e2df0286
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="add-publisher"></a>Adicionar Publicador
  A caixa de diálogo **Adicionar Publicador** permite a adição de um ou mais publicadores no painel esquerdo do Replication Monitor. Depois de adicionar um Publicador, selecioná-lo no painel esquerdo mostrará informações sobre o Publicador no painel à direita.  
  
## <a name="options"></a>Opções  
 **Adicionar**  
 Clique para selecionar um tipo de Publicador a ser adicionado que inicia a caixa de diálogo **Conectar ao Servidor** . As opções são:  
  
-   **Adicionar Editor SQL Server…**  
  
     Conectar-se ao Editor usando a caixa de diálogo **Conectar ao Servidor** .  
  
-   **Adicionar Editor Oracle…**  
  
     Conecte-se ao Distribuidor da [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com Editor Oracle usando a caixa de diálogo **Conectar ao Servidor** .  
  
-   **Especificar um Distribuidor e Adicionar seus Publicadores…**  
  
     Conecte-se ao Distribuidor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associado a um ou mais Publicadores usando a caixa de diálogo **Conectar ao Servidor** .  
  
 Depois de se conectar com êxito ao Publicador ou ao Distribuidor, o nome de cada publicador e seu distribuidor serão exibidos na grade, na parte superior da caixa de diálogo.  
  
> [!NOTE]  
>  O Distribuidor e o Publicador geralmente são executados na mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas o Distribuidor pode ser executado em outra instância (essa configuração é referenciada como Distribuidor remoto).  
  
 **Remover**  
 Selecione um Publicador na grade, na parte superior da caixa de diálogo, e clique em **Remover** para remover o Publicador da lista de Publicadores a serem selecionados.  
  
> [!NOTE]  
>  Esse botão não pode ser usado para remover um Publicador já exibido no Replication Monitor. Para remover um Publicador já exibido, clique no Publicador no painel esquerdo do Replication Monitor, e clique em **Remover**.  
  
 **Conectar automaticamente quando o Replication Monitor for iniciado**  
 Selecione para permitir que o Replication Monitor faça conexão automática com o Distribuidor e recupere informações de status para o Publicador selecionado na grade, na parte superior da caixa de diálogo. Se essa caixa de seleção estiver desmarcada, você terá de fazer a conexão manualmente após iniciar o Replication Monitor: clique com o botão direito no Publicador no painel esquerdo do Replication Monitor, e clique em **Conectar**.  
  
 **Atualizar automaticamente o status deste Publicador e de suas publicações**  
 Selecione para permitir que o Replication Monitor atualize automaticamente o status do Publicador selecionado na grade, na parte superior da caixa de diálogo. Se essa opção for selecionada, o Replication Monitor pesquisará no Distribuidor informações de status sobre o Publicador e suas publicações. O intervalo da sondagem é definido pela opção **Taxa de Atualização** . Para obter mais informações sobre a atualização no Replication Monitor, consulte [Cache, atualização e desempenho do Replication Monitor](../../relational-databases/replication/monitor/caching-refresh-and-replication-monitor-performance.md).  
  
 **Taxa de atualização**  
 Insira um valor (em segundos) para especificar a frequência de sondagem do Replication Monitor no Distribuidor, por status. Valores mais baixos resultam em sondagens mais frequentes, que podem afetar o desempenho no Distribuidor se você estiver monitorando um grande número de Publicadores. É recomendado que você teste seu sistema para determinar um valor apropriado. A configuração da **Taxa de Atualização** será também usada se você selecionar **Atualização Automática** em qualquer uma das janelas de detalhes no Replication Monitor.  
  
 **Mostrar este Publicador no grupo a seguir**  
 Selecione um grupo de Publicadores na lista. O Publicador é exibido nesse grupo no painel esquerdo. Grupos fornecem uma forma de organizar Publicadores e não causam nenhum efeito em funções de replicação. Se nenhum grupo estiver definido ou você quer criar um novo, clique em **Novo Grupo**.  
  
 **Novo Grupo**  
 Clique para criar um novo grupo de Publicadores. Um grupo de Publicadores é um modo conveniente de organizar Publicadores no Replication Monitor. Grupos não afetam a replicação de dados ou a relação entre servidores em uma topologia de replicação.  
  
## <a name="see-also"></a>Consulte também  
 [Iniciar o Replication Monitor](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [Monitorando a Replicação](../../relational-databases/replication/monitor/monitoring-replication-overview.md)  
  
  