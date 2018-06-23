---
title: Classe de evento QN:Subscription | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], QN:Subscription
ms.assetid: 4916167e-8541-43b4-900e-ec8e6adcbc34
caps.latest.revision: 20
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7dd4c06a89eeebe5c3b7e83a699ea17ca68bbd18
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36130772"
---
# <a name="qnsubscription-event-class"></a>Classe de evento QN:Subscription
  O evento QN:Subscription fornece informações sobre assinaturas de notificação.  
  
## <a name="qnsubscription-event-class-data-columns"></a>Coluna de dados de classe de evento QN:Subscription  
  
|Coluna de dados|Tipo|Description|Número da coluna|Filtrável|  
|-----------------|----------|-----------------|-------------------|----------------|  
|ApplicationName|`nvarchar`|O nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.|10|Sim|  
|ClientProcessID|`int`|A ID atribuída pelo computador host ao processo em que está sendo executado o aplicativo cliente. Essa coluna de dados será populada se a ID do processo do cliente for fornecida pelo cliente.|9|Sim|  
|DatabaseID|`int`|A ID do banco de dados especificada pela instrução de *banco de dados* USE ou a ID do banco de dados padrão se nenhuma instrução de *banco de dados*USE tiver sido emitida para determinada instância. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] exibirá o nome do banco de dados se a coluna de dados Server Name for capturada no rastreamento e o servidor estiver disponível. Determine o valor para um banco de dados usando a função DB_ID.|3|Sim|  
|DatabaseName|`nvarchar`|O nome do banco de dados no qual a instrução do usuário está sendo executada.|35|Sim|  
|EventClass|`int`|Tipo de evento = 199.|27|não|  
|EventSequence|`int`|Número de sequência para esse evento.|51|não|  
|EventSubClass|`nvarchar`|O tipo de subclasse de evento, fornecendo mais informações sobre cada classe de evento. Essa coluna pode conter os seguintes valores:<br /><br /> Assinatura registrada: indica quando a assinatura de notificação de consulta é registrada com êxito no banco de dados.<br /><br /> Assinatura rebobinada: indica quando o [!INCLUDE[ssDE](../../includes/ssde-md.md)] recebe uma solicitação de assinatura que corresponda exatamente uma assinatura existente. Nesse caso, [!INCLUDE[ssDE](../../includes/ssde-md.md)] define o valor do tempo-limite da assinatura existente para o tempo-limite especificado na nova solicitação de assinatura.<br /><br /> Assinatura acionada: indica quando uma assinatura de notificação produz uma mensagem de notificação.<br /><br /> Acionamento falhou com erro do agente: indica quando uma mensagem de notificação falha devido a um [!INCLUDE[ssSB](../../includes/sssb-md.md)] erro.<br /><br /> Acionamento falhou sem erro do agente: indica quando uma mensagem de notificação falha, mas não devido a um [!INCLUDE[ssSB](../../includes/sssb-md.md)] erro.<br /><br /> Erro interceptado do agente: indica que [!INCLUDE[ssSB](../../includes/sssb-md.md)] gerou um erro na conversa que usa a notificação de consulta.<br /><br /> Tentativa de exclusão da assinatura: indica que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] tentou excluir uma assinatura expirada para liberar recursos.<br /><br /> Falha na exclusão da assinatura: indica que a tentativa de excluir uma assinatura expirada falhou. O [!INCLUDE[ssDE](../../includes/ssde-md.md)] irá reagendar automaticamente a assinatura para exclusão, a fim de liberar recursos.<br /><br /> Assinatura destruída: indica que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] excluído com êxito uma assinatura expirada|21|Sim|  
|GroupID|`int`|ID do grupo de carga de trabalho no qual o evento de Rastreamento do SQL dispara.|66|Sim|  
|HostName|`nvarchar`|O nome do computador no qual o cliente está sendo executado. Essa coluna de dados será populada se o nome do host for fornecido pelo cliente. Para determinar o nome do host, use a função HOST_NAME.|8|Sim|  
|IsSystem|`int`|Indica se o evento ocorreu em um processo do sistema ou do usuário.<br /><br /> 0 = usuário<br /><br /> 1 = sistema|60|não|  
|LoginName|`nvarchar`|O nome de logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do Windows na forma DOMÍNIO/Nomedeusuário).|11|não|  
|LoginSID|`image`|Número SID (identificação de segurança) do usuário que fez logon. Você pode encontrar essas informações na exibição de catálogo sys.server_principals. Cada SID é exclusivo para cada logon no servidor.|41|Sim|  
|NTDomainName|`nvarchar`|O domínio do Windows ao qual o usuário pertence.|7|Sim|  
|NTUserName|`nvarchar`|O nome do usuário proprietário da conexão que gerou este evento.|6|Sim|  
|RequestID|`int`|Identificador da solicitação que contém a instrução.|49|Sim|  
|ServerName|`nvarchar`|O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.|26|não|  
|SessionLoginName|`nvarchar`|Nome de logon do usuário que originou a sessão. Por exemplo, se um aplicativo se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando Logon1 e executar uma instrução como Logon2, o SessionLoginName mostrará "Logon1" e LoginName mostrará "Logon2". Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.|64|Sim|  
|SPID|`int`|Identificação da sessão em que ocorreu o evento.|12|Sim|  
|StartTime|`datetime`|Hora de início do evento, se disponível.|14|Sim|  
|TextData|`ntext`|Retorna um documento XML que contém informações específicas para esse evento. Esse documento está de acordo com o esquema XML disponível na página [SQL Server Query Notification Profiler Event Schema](http://go.microsoft.com/fwlink/?LinkId=63331) .|1|Sim|  
  
  