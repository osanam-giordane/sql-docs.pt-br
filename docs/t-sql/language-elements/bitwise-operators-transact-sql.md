---
title: Operadores bit a bit (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 09/07/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- operators [Transact-SQL], bitwise
- bitwise operators
- bit manipulations
ms.assetid: 2b994cf5-2daa-438a-b8c7-4bd8d451ac8d
caps.latest.revision: 29
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 05976158e43d7dfafaf02289462d1537f5beeb36
ms.openlocfilehash: 5d04924a82578040f801864bb68905feebc53e94
ms.contentlocale: pt-br
ms.lasthandoff: 09/08/2017

---
# <a name="bitwise-operators-transact-sql"></a>Operadores bit a bit (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Os operadores bit a bit desempenham manipulações de bit entre duas expressões de qualquer um dos tipos de dados da categoria de tipo de dados inteiro.  
  Operadores bit a bit converter dois valores inteiros para bits binários, execute AND, OR, ou não a operação de cada bit, produzindo um resultado. Em seguida, converte o resultado em um inteiro.  
  
  Por exemplo, o inteiro 170 converte em 1010 1010 binário.
Converte o inteiro 75 0100 1011 binário.

|operador|matemática de bit a bit|
|---- |---- |
|AND <br> Se o bits em qualquer local forem 1, o resultado é 1. |1010 1010 = 170 <br>0100 1011 =  75 <br>-----------------  <br> 0000 1010 =  10 |
|ou <br> Se qualquer bit em qualquer local for 1, o resultado é 1. |1010 1010 = 170 <br>0100 1011 =  75 <br>-----------------  <br> 1110 1011 = 235|
|NOT  <br> Inverte o valor de bit em cada local de bit. |1010 1010 = 170 <br>----------------- <br>  0101 0101 =   85 |
  
Consulte os tópicos a seguir:   
* [& (AND bit a bit)](../../t-sql/language-elements/bitwise-and-transact-sql.md)  
* [& = (AND bit a bit é igual a)](../../t-sql/language-elements/bitwise-and-equals-transact-sql.md)   
* [&#124; (OR bit a bit)](../../t-sql/language-elements/bitwise-or-transact-sql.md)  
* [&#124; = (OR bit a bit é igual a)](../../t-sql/language-elements/bitwise-or-equals-transact-sql.md)   
* [^ (Bit a bit exclusivo)](../../t-sql/language-elements/bitwise-exclusive-or-transact-sql.md)  
* [^ = (Igual a OR exclusivo bit a bit)](../../t-sql/language-elements/bitwise-exclusive-or-equals-transact-sql.md)  
* [~ (NOT bit a bit)](../../t-sql/language-elements/bitwise-not-transact-sql.md)  
  
 Os operandos de operadores bit a bit podem ser qualquer um dos tipos de dados de inteiro ou categorias de tipo de dados de cadeia de caracteres binária (exceto para o **imagem** tipo de dados), exceto que os dois operandos não podem ser qualquer um dos tipos de dados da cadeia de caracteres binária categoria de tipo de dados. A tabela a seguir mostra os tipos de dados de operando com suporte.  
  
|Operando da esquerda|Operando da direita|  
|------------------|-------------------|  
|[binary](../../t-sql/data-types/binary-and-varbinary-transact-sql.md)|**int**, **smallint**, ou **tinyint**|  
|[bit](../../t-sql/data-types/bit-transact-sql.md)|**int**, **smallint**, **tinyint**, ou **bits**|  
|[int](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md)|**int**, **smallint**, **tinyint**, **binário**, ou **varbinary**|  
|[smallint](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md)|**int**, **smallint**, **tinyint**, **binário**, ou **varbinary**|  
|[tinyint](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md)|**int**, **smallint**, **tinyint**, **binário**, ou **varbinary**|  
|[varbinary](../../t-sql/data-types/binary-and-varbinary-transact-sql.md)|**int**, **smallint**, ou **tinyint**|  
  
## <a name="see-also"></a>Consulte também  
 [Operadores &#40; Transact-SQL &#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [Tipos de dados &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)  
  
  
