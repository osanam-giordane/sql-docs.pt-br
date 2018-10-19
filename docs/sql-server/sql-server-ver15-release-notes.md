---
title: Notas sobre a versão do SQL Server 2019 | Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
ms.prod: sql-server-2018
ms.reviewer: ''
ms.technology:
- server-general
ms.topic: article
ms.assetid: 13942af8-5a40-4cef-80f5-918386767a47
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
monikerRange: = sql-server-ver15 || = sqlallproducts-allversions
ms.openlocfilehash: c1c65ad5e2fc495479ec7801b779b242677c1c96
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47717584"
---
# <a name="sql-server-2019-preview-release-notes"></a>Notas sobre a versão a versão prévia do SQL Server 2019

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

Este artigo descreve as limitações e os problemas conhecidos para as versões do [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP (Community Technology Preview). Para obter informações relacionadas, consulte:
- [Novidades no SQL Server 2019](../sql-server/what-s-new-in-sql-server-ver15.md)

> [!NOTE]
> Versões prévias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] são disponibilizadas para você experimentar os recursos da versão futura. Elas não são compatíveis nem licenciadas para uso em produção. Os cenários a seguir não são explicitamente compatíveis:
>
> - Instalação lado a lado com outras versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]
> - Desinstalação
> - Atualização de uma edição anterior do SQL Server

**Experimente[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)]!**
- [![Baixar do Centro de Avaliação](../includes/media/download2.png)](http://go.microsoft.com/fwlink/?LinkID=862101) [Baixe o [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] para instalação no Windows](http://go.microsoft.com/fwlink/?LinkID=862101)
- Instalar no Linux para [Red Hat Enterprise Server](../linux/quickstart-install-connect-red-hat.md), [SUSE Linux Enterprise Server](../linux/quickstart-install-connect-suse.md) e [Ubuntu](../linux/quickstart-install-connect-ubuntu.md).
- [Executar no SQL Server 2019 no Docker](../linux/quickstart-install-connect-docker.md).

## <a name="ctp-20-september-2018"></a>CTP 2.0 (setembro de 2018)

[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0 é a primeira versão pública de [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)].

[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0 está disponível apenas como Evaluation Edition. Nenhuma outra edição está disponível. O suporte para o CTP 2.0 é descrito em license_Eval.rtf com a mídia de instalação.

Suporte limitado pode ser encontrado em um dos seguintes locais:

- Fóruns
  - [Comentários do SQL Server](http://aka.ms/sqlfeedback)
  - [Introdução ao SQL Server](https://social.msdn.microsoft.com/Forums/sqlserver/en-US/home?forum=sqlgetstarted)
  - [Transact-SQL](https://social.msdn.microsoft.com/Forums/sqlserver/en-US/home?forum=transactsql)
  - [SQL Server, documentação](https://social.msdn.microsoft.com/Forums/sqlserver/en-US/home?forum=sqldocumentation)

- Ou envie um tweet para [@SQLServer](http://twitter.com/SQLServer) com [#sqlhelp](https://twitter.com/search?q=%23sqlhelp)

### <a name="documentation-ctp-20"></a>Documentação (CTP 2.0)

- **Problema e impacto para o cliente:** a documentação para o SQL Server 2019 (15.x) é limitada e o conteúdo está incluído no conjunto de documentação [!INCLUDE[ssSQL17](../includes/sssql17-md.md)]. O conteúdo nesses artigos específico para o SQL Server 2019 (15.x) será indicado com **Aplica-se a**.

- **Problema e impacto para o cliente**: a documentação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pode ser filtrada por versão. Use o controle na parte superior esquerda de cada página de documentação para filtrar os requisitos. 

- **Problema e impacto para o cliente:** nenhum conteúdo offline está disponível para o SQL Server 2019 (15.x).

### <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

- **Problema e impacto para o cliente**: os requisitos de hardware e software ainda estão sendo analisados e não são definitivos para a versão do produto.

  - **Hardware**
    - [Windows – requisitos de processador, memória e sistema operacional](../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md#pmosr)
    - [Linux – requisitos do sistema](../linux/sql-server-linux-setup.md#system)
  - **Software**
    - Windows Server 2016 ou posterior. Para ver os requisitos adicionais, consulte [Requisitos para instalação do SQL Server](../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)
    - Para Linux, consulte [Linux – plataformas compatíveis](../linux/sql-server-linux-setup.md#supportedplatforms)

### <a name="sql-graph"></a>SQL Graph

**Problema e impacto para o cliente**: ferramentas que têm dependências de DacFx, como importação-exportação não funcionarão para os novos recursos de grafo – DML de restrições ou mesclagem do Edge. Os scripts em [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] podem não funcionar.

**Solução alternativa**: escrever scripts [!INCLUDE[tsql](../includes/tsql-md.md)] e execute-os no servidor usando [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou SQLCMD funcionará. A exportação ou importação de objetos de banco de dados que criam restrições do Edge, têm nova sintaxe de DML de mesclagem ou que criam exibições/tabelas derivadas em objetos de grafo não funcionarão. Os usuários precisarão criar manualmente esses objetos no seu banco de dados usando scripts [!INCLUDE[tsql](../includes/tsql-md.md)]. 

**Aplica-se a:** [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0.

### <a name="utf-8-collations"></a>Agrupamentos UTF-8

**Problema e impacto para o cliente**: os agrupamentos UTF-8 habilitados não poderão ser usados com alguns dos outros recursos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. O UTF-8 não é compatível quando os recursos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a seguir são usados:

- Replicação do SQL Server
- Servidor vinculado
- OLTP in-memory
- Tabela externa para Polybase

  Observe também que, no momento, não há nenhuma interface do usuário compatível para escolher os agrupamentos UTF-8 habilitados no Azure Data Studio ou SSDT. A versão mais recente do SSMS é compatível com a seleção de agrupamentos UTF-8 habilitados na interface do usuário.

**Solução alternativa:** não há solução alternativa para o [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0.

**Aplica-se a:** [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0.

### <a name="lightweight-query-profiling-infrastructure"></a>Infraestrutura de criação de perfil de consulta leve

**Problema e impacto para o cliente**: executar o comando `ALTER DATABASE SCOPED CONFIGURATION SET LIGHTWEIGHT_QUERY_PROFILING = ON` retorna um erro de sintaxe. Todos os cenários que dependem da execução desse comando falharão.

> [!NOTE]
> Atualmente, a LWP (infraestrutura de criação de perfil de consulta leve) não pode ser controlada no nível de banco de dados individuais e permanece habilitada para todos os bancos de dados por padrão. Para obter mais informações sobre a LWP, consulte [Novidades no SQL Server 2019](../sql-server/what-s-new-in-sql-server-ver15.md).

**Solução alternativa:** não há solução alternativa para o [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0.

**Aplica-se a:** [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0.

### <a name="always-encrypted-with-secure-enclaves"></a>Always Encrypted com enclaves seguros

**Problema e impacto para o cliente**: os cálculos avançados estão aguardando várias otimizações de desempenho, incluindo a funcionalidade limitada (sem indexação, etc.) e estão desabilitados por padrão no momento.

**Solução alternativa**: para habilitar cálculos avançados, execute `DBCC traceon(127,-1)`. Para obter detalhes, consulte [Habilitar cálculos avançados](../relational-databases/security/encryption/configure-always-encrypted-enclaves.md#configure-a-secure-enclave).

**Aplica-se a:** [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0.

### <a name="sql-server-integration-services-ssis-transfer-database-task"></a>Tarefa Transferir Banco de Dados do SSIS (SQL Server Integration Services)

**Problema e impacto para o cliente**: quando um `Transfer Database Task` é configurada para transferir um banco de dados no modo `Database Online`, ele poderá falhar com o seguinte erro:

>O método Execute na tarefa retornou o código de erro 0x80131500 (Ocorreu um erro durante a transferência de dados. Consulte a exceção interna para obter mais detalhes.). O método Execute deve ter êxito e indicar o resultado usando um parâmetro "out".

**Solução alternativa**: execute `DBCC TRACEON (7416,-1)` no servidor e tente novamente.

### <a name="sql-server-machine-learning-services-installation-failure"></a>Falha na instalação dos Serviços do Microsoft Machine Learning do SQL Server

**Problema/impacto para o cliente**: falha em instalações dos Serviços do Microsoft Machine Learning do SQL Server em computadores com problemas de relação de confiança com o domínio primário. Nesse caso, o seguinte erro será mostrado nos logs:
 
>  Error: 0 : System.SystemException:A relação de confiança entre esta estação de trabalho e o domínio primário falhou em System.Security.Principal.NTAccount.TranslateToSids(IdentityReferenceCollection sourceAccounts, Boolean& someFailed) ...

Confirme nos logs localizados em:

* `C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\R_SERVICES\library\RevoScaleR\rxLibs\x64\RegisterRExt.log`
* `C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\PYTHON_SERVICES\Lib\site-packages\revoscalepy\rxLibs\RegisterRExt.log`
**Solução alternativa**: resolva os problemas de confiança do domínio e tente instalar novamente.

**Aplica-se a:** SQL Server 2019 CTP 2.0.

[!INCLUDE[get-help-options-msft-only](../includes/paragraph-content/get-help-options.md)]

![MS_Logo_X-Small](../sql-server/media/ms-logo-x-small.png)