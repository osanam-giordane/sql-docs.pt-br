---
title: DOMAIN_CONSTRAINTS (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: system-information-schema-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DOMAIN_CONSTRAINTS
- DOMAIN_CONSTRAINTS_TSQL
dev_langs: TSQL
helpviewer_keywords:
- INFORMATION_SCHEMA.DOMAIN_CONSTRAINTS view
- DOMAIN_CONSTRAINTS view
ms.assetid: 436c4480-f1e3-403f-b2bd-de04539afe3c
caps.latest.revision: "28"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1e39387eb33957487c57764152d9532c2acd8dde
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="domainconstraints-transact-sql"></a>DOMAIN_CONSTRAINTS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna uma linha para cada tipo de dados de alias no banco de dados atual, que tem uma regra associada e que pode ser acessado pelo usuário atual.  
  
 Para recuperar informações dessas exibições, especifique o nome totalmente qualificado do **INFORMATION_SCHEMA.** *view_name*.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**CONSTRAINT_CATALOG**|**nvarchar (**128**)**|Banco de dados no qual a regra existe.|  
|**CONSTRAINT_SCHEMA**|**nvarchar (**128**)**|Nome do esquema que contém a restrição.<br /><br /> **\*\*Importante \* \***  não use exibições INFORMATION_SCHEMA para determinar o esquema de um objeto. O único modo seguro de localizar o esquema de um objeto é consultar a exibição de catálogo sys.objects.|  
|**CONSTRAINT_NAME**|**sysname**|Nome de regra.|  
|**DOMAIN_CATALOG**|**nvarchar (**128**)**|Banco de dados no qual o tipo de dados de alias existe.|  
|**DOMAIN_SCHEMA**|**nvarchar (**128**)**|Nome do esquema que contém o tipo de dados de alias.<br /><br /> **\*\*Importante \* \***  não use exibições INFORMATION_SCHEMA para determinar o esquema de um tipo de dados. O único modo seguro para localizar o esquema de um tipo é usar a função TYPEPROPERTY.|  
|**NOME_DO_DOMÍNIO**|**sysname**|Tipo de dados de alias.|  
|**IS_DEFERRABLE**|**varchar (**2**)**|Especifica se a verificação de restrição é adiável. Sempre retorna NO.|  
|**INITIALLY_DEFERRED**|**varchar (**2**)**|Especifica se a verificação de restrição é inicialmente adiada. Sempre retorna NO.|  
  
## <a name="see-also"></a>Consulte também  
 [Exibições do sistema &#40; Transact-SQL &#41;](http://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)   
 [Exibições do esquema de informações &#40; Transact-SQL &#41;](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [sys. Objects &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)   
 [Types &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-types-transact-sql.md)  
  
  