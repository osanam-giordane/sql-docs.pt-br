---
title: Eixos de coleção (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Axes
- Cellset::Axes
helpviewer_keywords:
- Axes collection [ADO MD]
ms.assetid: 072fb21a-ec0f-4b02-9022-1cef3ad4bfff
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 6c06faf6327d60be823ce9d99215655b5badf5e3
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67947401"
---
# <a name="axes-collection-ado-md"></a>Coleção Axes (ADO MD)
Contém o [eixo](../../../ado/reference/ado-md-api/axis-object-ado-md.md) objetos que definem um conjunto de células.  
  
## <a name="remarks"></a>Comentários  
 Um [Cellset](../../../ado/reference/ado-md-api/cellset-object-ado-md.md) objeto contém uma **eixos** coleção. Uma vez a **Cellset** é aberto, essa coleção conterá pelo menos um **eixo**. Consulte a [eixo](../../../ado/reference/ado-md-api/axis-object-ado-md.md) objeto para obter uma explicação mais detalhada de como usar **eixo** objetos.  
  
> [!NOTE]
>  Eixo do filtro de uma **Cellset** não está contido na **eixos** coleção. Consulte a [FilterAxis](../../../ado/reference/ado-md-api/filteraxis-property-ado-md.md) propriedade para obter mais informações.  
  
 **Eixos** é uma coleção padrão de ADO. Com as propriedades e métodos de uma coleção, você pode fazer o seguinte:  
  
-   Obter o número de objetos na coleção com o [contagem](../../../ado/reference/ado-api/count-property-ado.md) propriedade.  
  
-   Retornar um objeto da coleção com o padrão [Item](../../../ado/reference/ado-api/item-property-ado.md) propriedade.  
  
-   Atualizar os objetos na coleção do provedor com o [Refresh](../../../ado/reference/ado-api/refresh-method-ado.md) método.  
  
 Esta seção contém o tópico a seguir.  
  
-   [Propriedades, métodos e eventos](../../../ado/reference/ado-md-api/axes-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de conjunto de células (VB)](../../../ado/reference/ado-md-api/cellset-example-vb.md)   
 [Objeto Axis (ADO MD)](../../../ado/reference/ado-md-api/axis-object-ado-md.md)
