---
title: Propriedades personalizadas do destino DataReader | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f151c3e8-3811-457d-a3d3-6158ca65a646
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 44a9f26f1125f2c6b319653528aaa7eea04aa84f
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="datareader-destination-custom-properties"></a>Propriedades personalizadas do destino DataReader
  O destino DataReader tem propriedades personalizadas e propriedades comuns a todos os componentes de fluxo de dados.  
  
 A tabela a seguir descreve as propriedades personalizadas do destino DataReader. Todas as propriedades, exceto **DataReader** , são de leitura/gravação.  
  
|Nome da propriedade|Tipo de Dados|Description|  
|-------------------|---------------|-----------------|  
|DataReader|Cadeia de caracteres|O nome da classe do destino DataReader.|  
|FailOnTimeout|Booliano|Indica se deve haver falha na ocorrência de **ReadTimeout** . O valor padrão dessa propriedade é **False**.|  
|ReadTimeout|Integer|O número de milissegundos antes de um tempo limite. O valor padrão dessa propriedade é 30000 (30 segundos).|  
  
 A entrada e as colunas de entrada do destino DataReader não têm nenhuma propriedade personalizada.  
  
 Para obter mais informações, consulte [DataReader Destination](../../integration-services/data-flow/datareader-destination.md).  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades comuns](http://msdn.microsoft.com/library/51973502-5cc6-4125-9fce-e60fa1b7b796)  
  
  