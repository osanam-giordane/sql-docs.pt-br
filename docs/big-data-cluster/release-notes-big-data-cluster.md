---
title: Notas de versão
titleSuffix: SQL Server big data clusters
description: Este artigo descreve as atualizações mais recentes e problemas conhecidos para SQL Server clusters 2019 Big Data (versão prévia).
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.date: 07/24/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: c0dd96d4a3227fda76921764429b4566e3e5dd28
ms.sourcegitcommit: 1f222ef903e6aa0bd1b14d3df031eb04ce775154
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68419304"
---
# <a name="release-notes-for-big-data-clusters-on-sql-server"></a>Notas de versão para clusters de Big Data no SQL Server

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

Este artigo lista as atualizações e os problemas conhecidos para as versões mais recentes de clusters de SQL Server Big Data.

[!INCLUDE [Limited public preview note](../includes/big-data-cluster-preview-note.md)]

## <a id="ctp32"></a>CTP 3,2 (julho)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 3,2.

|Novo recurso ou atualização | Detalhes |
|:---|:---|
|Visualização pública |Antes do CTP 3,2, SQL Server Cluster Big Data estava disponível para os pioneiros registrados. Esta versão permite que qualquer pessoa experimente os recursos do SQL Server clusters de Big Data. <br/><br/> Consulte [introdução aos clusters de Big Data SQL Server](deploy-get-started.md).|
|`azdata` |O CTP 3,2 `azdata` apresenta um utilitário de linha de comando escrito em Python que permite aos administradores de cluster inicializar e gerenciar o cluster de Big data por meio de APIs REST. `azdata`Substitui `mssqlctl`. Consulte [instalar `azdata` ](deploy-install-azdata.md). |
|PolyBase |Os nomes de coluna da tabela externa agora são usados para consultar fontes de dados SQL Server, Oracle, Teradata, MongoDB e ODBC. |
|Atualização de camadas do HDFS |Introdução à funcionalidade de atualização para camadas do HDFS para que uma montagem existente possa ser atualizada para o instantâneo mais recente dos dados remotos. Consulte disposição em [camadas do HDFS](hdfs-tiering.md) |
|Solução de problemas baseada em Notebook |O CTP 3,2 introduz notebooks Jupyter para auxiliar na [implantação](deploy-notebooks.md) e [descoberta, diagnóstico e solução de problemas](manage-notebooks.md) de componentes em um cluster SQL Server Big Data. |
| &nbsp; | &nbsp; |

## <a id="ctp31"></a>CTP 3,1 (junho)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 3,1.

|Novo recurso ou atualização | Detalhes |
|:---|:---|
|Visualização pública |Antes do CTP 3,2, SQL Server Cluster Big Data estava disponível para os pioneiros registrados. Esta versão permite que qualquer pessoa experimente os recursos do SQL Server clusters de Big Data. <br/><br/> Consulte [introdução aos clusters de Big Data SQL Server](deploy-get-started.md).|
|Solução de problemas baseada no bloco de anotações.|O CTP 3,2 introduz blocos de anotações do Jupyter para auxiliar na [implantação](deploy-notebooks.md), na descoberta, no diagnóstico e na [solução de problemas](manage-notebooks.md) de componentes em um cluster SQL Server Big Data. |
|`azdata` |O CTP 3,2 `azdata` apresenta um utilitário de linha de comando escrito em Python que permite aos administradores de cluster inicializar e gerenciar o cluster de Big data por meio de APIs REST. `azdata`Substitui `mssqlctl`. Consulte [instalar `azdata` ](deploy-install-azdata.md). |
|Atualização de camadas do HDFS |Introdução à funcionalidade de atualização para camadas do HDFS para que uma montagem existente possa ser atualizada para o instantâneo mais recente dos dados remotos. Consulte disposição em [camadas do HDFS](hdfs-tiering.md) |
| &nbsp; | &nbsp; |

### <a name="whats-new"></a>O Que Há de Novo

| Novo recurso ou atualização | Detalhes |
|:---|:---|
| Alterações de comando `mssqlctl` | Comandos `mssqlctl cluster` foram renomeados para `mssqlctl bdc`. Para obter mais informações, consulte a [referência do `mssqlctl`](reference-azdata.md). |
| Novos `mssqlctl` comandos de status e remoção do portal de administração do cluster. | O portal de administração do cluster foi removido desta versão. Novos comandos de status foram adicionados a `mssqlctl` esse complemento comandos de monitoramento existentes. |
| Pools de computação do Spark | Crie nós adicionais para aumentar a potência de computação do Spark sem precisar escalar verticalmente o armazenamento. Além disso, você pode iniciar nós de pool de armazenamento que não são usados para o Spark. O Spark e o armazenamento são separados. Para obter mais informações, consulte [Configurar o armazenamento sem o Spark](deployment-custom-configuration.md#sparkstorage). |
| Conector do Spark MSSQL | Suporte para leitura/gravação para tabelas externas do pool de dados. As versões anteriores eram compatíveis apenas com leitura/gravação para tabelas da instância MASTER. Para obter mais informações, consulte [Como ler e gravar para o SQL Server no Spark usando o Conector do Spark MSSQL](spark-mssql-connector.md). |
| Machine Learning usando o MLeap | [Treine um modelo de machine learning do MLeap no Spark e pontue-o no SQL Server usando a extensão da linguagem Java](spark-create-machine-learning-model.md). |

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir descrevem os problemas conhecidos e as limitações desta versão.

#### <a name="hdfs"></a>HDFS

- Se você clicar com o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente, não há nenhuma maneira de visualizar arquivos com mais de 30 MB em Azure Data Studio.

- Não há suporte para alterações de configuração no HDFS que envolvem alterações em HDFS-site. xml.

#### <a name="deployment"></a>Implantação

- Não há suporte para a atualização de um cluster de dados Big Data de uma versão anterior.

   > [!IMPORTANT]
   > Você deve fazer backup dos dados e, em seguida, excluir o cluster de Big Data existente (usando a versão anterior do **azdata**) antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-upgrade.md).

- Depois de implantar o no AKS, você poderá ver os dois eventos de aviso a seguir da implantação. Esses dois eventos são problemas conhecidos, mas eles não impedem que você implante com êxito o cluster Big Data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster Big Data falhar, o namespace associado não será removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="external-tables"></a>Tabelas externas

- A implantação de cluster de Big data não cria mais as fontes de dados externas **SqlDataPool** e **SqlStoragePool** . Você pode criar essas fontes de dados manualmente para dar suporte à virtualização de dados para o pool de dados e o pool de armazenamento.

   > [!NOTE]
   > O URI para criar essas fontes de dados externas é diferente entre CTPs. Consulte os comandos Transact-SQL abaixo para ver como criá-los 

   ```sql
   -- Create default data sources for SQL Big Data Cluster
   IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlDataPool')
       CREATE EXTERNAL DATA SOURCE SqlDataPool
       WITH (LOCATION = 'sqldatapool://controller-svc/default');
 
   IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlStoragePool')
       CREATE EXTERNAL DATA SOURCE SqlStoragePool
       WITH (LOCATION = 'sqlhdfs://controller-svc/default');
   ```

- É possível criar uma tabela externa do pool de dados para uma tabela que tem tipos de coluna sem suporte. Se você consultar a tabela externa, receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, poderá receber um erro se o arquivo subjacente estiver sendo copiado para o HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

- Se você estiver criando uma tabela externa para a Oracle que usa tipos de dados de caractere, o assistente de virtualização Azure Data Studio interpretará essas colunas como VARCHAR na definição da tabela externa. Isso causará uma falha na DDL da tabela externa. Modifique o esquema Oracle para usar o tipo NVARCHAR2 ou crie instruções de tabela externa manualmente e especifique NVARCHAR em vez de usar o assistente.

#### <a name="application-deployment"></a>Implantação de aplicativo

- Ao chamar um aplicativo R, Python ou MLeap da API RESTful, o tempo limite da chamada é de 5 minutos.

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Os endereços IP POD podem mudar no ambiente kubernetes conforme o PODs é reiniciado. No cenário em que o Pod mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com novos endereços IP.

- Se você já tiver o Jupyter instalado e um Python separado no Windows, os notebooks Spark poderão falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar no comando **Adicionar texto** , a célula de texto será adicionada no modo de visualização, e não no modo de edição. Você pode clicar no ícone de visualização para alternar para o modo de edição e editar a célula.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e é detectável (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestra após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Os logs do AKS podem conter a senha SA para implantações de cluster Big Data.

#### <a name="kibana-logs-dashboards"></a>Painéis de logs do Kibana

- Entre o CTP resultante 3,0 e o 3,1, a versão Kibana foi atualizada de 6.3.1 para 7.0.1.  Isso tornou o navegador de borda incompatível com o Kibana. Os usuários verão uma página em branco ao carregar a versão atual dos painéis do Kibana no Edge. Consulte [aqui]( https://www.elastic.co/support/matrix#matrix_browse) para ver os navegadores com suporte para Kibana.RS 


## <a id="ctp30"></a>CTP 3,0 (maio)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 3,0.

### <a name="whats-new"></a>O Que Há de Novo

| Novo recurso ou atualização | Detalhes |
|:---|:---|
| Atualizações de **mssqlctl** | Várias [atualizações de comando e parâmetro](reference-azdata.md) do **mssqlctl**. Isso inclui uma atualização do comando **mssqlctl login**, que agora direciona o nome de usuário do controlador e o ponto de extremidade. |
| Melhorias no armazenamento | Suporte para diferentes configurações de armazenamento para logs e dados. Além disso, o número de declarações de volume persistente para um cluster de Big Data foi reduzido. |
| Várias instâncias do pool de computação | Suporte para várias instâncias do pool de computação. |
| Novas funcionalidades e novo comportamento do pool | O pool de computação agora é usado por padrão em operações do pool de dados e do pool de armazenamento apenas em uma distribuição **ROUND_ROBIN**. Agora o pool de dados pode usar um novo tipo de distribuição **REPLICATED**, o que significa que os mesmos dados estão presentes em todas as instâncias do pool de dados. |
| Melhorias na tabela externa | As tabelas externas do tipo de fonte de dados HADOOP agora dão suporte à leitura de linhas com até 1 MB. As tabelas externas (ODBC, pool de armazenamento, pool de dados) agora dão suporte a linhas da mesma largura de uma tabela do SQL Server. |

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir descrevem os problemas conhecidos e as limitações desta versão.

#### <a name="hdfs"></a>HDFS

- Azure Data Studio retorna um erro quando você tenta criar uma nova pasta no HDFS. Para habilitar essa funcionalidade, instale a compilação de pessoas de Azure Data Studio:
  
   - [Instalador de usuário do Windows- **compilação** de insideres](https://azuredatastudio-update.azurewebsites.net/latest/win32-x64-user/insider)
   - [Instalador de sistema do Windows- **compilação** de insideres](https://azuredatastudio-update.azurewebsites.net/latest/win32-x64/insider)
   - [Compilação de insideres ZIP **do** Windows](https://azuredatastudio-update.azurewebsites.net/latest/win32-x64-archive/insider)
   - [Build de COMPACTAdores **do** MacOS](https://azuredatastudio-update.azurewebsites.net/latest/darwin/insider)
   - [TAR do Linux. **Build** GZs](https://azuredatastudio-update.azurewebsites.net/latest/linux-x64/insider)

- Se você clicar com o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente, não há nenhuma maneira de visualizar arquivos com mais de 30 MB em Azure Data Studio.

- Não há suporte para alterações de configuração no HDFS que envolvem alterações em HDFS-site. xml.

#### <a name="deployment"></a>Implantação

- Os procedimentos de implantação anteriores para clusters de Big Data habilitados para GPU não têm suporte no CTP 3,0. Um procedimento de implantação alternativo está sendo investigado. Por enquanto, o artigo "implantar um cluster Big Data com suporte a GPU e executar TensorFlow" foi temporariamente cancelado para evitar confusão.

- Não há suporte para a atualização de um cluster de dados Big Data de uma versão anterior.

   > [!IMPORTANT]
   > Você deve fazer backup dos dados e, em seguida, excluir o cluster de Big Data existente (usando a versão anterior do **azdata**) antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-upgrade.md).

- Depois de implantar o no AKS, você poderá ver os dois eventos de aviso a seguir da implantação. Esses dois eventos são problemas conhecidos, mas eles não impedem que você implante com êxito o cluster Big Data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster Big Data falhar, o namespace associado não será removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="external-tables"></a>Tabelas externas

- A implantação de cluster de Big data não cria mais as fontes de dados externas **SqlDataPool** e **SqlStoragePool** . Você pode criar essas fontes de dados manualmente para dar suporte à virtualização de dados para o pool de dados e o pool de armazenamento.

   > [!NOTE]
   > O URI para criar essas fontes de dados externas é diferente entre CTPs. Consulte os comandos Transact-SQL abaixo para ver como criá-los 

   ```sql
   -- Create default data sources for SQL Big Data Cluster
   IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlDataPool')
       CREATE EXTERNAL DATA SOURCE SqlDataPool
       WITH (LOCATION = 'sqldatapool://controller-svc/default');
 
   IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlStoragePool')
       CREATE EXTERNAL DATA SOURCE SqlStoragePool
       WITH (LOCATION = 'sqlhdfs://controller-svc/default');
   ```

- É possível criar uma tabela externa do pool de dados para uma tabela que tem tipos de coluna sem suporte. Se você consultar a tabela externa, receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, poderá receber um erro se o arquivo subjacente estiver sendo copiado para o HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

- Se você estiver criando uma tabela externa para a Oracle que usa tipos de dados de caractere, o assistente de virtualização Azure Data Studio interpretará essas colunas como VARCHAR na definição da tabela externa. Isso causará uma falha na DDL da tabela externa. Modifique o esquema Oracle para usar o tipo NVARCHAR2 ou crie instruções de tabela externa manualmente e especifique NVARCHAR em vez de usar o assistente.

#### <a name="application-deployment"></a>Implantação de aplicativo

- Ao chamar um aplicativo R, Python ou MLeap da API RESTful, o tempo limite da chamada é de 5 minutos.

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Os endereços IP POD podem mudar no ambiente kubernetes conforme o PODs é reiniciado. No cenário em que o Pod mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com novos endereços IP.

- Se você já tiver o Jupyter instalado e um Python separado no Windows, os notebooks Spark poderão falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar no comando **Adicionar texto** , a célula de texto será adicionada no modo de visualização, e não no modo de edição. Você pode clicar no ícone de visualização para alternar para o modo de edição e editar a célula.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e é detectável (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestra após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Os logs do AKS podem conter a senha SA para implantações de cluster Big Data.

## <a id="ctp25"></a>CTP 2,5 (abril)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 2,5.

### <a name="whats-new"></a>O Que Há de Novo

| Novo recurso ou atualização | Detalhes |
|:---|:---|
| Perfis de implantação | Use os [arquivos JSON de configuração de implantação](deployment-guidance.md#configfile) para padrão e personalizados para implantações de cluster de Big Data, em vez de variáveis de ambiente. |
| Implantações solicitadas | O `azdata cluster create` agora solicitará qualquer configuração necessária para implantações padrão. |
| Alterações de nome de ponto de extremidade de serviço e de pod | Os seguintes pontos de extremidade externos têm nomes alterados:<br/>&nbsp;&nbsp;&nbsp;- **endpoint-master-pool** => **master-svc-external**<br/>&nbsp;&nbsp;&nbsp;- **endpoint-controller** => **controller-svc-external**<br/>&nbsp;&nbsp;&nbsp;- **endpoint-service-proxy** => **mgmtproxy-svc-external**<br/>&nbsp;&nbsp;&nbsp;- **endpoint-security** => **gateway-svc-external**<br/>&nbsp;&nbsp;&nbsp;- **endpoint-app-service-proxy** => **appproxy-svc-external**|
| aprimoramentos do **azdata** | Use **azdata** para [listar pontos de extremidade externos](deployment-guidance.md#endpoints) e verificar a versão do **azdata** com `--version` o parâmetro. |
| Instalação offline | Diretrizes para implantações de cluster Big Data offline. |
| Melhorias em camadas do HDFS | Nível S3, cache de montagem e suporte OAuth para ADLS Gen2. |
| Novo `mssql` conector Spark-SQL Server | |

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir descrevem os problemas conhecidos e as limitações desta versão.

#### <a name="deployment"></a>Implantação

- Não há suporte para a atualização de um cluster de dados Big Data de uma versão anterior.

   > [!IMPORTANT]
   > Você deve fazer backup dos dados e, em seguida, excluir o cluster de Big Data existente (usando a versão anterior do **azdata**) antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-upgrade.md).

- Depois de implantar o no AKS, você poderá ver os dois eventos de aviso a seguir da implantação. Esses dois eventos são problemas conhecidos, mas eles não impedem que você implante com êxito o cluster Big Data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster Big Data falhar, o namespace associado não será removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="external-tables"></a>Tabelas externas

- A implantação de cluster de Big data não cria mais as fontes de dados externas **SqlDataPool** e **SqlStoragePool** . Você pode criar essas fontes de dados manualmente para dar suporte à virtualização de dados para o pool de dados e o pool de armazenamento.

   ```sql
   -- Create default data sources for SQL Big Data Cluster
   IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlDataPool')
       CREATE EXTERNAL DATA SOURCE SqlDataPool
       WITH (LOCATION = 'sqldatapool://service-mssql-controller:8080/datapools/default');
 
   IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlStoragePool')
       CREATE EXTERNAL DATA SOURCE SqlStoragePool
       WITH (LOCATION = 'sqlhdfs://nmnode-0-svc:50070');
   ```

- É possível criar uma tabela externa do pool de dados para uma tabela que tem tipos de coluna sem suporte. Se você consultar a tabela externa, receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, poderá receber um erro se o arquivo subjacente estiver sendo copiado para o HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

- Se você estiver criando uma tabela externa para a Oracle que usa tipos de dados de caractere, o assistente de virtualização Azure Data Studio interpretará essas colunas como VARCHAR na definição da tabela externa. Isso causará uma falha na DDL da tabela externa. Modifique o esquema Oracle para usar o tipo NVARCHAR2 ou crie instruções de tabela externa manualmente e especifique NVARCHAR em vez de usar o assistente.

#### <a name="application-deployment"></a>Implantação de aplicativo

- Ao chamar um aplicativo R, Python ou MLeap da API RESTful, o tempo limite da chamada é de 5 minutos.

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Os endereços IP POD podem mudar no ambiente kubernetes conforme o PODs é reiniciado. No cenário em que o Pod mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com novos endereços IP.

- Se você já tiver o Jupyter instalado e um Python separado no Windows, os notebooks Spark poderão falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar no comando **Adicionar texto** , a célula de texto será adicionada no modo de visualização, e não no modo de edição. Você pode clicar no ícone de visualização para alternar para o modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se você clicar com o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente, não há nenhuma maneira de visualizar arquivos com mais de 30 MB em Azure Data Studio.

- Não há suporte para alterações de configuração no HDFS que envolvem alterações em HDFS-site. xml.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e é detectável (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestra após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Os logs do AKS podem conter a senha SA para implantações de cluster Big Data.

## <a id="ctp24"></a>CTP 2,4 (março)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 2,4.

### <a name="whats-new"></a>O Que Há de Novo

| Novo recurso ou atualização | Detalhes |
|:---|:---|
| Diretrizes de suporte de GPU para execução de aprendizado profundo com o TensorFlow no Spark. | [Implantar um cluster de Big Data com suporte GPU e executar o TensorFlow](spark-gpu-tensorflow.md). |
| As fontes de dados **SqlDataPool** e **SqlStoragePool** não são mais criadas por padrão. | Crie-os manualmente, se necessário. Veja os [problemas conhecidos](#externaltablesctp24). |
| Suporte a `INSERT INTO SELECT` para o pool de dados. | Para um exemplo, veja [Tutorial: Ingerir dados em um pool de dados do SQL Server com Transact-SQL](tutorial-data-pool-ingest-sql.md). |
| Opções `FORCE SCALEOUTEXECUTION` e `DISABLE SCALEOUTEXECUTION`. | Força ou desabilita o uso do pool de computação para consultas em tabelas externas. Por exemplo, `SELECT TOP(100) * FROM web_clickstreams_hdfs_book_clicks OPTION(FORCE SCALEOUTEXECUTION)`. |
| Recomendações atualizadas de implantação do AKS. | Ao avaliar a clusters de Big Data no AKS, agora recomendamos usar um único nó de tamanho **Standard_L8s**. |
| Atualização de tempo de execução do Spark para o Spark 2.4. | |

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir descrevem os problemas conhecidos e as limitações desta versão.

#### <a name="deployment"></a>Implantação

- Não há suporte para a atualização de um cluster de dados Big Data de uma versão anterior.

   > [!IMPORTANT]
   > Você deve fazer backup dos dados e, em seguida, excluir o cluster de Big Data existente (usando a versão anterior do **azdata**) antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-upgrade.md).

- Depois de implantar o no AKS, você poderá ver os dois eventos de aviso a seguir da implantação. Esses dois eventos são problemas conhecidos, mas eles não impedem que você implante com êxito o cluster Big Data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster Big Data falhar, o namespace associado não será removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="kubeadm-deployments"></a>implantações de kubeadm

Se você usar o kubeadm para implantar o kubernetes em vários computadores, o portal de administração de cluster não exibirá corretamente os pontos de extremidade necessários para se conectar ao cluster de Big Data. Se você estiver enfrentando esse problema, use a seguinte solução alternativa para descobrir os endereços IP do ponto de extremidade de serviço:

- Se você estiver se conectando de dentro do cluster, consulte kubernetes para o IP do serviço para o ponto de extremidade ao qual você deseja se conectar. Por exemplo, o seguinte comando **kubectl** exibe o endereço IP da instância mestra de SQL Server:

   ```bash
   kubectl get service endpoint-master-pool -n <clusterName> -o=custom-columns="IP:.spec.clusterIP,PORT:.spec.ports[*].nodePort"
   ```

- Se você estiver se conectando de fora do cluster, use as seguintes etapas para se conectar:

   1. Obtenha o endereço IP do nó que executa a instância mestra de SQL Server `kubectl get pod mssql-master-pool-0 -o jsonpath="Name: {.metadata.name} Status: {.status.hostIP}" -n <clusterName>`:.

   1. Conecte-se a SQL Server instância mestra usando este endereço IP.

   1. Consulte o **cluster_endpoint_table** no banco de dados mestre para outros pontos de extremidade externos.

      Se isso falhar com um tempo limite de conexão, é possível que o respectivo nó esteja em Firewall. Nesse caso, você deve entrar em contato com o administrador do cluster kubernetes e solicitar o IP do nó que é exposto externamente. Pode ser qualquer nó. Você pode usar esse IP e a porta correspondente para se conectar a vários serviços em execução no cluster. Por exemplo, o administrador pode encontrar esse IP executando:

      ```
      [root@m12hn01 config]# kubectl cluster-info
      Kubernetes master is running at https://172.50.253.99:6443
      KubeDNS is running at https://172.30.243.91:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
      ```

#### <a name="delete-cluster-fails"></a>Falha ao excluir cluster

Quando você tenta excluir um cluster com **azdata**, ele falha com o seguinte erro:

```
2019-03-26 20:38:11.0614 UTC | INFO | Deleting cluster ...
Error processing command: "TypeError"
delete_namespaced_service() takes 3 positional arguments but 4 were given
Makefile:61: recipe for target 'delete-cluster' failed
make[2]: *** [delete-cluster] Error 1
Makefile:223: recipe for target 'deploy-clean' failed
make[1]: *** [deploy-clean] Error 2
Makefile:203: recipe for target 'deploy-clean' failed
make: *** [deploy-clean] Error 2
```

Um novo cliente Python kubernetes (versão 9.0.0) alterou a API de exclusão de namespaces, que atualmente quebra o **azdata**. Isso só acontece se você tiver um cliente kubernetes Python mais recente instalado. Você pode contornar esse problema excluindo diretamente o cluster usando **kubectl** (`kubectl delete ns <ClusterName>`) ou pode instalar a versão mais antiga usando `sudo pip install kubernetes==8.0.1`o.

#### <a id="externaltablesctp24"></a>Tabelas externas

- A implantação de cluster de Big data não cria mais as fontes de dados externas **SqlDataPool** e **SqlStoragePool** . Você pode criar essas fontes de dados manualmente para dar suporte à virtualização de dados para o pool de dados e o pool de armazenamento.

   ```sql
   -- Create default data sources for SQL Big Data Cluster
   IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlDataPool')
       CREATE EXTERNAL DATA SOURCE SqlDataPool
       WITH (LOCATION = 'sqldatapool://service-mssql-controller:8080/datapools/default');
 
   IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlStoragePool')
       CREATE EXTERNAL DATA SOURCE SqlStoragePool
       WITH (LOCATION = 'sqlhdfs://service-master-pool:50070');
   ```

- É possível criar uma tabela externa do pool de dados para uma tabela que tem tipos de coluna sem suporte. Se você consultar a tabela externa, receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, poderá receber um erro se o arquivo subjacente estiver sendo copiado para o HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

- Se você estiver criando uma tabela externa para a Oracle que usa tipos de dados de caractere, o assistente de virtualização Azure Data Studio interpretará essas colunas como VARCHAR na definição da tabela externa. Isso causará uma falha na DDL da tabela externa. Modifique o esquema Oracle para usar o tipo NVARCHAR2 ou crie instruções de tabela externa manualmente e especifique NVARCHAR em vez de usar o assistente.

#### <a name="application-deployment"></a>Implantação de aplicativo

- Ao chamar um aplicativo R, Python ou MLeap da API RESTful, o tempo limite da chamada é de 5 minutos.

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Os endereços IP POD podem mudar no ambiente kubernetes conforme o PODs é reiniciado. No cenário em que o Pod mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com novos endereços IP.

- Se você já tiver o Jupyter instalado e um Python separado no Windows, os notebooks Spark poderão falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar no comando **Adicionar texto** , a célula de texto será adicionada no modo de visualização, e não no modo de edição. Você pode clicar no ícone de visualização para alternar para o modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se você clicar com o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente, não há nenhuma maneira de visualizar arquivos com mais de 30 MB em Azure Data Studio.

- Não há suporte para alterações de configuração no HDFS que envolvem alterações em HDFS-site. xml.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e é detectável (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestra após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Os logs do AKS podem conter a senha SA para implantações de cluster Big Data.

## <a id="ctp23"></a>CTP 2,3 (fevereiro)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 2,3.

### <a name="whats-new"></a>O Que Há de Novo

| Novo recurso ou atualização | Detalhes |
| :---------- | :------ |
| Enviar trabalhos do Spark em clusters de Big Data no IntelliJ. | [Enviar trabalhos do Spark em clusters de Big Data do SQL Server no IntelliJ](spark-submit-job-intellij-tool-plugin.md) |
| CLI comum para gerenciamento de cluster e de implantação do aplicativo. | [Como implantar um aplicativo no cluster de Big Data do SQL Server 2019 (versão prévia)](big-data-cluster-create-apps.md) |
| Extensão do VS Code para implantar aplicativos em um cluster de Big Data. | [Como usar o VS Code para implantar aplicativos em clusters de Big Data do SQL Server](app-deployment-extension.md) |
| Alterações no uso de comando da ferramenta **azdata** . | Para obter mais detalhes, consulte os [problemas conhecidos para azdata](#azdatactp23). |
| Usar Sparklyr no cluster Big Data | [Usar o Sparklyr em clusters de Big Data do SQL Server 2019](sparklyr-from-RStudio.md) |
| Montar armazenamento compatível com HDFS externo no cluster de Big Data com a disposição em **camadas do HDFS**. | Veja [Camadas do HDFS](hdfs-tiering.md). |
| Nova experiência de conexão unificada para a instância principal do SQL Server e o Gateway do HDFS/Spark. | Veja [Instância principal do SQL Server e o Gateway do HDFS/Spark](connect-to-big-data-cluster.md). |
| A exclusão de um cluster com o **azdata cluster Delete** agora exclui apenas os objetos no namespace que faziam parte do cluster Big Data. | O namespace não é excluído. No entanto, em versões anteriores, esse comando excluía todo o namespace. |
| Nomes de ponto de extremidade de _segurança_ foram alterados e consolidados. | **service-security-lb** e **service-security-nodeport** foram consolidados no ponto de extremidade **endpoint-security**. |
| Nomes de ponto de extremidade de _proxy_ foram alterados e consolidados. | **service-proxy-lb** e **service-proxy-nodeport** foram consolidados no ponto de extremidade **endpoint-service-proxy**. |
| Nomes de ponto de extremidade de _controlador_ foram alterados e consolidados. | **service-mssql-controller-lb** e **service-mssql-controller-nodeport** foram consolidados no ponto de extremidade **endpoint-controller**. |
| &nbsp; | &nbsp; |

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir descrevem os problemas conhecidos e as limitações desta versão.

#### <a name="deployment"></a>Implantação

- Não há suporte para a atualização de um cluster de dados Big Data de uma versão anterior.

   > [!IMPORTANT]
   > Você deve fazer backup dos dados e, em seguida, excluir o cluster de Big Data existente (usando a versão anterior do **azdata**) antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-upgrade.md).

- A variável de ambiente **ACCEPT_EULA** deve ser "Sim" ou "Sim" para aceitar o EULA. As versões anteriores permitiam "y" e "Y", mas elas não são mais aceitas e farão com que a implantação falhe.

- As variáveis de ambiente **CLUSTER_PLATFORM** não têm um padrão como fazia em versões anteriores.

- Depois de implantar o no AKS, você poderá ver os dois eventos de aviso a seguir da implantação. Esses dois eventos são problemas conhecidos, mas eles não impedem que você implante com êxito o cluster Big Data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster Big Data falhar, o namespace associado não será removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="kubeadm-deployments"></a>implantações de kubeadm

Se você usar o kubeadm para implantar o kubernetes em vários computadores, o portal de administração de cluster não exibirá corretamente os pontos de extremidade necessários para se conectar ao cluster de Big Data. Se você estiver enfrentando esse problema, use a seguinte solução alternativa para descobrir os endereços IP do ponto de extremidade de serviço:

- Se você estiver se conectando de dentro do cluster, consulte kubernetes para o IP do serviço para o ponto de extremidade ao qual você deseja se conectar. Por exemplo, o seguinte comando **kubectl** exibe o endereço IP da instância mestra de SQL Server:

   ```bash
   kubectl get service endpoint-master-pool -n <clusterName> -o=custom-columns="IP:.spec.clusterIP,PORT:.spec.ports[*].nodePort"
   ```

- Se você estiver se conectando de fora do cluster, use as seguintes etapas para se conectar:

   1. Obtenha o endereço IP do nó que executa a instância mestra de SQL Server `kubectl get pod mssql-master-pool-0 -o jsonpath="Name: {.metadata.name} Status: {.status.hostIP}" -n <clusterName>`:.

   1. Conecte-se a SQL Server instância mestra usando este endereço IP.

   1. Consulte o **cluster_endpoint_table** no banco de dados mestre para outros pontos de extremidade externos.

      Se isso falhar com um tempo limite de conexão, é possível que o respectivo nó esteja em Firewall. Nesse caso, você deve entrar em contato com o administrador do cluster kubernetes e solicitar o IP do nó que é exposto externamente. Pode ser qualquer nó. Você pode usar esse IP e a porta correspondente para se conectar a vários serviços em execução no cluster. Por exemplo, o administrador pode encontrar esse IP executando:

      ```
      [root@m12hn01 config]# kubectl cluster-info
      Kubernetes master is running at https://172.50.253.99:6443
      KubeDNS is running at https://172.30.243.91:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
      ```

#### <a id="azdatactp23"></a>azdata

- A ferramenta **azdata** mudou de uma ordenação de comando verbo-substantivo para uma ordem substantivo-Verb. Por exemplo, `azdata create cluster` é agora `azdata cluster create`.

- Agora `--name` , o parâmetro é necessário ao criar um cluster `azdata cluster create`com o.

   ```bash
   azdata cluster create --name <cluster_name>
   ```

- Para obter informações importantes sobre como atualizar para a versão mais recente do Big Data clusters e **azdata**, consulte [atualizar para uma nova versão](deployment-upgrade.md).

#### <a name="external-tables"></a>Tabelas externas

- É possível criar uma tabela externa do pool de dados para uma tabela que tem tipos de coluna sem suporte. Se você consultar a tabela externa, receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, poderá receber um erro se o arquivo subjacente estiver sendo copiado para o HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

- Se você estiver criando uma tabela externa para a Oracle que usa tipos de dados de caractere, o assistente de virtualização Azure Data Studio interpretará essas colunas como VARCHAR na definição da tabela externa. Isso causará uma falha na DDL da tabela externa. Modifique o esquema Oracle para usar o tipo NVARCHAR2 ou crie instruções de tabela externa manualmente e especifique NVARCHAR em vez de usar o assistente.

#### <a name="application-deployment"></a>Implantação de aplicativo

- Ao chamar um aplicativo R, Python ou MLeap da API RESTful, o tempo limite da chamada é de 5 minutos.

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Os endereços IP POD podem mudar no ambiente kubernetes conforme o PODs é reiniciado. No cenário em que o Pod mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com novos endereços IP.

- Se você já tiver o Jupyter instalado e um Python separado no Windows, os notebooks Spark poderão falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar no comando **Adicionar texto** , a célula de texto será adicionada no modo de visualização, e não no modo de edição. Você pode clicar no ícone de visualização para alternar para o modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se você clicar com o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente, não há nenhuma maneira de visualizar arquivos com mais de 30 MB em Azure Data Studio.

- Não há suporte para alterações de configuração no HDFS que envolvem alterações em HDFS-site. xml.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e é detectável (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestra após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Os logs do AKS podem conter a senha SA para implantações de cluster Big Data.

## <a id="ctp22"></a>CTP 2,2 (dezembro de 2018)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 2,2.

### <a name="new-features"></a>Novos recursos

- Portal de administração de cluster `/portal` acessado com ( **\<https://IP-address\>: 30777/portal**).
- O nome do serviço do pool `service-master-pool-lb` mestre `service-master-pool-nodeport` foi `endpoint-master-pool`alterado de e para.
- Nova versão do **azdata** e imagens atualizadas.
- Correções e aprimoramentos de bugs diversos.

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir descrevem os problemas conhecidos e as limitações desta versão.

#### <a name="deployment"></a>Implantação

- Não há suporte para a atualização de um cluster de dados Big Data de uma versão anterior. Você deve fazer backup e excluir qualquer cluster de Big Data existente antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-upgrade.md).

- Depois de implantar o no AKS, você poderá ver os dois eventos de aviso a seguir da implantação. Esses dois eventos são problemas conhecidos, mas eles não impedem que você implante com êxito o cluster Big Data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster Big Data falhar, o namespace associado não será removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="cluster-administration-portal"></a>Portal de administração de cluster

O portal de administração de cluster não exibe o ponto de extremidade para a instância mestra de SQL Server. Para localizar o endereço IP e a porta para a instância mestra, use o seguinte comando **kubectl** :

```
kubectl get svc endpoint-master-pool -n <your-big-data-cluster-name>
```

#### <a name="external-tables"></a>Tabelas externas

- É possível criar uma tabela externa do pool de dados para uma tabela que tem tipos de coluna sem suporte. Se você consultar a tabela externa, receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, poderá receber um erro se o arquivo subjacente estiver sendo copiado para o HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Os endereços IP POD podem mudar no ambiente kubernetes conforme o PODs é reiniciado. No cenário em que o Pod mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com novos endereços IP.

- Se você já tiver o Jupyter instalado e um Python separado no Windows, os notebooks Spark poderão falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar no comando **Adicionar texto** , a célula de texto será adicionada no modo de visualização, e não no modo de edição. Você pode clicar no ícone de visualização para alternar para o modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se você clicar com o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente, não há nenhuma maneira de visualizar arquivos com mais de 30 MB em Azure Data Studio.

- Não há suporte para alterações de configuração no HDFS que envolvem alterações em HDFS-site. xml.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e é detectável (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestra após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Os logs do AKS podem conter a senha SA para implantações de cluster Big Data.

## <a id="ctp21"></a>CTP 2,1 (novembro de 2018)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 2,1.

### <a name="new-features"></a>Novos recursos

- [Implante aplicativos Python e R](big-data-cluster-create-apps.md) em um cluster Big Data.
- Nova versão do **azdata** e imagens atualizadas. 
- Correções e aprimoramentos de bugs diversos.

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir fornecem problemas conhecidos para SQL Server clusters de Big Data no CTP 2,1.

#### <a name="deployment"></a>Implantação

- Não há suporte para a atualização de um cluster de dados Big Data de uma versão anterior. Você deve fazer backup e excluir qualquer cluster de Big Data existente antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-upgrade.md).

- Depois de implantar o no AKS, você poderá ver os dois eventos de aviso a seguir da implantação. Esses dois eventos são problemas conhecidos, mas eles não impedem que você implante com êxito o cluster Big Data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster Big Data falhar, o namespace associado não será removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="admin-portal"></a>Portal de administração

- Quando você [cria um aplicativo usando o comando msqlctl-CTP](big-data-cluster-create-apps.md) e o implanta em um cluster SQL Server Big data, o portal de administração de cluster mostra o pods em que o aplicativo foi implantado como "desconhecido" na seção controlador da parte de administração.

#### <a name="external-tables"></a>Tabelas externas

- É possível criar uma tabela externa do pool de dados para uma tabela que tem tipos de coluna sem suporte. Se você consultar a tabela externa, receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, poderá receber um erro se o arquivo subjacente estiver sendo copiado para o HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Os endereços IP POD podem mudar no ambiente kubernetes conforme o PODs é reiniciado. No cenário em que o Pod mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com novos endereços IP.

- Se você já tiver o Jupyter instalado e um Python separado no Windows, os notebooks Spark poderão falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar no comando **Adicionar texto** , a célula de texto será adicionada no modo de visualização, e não no modo de edição. Você pode clicar no ícone de visualização para alternar para o modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se você clicar com o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente, não há nenhuma maneira de visualizar arquivos com mais de 30 MB em Azure Data Studio.

- Não há suporte para alterações de configuração no HDFS que envolvem alterações em HDFS-site. xml.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e é detectável (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestra após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Os logs do AKS podem conter a senha SA para implantações de cluster Big Data.

## <a id="ctp20"></a>CTP 2,0 (outubro de 2018)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de Big Data no SQL Server 2019 CTP 2,0.

### <a name="new-features"></a>Novos recursos

- Experiência de implantação simples usando a ferramenta de gerenciamento azdata
- Experiência de notebook nativo no Azure Data Studio
- Consultar arquivos HDFS por meio da instância de armazenamento do SQL Server
- Virtualização de dados por meio do mestre para SQL Server, Oracle, MongoDB e HDFS
- Assistente de virtualização de dados para SQL Server e Oracle no Azure Data Studio
- Serviços de ML no mestre
- Portal de administração de cluster que você pode usar para monitoramento e solução de problemas
- Envio de trabalho do Spark no Azure Data Studio 
- Interface do usuário do Spark no portal de administração do cluster
- Montagem de volume para classes de armazenamento
- Consultas sobre pools de dados do mestre
- Mostrar plano para consultas distribuídas no SSMS
- Pacote Pip para ferramenta de gerenciamento de azdata
- Mecanismo de implantação interno por meio do serviço de controlador

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir fornecem problemas conhecidos para SQL Server clusters de Big Data no CTP 2,0.

#### <a name="deployment"></a>Implantação

- Se você estiver usando o AKS (serviço de kubernetes do Azure), a versão recomendada do kubernetes será 1,10. *, que não dá suporte ao redimensionamento de disco. Você deve verificar se está dimensionando o armazenamento adequadamente no momento da implantação. Para obter mais informações sobre como ajustar os tamanhos de armazenamento, consulte o artigo [persistência de dados](concept-data-persistence.md) . Para o kubernetes implantado em VMs, a versão recomendada é 1,11.

- Depois de implantar o no AKS, você poderá ver os dois eventos de aviso a seguir da implantação. Esses dois eventos são problemas conhecidos, mas eles não impedem que você implante com êxito o cluster Big Data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster Big Data falhar, o namespace associado não será removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="external-tables"></a>Tabelas externas

- É possível criar uma tabela externa do pool de dados para uma tabela que tem tipos de coluna sem suporte. Se você consultar a tabela externa, receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, poderá receber um erro se o arquivo subjacente estiver sendo copiado para o HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Os endereços IP POD podem mudar no ambiente kubernetes conforme o PODs é reiniciado. No cenário em que o Pod mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com novos endereços IP.

- Se você já tiver o Jupyter instalado e um Python separado no Windows, os notebooks Spark poderão falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar no comando **Adicionar texto** , a célula de texto será adicionada no modo de visualização, e não no modo de edição. Você pode clicar no ícone de visualização para alternar para o modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se você clicar com o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente, não há nenhuma maneira de visualizar arquivos com mais de 30 MB em Azure Data Studio.

- Não há suporte para alterações de configuração no HDFS que envolvem alterações em HDFS-site. xml.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e é detectável (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestra após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Os logs do AKS podem conter a senha SA para implantações de cluster Big Data.

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre clusters de Big Data SQL Server, consulte [o que são SQL Server 2019 Big data clusters?](big-data-cluster-overview.md).
