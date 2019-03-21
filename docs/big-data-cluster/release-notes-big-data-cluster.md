---
title: Notas de versão
titleSuffix: SQL Server 2019 big data clusters
description: Este artigo descreve as últimas atualizações e problemas conhecidos para clusters de big data de 2019 do SQL Server (versão prévia).
author: rothja
ms.author: jroth
manager: craigg
ms.date: 03/05/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.custom: seodec18
ms.openlocfilehash: 4c178c5868789bec2dc80a4b68558f12afbc90d2
ms.sourcegitcommit: 671370ec2d49ed0159a418b9c9ac56acf43249ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58073222"
---
# <a name="release-notes-for-big-data-clusters-on-sql-server"></a>Notas de versão para clusters de grandes dados no SQL Server

Este artigo lista as atualizações e saiba que esses problemas para as versões mais recentes dos clusters de grandes dados do SQL Server.

[!INCLUDE [Limited public preview note](../includes/big-data-cluster-preview-note.md)]

## <a id="ctp23"></a> CTP 2.3 (SQL 2019)

February 2019 &nbsp; &nbsp; / &nbsp; &nbsp; SQL Server 2019 &nbsp; &nbsp; / &nbsp; &nbsp; CTP2.3

### <a name="new-features"></a>Novos recursos

| Novo recurso | Detalhes |
| :---------- | :------ |
| [Enviar trabalhos do Spark em Big Data Clusters do SQL Server no IntelliJ](spark-submit-job-intellij-tool-plugin.md). | &nbsp; |
| [CLI comuns para gerenciamento de cluster e de implantação do aplicativo](big-data-cluster-create-apps.md). | &nbsp; |
| [Extensão do VS Code para implantar aplicativos em clusters de grandes dados do SQL Server](app-deployment-extension.md). | &nbsp; |
| [Altera para o **mssqlctl** ferramenta de uso do comando](#mssqlctlctp23). | &nbsp; |
| [Usar Sparklyr no cluster de dados do SQL Server de 2019 Big](sparklyr-from-RStudio.md). | &nbsp; |
| Montar o armazenamento externo de compatível com HDFS no cluster de big data com **HDFS camadas**. | Ver [HDFS camadas](hdfs-tiering.md). |
| Nova experiência de conexão unificado para a instância mestre do SQL Server e o Gateway HDFS/Spark. | Ver [instância mestre do SQL Server e o Gateway HDFS/Spark](connect-to-big-data-cluster.md). |
| Excluir um cluster com **mssqlctl cluster delete** agora exclui somente os objetos no namespace que faziam parte do cluster de big data. | O namespace não é excluído. No entanto, em versões anteriores, esse comando exclui todo o namespace. |
| _Segurança_ nomes de ponto de extremidade foram alterados e consolidados. | _Pontos de extremidade anteriores:_<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **service-security-lb**<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **service-security-nodeport**<br/><br/>_Novo ponto de extremidade:_<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **endpoint-security** |
| _Proxy_ nomes de ponto de extremidade foram alterados e consolidados. | _Pontos de extremidade anteriores:_<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **service-proxy-lb**<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **service-proxy-nodeport**<br/><br/>_Novo ponto de extremidade:_<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **endpoint-service-proxy** |
| _Controlador_ nomes de ponto de extremidade foram alterados e consolidados. | _Pontos de extremidade anteriores:_<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **service-mssql-controller-lb**<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **service-mssql-controller-nodeport**<br/><br/>_Novo ponto de extremidade:_<br/> &nbsp; &nbsp; &nbsp; &bull; &nbsp; **endpoint-controller** |
| &nbsp; | &nbsp; |

### <a name="known-issues-deployment"></a>Problemas conhecidos: Implantação

- Não há suporte para atualizar um cluster de dados de grandes dados de uma versão anterior.

   > [!IMPORTANT]
   > Você deve fazer backup dos dados e, em seguida, exclua seu cluster de big data existente (usando a versão anterior do **mssqlctl**) antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-guidance.md#upgrade).

- O **ACCEPT_EULA** variável de ambiente deve ser "Sim" ou "Sim" para aceitar o EULA. Versões anteriores permitidas "y" e "Y", mas eles não serão mais aceitos e causarão falha na implantação.

- O **CLUSTER_PLATFORM** variáveis de ambiente não tem um padrão como fazia nas versões anteriores.

- Depois de implantar no AKS, você poderá ver os seguintes dois eventos de aviso da implantação. Os dois eventos são problemas conhecidos, mas eles não evitam que você implantar com êxito o cluster de big data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster de big data falhar, o namespace associado não é removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

### <a name="known-issues-kubeadm-deployments"></a>Problemas conhecidos: kubeadm implantações

Se você usar kubeadm implantar Kubernetes em vários computadores, o portal de administração de cluster não exibe corretamente os pontos de extremidade necessários para se conectar ao cluster de big data. Se você estiver enfrentando esse problema, use a seguinte solução alternativa para descobrir os endereços IP do ponto de extremidade de serviço:

- Se você estiver se conectando de dentro do cluster, consulte Kubernetes para o IP do serviço para o ponto de extremidade que você deseja se conectar. Por exemplo, a seguinte **kubectl** comando exibe o endereço IP de instância mestre do SQL Server:

   ```bash
   kubectl get service endpoint-master-pool -n <clusterName> -o=custom-columns="IP:.spec.clusterIP,PORT:.spec.ports[*].nodePort"
   ```

- Se você estiver se conectando de fora do cluster, use as seguintes etapas para conectar-se:

   1. Obtenha o endereço IP do nó que executa a instância mestre do SQL Server: `kubectl get pod mssql-master-pool-0 -o jsonpath="Name: {.metadata.name} Status: {.status.hostIP}" -n <clusterName>`.

   1. Conecte-se à instância mestre do SQL Server usando este endereço IP.

   1. Consulta de **cluster_endpoint_table** no banco de dados mestre para outros pontos de extremidade externos.

      Se isso falhar com um tempo limite de conexão, é possível que o respectivo nó passa pelo firewall. Nesse caso, você deve entre em contato com seu administrador de cluster do Kubernetes e peça para o IP do nó que é exposto externamente. Isso pode ser qualquer nó. Em seguida, você pode usar esse IP e a porta correspondente para se conectar a vários serviços em execução no cluster. Por exemplo, o administrador pode encontrar esse IP executando:

      ```
      [root@m12hn01 config]# kubectl cluster-info
      Kubernetes master is running at https://172.50.253.99:6443
      KubeDNS is running at https://172.30.243.91:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
      ```

### <a id="mssqlctlctp23"></a> Problemas conhecidos: mssqlctl

- O **mssqlctl** ferramenta alterado de um comando de verbo-substantivo ordenação para uma ordem de verbo-substantivo. Por exemplo, `mssqlctl create cluster` agora é `mssqlctl cluster create`.

- O `--name` parâmetro agora é necessário ao criar um cluster com `mssqlctl cluster create`.

   ```bash
   mssqlctl cluster create --name <cluster_name>
   ```

- Para obter informações importantes sobre a atualização para a versão mais recente dos clusters de big data e **mssqlctl**, consulte [atualizar para uma nova versão](deployment-guidance.md#upgrade).

### <a name="known-issues-external-tables"></a>Problemas conhecidos: Tabelas externas

- É possível criar uma tabela externa do pool de dados para uma tabela que tem sem suporte a tipos de coluna. Se você consultar a tabela externa, você receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, você poderá receber um erro se o arquivo subjacente está sendo copiado no HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

- Se você estiver criando uma tabela externa para o Oracle que usam tipos de dados de caractere, o Assistente de virtualização do Azure Data Studio interpreta essas colunas como VARCHAR na definição da tabela externa. Isso causará uma falha na DDL da tabela externa. Modifique o esquema do Oracle para usar o tipo de NVARCHAR2, ou criar instruções de tabela externa manualmente e especificar NVARCHAR em vez de usar o assistente.

### <a name="known-issues-application-deployment"></a>Problemas conhecidos: Implantação de aplicativo

- Ao chamar um aplicativo de R, Python ou MLeap da API RESTful, a chamada expirará em 5 minutos.

### <a name="known-issues-spark-and-notebooks"></a>Problemas conhecidos: Spark e notebooks

- Endereços IP de POD podem mudar no ambiente do Kubernetes como reinicializações de PODs. No cenário em que o pod de mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com o novo IP endereços.

- Se você tiver o Jupyter já instalado e um Python separado no Windows, os blocos de anotações do Spark podem falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar na **adicionar texto** de comando, a célula de texto for adicionada no modo de visualização, em vez de modo de edição. Você pode clicar no ícone de visualização para alternar para modo de edição e editar a célula.

### <a name="known-issues-hdfs"></a>Problemas conhecidos: HDFS

- Se o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente não há nenhuma maneira de visualizar arquivos maiores do que 30 MB no estúdio de dados do Azure.

- Não há suporte para alterações de configuração para o HDFS que envolvem alterações para o hdfs-site. XML.

### <a name="known-issues-security"></a>Problemas conhecidos: Segurança

- O SA_PASSWORD faz parte do ambiente e detectáveis (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestre após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Logs AKS podem conter a senha SA para implantações de cluster de big data.

## <a id="ctp22"></a> CTP 2.2 (dezembro de 2018)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de grandes dados no SQL Server de 2019 CTP 2.2.

### <a name="whats-in-the-ctp-22-release"></a>Novidades na versão CTP 2.2

- Portal de administração de cluster é acessado com `/portal` (**https://\<endereço ip\>: 30777/portal**).
- Nome do serviço mestre do pool é alterado de `service-master-pool-lb` e `service-master-pool-nodeport` para `endpoint-master-pool`.
- Nova versão do **mssqlctl** e atualizada de imagens.
- Diversas correções de bugs e melhorias.

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir fornecem os problemas conhecidos para clusters de grandes dados do SQL Server no CTP 2.2.

#### <a name="deployment"></a>Implantação

- Não há suporte para atualizar um cluster de dados de grandes dados de uma versão anterior. Você deve fazer backup e excluir qualquer cluster de big data existente antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-guidance.md#upgrade).

- Depois de implantar no AKS, você poderá ver os seguintes dois eventos de aviso da implantação. Os dois eventos são problemas conhecidos, mas eles não evitam que você implantar com êxito o cluster de big data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster de big data falhar, o namespace associado não é removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="cluster-administration-portal"></a>Portal de administração de cluster

O portal de administração de cluster não exibe o ponto de extremidade para a instância mestre do SQL Server. Para localizar o endereço IP e porta para a instância mestre, use o seguinte **kubectl** comando:

```
kubectl get svc endpoint-master-pool -n <your-cluster-name>
```

#### <a name="external-tables"></a>Tabelas externas

- É possível criar uma tabela externa do pool de dados para uma tabela que tem sem suporte a tipos de coluna. Se você consultar a tabela externa, você receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, você poderá receber um erro se o arquivo subjacente está sendo copiado no HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Endereços IP de POD podem mudar no ambiente do Kubernetes como reinicializações de PODs. No cenário em que o pod de mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com o novo IP endereços.

- Se você tiver o Jupyter já instalado e um Python separado no Windows, os blocos de anotações do Spark podem falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar na **adicionar texto** de comando, a célula de texto for adicionada no modo de visualização, em vez de modo de edição. Você pode clicar no ícone de visualização para alternar para modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente não há nenhuma maneira de visualizar arquivos maiores do que 30 MB no estúdio de dados do Azure.

- Não há suporte para alterações de configuração para o HDFS que envolvem alterações para o hdfs-site. XML.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e detectáveis (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestre após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Logs AKS podem conter a senha SA para implantações de cluster de big data.

## <a id="ctp21"></a> CTP 2.1 (novembro de 2018)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de grandes dados no SQL Server de 2019 CTP 2.1.

### <a name="whats-in-the-ctp-21-release"></a>Novidades na versão CTP 2.1

- [Implantar aplicativos de Python e R](big-data-cluster-create-apps.md) em um cluster de big data.
- Nova versão do **mssqlctl** e atualizada de imagens. 
- Diversas correções de bugs e melhorias.

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir fornecem os problemas conhecidos para clusters de grandes dados do SQL Server no CTP 2.1.

#### <a name="deployment"></a>Implantação

- Não há suporte para atualizar um cluster de dados de grandes dados de uma versão anterior. Você deve fazer backup e excluir qualquer cluster de big data existente antes de implantar a versão mais recente. Para obter mais informações, consulte [atualizar para uma nova versão](deployment-guidance.md#upgrade).

- Depois de implantar no AKS, você poderá ver os seguintes dois eventos de aviso da implantação. Os dois eventos são problemas conhecidos, mas eles não evitam que você implantar com êxito o cluster de big data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster de big data falhar, o namespace associado não é removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="admin-portal"></a>Portal de administração

- Quando você [criar um aplicativo usando o comando msqlctl ctp](big-data-cluster-create-apps.md) e implantá-lo em um cluster de big data, o Portal de administração de Cluster mostra os pods em que o aplicativo foi implantado como "Desconhecido" na seção de controlador da parte do administrador do SQL Server.

#### <a name="external-tables"></a>Tabelas externas

- É possível criar uma tabela externa do pool de dados para uma tabela que tem sem suporte a tipos de coluna. Se você consultar a tabela externa, você receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, você poderá receber um erro se o arquivo subjacente está sendo copiado no HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Endereços IP de POD podem mudar no ambiente do Kubernetes como reinicializações de PODs. No cenário em que o pod de mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com o novo IP endereços.

- Se você tiver o Jupyter já instalado e um Python separado no Windows, os blocos de anotações do Spark podem falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar na **adicionar texto** de comando, a célula de texto for adicionada no modo de visualização, em vez de modo de edição. Você pode clicar no ícone de visualização para alternar para modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente não há nenhuma maneira de visualizar arquivos maiores do que 30 MB no estúdio de dados do Azure.

- Não há suporte para alterações de configuração para o HDFS que envolvem alterações para o hdfs-site. XML.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e detectáveis (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestre após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Logs AKS podem conter a senha SA para implantações de cluster de big data.

## <a id="ctp20"></a> CTP 2.0 (outubro de 2018)

As seções a seguir descrevem os novos recursos e problemas conhecidos para clusters de grandes dados no SQL Server de 2019 CTP 2.0.

### <a name="whats-in-the-ctp-20-release"></a>Novidades na versão CTP 2.0

- Experiência de implantação simples usando a ferramenta de gerenciamento mssqlctl
- Experiência de notebook nativo no estúdio de dados do Azure
- Arquivos HDFS de consulta por meio do armazenamento de instância do SQL Server
- Virtualização de dados por meio do mestre do SQL Server, Oracle, MongoDB e HDFS
- Assistente de virtualização de dados do SQL Server e Oracle no estúdio de dados do Azure
- Serviços de ML no mestre
- Portal de administração de cluster que você pode usar para monitoramento e solução de problemas
- Envio de trabalho do Spark no estúdio de dados do Azure 
- Interface do usuário do Spark no portal de administração do cluster
- Volume de montagem para classes de armazenamento
- Consultas em pools de dados do mestre
- Mostrar plano para consultas distribuídas no SSMS
- Pacote de PIP para a ferramenta de gerenciamento mssqlctl
- Mecanismo de implantação interna por meio do serviço de controlador

### <a name="known-issues"></a>Problemas conhecidos

As seções a seguir fornecem os problemas conhecidos para clusters de grandes dados do SQL Server no CTP 2.0.

#### <a name="deployment"></a>Implantação

- Se você estiver usando o serviço de Kubernetes do Azure (AKS), a versão recomendada do Kubernetes é 1.10. *, que não oferece suporte a redimensionamento de disco. Você deve verificar se você está dimensionando o armazenamento de forma adequada no momento da implantação. Para obter mais informações sobre como ajustar os tamanhos de armazenamento, consulte o [persistência de dados](concept-data-persistence.md) artigo. Para o Kubernetes implantado em VMs, a versão recomendada é 1.11.

- Depois de implantar no AKS, você poderá ver os seguintes dois eventos de aviso da implantação. Os dois eventos são problemas conhecidos, mas eles não evitam que você implantar com êxito o cluster de big data no AKS.

   `Warning  FailedMount: Unable to mount volumes for pod "mssql-storage-pool-default-1_sqlarisaksclus(c83eae70-c81b-11e8-930f-f6b6baeb7348)": timeout expired waiting for volumes to attach or mount for pod "sqlarisaksclus"/"mssql-storage-pool-default-1". list of unmounted volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs]. list of unattached volumes=[storage-pool-storage hdfs storage-pool-mlservices-storage hadoop-logs storage-pool-java-storage secrets default-token-q9mlx]`

   `Warning  Unhealthy: Readiness probe failed: cat: /tmp/provisioner.done: No such file or directory`

- Se uma implantação de cluster de big data falhar, o namespace associado não é removido. Isso pode resultar em um namespace órfão no cluster. Uma solução alternativa é excluir o namespace manualmente antes de implantar um cluster com o mesmo nome.

#### <a name="external-tables"></a>Tabelas externas

- É possível criar uma tabela externa do pool de dados para uma tabela que tem sem suporte a tipos de coluna. Se você consultar a tabela externa, você receberá uma mensagem semelhante à seguinte:

   `Msg 7320, Level 16, State 110, Line 44 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 105079; Columns with large object types are not supported for external generic tables.`

- Se você consultar uma tabela externa do pool de armazenamento, você poderá receber um erro se o arquivo subjacente está sendo copiado no HDFS ao mesmo tempo.

   `Msg 7320, Level 16, State 110, Line 157 Cannot execute the query "Remote Query" against OLE DB provider "SQLNCLI11" for linked server "(null)". 110806;A distributed query failed: One or more errors occurred.`

#### <a name="spark-and-notebooks"></a>Spark e notebooks

- Endereços IP de POD podem mudar no ambiente do Kubernetes como reinicializações de PODs. No cenário em que o pod de mestre é reiniciado, a sessão do Spark pode falhar com `NoRoteToHostException`. Isso é causado por caches JVM que não são atualizados com o novo IP endereços.

- Se você tiver o Jupyter já instalado e um Python separado no Windows, os blocos de anotações do Spark podem falhar. Para contornar esse problema, atualize o Jupyter para a versão mais recente.

- Em um bloco de anotações, se você clicar na **adicionar texto** de comando, a célula de texto for adicionada no modo de visualização, em vez de modo de edição. Você pode clicar no ícone de visualização para alternar para modo de edição e editar a célula.

#### <a name="hdfs"></a>HDFS

- Se o botão direito do mouse em um arquivo no HDFS para visualizá-lo, você poderá ver o seguinte erro:

   `Error previewing file: File exceeds max size of 30MB`

   Atualmente não há nenhuma maneira de visualizar arquivos maiores do que 30 MB no estúdio de dados do Azure.

- Não há suporte para alterações de configuração para o HDFS que envolvem alterações para o hdfs-site. XML.

#### <a name="security"></a>Segurança

- O SA_PASSWORD faz parte do ambiente e detectáveis (por exemplo, em um arquivo de despejo de cabo). Você deve redefinir o SA_PASSWORD na instância mestre após a implantação. Isso não é um bug, mas uma etapa de segurança. Para obter mais informações sobre como alterar o SA_PASSWORD em um contêiner do Linux, consulte [alterar a senha SA](../linux/quickstart-install-connect-docker.md#sapassword).

- Logs AKS podem conter a senha SA para implantações de cluster de big data.

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre clusters de grandes dados do SQL Server, consulte [quais são os clusters do SQL Server 2019 big data?](big-data-cluster-overview.md).