---
title: Elemento capability (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Capability Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#Capability
- http://schemas.microsoft.com/analysisservices/2003/engine#Capability
- microsoft.xml.analysis.capability
helpviewer_keywords:
- Capability element
ms.assetid: 544a733e-77fc-48a0-8f92-9cd1fdbcf824
caps.latest.revision: 16
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 50a1509e5b4b51778e329dec7bea9554cfca4234
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="capability-element-xmla"></a>Elemento Capability (XMLA)
  Indica suporte para uma capacidade de protocolo no pai [ProtocolCapabilities](../../../analysis-services/xmla/xml-elements-headers/protocolcapabilities-element-xmla.md) elemento de cabeçalho.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<ProtocolCapabilities>  
   ...  
   <Capability>...</Capability>  
   ...  
</ProtocolCapabilities>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|String|  
|Valor padrão|Nenhuma|  
|Cardinalidade|0-n: Elemento opcional que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[ProtocolCapabilities](../../../analysis-services/xmla/xml-elements-headers/protocolcapabilities-element-xmla.md)|  
|Elementos filho|Nenhuma|  
  
## <a name="remarks"></a>Comentários  
 O **recurso** elemento indica que um recurso específico, como binário ou compactação, tem suporte no aplicativo que incluído o **ProtocolCapabilities** elemento de cabeçalho no Cabeçalho SOAP da solicitação SOAP ou pela instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] que incluído o **ProtocolCapabilities** elemento de cabeçalho no cabeçalho SOAP da resposta SOAP. O valor do elemento **Capability** é o nome do recurso com suporte.  
  
 O [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] oferece suporte aos recursos listados na tabela a seguir.  
  
|Nome do recurso|Descrição|  
|---------------------|-----------------|  
|sx|Suporte a XML binário|  
|xpress|Suporte à compactação|  
  
## <a name="see-also"></a>Consulte também  
 [Gerenciando conexões e sessões & #40; XMLA & #41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md)   
 [Propriedades & #40; XMLA & #41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  