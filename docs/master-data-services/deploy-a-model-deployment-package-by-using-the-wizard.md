---
title: "Implantar um pacote de implantação de modelo usando o Assistente | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deployment packages [Master Data Services], deploying
- models [Master Data Services], deploying a package
ms.assetid: 4f65dc60-0ff8-46e6-9988-5bc5b9603ad0
caps.latest.revision: 16
author: smartysanthosh
ms.author: nagavo
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 0b832a9306244210e693bde7c476269455e9b6d8
ms.openlocfilehash: 6f9206369f5111cbc74556d71dc815b26d03af7b
ms.contentlocale: pt-br
ms.lasthandoff: 09/07/2017

---
# <a name="deploy-a-model-deployment-package-by-using-the-wizard"></a>Implantar um pacote de implantação de modelo usando o Assistente
  Use o assistente de implantação de modelo do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para implantar pacotes que contêm somente objetos de modelo. Se você precisar implantar um pacote com dados, consulte [Implantar um pacote de implantação de modelo usando MDSModelDeploy](../master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).  
  
> [!IMPORTANT]  
>  Os pacotes podem ser implantados somente na edição do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] na qual eles foram criados. Isso significa que os pacotes criados no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] não podem ser implantados no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].  
  
## <a name="prerequisites"></a>Pré-requisitos  
 Para executar esse procedimento:  
  
-   Você deverá ter permissão para acessar a área funcional **Administração do Sistema** no ambiente [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] de destino.  
  
-   Um pacote de implantação de modelo deverá existir. Para obter mais informações, consulte [Criar um pacote de implantação de modelo usando o assistente](../master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).  
  
-   Você deve ser um administrador no ambiente onde está implantando o modelo. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-deploy-a-model-deployment-package-of-model-objects-only"></a>Para implantar um pacote de implantação de modelo somente de objetos de modelo  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.  
  
2.  Na barra de menus da página **Exibição de Modelo** , aponte para **Sistema** e clique em **Implantação**.  
  
3.  No **Assistente de Implantação de Modelo**, clique em **Implantar**.  
  
4.  Clique em **Procurar**.  
  
5.  Localize seu pacote de implantação (arquivo .pkg) e clique em **Abrir**.  
  
6.  Clique em **Avançar**.  
  
7.  Depois que o pacote for carregado, clique em **Avançar**.  
  
8.  Se o modelo já existir, você poderá atualizá-lo selecionando **Atualizar o modelo existente**. Para criar um novo modelo, selecione **Criar novo modelo** e, depois de clicar em **Avançar** , digite o nome do novo modelo.  
  
9. Clique em **Concluir** para sair do assistente.  
  
 **Observações:**  
  
-   Se uma exibição de assinatura no pacote tiver o mesmo nome que uma exibição de assinatura em um modelo existente, este aviso será exibido: **Exibição da assinatura do implantador renomeada**. Além disso, a exibição é criada como *modelname.subscriptionviewname*. Se esse nome já estiver em uso, a exibição de assinatura não será criada.  
  
-   O processo de implantação tem quatro etapas:  
  
    1.  Os objetos de modelo são criados.  
  
    2.  As exibições de assinatura são criadas.  
  
    3.  As regras de negócio são criadas.  
  
-   Ao criar um modelo novo ou clonado, se o processo falhar durante alguma etapa, o modelo será excluído.  
  
     Na atualização de um modelo, se o processo falhar durante alguma das três primeiras etapas, ele não irá além dessa etapa; no entanto, as alterações já feitas não serão revertidas.  
  
## <a name="next-steps"></a>Próximas etapas  
 Os atributos de arquivo e permissões de usuário e de grupo não estão incluídos em pacotes de implantação de modelo. Depois de implantar um modelo, você deve atualizar esses objetos manualmente. Para obter mais informações, consulte:  
  
-   [Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](../master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a>Consulte também  
 [Implantando modelos &#40;Master Data Services&#41;](../master-data-services/deploying-models-master-data-services.md)  
  
  