---
title: SQL Server:Buffer Node | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLServer:Buffer Node
- Buffer Node object
ms.assetid: fd3f9f0f-7c38-4cfd-a0c5-ee93dd52d9a5
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: dfa6d195bea68fbc4d2beed8ad74e51c89d57c71
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="sql-serverbuffer-node"></a>SQL Server:Buffer Node
  O objeto **Buffer Node** fornece contadores que complementam aqueles fornecidos pelo objeto **Buffer Manager** . Ele lhe permite monitorar a distribuição de páginas de pool de buffer do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cada nó NUMA (non-uniform memory access). Há uma instância do objeto **Buffer Node** para cada nó NUMA em uso. Em arquiteturas diferentes de NUMA, haverá uma única instância do objeto **Buffer Node** .  
  
## <a name="buffer-node-performance-objects"></a>Objetos de desempenho do Buffer Node  
 Esta tabela descreve os objetos de desempenho de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Buffer Node** .  
  
|Contadores de Buffer Node do SQL Server|Descrição|  
|-------------------------------------|-----------------|  
|**Páginas do banco de dados**|Indica o número de páginas no pool de buffers do nó com conteúdo de banco de dados.|  
|**Expectativa de vida da página**|Indica o número mínimo de segundos que uma página ficará no pool de buffers do nó sem referências.|  
|**Pesquisas de página de nó local/s**|Indica o número de solicitações de pesquisa desse nó que foram atendidas nesse nó.|  
|**Pesquisas de página de nó remoto/s**|Indica o número de solicitações de pesquisa desse nó que foram atendidas em outros nós.|  
  
 Se o SQL Server estiver em execução em um hardware diferente de NUMA, os contadores dos objetos **Buffer Node** e **Buffer Manager** deverão ser correspondentes.  
  
 No hardware NUMA, as somas dos respectivos contadores de todos os objetos **Buffer Node** devem corresponder aos seus equivalentes no **Buffer Manager**.  
  
> [!NOTE]  
>  Os valores e somas dos contadores podem não corresponder exatamente, devido à natureza dinâmica dos contadores e à exatidão da amostragem.  
  
## <a name="see-also"></a>Consulte também  
 [SQL Server, objeto Buffer Manager](../../relational-databases/performance-monitor/sql-server-buffer-manager-object.md)   
 [Opções Server Memory de configuração do servidor](../../database-engine/configure-windows/server-memory-server-configuration-options.md)   
 [Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)   
 [sys.dm_os_performance_counters &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql.md)  
  
  