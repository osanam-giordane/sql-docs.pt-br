---
title: "! (Não lógico) (Expressão SSIS) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- logical Not (!)
- '! (logical Not)'
ms.assetid: d5c4d1e1-7be4-4d25-bcd9-5b6ddb53b3b3
caps.latest.revision: 35
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 003e0fcc98a267342aaf7c77bf344cdfdc71880b
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="-logical-not-ssis-expression"></a>! (Não lógico) (Expressão do SSIS)
  Nega um operando booliano.  
  
> [!NOTE]  
>  O operador ! não pode ser usado em conjunto com outros operadores. Por exemplo, você não pode combinar os operadores ! e os operadores > no operador !>.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
!boolean_expression  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *boolean_expression*  
 É qualquer expressão válida avaliada como um Booliano. Para obter mais informações, consulte [Integration Services Data Types](../../integration-services/data-flow/integration-services-data-types.md).  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_BOOL  
  
## <a name="remarks"></a>Comentários  
 A tabela a seguir mostra o resultado da operação publicação.  
  
|Expressão booliana original|Depois de aplicar o operador|  
|---------------------------------|------------------------------------|  
|TRUE|FALSE|  
|NULL|NULL|  
|FALSE|TRUE|  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Este exemplo será avaliado como FALSE se o valor da coluna **Color** for "vermelho".  
  
```  
!(Color == "red")  
```  
  
 Esse exemplo será avaliado como TRUE se o valor da variável **MonthNumber** for o mesmo que o inteiro que representa o mês atual. Para obter mais informações, consulte [MONTH &#40;Expressão SSIS&#41;](../../integration-services/expressions/month-ssis-expression.md) e [GETDATE &#40;Expressão SSIS&#41;](../../integration-services/expressions/getdate-ssis-expression.md).  
  
```  
!(@MonthNumber != MONTH(GETDATE())  
```  
  
## <a name="see-also"></a>Consulte também  
 [Precedência do operador e capacidade de associação](../../integration-services/expressions/operator-precedence-and-associativity.md)   
 [Operadores &#40; Expressão SSIS &#41;](../../integration-services/expressions/operators-ssis-expression.md)  
  
  