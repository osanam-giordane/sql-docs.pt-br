---
title: "LATÊNCIA (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 10/20/2015
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- LAG_TSQL
- LAG
dev_langs:
- TSQL
helpviewer_keywords:
- LAG function
- analytic functions, LAG
ms.assetid: a9a90bdb-3f80-4c97-baca-b7407bcdc7f0
caps.latest.revision: 23
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 77598feb87f6766f6c24c454dace2c138315e69b
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="lag-transact-sql"></a>LAG (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all_md](../../includes/tsql-appliesto-ss2012-all-md.md)]

  Acessa os dados de uma linha anterior no mesmo conjunto de resultados sem o uso de uma autojunção no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. LAG fornece acesso a uma linha a um determinado deslocamento físico que antecede a linha atual. Use essa função analítica em uma instrução SELECT para comparar valores na linha atual com valores em uma linha anterior.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "ícone de link do tópico") [convenções de sintaxe do Transact-SQL &#40; Transact-SQL &#41;](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
LAG (scalar_expression [,offset] [,default])  
    OVER ( [ partition_by_clause ] order_by_clause )  
```  
  
## <a name="arguments"></a>Argumentos  
 *scalar_expression*  
 O valor a ser retornado com base no deslocamento especificado. É uma expressão de qualquer tipo que retorna um único valor (escalar). *scalar_expression* não pode ser uma função analítica.  
  
 *deslocamento*  
 O número de linhas atrás da linha atual da qual obter um valor. Se não for especificado, o padrão será 1. *deslocamento* pode ser uma coluna, subconsulta ou outra expressão que é avaliada como um número inteiro positivo ou pode ser convertido implicitamente em **bigint**. *deslocamento* não pode ser um valor negativo ou uma função analítica.  
  
 *padrão*  
 O valor a ser retornado quando *scalar_expression* em *deslocamento* é NULL. Se um valor padrão não for especificado, NULL será retornado. *padrão* pode ser uma coluna, subconsulta ou outra expressão, mas ele não pode ser uma função analítica. *padrão* devem ser do tipo compatível com *scalar_expression*.  
  
 SOBRE **(** [ *partition_by_clause* ] *order_by_clause***)**  
 *partition_by_clause* divide o conjunto de resultados produzido pela cláusula FROM em partições para o qual a função é aplicada. Se não for especificado, a função tratará todas as linhas do conjunto de resultados da consulta como um único grupo. *order_by_clause* determina a ordem dos dados antes da função é aplicada. Se *partition_by_clause* for especificado, ele determina a ordem dos dados na partição. O *order_by_clause* é necessário. Para obter mais informações, consulte [a cláusula OVER &#40; Transact-SQL &#41; ](../../t-sql/queries/select-over-clause-transact-sql.md).  
  
## <a name="return-types"></a>Tipos de retorno  
 O tipo de dados especificada *scalar_expression*. NULL será retornado se *scalar_expression* é anulável ou *padrão* é definido como NULL.  
  
## <a name="general-remarks"></a>Comentários gerais  
 LAG é não determinística. Para obter mais informações, veja [Funções determinísticas e não determinísticas](../../relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions.md).  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-compare-values-between-years"></a>A. Comparar valores entre anos  
 O exemplo a seguir usa a função LAG para retornar a diferença em cotas de vendas para um funcionário específico nos anos anteriores. Observe que, como não há um valor de retardo disponível para a primeira linha, o padrão de zero (0) é retornado.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT BusinessEntityID, YEAR(QuotaDate) AS SalesYear, SalesQuota AS CurrentQuota,   
       LAG(SalesQuota, 1,0) OVER (ORDER BY YEAR(QuotaDate)) AS PreviousQuota  
FROM Sales.SalesPersonQuotaHistory  
WHERE BusinessEntityID = 275 and YEAR(QuotaDate) IN ('2005','2006');  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
  
BusinessEntityID SalesYear   CurrentQuota          PreviousQuota  
---------------- ----------- --------------------- ---------------------  
275              2005        367000.00             0.00  
275              2005        556000.00             367000.00  
275              2006        502000.00             556000.00  
275              2006        550000.00             502000.00  
275              2006        1429000.00            550000.00  
275              2006        1324000.00            1429000.00  
  
```  
  
### <a name="b-compare-values-within-partitions"></a>B. Comparar valores dentro de partições  
 O exemplo a seguir usa a função LAG para comparar as vendas no ano até o momento entre funcionários. A cláusula PARTITION BY é especificada para dividir as linhas no conjunto de resultados por território de vendas. A função LAG é aplicada separadamente a cada partição e a computação é reiniciada para cada partição. A cláusula ORDER BY na cláusula OVER ordena as linhas em cada partição. A cláusula ORDER BY na instrução SELECT classifica as linhas em todo o conjunto de resultados. Observe que, como não há um valor de retardo disponível para a primeira linha de cada partição, o padrão de zero (0) é retornado.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT TerritoryName, BusinessEntityID, SalesYTD,   
       LAG (SalesYTD, 1, 0) OVER (PARTITION BY TerritoryName ORDER BY SalesYTD DESC) AS PrevRepSales  
FROM Sales.vSalesPerson  
WHERE TerritoryName IN (N'Northwest', N'Canada')   
ORDER BY TerritoryName;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
  
TerritoryName            BusinessEntityID SalesYTD              PrevRepSales  
-----------------------  ---------------- --------------------- ---------------------  
Canada                   282              2604540.7172          0.00  
Canada                   278              1453719.4653          2604540.7172  
Northwest                284              1576562.1966          0.00  
Northwest                283              1573012.9383          1576562.1966  
Northwest                280              1352577.1325          1573012.9383  
  
```  
  
### <a name="c-specifying-arbitrary-expressions"></a>C. Especificando expressões arbitrárias  
 O exemplo a seguir demonstra como especificar uma variedade de expressões arbitrárias na sintaxe da função LAG.  
  
```  
CREATE TABLE T (a int, b int, c int);   
GO  
INSERT INTO T VALUES (1, 1, -3), (2, 2, 4), (3, 1, NULL), (4, 3, 1), (5, 2, NULL), (6, 1, 5);   
  
SELECT b, c,   
    LAG(2*c, b*(SELECT MIN(b) FROM T), -c/2.0) OVER (ORDER BY a) AS i  
FROM T;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
b           c           i  
----------- ----------- -----------  
1           -3          1  
2           4           -2  
1           NULL        8  
3           1           -6  
2           NULL        NULL  
1           5           NULL  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="d-compare-values-between-quarters"></a>Unidade d: comparar valores entre trimestres  
 O exemplo a seguir demonstra a função LAG. A consulta usa a função LAG para retornar a diferença em cotas de vendas para um funcionário específico nos trimestres do calendário anterior. Observe que, como não há um valor de retardo disponível para a primeira linha, o padrão de zero (0) é retornado.  
  
```  
-- Uses AdventureWorks  
  
SELECT CalendarYear, CalendarQuarter, SalesAmountQuota AS SalesQuota,  
       LAG(SalesAmountQuota,1,0) OVER (ORDER BY CalendarYear, CalendarQuarter) AS PrevQuota,  
       SalesAmountQuota - LAG(SalesAmountQuota,1,0) OVER (ORDER BY CalendarYear, CalendarQuarter) AS Diff  
FROM dbo.FactSalesQuota  
WHERE EmployeeKey = 272 AND CalendarYear IN (2001, 2002)  
ORDER BY CalendarYear, CalendarQuarter;   
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
Year Quarter  SalesQuota  PrevQuota  Diff  
---- -------  ----------  ---------  -------------  
2001 3        28000.0000      0.0000   28000.0000  
2001 4         7000.0000  28000.0000  -21000.0000  
2001 1        91000.0000   7000.0000   84000.0000  
2002 2       140000.0000  91000.0000   49000.0000  
2002 3         7000.0000 140000.0000  -70000.0000  
2002 4       154000.0000   7000.0000   84000.0000
```  
  
## <a name="see-also"></a>Consulte também  
 [Cliente potencial &#40; Transact-SQL &#41;](../../t-sql/functions/lead-transact-sql.md)  
  
  


