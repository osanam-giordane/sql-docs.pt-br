---
title: Erro tratamento (MDX) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scripts [MDX], exceptions
- exceptions [MDX]
ms.assetid: bc6ff0af-9fe6-44d6-bc3c-801d71ea41a9
caps.latest.revision: 26
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: bbd604d132fa204da606b44d72551f198661c81a
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="error-handling-mdx"></a>Tratamento de erros (MDX)
  Cada cubo pode controlar como são tratados os erros em um script MDX. O tratamento de erro é feito por meio do enumerador **ScriptErrorHandlingMode** . Os valores possíveis para esse enumerador são:  
  
 **IgnoreNone**  
 Faz com que o servidor produza um erro se o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] localizar algum erro no script MDX.  
  
 **IgnoreAll**  
 Faz com que o servidor ignore todos os comandos do script MDX que contém um erro, incluindo erros de sintaxe, de resolução de nomes, entre outros.  
  
## <a name="see-also"></a>Consulte também  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  