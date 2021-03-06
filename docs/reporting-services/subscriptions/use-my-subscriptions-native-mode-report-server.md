---
title: Usar Minhas Assinaturas (Servidor de Relatório no modo nativo) | Microsoft Docs
ms.date: 07/01/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: subscriptions
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], My Subscriptions page
- My Subscriptions page [Reporting Services]
ms.assetid: e96623ba-677e-4748-8787-f32bed3b5c12
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 2fc2566e643c247c5fb1ea79c5ef5f03ac032d2d
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "65578023"
---
# <a name="use-my-subscriptions-native-mode-report-server"></a>Usar Minhas Assinaturas (Servidor de Relatório no Modo Nativo)
O portal da Web do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] inclui uma página chamada **Minhas Assinaturas** que organiza todas as suas assinaturas em um único lugar. É possível usar *Minhas Assinaturas* para exibir, modificar, habilitar, desabilitar e excluir assinaturas existentes. Entretanto, você não pode usar Minhas Assinaturas para criar assinaturas.  Minhas Assinaturas exibe somente as assinaturas criadas pelo usuário. Minhas Assinaturas não relaciona assinaturas de propriedade de outros usuários, ainda que você tenha sido adicionado como assinante dessas assinaturas, tampouco exibe assinaturas controladas por dados.
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Modo nativo|  
  
O campo de pesquisa filtrará dinamicamente a lista de assinaturas, visto que não é possível procurar assinaturas por nome, nem procurar uma assinatura com base em informações de gatilho, informações de status etc. Para saber mais, consulte [Crie e gerencie assinaturas de servidores de relatório no modo Nativo](../../reporting-services/subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md).
  
## <a name="to-open-the-my-subscriptions-page"></a>Para abrir a página Minhas Assinaturas  
1. Abra o portal da Web do [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] .
2. Clique em Configurações ![ssrs_portal_settings_gear](../../reporting-services/subscriptions/media/ssrs-portal-settings-gear.png) na barra de ferramentas.
3. Clique em **Minhas Assinaturas**.

Para obter mais informações, veja [Web portal (SSRS Native Mode)](../../reporting-services/web-portal-ssrs-native-mode.md).

## <a name="use-windows-powershell-to-list-mysubscriptions"></a>Usar o Windows PowerShell para listar MySubscriptions  
 ![Conteúdo relacionado ao PowerShell](../../analysis-services/instances/install-windows/media/rs-powershellicon.jpg "Conteúdo relacionado ao PowerShell")  
  
 O seguinte script do PowerShell retornará a lista de assinaturas e as propriedades de assinatura do usuário atual. Para obter mais informações, consulte [Método ReportingService2010.ListMySubscriptions](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).  
  
```  
#server -  all subscriptions of the current user at the given server or site  
$server="[server name]/reportserver"  
$rs2010 = New-WebServiceProxy -Uri "https://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential;  
  
$subscriptions=ListMySubscriptions(ItemPathOrSiteURL)  
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status  
#uncomment the following to list all the subscription properties  
#$subscriptions

```  
  
## <a name="see-also"></a>Consulte Também  
 [Assinaturas controladas por dados](../../reporting-services/subscriptions/data-driven-subscriptions.md)   
 [Assinaturas e entrega &#40;Reporting Services&#41;](../../reporting-services/subscriptions/subscriptions-and-delivery-reporting-services.md)   
 [old_Crie e gerencie assinaturas de servidores de relatório no modo nativo](https://msdn.microsoft.com/7f46cbdb-5102-4941-bca2-5e0ff9012c6b)  
  
  
