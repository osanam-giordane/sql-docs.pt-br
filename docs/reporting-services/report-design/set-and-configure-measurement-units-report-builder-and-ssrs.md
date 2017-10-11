---
title: "Definir e configurar unidades de medida (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a15a96c3-7d2c-433e-a440-4ea051e967a9
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 46d639df93661b5cd27810c72a44f698539aac2f
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="set-and-configure-measurement-units-report-builder-and-ssrs"></a>Definir e configurar unidades de medida (Construtor de Relatórios e SSRS)
  Em um relatório paginado do [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] , os indicadores usam uma das duas unidades de medida: percentual ou numérica.   
    
  Por padrão, indicadores são configurados para usar percentuais como a unidade de medida. Isso significa que os valores de indicador atribuídos a cada ícone no conjunto de indicadores são determinados por um intervalo de percentuais. Os intervalos de percentuais são divididos uniformemente pelos ícones no conjunto de indicadores. Cada ícone representa um estado de indicador. Você pode alterar os percentuais para cada ícone no conjunto de indicadores especificando percentuais inicial e final diferentes. Os indicadores também detectam automaticamente os valores mínimo e máximo nos dados.  
  
 Você pode alterar a unidade de medida para ser um valor numérico. Nesse caso, você não especifica o mínimo ou o máximo para obter os dados; em vez disso, fornece apenas os valores inicial e final para cada ícone usado pelo indicador.  
  
 Opções como unidades de medida podem ser definidas usando expressões. Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md).  
  
## <a name="to-use-the-numeric-state-measurement-unit"></a>Para usar a unidade de medida em estado numérico  
  
1.  Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.  
  
2.  Clique em **Valores e Estados** no painel esquerdo.  
  
3.  Na lista **Unidade de Medida de Estados** , clique em **Numérico**.  
  
     Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define o valor da opção.  
  
4.  Para cada ícone no conjunto de indicadores, atualize os valores nas caixas de texto **Início** e **Fim** .  
  
     Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define os valores das opções **Início** e **Fim** .  
  
    > [!NOTE]  
    >  Os valores das caixas de texto **Início** e **Fim** devem ser numéricos.  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="to-use-the-percentage-measurement-unit"></a>Para usar a unidade de medida em percentual  
  
1.  Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.  
  
2.  Clique em **Valores e Estados** no painel esquerdo.  
  
3.  Na lista **Unidade de Medida de Estados** , clique em **Percentual**.  
  
     Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define o valor da opção.  
  
4.  Opcionalmente, altere as opções **Mínimo** e **Máximo** para usar valores específicos em vez de detectar automaticamente os valores mínimo e máximo dos dados que o indicador usa. O valor **Mínimo** deve ser menor do que o valor **Máximo**.  
  
    > [!NOTE]  
    >  Se você definir explicitamente os valores mínimo e máximo, aquele intervalo de valor será usado pelo indicador independentemente dos valores reais mínimo e máximo nos dados. Isto significa que valores menores que o mínimo e maiores que o máximo serão excluídos da avaliação que determina o ícone de indicador que será mostrado no relatório.  
  
     Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define os valores da opção.  
  
5.  Para cada ícone no conjunto de indicadores, atualize os valores nas caixas de texto **Início** e **Fim** .  
  
     Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define os valores das opções **Início** e **Fim** .  
  
    > [!NOTE]  
    >  Os valores das caixas de texto **Início** e **Fim** devem ser numéricos.  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Indicadores &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/indicators-report-builder-and-ssrs.md)  
  
  