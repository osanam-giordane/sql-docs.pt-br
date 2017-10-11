---
title: "Linha de gráficos (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 194e6679-890d-4a3e-a756-130d32ef7e29
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b309753291bfae573be58b124c033d021adb254c
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="line-charts-report-builder-and-ssrs"></a>Gráficos de linhas (Construtor de Relatórios e SSRS)
  Um gráfico de linhas exibe uma série como um conjunto de pontos conectado por uma única linha. As linhas de gráfico são usadas para representar grandes quantidades de dados que ocorrem em um período de tempo contínuo. Para obter mais informações sobre como adicionar dados a um gráfico de linhas, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md).  
  
 A ilustração a seguir mostra um gráfico de linhas que contém três séries.  
  
 ![Gráfico de linhas](../../reporting-services/report-design/media/rs-linechart.gif "gráfico de linhas")  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a>Variações  
  
-   **Linha suave**. Um gráfico de linhas que usa uma linha curva em vez de uma linha regular.  
  
-   **Linha escalonada**. Um gráfico de linhas que usa uma linha escalonada em vez de uma linha regular. A linha escalonada conecta os pontos usando uma linha que a deixa com uma aparência semelhante aos degraus de uma escadaria.  
  
-   **Minigráficos**. Variações do gráfico de linha que mostram apenas a série de linha na célula de uma tabela ou matriz. Para obter mais informações, consulte [Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).  
  
## <a name="data-considerations-for-line-charts"></a>Considerações de dados para gráficos de linhas  
  
-   Para melhorar o impacto visual do gráfico de linhas padrão, altere a largura das bordas para 3 e adicione um deslocamento de sombra de 1. Esse processo criará um gráfico de linhas mais espesso. Será preciso reverter essas propriedades para os valores originais caso você altere o tipo de gráfico definido como Linha para outro tipo.  
  
-   Se o conjunto de dados incluir valores vazios, o gráfico de linhas adicionará pontos vazios, no formulário de linhas como espaços reservados para manter a continuidade no gráfico. Se você optar por não ver essas linhas, exiba o conjunto de dados usando um gráfico não contínuo, como, por exemplo, um gráfico de barras ou colunas.  
  
-   Um gráfico de linhas requer pelo menos dois pontos para desenhar uma linha.  Se o conjunto de dados tiver apenas um ponto de dados, o gráfico de linhas exibirá apenas um marcador de ponto de dados.  
  
-   Uma série que é desenhada como uma linha não ocupará muito espaço dentro de uma área de gráfico.  Por isso, os gráficos de linhas são frequentemente combinados com outros tipos de gráficos, como gráficos de colunas. Entretanto, não é possível combinar um gráfico de linhas com gráficos do tipo barras, polares, tortas ou formas.  
  
## <a name="see-also"></a>Consulte também  
 [Gráficos de barras &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/bar-charts-report-builder-and-ssrs.md)   
 [Gráficos de colunas &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/column-charts-report-builder-and-ssrs.md)   
 [Gráficos de &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
 [Tipos de gráfico &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/chart-types-report-builder-and-ssrs.md)   
 [Gráficos de área &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/area-charts-report-builder-and-ssrs.md)   
 [Pontos de dados vazios e nulos em gráficos &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)   
 [Gráficos de &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  