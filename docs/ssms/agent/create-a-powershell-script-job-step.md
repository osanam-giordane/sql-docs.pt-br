---
title: Criar uma etapa de trabalho de script do PowerShell | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PowerShell [SQL Server], job steps
- jobs [SQL Server Agent], PowerShell
- job steps [PowerShell]
- SQL Server Agent jobs, PowerShell steps
ms.assetid: 50afcf84-fae0-4eb5-9b0f-f2cf144c1433
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: e40a0516135c42ab8bbfe0df1e21f05cbd41c8a1
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="create-a-powershell-script-job-step"></a>Create a PowerShell Script Job Step
Este tópico descreve como criar e definir uma etapa de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent que execute um script PowerShell no [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] ou o [!INCLUDE[tsql](../../includes/tsql_md.md)].  
  
**Neste tópico**  
  
-   **Antes de começar:**  
  
    [Segurança](#Security)  
  
-   **Para criar uma etapa de trabalho de script do PowerShell usando:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server Management Objects](#SMO)  
  
## <a name="BeforeYouBegin"></a>Antes de começar  
  
### <a name="Security"></a>Segurança  
Para obter informações detalhadas, consulte [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Usando o SQL Server Management Studio  
  
#### <a name="to-create-a-powershell-script-job-step"></a>Para criar uma etapa de trabalho de script PowerShell  
  
1.  No **Pesquisador de Objetos** , conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)]e a expanda.  
  
2.  Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**. Para obter mais informações sobre como criar um trabalho, consulte [Criando trabalhos](../../ssms/agent/create-jobs.md).  
  
3.  Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.  
  
4.  Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.  
  
5.  Na lista **Tipo** , clique em **PowerShell**.  
  
6.  Na lista **Executar como** , selecione a conta proxy com as credenciais que o trabalho usará.  
  
7.  Na caixa **Comando** , digite a sintaxe do script PowerShell que será executada para a etapa de trabalho. Como alternativa, clique em **Abrir** e selecione um arquivo que contenha a sintaxe de script. Para obter um exemplo de um script do PowerShell, consulte **Como usar o Transact-SQL** abaixo.  
  
8.  Clique na página **Avançado** para definir as seguintes opções de etapa de trabalho: a ação a tomar em caso de êxito ou falha da etapa, quantas vezes o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent deve tentar executar a etapa e com que frequência.  
  
## <a name="TSQL"></a>Como usar o Transact-SQL  
  
#### <a name="to-create-a-powershell-script-job-step"></a>Para criar uma etapa de trabalho de script PowerShell  
  
1.  No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  Na barra Padrão, clique em **Nova Consulta**.  
  
3.  Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.  
  
    ```  
    -- creates a PowerShell job step that finds the processes
    -- that use more than 1000 MB of memory and kills them  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Kills all processes that use more than 1000 MB of memory',  
        @subsystem = N'PowerShell',  
        @command = N'Get-Process | Where-Object { $_.WS -gt 1000MB } | Stop-Process',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
Para obter mais informações, consulte [sp_add_jobstep (Transact-SQL)](http://msdn.microsoft.com/en-us/97900032-523d-49d6-9865-2734fba1c755).  
  
## <a name="SMO"></a>Usando o SQL Server Management Objects  
**Para criar uma etapa de trabalho de script PowerShell**  
  
Use a classe **JobStep** com uma linguagem de programação à sua escolha, como Visual Basic, Visual C# ou PowerShell.  
  
