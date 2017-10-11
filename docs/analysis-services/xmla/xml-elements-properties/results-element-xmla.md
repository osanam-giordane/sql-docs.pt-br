---
title: resultados Element (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- results Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.results
- urn:schemas-microsoft-com:xml-analysis#results
- http://schemas.microsoft.com/analysisservices/2003/engine#results
helpviewer_keywords:
- results element
ms.assetid: 3249a17a-7bfa-4753-b605-8f611ba7ae2b
caps.latest.revision: 11
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 791512ba71ef92a9e220936b138faf9eff2a4872
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="results-element-xmla"></a>Elemento Results (XMLA)
  Contém uma coleção de elementos [root](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md) retornada pelo método [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) que usa o comando [Batch](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md) .  
  
 **Namespace**`http://schemas.microsoft.com/analysisservices/2003/xmla-multipleresults`  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<return>  
   <results>  
      <root>...</root>  
   </results>  
</return>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhuma|  
|Valor padrão|Nenhuma|  
|Cardinalidade|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[retornar](../../../analysis-services/xmla/xml-elements-properties/return-element-xmla.md)|  
|Elementos filho|[raiz](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md)|  
  
## <a name="remarks"></a>Comentários  
 Se um comando **Batch** for executado pelo método **Execute** , o elemento **return** conterá um único elemento **results** em vez de um único elemento **root** . O conteúdo do elemento **results** depende das configurações utilizadas para executar o comando **Batch** .  
  
 Para comandos **Batch** não transacionais, o elemento **results** contém um elemento **root** para cada comando executado pelo comando **Batch** , independentemente de o comando ser concluído com sucesso ou não. Para comandos **Batch** transacionais, o elemento **results** contém apenas um elemento **root** , que contém informações de erro para o comando que falhou no comando **Batch** .  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  