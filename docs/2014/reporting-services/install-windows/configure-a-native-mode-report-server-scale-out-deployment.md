---
title: Configurar uma implantação de expansão de servidor de relatório do modo nativo (Gerenciador de configuração do SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], deployments
- deploying [Reporting Services], scale-out deployment model
- scale-out deployments [Reporting Services]
ms.assetid: b30d0308-4d9b-4f85-9f83-dece4dcb2775
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0281a487de123adfeb3739066628694b1da17a3
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66108896"
---
# <a name="configure-a-native-mode-report-server-scale-out-deployment-ssrs-configuration-manager"></a>Configurar uma implantação de expansão do servidor de relatório no modo nativo (Gerenciador de configurações do SSRS)

  O modo nativo do Reporting Services oferece suporte a um modelo de implantação em expansão que permite executar várias instâncias do servidor de relatório que compartilham um único banco de dados do servidor de relatório. As implantações em expansão são usadas para aumentar a escalabilidade dos servidores de relatório para manipular mais usuários simultâneos e cargas maiores de execução de relatório. Elas também podem ser usadas para dedicar servidores específicos para processar relatórios interativos ou agendados  
  
 Servidores de relatório do modo do SharePoint utilizam a infraestrutura de produtos do SharePoint para expandir. A expansão do modo do SharePoint é executada acrescentando mais servidores de relatório de modo do SharePoint ao farm do SharePoint. Para obter informações sobre a expansão no modo do SharePoint, consulte [Adicionar outro servidor de relatório a um farm &#40;Expansão do SSRS&#41;](../../reporting-services/install-windows/add-an-additional-report-server-to-a-farm-ssrs-scale-out.md).  
  
 **As implantações em expansão consistem de:**  
  
-   Duas ou mais instâncias do servidor de relatório que compartilham um único banco de dados do servidor de relatório.  
  
-   Opcionalmente, um cluster NLB (balanceamento de carga de rede) para difundir carga de usuário interativo nas instâncias do servidor de relatório.  
  
 Ao implantar o Reporting Services em um cluster NLB, você precisa assegurar que o nome do servidor virtual NLB é usado na configuração das URLs de servidor de relatório e que os servidores estão configurados para compartilhar o mesmo estado de exibição.  
  
 O Reporting Services não participa dos clusters do Microsoft Cluster Services. No entanto, é possível criar um banco de dados do servidor de relatório em uma instância do Mecanismo de Banco de Dados que faz parte de um cluster de failover.  
  
 **Para planejar, instalar e configurar uma implantação em expansão, siga estas etapas:**  
  
-   Revisão [instalar o SQL Server 2014 do Assistente de instalação do &#40;instalação&#41; ](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) na [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Manuais Online para obter instruções sobre como instalar instâncias do servidor de relatório.  
  
-   Se você estiver planejando hospedar a implantação em expansão em um cluster NLB (balanceamento de carga de rede), deverá configurar o cluster NLB antes de configurar a implantação em expansão. Para obter mais informações, consulte [Configurar um servidor de relatório em um cluster com balanceamento de carga de rede](../report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).  
  
-   Examine os procedimentos neste tópico para obter instruções sobre como compartilhar um banco de dados do servidor de relatório e associar servidores de relatório a uma expansão.  
  
     Os procedimentos explicam como configurar uma implantação em expansão do servidor de relatório com dois nós. Repita as etapas descritas neste tópico para adicionar nós adicionais do servidor de relatório à implantação.  
  
    -   Use a Instalação para instalar cada instância do servidor de relatório que será associada à implantação em expansão.  
  
         Para evitar erros de compatibilidade de banco de dados ao conectar as instâncias de servidor ao banco de dados compartilhado, certifique-se de que todas as instâncias tenham a mesma versão. Por exemplo, se você criar o banco de dados do servidor de relatório usando uma instância do servidor de relatório do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , todas as demais instâncias na mesma implantação também deverão ser do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
    -   Use o gerenciador de Configuração do Reporting Services para conectar cada servidor de relatório ao banco de dados compartilhado. Você pode se conectar e configurar somente um servidor de relatório de cada vez.  
  
    -   Use a ferramenta Configuração do Reporting Services para concluir a expansão por meio da associação de novas instâncias do servidor de relatório à primeira instância do servidor de relatório já conectada ao banco de dados do servidor de relatório.  
  
### <a name="to-install-a-sql-server-instance-to-host-the-report-server-databases"></a>Para instalar uma instância do SQL Server que hospedará os bancos de dados do servidor de relatório  
  
1.  Instale uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um computador que hospedará os bancos de dados do servidor de relatório. Instale pelo menos o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
2.  Se necessário, habilite o servidor de relatório para conexões remotas. Por padrão, algumas versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não permitem conexões remotas TCP/IP e de Pipes Nomeados. Para confirmar se conexões remotas são permitidas, use o Gerenciador de Configurações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e exiba os parâmetros de configuração de rede da instância de destino. Se a instância remota também for uma instância nomeada, verifique se o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitado e em execução no servidor de destino. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece o número da porta usado para estabelecer conexão com a instância nomeada.  
  
### <a name="to-install-the-first-report-server-instance"></a>Para instalar a primeira instância do servidor de relatório  
  
1.  Instale a primeira instância do servidor de relatório que faz parte da implantação. Quando instalar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], escolha a opção **Instalar, mas não configurar o servidor** na página Opções de Instalação do Servidor de Relatório.  
  
2.  Inicie a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .  
  
3.  Configure a URL do serviço Web Servidor de Relatórios, a URL do Gerenciador de Relatórios e o banco de dados do servidor de relatório. Para obter mais informações, veja [Configurar um servidor de relatório &#40;Modo Nativo do Reporting Services&#41;](../report-server/configure-a-report-server-reporting-services-native-mode.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
4.  Verifique se o servidor de relatório está operacional. Para obter mais informações, veja [Verificar uma instalação do Reporting Services](../../reporting-services/install-windows/verify-a-reporting-services-installation.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
### <a name="to-install-and-configure-the-second-report-server-instance"></a>Para instalar e configurar a segunda instância do servidor de relatório  
  
1.  Execute a instalação para instalar uma segunda instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em outro computador ou como instância nomeada no mesmo computador. Ao instalar o Reporting Services, escolha a opção **Instalar, mas não configurar o servidor** na página Opções de Instalação do Servidor de Relatório.  
  
2.  Inicie a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e conecte-se à nova instância que você acabou de instalar.  
  
3.  Conecte o servidor de relatório ao mesmo banco de dados usado para a primeira instância do servidor de relatório:  
  
    1.  Clique em **Banco de Dados** para abrir a página Banco de Dados.  
  
    2.  Clique em **Alterar Banco de Dados**.  
  
    3.  Clique em **Escolher um banco de dados existente do servidor de relatório**.  
  
    4.  Digite o nome do servidor da instância do Mecanismo de Banco de Dados do SQL Server que hospeda o banco de dados do servidor de relatório a ser usado. Esse deve ser o mesmo servidor ao qual você se conectou no conjunto de instruções anterior.  
  
    5.  Clique em **Testar Conexão**e clique em **Avançar**.  
  
    6.  Em **Banco de Dados do Servidor de Relatório**, selecione o banco de dados que você criou para o primeiro servidor de relatório e clique em **Avançar**. O nome padrão é ReportServer. Não selecione ReportServerTempDB; ele é usado somente para armazenar dados temporários durante o processamento de relatórios. Se a lista de bancos de dados estiver vazia, repita as quatro etapas anteriores para estabelecer uma conexão com o servidor.  
  
    7.  Na página Credenciais, selecione o tipo de conta e as credenciais que o servidor de relatório usará para se conectar ao banco de dados do servidor de relatório. Você pode usar as mesmas credenciais que as da primeira instância do servidor de relatório ou credenciais diferentes. Clique em **Avançar**.  
  
    8.  Clique em **Resumo** e clique em **Concluir**.  
  
4.  Configure a URL do serviço Web Servidor de Relatórios. Não teste a URL neste momento. Ela não será resolvida até que o servidor de relatório seja associado à implantação em expansão.  
  
5.  Configure a URL do Gerenciador de Relatórios. Não teste a URL neste momento nem tente verificar a implantação. O servidor de relatório estará indisponível até que ele seja associado à implantação em expansão.  
  
### <a name="to-join-the-second-report-server-instance-to-the-scale-out-deployment"></a>Para unir a segunda instância do servidor de relatório à implantação em expansão  
  
1.  Abra a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e se reconecte à primeira instância do servidor de relatório. O primeiro servidor de relatório já está inicializado para operações de criptografia reversível, portanto ele pode ser usado para unir instâncias adicionais do servidor de relatório à implantação em expansão.  
  
2.  Clique em **Implantação em Expansão** para abrir a página Implantação em Expansão. Você deve ver duas entradas, um para cada instância do servidor de relatório que está conectada ao banco de dados do servidor de relatório. A primeira instância do servidor de relatório deve estar associada. O segundo servidor de relatório deve estar "Aguardando para unir". Se não vir entradas semelhantes para a sua implantação, verifique se você está conectado ao primeiro servidor de relatório que já está configurado e inicializado para usar o banco de dados do servidor de relatório.  
  
     ![Captura de tela parcial da página Implantação Escalável](../../../2014/sql-server/install/media/scaloutscreen.gif "Captura de tela parcial da página Implantação Escalável")  
  
3.  Na página implantação em expansão, selecione a instância de servidor de relatório que está aguardando para se unir à implantação e, em seguida, clique em **Adicionar servidor**.  
  
    > [!NOTE]  
    >  **Problema:** Quando você tenta unir uma instância de servidor de relatório do Reporting Services à implantação em expansão, você pode receber mensagens de erro semelhantes a "Acesso negado".  
    >   
    >  **Solução alternativa:** Fazer backup de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] chave de criptografia da primeira [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] da instância e restaurar a chave para o segundo [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servidor de relatório. Tente unir o segundo servidor à implantação em expansão do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .  
  
4.  Agora, deverá ser possível verificar que ambas as instâncias do servidor de relatório estão operacionais. Para verificar a segunda instância, você pode usar a ferramenta Configuração do Reporting Services para se conectar ao servidor de relatório e clicar na URL do Serviço da Web ou na URL do Gerenciador de Relatórios.  
  
 Se você planejar executar os servidores de relatório em um cluster de servidores com balanceamento de carga, será necessária uma configuração adicional. Para obter mais informações, consulte [Configurar um servidor de relatório em um cluster com balanceamento de carga de rede](../report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).  
  
## <a name="see-also"></a>Consulte também  
 [Configurar uma conta de serviço &#40;SSRS Configuration Manager&#41;](../../../2014/sql-server/install/configure-a-service-account-ssrs-configuration-manager.md)   
 [Configurar uma URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md)   
 [Criar um banco de dados de servidor de relatório do modo nativo &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)   
 [Configurar as URLs do servidor de relatório &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)   
 [Configurar uma conexão de banco de dados do servidor de relatório &#40;SSRS Configuration Manager&#41;](../../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)   
 [Adicionar e remover chaves de criptografia para implantação escalável &#40;Gerenciador de Configurações do SSRS&#41;](../../reporting-services/install-windows/add-and-remove-encryption-keys-for-scale-out-deployment.md)   
 [Gerenciar um servidor de relatórios de Modo Nativo do Reporting Services](../report-server/manage-a-reporting-services-native-mode-report-server.md)  
  
  
