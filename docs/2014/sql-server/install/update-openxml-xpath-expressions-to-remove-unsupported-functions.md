---
title: Atualizar expressões OPENXML XPath para remover funções sem suporte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- OPENXML queries
ms.assetid: b459abaf-8787-4b65-9231-ae30e5469fd0
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: ec0edb2e72143fd41709355a3e9cc338544289a6
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66091693"
---
# <a name="update-openxml-xpath-expressions-to-remove-unsupported-functions"></a>Atualizar expressões OPENXML XPath para remover funções para as quais não há suporte
  O Supervisor de Atualização detectou o uso da funcionalidade XPath. Você pode ser afetado por alterações na funcionalidade XPath para recursos OPENXML depois de atualizar.  
  
## <a name="component"></a>Componente  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>Descrição  
 Agora, o MSXML 3.0 é o mecanismo subjacente usado para processar expressões que são usadas dentro de consultas OPENXML. O MSXML 3.0 tem um mecanismo XPath 1.0 mais restrito, do qual foi removido o suporte para as seguintes funções:  
  
-   format-number()  
  
-   formatNumber ()  
  
-   current()  
  
-   element-available()  
  
-   function-available()  
  
-   system-property()  
  
## <a name="corrective-action"></a>Ação corretiva  
 No caso das funções format-number() e formatNumber(), você pode usar [!INCLUDE[tsql](../../includes/tsql-md.md)]. Para as outras funções sem-suporte listadas anteriormente, não há nenhuma solução alternativa direta.  
  
## <a name="see-also"></a>Consulte também  
 [Problemas de atualização de mecanismo de banco de dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [Supervisor de atualização do SQL Server 2014 &#91;novo&#93;](sql-server-2014-upgrade-advisor.md)  
  
  
