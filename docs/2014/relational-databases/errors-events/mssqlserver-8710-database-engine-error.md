---
title: MSSQLSERVER_8710 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8710 (Database Engine error)
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 79c9fc7c9c15d83dafc8d117e142fc06741c11ee
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "62912491"
---
# <a name="mssqlserver8710"></a>MSSQLSERVER_8710
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|MSSQLSERVER|  
|ID do evento|8710|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|QUERY2_CUBE_ILLEGAL_AGG_FUNC|  
|Texto da mensagem|As funções de agregação usadas com consultas CUBE, ROLLUP ou GROUPING SET devem ser fornecidas para a mesclagem de subagregações. Para corrigir esse problema, remova a função de agregação ou grave a consulta que está usando as cláusulas UNION ALL sobre GROUP BY.|  
  
## <a name="explanation"></a>Explicação  
 Uma função de agregação foi usada com CUBE, ROLLUP ou GROUPING SET e não forneceu um método para mesclar subagregações.  
  
## <a name="user-action"></a>Ação do usuário  
 Para corrigir esse problema, remova a função de agregação ou grave a consulta que está usando as cláusulas UNION ALL sobre GROUP BY.  
  
  
