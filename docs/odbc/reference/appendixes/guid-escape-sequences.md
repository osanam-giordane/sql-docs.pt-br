---
title: Sequências de Escape GUID | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC escape sequences [ODBC], GUID
- escape sequences [ODBC], guid
- guid escape sequence [ODBC]
ms.assetid: 71d43ef9-4a31-493e-b9e0-f864e9ef3ce6
author: MightyPen
ms.author: genemi
ms.openlocfilehash: a74ed9d4dfe0afb8bf59abb11220a0677d000bfb
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67947581"
---
# <a name="guid-escape-sequences"></a>Sequências de escape GUID
ODBC usa sequências de escape para literais GUID. A sintaxe dessa sequência de escape é da seguinte maneira:  
  
```  
{guid 'nnnnnnnn-nnnn-nnnn-nnnn-nnnnnnnnnnnn'}  
```  
  
## <a name="remarks"></a>Comentários  
 Na notação BNF, a sintaxe é:  
  
 *Escape de ODBC-guid* :: =  
     *Guid de iniciador do ODBC-esc* '*valor de guid*' *terminador de esc ODBC*  
  
 *Iniciador do ODBC-esc* :: = {  
  
 *Terminador de esc ODBC* :: =}  
  
 *valor de GUID* :: = *separador relógio baixo valor guid guid-separador de valor do relógio intermediária separador do relógio de alto valor guid guid-separador de valor do relógio seq nó-valor*  
  
 *guid-separator* ::= -  
  
 *valor de baixa de relógio* :: = *hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit*  
  
 *valor do relógio intermediária* :: = *hex_digit hex_digit hex_digit hex_digit*  
  
 *relógio valioso* :: = *hex_digit hex_digit hex_digit hex_digit*  
  
 *clock-seq-value* ::= *hex_digit hex_digit hex_digit hex_digit*  
  
 *valor do nó de relógio* :: = *hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit*  
  
 *hex_digit* :: = 0 &#124; 1 &#124; 2 &#124; 3 &#124; 4 &#124; 5 &#124; 6 &#124; 7 &#124; 8 &#124; 9 &#124; A &#124; B &#124; C &#124; 1!d &#124; E &#124; F  
  
 A sequência de escape literal GUID tem suporte se o tipo de dados GUID é suportado pela fonte de dados. Um aplicativo deve chamar **SQLGetTypeInfo** para determinar se esse tipo de dados tem suporte.
