---
title: Repetir rastreamentos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Profiler, replaying traces
- Run to Cursor option
- Toggle Breakpoint option
- traces [SQL Server], replaying
- replaying traces
- playback engine [SQL Server Profiler]
- events [SQL Server], replaying traces
- Profiler [SQL Server Profiler], replaying traces
ms.assetid: da958d3c-7f3e-44c9-aecc-8a9493bea7c0
caps.latest.revision: 28
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4e6f0b2068faf1fb5282eb0effd348cb01d4ac91
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36122074"
---
# <a name="replay-traces"></a>Repetir rastreamentos
  Reprodução é a capacidade para reproduzir a atividade que foi capturada em um rastreamento. Ao criar ou editar um rastreamento, você pode salvá-lo em um arquivo para reproduzi-lo posteriormente. Você pode usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para reproduzir a atividade de rastreamento de um único computador. Para cargas de trabalho grandes, use o Distributed Replay Utility para reproduzir dados de rastreamento de vários computadores.  
  
 Esta seção descreve como usar os recursos de reprodução do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]. Para obter mais informações sobre o Distributed Replay Utility, consulte [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] apresenta um mecanismo de repetição multi-threaded que consegue simular as conexões de usuário e a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . A repetição é útil para solucionar problemas de aplicativos ou processos. Tendo identificado o problema e implementado correções, execute o rastreamento que encontrou o problema potencial contra o aplicativo ou processo corrigido. Em seguida, repita o rastreamento original e compare os resultados.  
  
 A repetição de rastreamentos dá suporte à depuração por meio das opções **Alternar Ponto de Interrupção** e **Executar até o Cursor** do menu [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Replay** menu. Essas opções melhoram, em especial, a análise de scripts longos, pois elas podem dividir a repetição do rastreamento em segmentos curtos que podem ser analisados incrementalmente.  
  
 Para obter informações sobre as permissões necessárias para reproduzir rastreamentos, consulte [Permissões necessárias para executar o SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).  
  
## <a name="in-this-section"></a>Nesta seção  
  
|Tópico|Description|  
|-----------|-----------------|  
|[Requisitos para reprodução](replay-requirements.md)|Descreve os eventos que devem ser incluídos na definição de um rastreamento para que ele possa ser reproduzido com o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].|  
|[Opções de repetição &#40;SQL Server Profiler&#41;](replay-options-sql-server-profiler.md)|Descreve as opções que podem ser definidas na caixa de diálogo **Configuração de Reprodução** do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].|  
|[Considerações para reproduzir rastreamentos &#40;SQL Server Profiler&#41;](considerations-for-replaying-traces-sql-server-profiler.md)|Descreve os eventos de rastreamento que não podem ser reproduzidos com o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] e os efeitos da reprodução de rastreamentos no desempenho do servidor.|  
  
## <a name="see-also"></a>Consulte também  
 [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md)  
  
  