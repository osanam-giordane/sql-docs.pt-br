---
title: O nível (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: b419cbb05aa616f163f5878bda83c9d68203575d
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67905667"
---
# <a name="level-mdx"></a>Level (MDX)


  Retorna o nível de um membro.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Member_Expression.Level  
```  
  
## <a name="arguments"></a>Argumentos  
 *Member_Expression*  
 Um válido MDX (Multidimensional Expression) que retorna um membro.  
  
### <a name="examples"></a>Exemplos  
 O exemplo a seguir usa o **nível** função para retornar todos os meses no cubo Adventure Works.  
  
```  
SELECT[Date].[Fiscal].[Month].[February 2002].Level.Members ON 0,  
[Measures].[Internet Sales Amount] ON 1  
FROM [Adventure Works]  
```  
  
 O exemplo a seguir usa o **nível** função para retornar o nome do nível de bicicleta multifuncional na hierarquia de atributo de nome do modelo no cubo Adventure Works.  
  
```  
WITH MEMBER Measures.x AS   
   [Product].[Model Name].[All-Purpose Bike Stand].Level.Name  
SELECT Measures.x ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Consulte também  
 [Referência da Função MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
