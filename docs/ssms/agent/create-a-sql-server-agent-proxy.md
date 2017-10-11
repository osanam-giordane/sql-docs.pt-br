---
title: Criar um proxy do SQL Server Agent | Microsoft Docs
ms.custom: 
ms.date: 05/04/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- proxies [SQL Server Agent], creating
ms.assetid: 142e0c55-a8b9-4669-be49-b9dc602d5988
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: ceddddafe0c052d0477e218955949012818e9a73
ms.openlocfilehash: 2853583d3902f9b0da32e2b0e1c5a55b696d34e0
ms.contentlocale: pt-br
ms.lasthandoff: 07/31/2017

---
# <a name="create-a-sql-server-agent-proxy"></a>Criar um proxy do SQL Server Agent
Este tópico descreve como criar um proxy do SQL Server Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] ou o [!INCLUDE[tsql](../../includes/tsql_md.md)].  
  
Uma conta proxy do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent define o contexto de segurança no qual uma etapa de trabalho pode ser executada. Cada proxy corresponde a uma credencial de segurança. Para definir as permissões para uma etapa de trabalho em particular, crie um proxy com as permissões necessárias para um subsistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent e atribua-o à etapa de trabalho.  
  
**Neste tópico**  
  
-   **Antes de começar:**  
  
    [Limitações e restrições](#Restrictions)  
  
    [Segurança](#Security)  
  
-   **Para criar um proxy do SQL Server Agent usando:**  
  
    [SQL Server Management Studio](#SSMSProcedure)  
  
    [Transact-SQL](#TsqlProcedure)  
  
## <a name="BeforeYouBegin"></a>Antes de começar  
  
### <a name="Restrictions"></a>Limitações e restrições  
  
-   Primeiro, é necessário criar uma credencial antes de criar um proxy, caso não haja nenhuma disponível.  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent usam credenciais para armazenar informações sobre as contas de usuário do Windows. O usuário especificado na credencial deve ter permissão para “Acessar esse computador pela rede” (SeNetworkLogonRight) no computador em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] está sendo executado.  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent verifica o acesso a subsistemas de um proxy e fornece acesso ao proxy sempre que a etapa de trabalho é executada. Se o proxy já não tiver acesso ao subsistema, a etapa de trabalho falhará. Caso contrário, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent representará o usuário especificado no proxy e executará a etapa de trabalho.  
  
-   A criação de um proxy não altera as permissões do usuário especificado na credencial do proxy. Por exemplo, você pode criar um proxy para um usuário que não tem permissão de se conectar a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Nesse caso, as etapas de trabalho que usarem esse proxy não conseguirão se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].  
  
-   Se o logon do usuário tiver acesso ao proxy ou se o usuário pertencer a alguma função com acesso ao proxy, ele poderá utilizá-lo em uma etapa de trabalho.  
  
### <a name="Security"></a>Segurança  
  
#### <a name="Permissions"></a>Permissões  
  
-   Apenas membros da função de servidor fixa **sysadmin** têm permissão para criar, modificar ou excluir contas proxy. Usuários que não sejam membros da função de servidor fixa **sysadmin** devem ser adicionados a uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent no banco de dados **msdb** para poderem usar proxies: **SQLAgentUserRole**, **SQLAgentReaderRole**ou **SQLAgentOperatorRole**.  
  
-   Requer a permissão **ALTER ANY CREDENTIAL** para criar uma credencial além do proxy.  
  
## <a name="SSMSProcedure"></a>Usando o SQL Server Management Studio  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a>Para criar um proxy do SQL Server Agent  
  
1.  No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja criar um proxy no SQL Server Agent.  
  
2.  Clique no sinal de adição para expandir o **SQL Server Agent**.  
  
3.  Clique com o botão direito do mouse na pasta **Proxies** e selecione **Novo Proxy**.  
  
4.  Na caixa de diálogo **Nova Conta Proxy** , na página **Geral** , digite o nome da nova conta proxy na caixa **Nome do proxy** .  
  
5.  Na caixa de diálogo **Nome da credencial** , digite o nome da credencial de segurança que a conta proxy usará.  
  
6.  Na caixa **Descrição** , digite uma descrição da conta proxy.  
  
7.  Em **Ativo nos seguintes subsistemas**, selecione o subsistema ou os subsistemas apropriados para esse proxy.  
  
8.  Na página **Entidades** , adicione ou remova logons ou funções para conceder ou remover acesso à conta proxy.  
  
9. Quando terminar, clique em **OK**.  
  
## <a name="TsqlProcedure"></a>Usando Transact-SQL  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a>Para criar um proxy do SQL Server Agent  
  
1.  No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  Na barra Padrão, clique em **Nova Consulta**.  
  
3.  Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.  
  
    ```  
    -- creates credential CatalogApplicationCredential  
    USE msdb ;  
    GO  
    CREATE CREDENTIAL CatalogApplicationCredential WITH IDENTITY = 'REDMOND/TestUser',   
        SECRET = 'G3$1o)lkJ8HNd!';  
    GO  
    -- creates proxy "Catalog application proxy" and assigns
    -- the credential 'CatalogApplicationCredential' to it.  
    EXEC dbo.sp_add_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 1,  
        @description = 'Maintenance tasks on catalog application.',  
        @credential_name = 'CatalogApplicationCredential' ;  
    GO  
    -- grants the proxy "Catalog application proxy" access to 
    -- the ActiveX Scripting subsystem.  
    EXEC dbo.sp_grant_proxy_to_subsystem  
        @proxy_name = N'Catalog application proxy',  
        @subsystem_id = 2 ;  
    GO  
    ```  
  
Para obter mais informações, consulte:  
  
-   [CREATE CREDENTIAL (Transact-SQL)](http://msdn.microsoft.com/en-us/d5e9ae69-41d9-4e46-b13d-404b88a32d9d)  
  
-   [sp_add_proxy (Transact-SQL)](http://msdn.microsoft.com/en-us/cb59df37-f103-439b-bec1-2871fb669a8b)  
  
-   [sp_grant_proxy_to_subsystem (Transact-SQL)](http://msdn.microsoft.com/en-us/866aaa27-a1e0-453a-9b1b-af39431ad9c2)  
  
