---
title: Propriedade NamedParameters (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Command::NamedParameters
helpviewer_keywords:
- NamedParameters property [ADO]
ms.assetid: 42409387-026c-435f-a9b1-bf4167095875
author: MightyPen
ms.author: genemi
ms.openlocfilehash: d63c413ebed585782ca5ce0568119dd7e05bf8ac
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67932069"
---
# <a name="namedparameters-property-ado"></a>Propriedade NamedParameters (ADO)
Indica se os nomes de parâmetro devem ser passados para o provedor.  
  
## <a name="remarks"></a>Comentários  
 Quando essa propriedade é true, o ADO passa o valor da **nome** propriedade de cada parâmetro na **parâmetro** coleta para o [objeto de comando](../../../ado/reference/ado-api/command-object-ado.md). O provedor usa um nome de parâmetro para corresponder aos parâmetros na **CommandText** ou **CommandStream** propriedades. Se essa propriedade for false (padrão), nomes de parâmetro são ignorados e o provedor usa a ordem dos parâmetros para corresponder aos valores aos parâmetros na **CommandText** ou **CommandStream** propriedades.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [Propriedade CommandText (ADO)](../../../ado/reference/ado-api/commandtext-property-ado.md)   
 [Propriedade CommandStream (ADO)](../../../ado/reference/ado-api/commandstream-property-ado.md)   
 [Coleção Parameters (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)
