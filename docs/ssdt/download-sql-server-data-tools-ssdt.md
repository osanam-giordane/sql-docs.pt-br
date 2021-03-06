---
title: Baixar o SSDT (SQL Server Data Tools) | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2019
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssdt
ms.topic: conceptual
keywords:
- instalar o ssdt, baixar o ssdt, ssdt mais recente
ms.assetid: b0fc4987-d260-4d0a-9dd1-98099835b361
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||=azuresqldb-mi-current'
ms.openlocfilehash: 62b3db01792005afa7c124f4f31b78cdc350b2dd
ms.sourcegitcommit: 40f3b1f2340098496d8428f50616095a190ae94b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68290341"
---
# <a name="download-and-install-sql-server-data-tools-ssdt-for-visual-studio"></a>Baixar e instalar o SSDT (SQL Server Data Tools) para o Visual Studio
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md.md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]


O **SQL Server Data Tools** é uma moderna ferramenta de desenvolvimento para criar bancos de dados relacionais do SQL Server, bancos de dados SQL do Azure, modelos de dados do AS (Analysis Services), pacotes do IS (Integration Services) e relatórios do RS (Reporting Services). Com o SSDT, você pode projetar e implantar qualquer tipo de conteúdo do SQL Server com a mesma facilidade com que desenvolve um aplicativo no Visual Studio.


## <a name="changes-in-ssdt-for-visual-studio-2019"></a>Alterações no SSDT para Visual Studio 2019 ##

Com o Visual Studio de 2019, a funcionalidade necessária para habilitar os projetos do Analysis Services, do Integration Services e do Reporting Services foi movida para as respectivas extensões do Visual Studio. A principal funcionalidade do SSDT para criar Projetos de banco de dados permaneceu integral no Visual Studio (você precisará selecionar a carga de trabalho de processamento e armazenamento de Dados durante a instalação).  Não há mais necessidade da instalação autônoma SSDT. 

Se você já tiver uma licença do Visual Studio de 2019:
- Para Projetos de Banco de Dados SQL, instalar a carga de trabalho de processamento e armazenamento de dados do Visual Studio
- Para os projetos do Analysis Services, do Integration Services ou do Reporting Services, instalar as extensões apropriadas do marketplace

Se você não tiver uma licença do Visual Studio de 2019:
- Instalar o [Visual Studio Community 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_content=sqlssdt) 
- Instalar o Analysis Services, o Integration Services e a extensão de Reporting Services, conforme necessário

## <a name="changes-in-ssdt-for-visual-studio-2017"></a>Alterações no SSDT para Visual Studio 2017 ##

Iniciando no Visual Studio 2017, foi integrada a funcionalidade de criação de Projetos de banco de dados na instalação do Visual Studio. Não é necessário executar o instalador autônomo do SSDT na experiência principal do SSDT. Para criar projetos do Integration Services/Analysis Services/Reporting Services, você ainda precisa do instalador autônomo do SSDT. 

- Para Projetos de banco de dados, instalar a carga de trabalho de processamento e armazenamento de dados do Visual Studio
- Para os projetos do Analysis Services, do Integration Services ou do Reporting Services, baixe e instale as [SQL Server Data Tools](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017)




## <a name="install-ssdt-with-visual-studio-2017"></a>Instalar o SSDT com o Visual Studio 2017

Para instalar o SSDT durante a [instalação do Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio), selecione a carga de trabalho **Armazenamento e processamento de dados** e, em seguida, selecione **SQL Server Data Tools**. Se o Visual Studio já estiver instalado, você poderá [editar a lista de cargas de trabalho](https://docs.microsoft.com/visualstudio/install/modify-visual-studio) para incluir o SSDT: ![carga de trabalho de armazenamento e processamento de dados](../ssdt/media/download-sql-server-data-tools-ssdt/data-workload.png)

## <a name="install-analysis-services-integration-services-and-reporting-services-tools"></a>Instalar ferramentas do Analysis Services, do Integration Services e do Reporting Services

Para instalar suporte ao projeto do AS, do IS e do RS, execute o [instalador autônomo do SSDT](#ssdt-for-vs-2017-standalone-installer). 

O instalador lista instâncias disponíveis do Visual Studio às quais adicionar as ferramentas do SSDT. Se o Visual Studio não está instalado, ao selecionar **Instalar uma nova instância do SQL Server Data Tools**, o SSDT é instalado com um versão mínima do Visual Studio, mas para obter a melhor experiência, recomendamos usar o SSDT com [a versão mais recente do Visual Studio](https://www.visualstudio.com/downloads). 

![selecione AS, IS, RS](../ssdt/media/download-sql-server-data-tools-ssdt/select-services.png)



## <a name="ssdt-for-vs-2017-standalone-installer"></a>SSDT para VS 2017 (instalador autônomo)

[![baixar](../ssdt/media/download.png) Baixe o SSDT para Visual Studio 2017 (15.9.2)](https://go.microsoft.com/fwlink/?linkid=2095463) 

> [!IMPORTANT]
> - Antes de instalar o SSDT para o Visual Studio 2017 (15.9.2), desinstale as extensões *Projetos do Analysis Services* e *Projetos do Reporting Services*, caso já estejam instaladas, e feche todas as instâncias do VS.
> - Use o SSDT para Visual Studio 2017 (15.8.0) ou versões anteriores para criar pacotes do SSIS que contêm a Origem/destino Teradata. As versões do SSDT para Visual Studio 2017 após a versão 15.8.0 não podem criar pacotes do SSIS que contêm a Origem/destino Teradata.


**Informações da versão**  
  
Número da versão: 15.9.2  
Número de build: 14.0.16194.0  
Data de lançamento: 17 de julho de 2019  

Para obter uma lista completa de alterações, confira [Notas sobre a versão para o SSDT (SQL Server Data Tools)](release-notes-ssdt.md).

O SSDT para Visual Studio 2017 tem os mesmos [requisitos de sistema](https://docs.microsoft.com/visualstudio/productinfo/vs2017-system-requirements-vs) que o Visual Studio.  

### <a name="available-languages---ssdt-for-vs-2017"></a>Idiomas disponíveis – SSDT para VS 2017

Esta versão do **SSDT para VS 2017** pode ser instalada nos seguintes idiomas:

- [Chinês (simplificado)]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x804)
- [Chinês (tradicional)]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x404)
- [Inglês (Estados Unidos)]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x409)
- [Francês]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x40c)
- [Alemão]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x407)
- [Italiano]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x410)
- [Japonês]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x411)
- [Coreano]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x412)
- [Português (Brasil)]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x416)
- [Russo]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x419)
- [Espanhol]( https://go.microsoft.com/fwlink/?linkid=2095463&clcid=0x40a)

## <a name="offline-install"></a>Instalação offline

Para instalar o SSDT quando você não estiver conectado à Internet, siga as etapas nesta seção. Para obter mais informações, confira [Criar uma instalação de rede do Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/create-a-network-installation-of-visual-studio).

Primeiro, conclua as etapas a seguir enquanto estiver online:

1. [Baixe o instalador autônomo do SSDT](#ssdt-for-vs-2017-standalone-installer).
2. [Baixe o vs_sql.exe](https://aka.ms/vs/15/release/vs_sql.exe).
3. Enquanto estiver online, execute um dos comandos a seguir para baixar todos os arquivos necessários para a instalação offline. Usando a opção `--layout` como chave, os arquivos reais para instalação offline serão baixados. Substitua `<filepath>` pelo demarcador de layouts real para salvar os arquivos.

   
   A.   Para um idioma específico, passe a localidade: `vs_sql.exe --layout c:\<filepath> --lang en-us` (um único idioma tem aproximadamente 1 GB)  
   B. Para todos os idiomas, omita o argumento `--lang`: `vs_sql.exe --layout c:\<filepath>` (todos os idiomas têm aproximadamente 3.9 GB).

4. Execute `SSDT-Setup-ENU.exe /layout c:\<filepath>` para extrair o conteúdo do SSDT para o mesmo local `<filepath>` em que os arquivos do VS2017 foram baixados. Isso garante que todos os arquivos de ambos sejam combinados em uma única pasta de layouts.

Depois de concluir as etapas anteriores, o seguinte pode ser realizado enquanto estiver offline:

1. Execute `vs_setup.exe --NoWeb` para instalar o Shell do VS2017 e o projeto de dados do SQL Server.
2. Na pasta de layouts, execute `SSDT-Setup-ENU.exe /install` e selecione o SSIS/SSRS/SSAS.

   - Ou para uma instalação autônoma, execute `SSDT-Setup-ENU.exe /INSTALLALL[:vsinstances] /passive`  

Para ver as opções disponíveis, execute `SSDT-Setup-ENU.exe /help`

> [!NOTE]
> Se você usar uma versão completa do Visual Studio 2017, crie uma pasta offline somente para o SSDT e execute `SSDT-Setup-ENU.exe` nessa pasta recém-criada (não adicione o SSDT em outro layout offline do Visual Studio 2017). Se você adicionar o layout do SSDT em um layout offline do Visual Studio existente, os componentes de tempo de execução necessários (.exe) não serão criados lá.

## <a name="supported-sql-versions"></a>Versões do SQL com suporte
  
|Modelos de projeto|Plataformas SQL com suporte|  
|-------------------|--------------------|  
|Bancos de dados relacionais|  SQL Server 2005\* – SQL Server 2017<br> (use o SSDT 17.x ou o SSDT para Visual Studio 2017 para conectar-se ao [SQL Server no Linux](../linux/sql-server-linux-overview.md))<br /><br />Banco de dados SQL do Azure<br /><br />SQL Data Warehouse do Azure (dá suporte somente a consultas; ainda não há suporte para projetos de banco de dados)<br /><br /> \* O suporte ao SQL Server 2005 está preterido,<br /><br /> passe para uma versão do SQL oficialmente com suporte|
|Modelos do Analysis Services<br /><br />Relatórios do Reporting Services | SQL Server 2008 – SQL Server 2017|
|pacotes do Integration Services| SQL Server 2012 – SQL Server 2019 |
  
## <a name="dacfx"></a>DacFx

O SSDT para Visual Studio 2015 e o SSDT para Visual Studio 2017 usam o DacFx 17.4.1: [Baixar a estrutura de aplicativo da camada de dados (DacFx) 17.4.1](https://www.microsoft.com/download/details.aspx?id=56508).

## <a name="previous-versions"></a>Versões anteriores

Para baixar e instalar o SSDT para o Visual Studio 2015 ou uma versão mais antiga de SSDT, confira [Versões anteriores do SQL Server Data Tools (SSDT e SSDT-BI)](previous-releases-of-sql-server-data-tools-ssdt-and-ssdt-bi.md).

## <a name="next-steps"></a>Próximas etapas

Depois de instalar o SSDT, trabalhe com esses tutoriais para aprender a criar bancos de dados, pacotes, modelos de dados e relatórios usando o SSDT:  

- [Desenvolvimento de banco de dados offline orientado a projetos](project-oriented-offline-database-development.md)  
- [Tutorial do SSIS: criar um pacote ETL simples](../integration-services/ssis-how-to-create-an-etl-package.md)  
- [Tutoriais do Analysis Services](../analysis-services/analysis-services-tutorials-ssas.md)  
- [Criando um relatório de tabela básico (Tutorial do SSRS)](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)  

[!INCLUDE[get-help-options](../includes/paragraph-content/get-help-options.md)]

## <a name="see-also"></a>Consulte Também

[Fórum do MSDN do SSDT](https://social.msdn.microsoft.com/Forums/sqlserver/home?forum=ssdt)  
[Blog da equipe do SSDT](https://blogs.msdn.com/b/ssdt/)  
[Referência DACFx API](https://msdn.microsoft.com/library/dn645454.aspx)  
[Baixar o SQL Server Management Studio (SSMS)](../ssms/download-sql-server-management-studio-ssms.md)  
