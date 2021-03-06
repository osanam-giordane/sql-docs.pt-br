---
title: SQL Server, Réplica de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- SQLServer:Database Replica
- performance counters [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], performance counters
ms.assetid: a5f6bdce-2b13-4924-aaeb-b50b57d624d8
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 9ea811d8fcc598342781111aa559795888a889b2
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "63250768"
---
# <a name="sql-server-database-replica"></a>SQL Server, Réplica de Banco de Dados
  O objeto de desempenho **SQLServer:Database Replica** contém contadores de desempenho que relatam informações sobre os bancos de dados secundários na réplica secundária de um grupo de disponibilidade AlwaysOn no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. Esse objeto só é válido em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda uma réplica secundária.  
  
|Nome do contador|Descrição|Exibir em...|  
|------------------|-----------------|--------------|  
|**Bytes de Arquivo Recebidos/s**|Quantidade de dados FILESTREAM recebida pela réplica secundária para o banco de dados secundário no último segundo.|Réplica secundária|  
|**Bytes de Log Recebidos/s**|Quantidade registros de log recebida pela réplica secundária para o banco de dados secundário no último segundo.|Réplica secundária|  
|**Log restante para desfazer**|A quantidade de log em quilobytes restante para a conclusão da fase desfazer.|Réplica secundária|  
|**Fila de Envio de Log**|Quantidade de registros de log nos arquivos de log do banco de dados primário, em quilobytes, que ainda não foram enviados à réplica secundária. Esse valor é enviado à réplica secundária da réplica primária. O tamanho da fila não inclui arquivos FILESTREAM enviados a um secundário.|Réplica secundária|  
|**Transação de Gravação Espelhada/s**|Número de transações que foram gravadas no banco de dados primário e depois aguardaram para confirmar até que o log fosse enviado para o banco de dados secundário, no último segundo.|Réplica primária|  
|**Fila de Recuperação**|Quantidade de registros de log nos arquivos de log da réplica secundária que ainda não foram refeitos.|Réplica secundária|  
|**Ações de refazer bloqueadas/s**|Número de vezes que o thread de restauração é bloqueado nos bloqueios mantidos por leitores do banco de dados.|Réplica secundária|  
|**Bytes de Restauração Restantes**|A quantidade de log em quilobytes a ser refeita para concluir a fase de reversão.|Réplica secundária|  
|**Bytes Refeitos/s**|Quantidade de registros de log refeitos no banco de dados secundário no último segundo.|Réplica secundária|  
|**Total de Log a ser desfeito**|Total de quilobytes de log que deve ser desfeito.|Réplica secundária|  
|**Atraso na Transação**|Atraso na espera por reconhecimento de confirmação não terminado, em milissegundos.|Réplica primária|  
  
## <a name="see-also"></a>Consulte também  
 [Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](monitor-resource-usage-system-monitor.md)   
 [SQL Server, Réplica de Disponibilidade](sql-server-availability-replica.md)   
 [SQL Server, objeto Databases](sql-server-databases-object.md)   
 [Grupos de disponibilidade AlwaysOn (SQL Server)](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
