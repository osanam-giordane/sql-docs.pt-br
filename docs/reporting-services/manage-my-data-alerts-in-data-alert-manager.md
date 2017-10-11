---
title: Gerenciar Meus alertas de dados no Gerenciador de alertas de dados | Microsoft Docs
ms.custom: 
ms.date: 08/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: e0e4ffdf-bd4c-4ebd-872b-07486cbb47c2
caps.latest.revision: 13
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 7d5bc198ae3082c1b79a3a64637662968b0748b2
ms.openlocfilehash: 84bd8143bbc487ad38416f7b4c7fed48ab0f0369
ms.contentlocale: pt-br
ms.lasthandoff: 08/17/2017

---
# <a name="manage-my-data-alerts-in-data-alert-manager"></a>Gerenciar meus alertas de dados no Gerenciador de Alertas de Dados

[!INCLUDE[ssrs-appliesto](../includes/ssrs-appliesto.md)] [!INCLUDE[ssrs-appliesto-2016](../includes/ssrs-appliesto-2016.md)] [!INCLUDE[ssrs-appliesto-not-pbirsi](../includes/ssrs-appliesto-not-pbirs.md)] [!INCLUDE[ssrs-appliesto-sharepoint-2013-2016i](../includes/ssrs-appliesto-sharepoint-2013-2016.md)]

Os usuários do SharePoint podem exibir uma lista dos alertas de dados que criaram e informações sobre os alertas. Os usuários também podem excluir seus alertas, abrir definições de alerta para edição no Designer de Alertas de Dados e executar seus alertas. A imagem a seguir mostra os recursos disponíveis para os usuários no Gerenciador de Alertas de Dados.

 ![Recursos do Gerenciador de usuários do SharePoint de alerta](../reporting-services/media/rs-alertmanageriw.gif "recursos do Gerenciador de alertas para os usuários do SharePoint")

> [!NOTE]
> Integração do Reporting Services com o SharePoint não está mais disponível após o SQL Server 2016.

### <a name="to-view-a-list-of-your-alerts"></a>Para exibir uma lista dos seus alertas  
  
1.  Vá para a biblioteca do SharePoint onde você salvou os relatórios em que criou os alertas de dados.  
  
2.  Clique no ícone para expandir o menu suspenso em um relatório e clique em **Gerenciar Alertas de Dados**. A imagem a seguir mostra o menu suspenso.  
  
     ![Abra o Gerenciador de alertas no menu de contexto do relatório](../reporting-services/media/rs-openalertmanager.gif "abrir o Gerenciador de alerta no menu de contexto do relatório")  
  
     O Gerenciador de Alertas de Dados é aberto. Por padrão, ele lista os alertas para o relatório que você selecionou na biblioteca.  
  
3.  Clique na seta para baixo ao lado de **Exibir alertas para o relatório** e selecione um relatório para exibir seus alertas ou clique em **Mostrar Tudo** para listar todos os alertas.  
  
    > [!NOTE]  
    >  Se o relatório que você selecionou não tiver nenhum alerta, você não precisará voltar à biblioteca do SharePoint para localizar e selecionar um relatório que tenha alertas. Em vez disso, clique em **Mostrar Tudo** para consultar uma lista com todos os alertas.  
  
     Uma tabela lista o nome do alerta, o nome do relatório, seu nome como criador do alerta, o número com o qual o alerta foi enviado, a última vez que a definição de alerta foi modificada e o status do alerta. Se o alerta não puder ser gerado ou enviado, a coluna de status conterá informações sobre o erro e ajudará a solucionar o problema.  
  
### <a name="to-edit-an-alert-definition"></a>Para editar uma definição de alerta  
  
-   Clique com o botão direito do mouse no alerta de dados para o qual você deseja editar a definição de alerta e clique em **Editar**.  
  
     A definição de alerta é aberta no Designer de Alertas de Dados. Para obter mais informações, consulte [Editar um Alerta de Dados no Designer de Alertas](../reporting-services/edit-a-data-alert-in-alert-designer.md) e [Designer de Alertas de Dados](../reporting-services/data-alert-designer.md).  
  
    > [!NOTE]  
    >  Apenas o usuário que criou a definição de alerta de dados pode editá-la.  
  
    > [!NOTE]  
    >  Se o relatório tiver sido alterado e os feeds de dados gerados no relatório tiverem sido alterados, a definição de alerta talvez não seja mais válida. Isso ocorre quando uma coluna referenciada pelo alerta nas regras é excluída do relatório, altera o tipo de dados ou é incluída em outro feed de dados, ou quando o relatório é excluído ou movido. Você pode abrir uma definição de alerta que não é válida, mas só pode salvá-la novamente depois que ela estiver válida com base na versão atual do feed de dados de relatório do qual ela depende. Para saber mais sobre como os feeds de dados são gerados de relatórios, consulte [Gerando feeds de dados de relatórios &#40;Construtor de Relatórios e SSRS&#41;](../reporting-services/report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).  
  
### <a name="to-delete-an-alert-definition"></a>Para excluir uma definição de alerta  
  
-   Clique com o botão direito do mouse no alerta de dados que você deseja excluir e clique em **Excluir**.  
  
     Quando você excluir o alerta, nenhuma mensagem de alerta adicional será enviada.  
  
### <a name="to-run-an-alert"></a>Para executar um alerta  
  
-   Clique com o botão direito do mouse no alerta de dados que você deseja executar e clique em **Executar**.  
  
     A instância do alerta é criada e a mensagem de alerta de dados é enviada imediatamente, independentemente das opções de agenda especificadas no Designer de Alerta de Dados. Por exemplo, um alerta configurado para ser enviado semanalmente e, depois, somente se a alteração de resultados for enviada.  

## <a name="see-also"></a>Consulte também

[Gerenciador de alertas de dados para os administradores de alerta](../reporting-services/data-alert-manager-for-alerting-administrators.md)   
[Alertas de dados do Reporting Services](../reporting-services/reporting-services-data-alerts.md)  

Mais perguntas? [Tente fazer o fórum do Reporting Services](http://go.microsoft.com/fwlink/?LinkId=620231)