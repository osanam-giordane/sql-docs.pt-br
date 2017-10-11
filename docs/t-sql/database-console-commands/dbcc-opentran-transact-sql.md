---
title: DBCC OPENTRAN (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DBCC_OPENTRAN_TSQL
- DBCC OPENTRAN
- OPENTRAN_TSQL
- OPENTRAN
dev_langs:
- TSQL
helpviewer_keywords:
- status information [SQL Server], transactions
- transactions [SQL Server], status information
- DBCC OPENTRAN statement
- open transactions
- displaying transaction information
- checking open transactions
- oldest transactions [SQL Server]
ms.assetid: 63163843-226f-42d3-9e2c-b634fbf06943
caps.latest.revision: 40
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f3d3b47d9bc553edd49f6f401d1a1c7a857d0a7d
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-opentran-transact-sql"></a>DBCC OPENTRAN (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

DBCC OPENTRAN ajuda a identificar as transações ativas que podem impedir o truncamento do log. DBCC OPENTRAN exibe informações sobre a transação ativa mais antiga e sobre as transações replicadas distribuídas e não distribuídas mais antigas, se houver, dentro do log de transação do banco de dados especificado. Os resultados serão exibidos somente se houver uma transação ativa que existe no log ou se o banco de dados contiver informações de replicação. Uma mensagem informativa será exibida se não houver transações ativas no log.
  
> [!NOTE]  
>  DBCC OPENTRAN não tem suporte em Publicadores que não sejam do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Sintaxe  
  
```sql
DBCC OPENTRAN   
[   
    ( [ database_name | database_id | 0 ] ) ]  
    { [ WITH TABLERESULTS ]  
      [ , [ NO_INFOMSGS ] ]  
    }  
]   
```  
  
## <a name="arguments"></a>Argumentos  
 *Database_Name* | *database_id*| 0  
 É o nome ou a ID do banco de dados para o qual exibir as informações de transação mais antigas. Se não for especificado ou se 0 for especificado, o banco de dados atual será usado. Nomes de banco de dados devem estar em conformidade com as regras de [identificadores](../../relational-databases/databases/database-identifiers.md).  
  
 TABLERESULTS  
 Especifica os resultados em um formato de tabela que pode ser carregado em uma tabela. Use essa opção para criar uma tabela de resultados que possa ser inserida em uma tabela para comparações. Quando essa opção não é especificada, os resultados são formatados para leitura.  
  
 NO_INFOMSGS  
 Suprime todas as mensagens informativas.  
  
## <a name="remarks"></a>Comentários  
Use DBCC OPENTRAN para determinar se uma transação aberta existe no log de transações. Quando você usa a instrução BACKUP LOG, só a parte inativa do log pode ser truncada; uma transação aberta pode impedir que o log seja truncado completamente. Para identificar uma transação aberta, use sp_who para obter a ID de processo do sistema.
  
## <a name="result-sets"></a>Conjuntos de resultados  
DBCC OPENTRAN retorna o seguinte conjunto de resultados quando não há transações abertas:
  
```sql
No active open transactions.  
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
```  
  
## <a name="permissions"></a>Permissões  
Exige associação à função de servidor fixa **sysadmin** ou à função de banco de dados fixa **db_owner** .
  
## <a name="examples"></a>Exemplos  
### <a name="a-returning-the-oldest-active-transaction"></a>A. Retornando a transação ativa mais antiga  
O exemplo a seguir obtém informações de transação para o banco de dados atual. Os resultados podem variar.
  
```sql  
CREATE TABLE T1(Col1 int, Col2 char(3));  
GO  
BEGIN TRAN  
INSERT INTO T1 VALUES (101, 'abc');  
GO  
DBCC OPENTRAN;  
ROLLBACK TRAN;  
GO  
DROP TABLE T1;  
GO  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```
Transaction information for database 'master'.
Oldest active transaction:
SPID (server process ID) : 52
UID (user ID) : -1
Name          : user_transaction
LSN           : (518:1576:1)
Start time    : Jun  1 2004  3:30:07:197PM
SID           : 0x010500000000000515000000a065cf7e784b9b5fe77c87709e611500
DBCC execution completed. If DBCC printed error messages, contact your system administrator.
```
  
> [!NOTE]  
>  O resultado "UID (ID do usuário)" não faz sentido e será removido em uma versão futura do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
### <a name="b-specifying-the-with-tableresults-option"></a>B. Especificando a opção WITH TABLERESULTS  
O exemplo a seguir carrega os resultados do comando DBCC OPENTRAN como uma tabela temporária.
  
```sql  
-- Create the temporary table to accept the results.  
CREATE TABLE #OpenTranStatus (  
   ActiveTransaction varchar(25),  
   Details sql_variant   
   );  
-- Execute the command, putting the results in the table.  
INSERT INTO #OpenTranStatus   
   EXEC ('DBCC OPENTRAN WITH TABLERESULTS, NO_INFOMSGS');  
  
-- Display the results.  
SELECT * FROM #OpenTranStatus;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
[BEGIN TRANSACTION &#40;Transact-SQL&#41;](../../t-sql/language-elements/begin-transaction-transact-sql.md)  
[CONFIRMAR transação &#40; Transact-SQL &#41;](../../t-sql/language-elements/commit-transaction-transact-sql.md)  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[DB_ID &#40; Transact-SQL &#41;](../../t-sql/functions/db-id-transact-sql.md)  
[ROLLBACK TRANSACTION &#40; Transact-SQL &#41;](../../t-sql/language-elements/rollback-transaction-transact-sql.md)
  
  
