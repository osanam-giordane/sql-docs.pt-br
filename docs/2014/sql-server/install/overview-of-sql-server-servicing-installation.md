---
title: Visão geral da instalação de manutenção do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6a9fd19b-2367-4908-b638-363b1e929e1e
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: b8e9532c9d3ecbc32942e6a70d82f5837856a329
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66093588"
---
# <a name="overview-of-sql-server-servicing-installation"></a>Visão geral da instalação de manutenção do SQL Server
  Você pode aplicar uma atualização a qualquer componente do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instalado com uma atualização de manutenção do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] . Se o nível da versão de um componente existente do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for posterior ao da versão de atualização, o programa de Instalação o excluirá da atualização. Para obter mais informações sobre como aplicar uma manutenção de atualização, consulte [instalar o SQL Server 2014 atualizações de serviço](../../database-engine/install-windows/install-sql-server-servicing-updates.md).  
  
 As seguintes considerações se aplicam à instalação de atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:  
  
-   Todos os recursos que pertencem a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devem ser atualizados ao mesmo tempo. Por exemplo, quando atualizar o [!INCLUDE[ssDE](../../includes/ssde-md.md)], você também deverá atualizar os componentes [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se eles estiverem instalados como parte da mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Recursos compartilhados, como as Ferramentas de Gerenciamento, o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], sempre devem ser atualizados para a versão mais recente. Se nenhuma instância ou nenhum componente da árvore de recursos estiver selecionado, ele não será atualizado.  
  
-   Por padrão, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] arquivos de log de atualização são salvos como % arquivos de programas %\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\LOG\\.  
  
-   A instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agora pode integrar uma atualização à mídia original para executar a mídia original e a atualização ao mesmo tempo. Para obter mais informações, consulte [o que há de novo na instalação do SQL Server](../../../2014/sql-server/install/what-s-new-in-sql-server-installation.md).  
  
-   Antes de aplicar uma atualização de manutenção do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , é recomendável fazer backup dos dados.  
  
-   As atualizações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estão disponíveis por meio do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update. É recomendável que você procure atualizações regularmente para manter a sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atualizada e segura. [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] SP1 está sendo fornecido como uma instalação completa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Em vez de fornecer o Service Pack no pacote executável do patch padrão a ser aplicado às instâncias do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] RTM, nesta versão é fornecido um pacote de instalação que consiste em 2 arquivos. Quando executado, ele instalará uma nova instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o SP1 pré-instalado.  
  
## <a name="requirements-and-known-issues"></a>Requisitos e problemas conhecidos  
 Os requisitos de espaço em disco recomendados são, aproximadamente, 2,5 vezes o tamanho do pacote para instalação, download e extração do pacote. Após instalar um service pack, você pode remover o pacote baixado. Todos os arquivos temporários serão removidos automaticamente.  
  
 **Examine os problemas conhecidos:** Para obter mais informações sobre os problemas conhecidos da versão atual, consulte o tópico notas versão correspondentes aqui: [Notas de versão do SQL Server](https://msdn.microsoft.com/f617a0af-92dd-47aa-82c3-f51b1346bcd8).  
  
## <a name="installation-overview"></a>Visão geral da instalação  
 Esta seção aborda a instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para atualizações cumulativas e service packs, inclusive como fazer o seguinte:  
  
-   Preparar-se para uma instalação de atualização do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
  
-   Instalar atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
  
-   Reiniciar serviços e aplicativos  
  
### <a name="prepare-for-a-includesscurrentincludessscurrent-mdmd-update-installation"></a>Preparar-se para uma instalação de atualização do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 É altamente recomendável que você faça o seguinte antes de instalar atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] :  
  
-   **Fazer backup de seu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bancos de dados do sistema** - antes de instalar [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] atualizações, fazer backup de `master`, `msdb`, e `model` bancos de dados. A instalação de uma atualização do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] altera esses bancos de dados, tornando-os incompatíveis com versões anteriores do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. Os backups desses bancos de dados serão necessários se você decidir reinstalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sem essas atualizações.  
  
     Também é recomendável fazer backup dos bancos de dados de usuário.  
  
    > [!IMPORTANT]  
    >  Ao aplicar atualizações a instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que participam de uma topologia de replicação, você deverá fazer backup dos bancos de dados replicados junto com os bancos de dados do sistema antes de aplicar a atualização.  
  
-   **Fazer backup de seu [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bancos de dados, arquivo de configuração e repositório** – antes de atualizar uma instância de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], você deve fazer backup do seguinte:  
  
    -   Bancos de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Por padrão, eles são instalados em C:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSAS12.\< InstanceID > \OLAP\Data\\. Para a instalação do WOW, o caminho padrão é C:\ProgramFiles (x86) \ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSAS12.\< InstanceID > \OLAP\Data\\.  
  
    -   Parâmetro de configuração do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no arquivo de configuração msmdsrv.ini. Por padrão, ele fica localizado em C:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSAS12.\< InstanceID > \OLAP\Config\ directory.  
  
    -   (Opcional) O banco de dados que contém o repositório do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . Esta etapa será necessária somente se o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tiver sido configurado para funcionar com a biblioteca de DSO (Decision Support Objects).  
  
    > [!NOTE]  
    >  Se não for feito o backup dos bancos de dados, do arquivo de configuração e do repositório do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , você não poderá reverter uma instância atualizada do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para a versão anterior.  
  
-   **Verifique se os bancos de dados do sistema têm espaço livre suficiente** - se a opção de crescimento automático não estiver selecionada para o `master` e `msdb` bancos de dados do sistema, esses bancos de dados devem ter pelo menos 500 KB de espaço livre. Para verificar se os bancos de dados têm espaço suficiente, execute o procedimento armazenado do sistema `sp_spaceused` nos bancos de dados `master` e `msdb`. Se o espaço não alocado de um deles for inferior a 500 KB, aumente o tamanho do banco de dados.  
  
-   **Interromper serviços e aplicativos** - para evitar uma possível reinicialização do sistema, pare todos os aplicativos e serviços que estabelecem conexões com instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que estão sendo atualizadas, antes de instalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] atualizações. Isso inclui o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]. Para obter mais informações, consulte [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).  
  
    > [!NOTE]  
    >  Você não pode interromper serviços em um ambiente de cluster de failover. Para obter mais informações, consulte a seção de instalação de cluster de failover mais adiante neste tópico.  
  
-   Para eliminar a necessidade de reiniciar o computador após a instalação da atualização, a Instalação mostrará uma lista com os processos que estão bloqueando arquivos. Se o programa de Instalação da atualização precisar encerrar um serviço durante a instalação, ele reiniciará o serviço depois que a instalação for concluída.  
  
-   Se a Instalação determinar que os arquivos sejam bloqueados durante a instalação, talvez seja necessário reiniciar o computador após a conclusão da instalação. Se necessário, a Instalação solicitará que você reinicie o computador.  
  
### <a name="install-includesscurrentincludessscurrent-mdmd-updates"></a>Instalar atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 Esta seção descreve o processo de instalação.  
  
> [!IMPORTANT]  
>  As atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] devem ser instaladas com uma conta que tenha privilégios administrativos no computador em que serão instaladas. Para instalações locais, você deve executar a Instalação como um administrador. Se você instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de um compartilhamento remoto, deverá usar uma conta de domínio que tenha permissões de leitura e de execução no compartilhamento remoto.  
  
#### <a name="starting-a-includesscurrentincludessscurrent-mdmd-update"></a>Iniciando uma atualização do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 Para instalar uma atualização do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , execute o arquivo de pacote autoextraível.  
  
 Pacote de atualização cumulativa (CU): \<SQLServer2014>-KBxxxxxx-*PPP*.exe  
  
 Pacote de service pack (PCU): \<SQLServer2014>\<SPx> -KBxxxxxx-PPP-LLL.exe  
  
-   x indica o número do service pack  
  
-   PPP indica a plataforma específica.  
  
-   LLL indica a abreviação de caracteres para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] idioma, por exemplo: LLL do inglês é ENU.  
  
 Para aplicar as atualizações aos componentes do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que fazem parte de um cluster de failover, consulte a seção sobre a instalação de cluster de failover. Para obter mais informações sobre como executar uma instalação de atualização no modo autônomo, consulte [instalar o SQL Server 2014 do Prompt de comando](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).  
  
####  <a name="Slipstream"></a> Atualizações de produto no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instalação  
 A Atualização de Produto é um recurso na Instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] . Ela integra as últimas atualizações de produto com a instalação principal, para que o produto principal e suas atualizações aplicáveis sejam instalados ao mesmo tempo. A Atualização de Produto pode procurar as atualizações aplicáveis no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update, no WSUS (Windows Server Update Services), em uma pasta local ou em um compartilhamento de rede.  Depois que a Instalação localizar as versões mais recentes das atualizações aplicáveis, ela baixará e integrará essas atualizações com o processo de instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atual. A Atualização de Produto pode efetuar pull de uma atualização cumulativa, service pack ou service pack mais atualização cumulativa. A funcionalidade da Atualização de Produto é uma extensão da funcionalidade Instalação Integrada que estava disponível no PCU1 do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .  
  
## <a name="updating-a-prepared-image-of-includessnoversionincludesssnoversion-mdmd"></a>Atualizando uma imagem preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
 É possível aplicar uma atualização a uma instância preparada não configurada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sem concluir a configuração da instância preparada. As diferentes maneiras de aplicar uma atualização a uma instância preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são explicados a seguir:  
  
-   Atualizando uma instância previamente preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
  
     As atualizações para uma instância preparada podem ser aplicadas antes da configuração. O pacote de atualização detecta que a instância está no estado preparado e aplica o patch à instância preparada, sem concluir a configuração.  
  
-   Atualizações para uma instância preparada usando o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update:  
  
     É possível aplicar atualizações a uma instância preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update. O pacote do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update detectará que a instância está no estado preparado e aplicará o patch à instância preparada, sem concluir a configuração.  
  
 Se estiver atualizando uma imagem preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você precisará especificar o parâmetro InstanceID. Para obter mais informações e uma sintaxe de exemplo, consulte [Installing Updates from the Command Prompt](../../database-engine/install-windows/installing-updates-from-the-command-prompt.md).  
  
## <a name="updating-a-completed-image-of-includessnoversionincludesssnoversion-mdmd"></a>Atualizando uma imagem concluída do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
 A atualização de uma instância completa e configurada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] segue os mesmos processos de qualquer outra instância instalada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="rebuilding-a-includesscurrentincludessscurrent-mdmd-failover-cluster-node"></a>Recriando um nó de cluster de failover do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 Se você precisar recriar um nó no cluster de failover após a aplicação das atualizações, siga estas etapas:  
  
1.  Recrie o nó no cluster de failover. Para obter mais informações sobre como reconstruir um nó, consulte [Recover from Failover Cluster Instance Failure](../failover-clusters/windows/recover-from-failover-cluster-instance-failure.md).  
  
2.  Execute o programa de Instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] original para instalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] no nó do cluster de failover.  
  
3.  Execute a Instalação das atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] no nó adicionado.  
  
## <a name="restart-services-and-applications"></a>Reiniciar serviços e aplicativos  
 Quando a Instalação estiver concluída, a reinicialização do computador poderá ser solicitada. Após a reinicialização do sistema, ou após a conclusão do programa de Instalação sem uma solicitação de reinicialização, use o nó **Serviços** no Painel de Controle para reiniciar os serviços que você interrompeu antes de aplicar as atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] . Isso inclui serviços como o Distributed Transaction Coordinator e o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Search, ou equivalentes específicos das instâncias.  
  
 Reinicie os aplicativos fechados antes de executar a Instalação da atualização do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] . Talvez você queira fazer outro backup dos bancos de dados atualizados `master`, `msdb` e `model` logo após a instalação bem-sucedida.  
  
## <a name="uninstalling-updates-from-includesscurrentincludessscurrent-mdmd"></a>Desinstalando atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 Você pode desinstalar as atualizações cumulativas ou os service packs do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] em **Programas e Recursos** no Painel de Controle. Para ver a lista de atualizações instaladas, abra Atualizações Instaladas clicando em **Iniciar** , **Painel de Controle**, **Programas**e, em **Programas e Recursos**, clique em **Exibir atualizações instaladas**. Cada atualização cumulativa é relacionada separadamente. No entanto, quando um service pack está instalado num nível superior ao das atualizações cumulativas, as entradas de atualizações cumulativas são ocultadas e só ficarão disponíveis se você desinstalar o service pack.  
  
 Para desinstalar um service pack e uma atualização, é necessário iniciar a atualização mais recente ou o service pack aplicado à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e trabalhar retroativamente. Em cada um dos exemplos a seguir, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] acaba com a Atualização Cumulativa 1 depois que a desinstalação é concluída para os outros service packs ou as outras atualizações:  
  
-   Para uma instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] com a Atualização Cumulativa 1 e o SP1 instalados, desinstale o SP1.  
  
-   Para cada instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] com a Atualização Cumulativa 1, o SP1 e a Atualização Cumulativa 2 instalados, desinstale a Atualização Cumulativa 2 primeiro e, em seguida, o SP1.  
  
## <a name="see-also"></a>Consulte também  
 [Instalar o SQL Server 2014 do Prompt de comando](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)   
 [Instalar atualizações de serviço do SQL Server 2014](../../database-engine/install-windows/install-sql-server-servicing-updates.md)   
 [Validar uma instalação do SQL Server](../../database-engine/install-windows/validate-a-sql-server-installation.md)   
 [Exibir e ler arquivos de log da Instalação do SQL Server](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
  
