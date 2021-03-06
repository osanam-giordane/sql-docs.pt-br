---
title: Programação de modelo de propriedades do cubo – Multidimensional | Microsoft Docs
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: olap
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 85453133ab9facd9f3ed56ad98fa2761ac527e40
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "68209368"
---
# <a name="cube-properties---multidimensional-model-programming"></a>Propriedades do cubo – Programação de modelo multidimensional
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  Os cubos têm várias propriedades que você pode definir para afetar o comportamento de todo o cubo. Essas propriedades são resumidas na tabela a seguir.  
  
> [!NOTE]  
>  Algumas propriedades são definidas automaticamente na criação do cubo e não podem ser alteradas.  
  
 Para obter mais informações sobre como definir as propriedades do cubo, consulte [Designer de cubo &#40;Analysis Services - dados multidimensionais&#41;](http://msdn.microsoft.com/library/a6692467-da88-4312-8b03-d812f2ae5a96).  
  
|Propriedade|Descrição|  
|--------------|-----------------|  
|**AggregationPrefix**|Especifica o prefixo comum usado para nomes de agregação.|  
|**Ordenação**|Especifica o identificador de localidade (LCID) e o sinalizador de comparação, separados por um sublinhado: por exemplo, Latin1_General_C1_AS.|  
|**DefaultMeasure**|Contém uma linguagem MDX que define a medida padrão para o cubo.|  
|**Descrição**|Fornece uma descrição do cubo que pode ser exposta em aplicativos cliente.|  
|**ErrorConfiguration**|Contêm configurações de tratamento de erros que podem ser definidas para tratar chaves duplicadas, chaves desconhecidas, limites de erros, ação devido à detecção de erros, arquivo de log de erros e tratamento de chaves nulas.|  
|**EstimatedRows**|Especifica o número de linhas estimadas no cubo.|  
|**ID**|Contém o identificador exclusivo (ID) do cubo.|  
|**Idioma**|Especifica o identificador de idioma padrão do cubo.|  
|**Name**|Especifica o nome amigável do cubo.|  
|**ProactiveCaching**|Define configurações de cache pró-ativas para o cubo.|  
|**ProcessingMode**|Indica se a indexação e a agregação devem ocorrer durante ou após o processamento. As opções são **regular** ou **lento**.|  
|**ProcessingPriority**|Determina a prioridade de processamento do cubo durante as operações em segundo plano, como agregações lentas e indexação. O valor padrão é **0**.|  
|**ScriptCacheProcessingMode**|Indica se o cache de script deve ser criado durante ou após o processamento. As opções são **regular** e **lento**.|  
|**ScriptErrorHandlingMode**|Determina o tratamento de erros. As opções são **IgnoreNone** ou **IgnoreAll**|  
|**Source**|Mostra a exibição da fonte de dados usada para o cubo.|  
|**StorageLocation**|Especifica o local de armazenamento do sistema de arquivos para o cubo. Se nenhum for especificado, o local será herdado do banco de dados que contém o objeto de cubo.|  
|**StorageMode**|Especifica o modo de armazenamento para o cubo. Os valores são **MOLAP**, **ROLAP**, ou **HOLAP**.|  
|**Visível**|Determina a visibilidade do cubo.|  
  
> [!NOTE]  
>  Para obter mais informações sobre como definir valores para a propriedade ErrorConfiguration ao trabalhar com valores nulos e outros problemas de integridade de dados, consulte [Handling Data Integrity Issues in Analysis Services 2005](http://go.microsoft.com/fwlink/?LinkId=81891).  
  
## <a name="see-also"></a>Consulte também  
 [Cache pró-ativo &#40;partições&#41;](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-proactive-caching.md)  
  
  
