---
title: LinkMember (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 8a00388e067878d9c2165cbae6844f8020b7c63e
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67905599"
---
# <a name="linkmember-mdx"></a>LinkMember (MDX)


  Retorna o membro equivalente a um membro especificado em uma hierarquia especificada.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
LinkMember(Member_Expression, Hierarchy_Expression)   
```  
  
## <a name="arguments"></a>Argumentos  
 *Member_Expression*  
 Uma linguagem MDX válida que retorna um membro.  
  
 *Expressão_Hierarquia*  
 Uma linguagem MDX válida que retorna uma hierarquia.  
  
## <a name="remarks"></a>Comentários  
 O **LinkMember** função retorna o membro da hierarquia especificada que coincide com os valores de chave em cada nível do membro especificado em uma hierarquia relacionada. Os atributos em cada nível devem ter a mesma cardinalidade de chave e tipo de dados. Em hierarquias não naturais, se houver mais de uma correspondência para um valor de chave do atributo, o resultado será um erro ou indeterminado.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir usa o **LinkMember** função para retornar a medida padrão no cubo Adventure Works para os ascendentes do membro 1º de julho de 2002 da hierarquia de atributo Date na hierarquia calendário.  
  
```  
SELECT  Hierarchize  
   (Ascendants   
      (LinkMember   
         ([Date].[Date].[July 1, 2002], [Date].[Calendar]  
         )  
       )  
    ) ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Consulte também  
 [Hierarchize &#40;MDX&#41;](../mdx/hierarchize-mdx.md)   
 [Ascendentes &#40;MDX&#41;](../mdx/ascendants-mdx.md)   
 [Referência da Função MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
