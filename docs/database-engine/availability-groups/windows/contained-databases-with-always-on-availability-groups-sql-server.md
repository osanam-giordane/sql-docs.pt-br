---
title: Bancos de dados independentes com Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: 
ms.date: 05/17/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-high-availability
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- contained database, AlwaysOnAvailabilityGroups
ms.assetid: cacce3ae-e940-4566-8298-6607c4268e74
caps.latest.revision: 9
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: a1ea761be7b1009cabe6f12c1ca338af3eb97490
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="contained-databases-with-always-on-availability-groups-sql-server"></a>Bancos de dados independentes com grupos de disponibilidade AlwaysOn (SQL Server)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Este tópico contém informações sobre como usar um banco de dados independente com o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].  
  
 **Neste tópico:**  
  
-   [Pré-requisitos](#Prerequisites)  
  
-   [Tarefas relacionadas](#RelatedTasks)  
  
##  <a name="Prerequisites"></a> Pré-requisitos  
  
-   Antes de adicionar um banco de dados independente a um grupo de disponibilidade, verifique se a opção de servidor **autenticação de banco de dados independente** está definida como **1** em cada instância de servidor que hospeda uma réplica de disponibilidade do grupo de disponibilidade. Para obter mais informações, veja [Opção contained database authentication de configuração de servidor](../../../database-engine/configure-windows/contained-database-authentication-server-configuration-option.md) e [Opções de configuração do servidor &#40;SQL Server&#41;](../../../database-engine/configure-windows/server-configuration-options-sql-server.md).  
  
##  <a name="RelatedTasks"></a> Tarefas relacionadas  
  
-   [Opções de configuração do servidor &#40;SQL Server&#41;](../../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Bancos de dados independentes](../../../relational-databases/databases/contained-databases.md)  
  
  
