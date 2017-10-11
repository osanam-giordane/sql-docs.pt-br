---
title: "Alterar a ordem de um parâmetro de relatório (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
caps.latest.revision: 9
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 3377e943ddf7d8c7bd06aeab52ee263a754af25c
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a>Alterar a ordem de um parâmetro de relatório (Construtor de Relatórios e SSRS)
  Altere a ordem dos parâmetros de relatório quando você tiver um parâmetro dependente que tenha sido listado antes de o parâmetro ser dependente. A ordem do parâmetro é importante quando você tem parâmetros em cascata ou quando você deseja mostrar aos usuários o valor padrão de um parâmetro antes que eles escolham os valores para outros parâmetros. Um parâmetro de relatório dependente contém uma referência, seja a consulta de valores padrão ou na consulta de valores válidos, a um parâmetro de consulta que aponta para um parâmetro de relatório que está depois dele na lista de parâmetros no painel **Dados do Relatório** .  
  
 A ordem em que você vê os parâmetros exibidos na barra de ferramentas do visualizador de relatórios é determinada pela ordem dos parâmetros no painel **Dados do Relatório** e do local dos parâmetros no painel de parâmetros personalizados. Para obter mais informações, consulte [personalizar o painel de parâmetros em um relatório &#40; Construtor de relatórios &#41;](../../reporting-services/report-design/customize-the-parameters-pane-in-a-report-report-builder.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-change-the-order-of-report-parameters"></a>Para alterar a ordem dos parâmetros de relatório  
  
Você pode alterar a ordem dos parâmetros de relatório seguindo um destes procedimentos:  
  
-   Clique em um parâmetro no painel **Dados do Relatório** e use os botões de seta para cima e para baixo para movê-lo para cima ou para baixo na lista, como mostrado na imagem a seguir.  Quando você altera a ordem do parâmetro no painel **Dados do Relatório** , o local do parâmetro no painel de parâmetros é alterado.  
  
     ![Alterar a ordem dos parâmetros no painel dados do relatório](../../reporting-services/report-design/media/ssrs-changeorderofparameters-reportdata.png "alterar a ordem dos parâmetros no painel dados do relatório")  
  
-   No painel de parâmetros, arraste o parâmetro para uma nova coluna ou linha no painel. Quando você altera a localização do parâmetro no painel, a ordem do parâmetro é alterada no painel **Dados do Relatório** . Para obter mais informações sobre como mover os parâmetros no painel, consulte [personalizar o painel de parâmetros em um relatório &#40; Construtor de relatórios &#41; ](../../reporting-services/report-design/customize-the-parameters-pane-in-a-report-report-builder.md).  
  
## <a name="see-also"></a>Consulte também  
 [Parâmetros de relatório e &#40; Construtor de relatórios, Report Designer e &#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)   
 [Ajuda do construtor de relatórios para caixas de diálogo, painéis e assistentes](http://msdn.microsoft.com/en-us/2da24891-0b6d-4d3c-8b18-81b98752642f)   
 [Adicionar parâmetros em cascata a um relatório &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Tutorial: Adicionar um parâmetro ao seu relatório &#40; Construtor de relatórios &#41;](../../reporting-services/tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Adicionar filtros de conjunto de dados, filtros de região de dados e filtros de grupo &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Referências de coleção de parâmetros &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/built-in-collections-parameters-collection-references-report-builder.md)  
  
  