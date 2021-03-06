---
title: Configurações de informações de dispositivo de imagem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- images [Reporting Services], rendering
- device information settings [Reporting Services], IMAGE rendering
ms.assetid: edad9498-69f7-4726-8699-fa615f704dff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 32498fbed24ddab591745ae1d01c5f123e976114
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66109005"
---
# <a name="image-device-information-settings"></a>Configurações das informações do dispositivo do Image
  A tabela a seguir lista as configurações de informações de dispositivo para renderização no formato do IMAGE.  
  
|Configuração|Valor|  
|-------------|-----------|  
|**Colunas**|O número de colunas a ser definido para o relatório. Esse valor substitui as configurações originais do relatório.|  
|**ColumnSpacing**|O espaçamento entre colunas a ser definido para o relatório. Esse valor substitui as configurações originais do relatório.|  
|`DpiX`|A resolução horizontal da imagem de saída. O valor padrão é **96**. Aplica-se ao `BMP`, `GIF`, `PNG`, e `TIFF` formatos de saída.|  
|`DpiY`|A resolução vertical da imagem de saída. O valor padrão é **96**. Aplica-se ao `BMP`, `GIF`, `PNG`, e `TIFF` formatos de saída.|  
|**EndPage**|A última página do relatório a ser renderizado. O valor padrão é o valor de `StartPage`.|  
|**MarginBottom**|O valor da margem inferior, em polegadas, a ser definido para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `1in`). Esse valor substitui as configurações originais do relatório.|  
|**MarginLeft**|O valor da margem esquerda, em polegadas, a ser definido para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `1in`). Esse valor substitui as configurações originais do relatório.|  
|**MarginRight**|O valor da margem direita, em polegadas, a ser definido para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `1in`). Esse valor substitui as configurações originais do relatório.|  
|**MarginTop**|O valor da margem superior, em polegadas, a ser definido para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `1in`). Esse valor substitui as configurações originais do relatório.|  
|**OutputFormat**|Um dos formatos de saída com suporte do [!INCLUDE[ndptecgdiexpanded](../includes/ndptecgdiexpanded-md.md)] ([!INCLUDE[ndptecgdi](../includes/ndptecgdi-md.md)]): `BMP`, `EMF`, `GIF`, `JPEG`, `PNG` ou `TIFF`.|  
|**PageHeight**|A altura da página, em polegadas, a ser definida para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `11in`). Esse valor substitui as configurações originais do relatório.|  
|**PageWidth**|A largura da página, em polegadas, a ser definida para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `8.5in`). Esse valor substitui as configurações originais do relatório.|  
|**PrintDpiX**|A resolução horizontal da imagem de saída. O valor padrão é `300`. Aplica-se a metarquivo avançado (`EMF`) formato de saída.|  
|**PrintDpiY**|A resolução vertical da imagem de saída. O valor padrão é `300`. Aplica-se a metarquivo avançado (`EMF`) formato de saída.|  
|`StartPage`|A primeira página do relatório a ser renderizada. O valor `0` indica que todas as páginas serão renderizadas. O valor padrão é `1`.|  
  
## <a name="see-also"></a>Consulte também  
 [Passando configurações de informações de dispositivos para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Personalizar parâmetros de extensão de renderização em RSReportServer.config](customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Referência técnica &#40;SSRS&#41;](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
