---
title: Propriedades do navegador do SQL Server (guia fazer logon) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c77871ec-c2f4-4e4a-9a10-5aeb4ae70507
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: ac257d9a9044be9d1d7003fe066337fff116dcf0
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="sql-server-browser-properties-log-on-tab"></a>Propriedades do Navegador do SQL Server (guia Fazer Logon)
  O programa Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executado como um serviço no servidor. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Escuta as solicitações de entrada de recursos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornece informações sobre as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no computador.  
  
 O Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escuta em uma porta UDP e aceita as solicitações não autenticadas usando o protocolo SSRP do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 A alteração da senha de uma conta entra em vigor imediatamente sem a reinicialização do serviço.  
  
## <a name="options"></a>Opções  
 **Conta Sistema Local**  
 Execute o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no contexto de segurança da conta Sistema Local. Quando possível, use uma conta de baixa permissão.  
  
 **Esta conta**  
 Especifique um local ou conta de usuário do domínio que utilize Autenticação do Windows. É recomendável usar uma conta de usuário do domínio com direitos mínimos para serviços. Para obter informações sobre como selecionar uma conta, consulte "Configurando as contas de serviço do Windows" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Procurar**  
 Procure um usuário ou uma entidade de segurança incorporada.  
  
> [!IMPORTANT]  
>  Use uma conta da baixa-permissão. Para obter informações sobre as permissões necessárias para o Serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte a seção Segurança do tópico [Serviço Navegador do SQL Server](../../tools/configuration-manager/sql-server-browser-service.md).  
  
 **Senha**  
 Digite a senha da entidade de segurança.  
  
 **Confirmar senha**  
 Confirme a senha da entidade de segurança.  
  
 **Status do serviço**  
 Indica se este serviço está sendo executado, se está parado ou desabilitado. "**…**" indica que uma alteração no estado está pendente.  
  
 **Iniciar**  
 Iniciar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Parar**  
 Parar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Pausar**  
 Pausar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Retomar**  
 Retomar um serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em pausa.  
  
## <a name="see-also"></a>Consulte também  
 [Serviço Navegador do SQL Server](../../tools/configuration-manager/sql-server-browser-service.md)  
  
  