---
title: "Editor da tarefa (página geral) de criação de perfil de dados | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.dataprofilingtask.general.f1
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: eec15906-d757-4079-b2f6-aca4e52b3b4c
caps.latest.revision: 19
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f5acdf3ae4f27685fce7aab56aab423044491ee1
ms.openlocfilehash: bed1fa78db9ee0beca66efe57f088d1d74d377f2
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="data-profiling-task-editor-general-page"></a>Editor da tarefa Criação de Perfil de Dados (página Geral)
  Use a página **Geral** do **Editor da Tarefa Criação de Perfil de Dados** para configurar as seguintes opções:  
  
-   Especifique o destino do perfil de saída.  
  
-   Use as configurações padrão para simplificar a tarefa de criar um perfil para uma única tabela ou exibição.  
  
 Para obter mais informações sobre como usar a Tarefa Criação de Perfil de Dados, consulte [Configuração da Tarefa Criação de Perfil de Dados](../../integration-services/control-flow/setup-of-the-data-profiling-task.md). Para obter mais informações sobre como usar o Visualizador de Perfil de Dados para analisar a saída da Tarefa Criação de Perfil de Dados, consulte [Visualizador de Perfil de Dados](../../integration-services/control-flow/data-profile-viewer.md).  
  
 **Para abrir a página Geral do Editor da Tarefa de Criação de Perfil de Dados**  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a tarefa Criação de Perfil de Dados.  
  
2.  Na guia **Fluxo de Controle** , clique duas vezes na tarefa Criação de Perfil de Dados.  
  
3.  No **Editor da Tarefa Criação de Perfil de Dados**, clique em **Geral**.  
  
## <a name="data-profiling-options"></a>Opções de Criação de Perfil de Dados  
 **Tempo Limite**  
 Especifique o número de segundos após o qual a tarefa Criação de Perfil de Dados deve alcançar o tempo limite e interromper a execução. O valor padrão é 0, que não indica nenhum tempo limite.  
  
## <a name="destination-options"></a>Opções de destino  
  
> [!IMPORTANT]  
>  O arquivo de saída pode conter dados confidenciais sobre seu banco de dados e os dados contidos no banco de dados. Para obter sugestões sobre como tornar esse arquivo mais seguro, consulte [Acesso aos arquivos usados por pacotes](../../integration-services/security/security-overview-integration-services.md#files).  
  
 **DestinationType**  
 Especifique se deseja salvar a saída do perfil de dados para um arquivo ou uma variável:  
  
|Value|Description|  
|-----------|-----------------|  
|**FileConnection**|Salve o perfil produzido em um arquivo no local especificado em um gerenciador de conexões do Arquivo.<br /><br /> Observação: especifique qual gerenciador de conexões do Arquivo deve ser usado na opção **Destino** .|  
|**Variável**|Salve a saída do perfil em uma variável de pacote.<br /><br /> Observação: especifique qual variável de pacote deve ser usada na opção **Destino** .|  
  
 **Destino**  
 Especifique qual gerenciador de conexões do Arquivo ou variável de pacote contém a saída do perfil de dados:  
  
-   Se a opção **DestinationType** for definida como **FileConnection**, a opção **Destino** exibirá os gerenciadores de conexões do Arquivo disponíveis. Selecione um desses gerenciadores de conexão, ou selecione \<conexão de arquivo novo > criar uma nova conexão de arquivo manager.  
  
-   Se a opção **DestinationType** for definida como **Variável**, a opção **Destino** exibirá as variáveis de pacote disponíveis na lista **Destino** . Selecione uma dessas variáveis ou selecione \<nova variável > para criar uma nova variável.  
  
 **OverwriteDestination**  
 Especifique se deseja substituir o arquivo de saída, se este já existir. O valor padrão é **Falso**. O valor desta propriedade é usado somente quando a opção DestinationType for definida como FileConnection. Quando a opção DestinationType é definida como Variável, a tarefa sempre substitui o valor anterior da variável.  
  
> [!IMPORTANT]  
>  Se tentar executar a tarefa Criação de Perfil de Dados mais de uma vez sem alterar o nome do arquivo de saída ou alterar o valor da propriedade **OverwriteDestination** para **True**, a tarefa falhará, exibindo uma mensagem que informa que o arquivo de saída já existe.  
  
## <a name="other-options"></a>Outras opções  
 **Perfil Rápido**  
 Exibe o **Formulário de Perfil Rápido de Tabela Única**. Este formulário simplifica a tarefa de criação de perfil de uma tabela ou exibição única usando configurações padrão. Para obter mais informações, consulte [Formulário de Perfil Rápido de Tabela Única &#40;Tarefa Criação de Perfil de Dados&#41;](../../integration-services/control-flow/single-table-quick-profile-form-data-profiling-task.md).  
  
 **Abrir o Visualizador de Perfil**  
 Abra o Visualizador de Perfil de Dados. O visualizador de Perfil de Dados autônomo exibe a saída de perfil de dados da tarefa Criação de Perfil de Dados. A saída do perfil de dados pode ser exibida após a execução da tarefa Criação de Perfil de Dados no pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e a computação de perfis de dados.  
  
> [!NOTE]  
>  Você também pode abrir o Visualizador de perfil de dados, executando o DataProfileViewer.exe na pasta,  *\<drive >*: \Program Files (x86) | O programa de Programas\Microsoft SQL Server\110\DTS\Binn.  
  
## <a name="see-also"></a>Consulte também  
 [Formulário de Perfil Rápido de Tabela Única &#40;Tarefa Criação de Perfil de Dados&#41;](../../integration-services/control-flow/single-table-quick-profile-form-data-profiling-task.md)   
 [Editor da tarefa &#40; de criação de perfil de dados Página de solicitações de perfil &#41;](../../integration-services/control-flow/data-profiling-task-editor-profile-requests-page.md)  
  
  