---
title: Usando funções lógicas | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 723d481bc858d7d1db4a63cbb32ab5614eddbb55
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68097163"
---
# <a name="using-logical-functions"></a>Usando funções lógicas


  Uma função lógica executa uma operação ou comparação lógica em objetos e expressões e retorna um valor booliano. As funções lógicas são essenciais na linguagem MDX para determinar a posição de um membro.  
  
 A função lógica mais comumente usada é a **IsEmpty** função. Para obter mais informações sobre como usar o **IsEmpty** , consulte [trabalhando com valores vazios](../mdx/working-with-empty-values.md).  
  
 A consulta a seguir mostra como usar o **IsLeaf** e **IsAncestor** funções:  
  
 `WITH`  
  
 `//Returns true if the CurrentMember on Calendar is a leaf member, ie it has no children`  
  
 `MEMBER MEASURES.[IsLeafDemo] AS IsLeaf([Date].[Calendar].CurrentMember)`  
  
 `//Returns true if the CurrentMember on Calendar is an Ancestor of July 1st 2001`  
  
 `MEMBER MEASURES.[IsAncestorDemo] AS IsAncestor([Date].[Calendar].CurrentMember, [Date].[Calendar].[Date].&[1])`  
  
 `SELECT{MEASURES.[IsLeafDemo],MEASURES.[IsAncestorDemo] } ON 0,`  
  
 `[Date].[Calendar].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Consulte também  
 [Funções &#40;sintaxe MDX&#41;](../mdx/functions-mdx-syntax.md)  
  
  
