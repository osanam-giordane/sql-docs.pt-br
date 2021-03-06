---
title: Resumir os resultados da consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- queries [SQL Server], results
- aggregate queries [SQL Server]
ms.assetid: c9e15350-ed57-4d95-814d-815fbebfd86b
author: markingmyname
ms.author: maghan
ms.openlocfilehash: c87d6eae1096d2c59e90895d4de5e44ac18843a4
ms.sourcegitcommit: e7d921828e9eeac78e7ab96eb90996990c2405e9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68263172"
---
# <a name="summarize-query-results-visual-database-tools"></a>Resumir resultados da consulta (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
Quando você cria consultas de agregação, certos princípios lógicos se aplicam. Por exemplo, você não pode exibir o conteúdo de linhas individuais em uma consulta resumida. O Designer de Consulta e Exibição o ajuda a seguir esses princípios segundo a maneira como o [painel de Diagrama](../../ssms/visual-db-tools/diagram-pane-visual-database-tools.md) e o [painel Critérios](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md) se comportam.  
  
Compreendendo os princípios de consultas de agregação e o comportamento do Designer de Consulta e Exibição, você pode criar consultas de agregação logicamente corretas. O princípio prioritário é que consultas de agregação podem resultar apenas em informações resumidas. Assim, a maioria dos princípios que se seguem descreve as maneiras como você pode referenciar colunas de dados individuais dentro de uma consulta de agregação.  
  
## <a name="in-this-section"></a>Nesta seção  
[Trabalhar com colunas em consultas de agregação &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/work-with-columns-in-aggregate-queries-visual-database-tools.md)  
Descreve conceitos sobre como agrupar e resumir colunas com as cláusulas GROUP BY, WHERE e HAVING.  
  
[Contar linhas em uma tabela &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/count-rows-in-a-table-visual-database-tools.md)  
Fornece etapas para contar o número de linhas em uma tabela ou o número das linhas de uma tabela que atendem a um conjunto de critérios.  
  
[Resumir ou agregar valores para todas as linhas em uma tabela &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
Oferece etapas para resumir todas as linhas, em vez de um conjunto de linhas agrupadas.  
  
[Resumir ou agregar valores usando expressões personalizadas &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
Oferece etapas para usar expressões para resumir ou agregar, em vez de usar as cláusulas predefinidas.  
  
## <a name="related-sections"></a>Seções relacionadas  
[Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
Oferece links para tópicos que cobrem o modo de usar o Designer de Consulta e Exibição.  
  
