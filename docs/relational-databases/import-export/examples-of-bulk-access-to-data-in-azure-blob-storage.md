---
title: Exemplos de acesso em massa a dados no Armazenamento de Blobs do Azure | Microsoft Docs
ms.custom: 
ms.date: 01/04/2017
ms.prod: sql-server-2017
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bulk importing [SQL Server], from Azure blob storage
- Azure blob storage, bulk import to SQL Server
- BULK INSERT, Azure blob storage
- OPENROWSET, Azure blob storage
ms.assetid: f7d85db3-7a93-400e-87af-f56247319ecd
caps.latest.revision: 2
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 6e754198cf82a7ba0752fe8f20c3780a8ac551d7
ms.openlocfilehash: ece80f578fc797dcd721dfb3f831e9bf3937abd1
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2017

---
# <a name="examples-of-bulk-access-to-data-in-azure-blob-storage"></a>Exemplos de acesso em massa a dados no Armazenamento de Blobs do Azure
[!INCLUDE[tsql-appliesto-ssvNxt-xxxx-xxxx-xxx](../../includes/tsql-appliesto-ssvnxt-xxxx-xxxx-xxx.md)]

As instruções `BULK INSERT` e `OPENROWSET` podem acessar diretamente um arquivo no armazenamento de blobs do Azure. Os exemplos a seguir usam dados de um arquivo CSV (valores separados por vírgula) (denominado `inv-2017-01-19.csv`), armazenado em um contêiner (chamado `Week3`), armazenado em uma conta de armazenamento (chamada `newinvoices`). O caminho para o arquivo de formato pode ser usado, mas não está incluído nesses exemplos. 

O acesso em massa para o armazenamento de blobs do Azure do SQL Server requer, no mínimo, [!INCLUDE[ssSQLv14_md](../../includes/sssqlv14-md.md)] CTP 1.1.

## <a name="create-the-credential"></a>Criar credencial   
   
Todos os exemplos a seguir exigem uma credencial com escopo de banco de dados fazendo referência a uma assinatura de acesso compartilhado.   

>  [!IMPORTANT]
>  A fonte de dados externa deve ser criada com uma credencial com escopo de banco de dados que usa a identidade `SHARED ACCESS SIGNATURE`. Para criar uma assinatura de acesso compartilhado para sua conta de armazenamento, consulte a propriedade **Assinatura de acesso compartilhado** na página de propriedades da conta de armazenamento, no portal do Azure. Para mais informações sobre assinaturas de acesso compartilhado, consulte [Usando SAS (Assinatura de Acesso Compartilhado)](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1). Para mais informações, consulte [CRIAR CREDENCIAL COM ESCOPO DE BANCO DE DADOS](../../t-sql/statements/create-database-scoped-credential-transact-sql.md).  
 
Crie uma credencial com escopo de banco de dados usando o `IDENTITY`, que deve ser `SHARED ACCESS SIGNATURE`. Use o segredo do portal do Azure. Por exemplo:  

```tsql
CREATE DATABASE SCOPED CREDENTIAL UploadInvoices  
WITH IDENTITY = 'SHARED ACCESS SIGNATURE',
SECRET = 'QLYMgmSXMklt%2FI1U6DcVrQixnlU5Sgbtk1qDRakUBGs%3D';
```


## <a name="accessing-data-in-a-csv-file-referencing-an-azure-blob-storage-location"></a>Acessando dados em um arquivo CSV que referencia um local de armazenamento de blobs do Azure   
O exemplo a seguir usa uma fonte de dados externa apontando para uma conta de armazenamento do Azure, denominada `newinvoices`.   
```tsql
CREATE EXTERNAL DATA SOURCE MyAzureInvoices
    WITH  (
        TYPE = BLOB_STORAGE,
        LOCATION = 'https://newinvoices.blob.core.windows.net', 
        CREDENTIAL = UploadInvoices  
    );
```   

A instrução `OPENROWSET` adiciona o nome do contêiner (`week3`) à descrição do arquivo. O arquivo é denominado `inv-2017-01-19.csv`.
```tsql     
SELECT * FROM OPENROWSET(
   BULK  'week3/inv-2017-01-19.csv',
   DATA_SOURCE = 'MyAzureInvoices',
   SINGLE_CLOB) AS DataFile;
```

Usando `BULK INSERT`, use o contêiner e a descrição do arquivo:

```tsql
BULK INSERT Colors2
FROM 'week3/inv-2017-01-19.csv'
WITH (DATA_SOURCE = 'MyAzureInvoices',
      FORMAT = 'CSV'); 
```

## <a name="accessing-data-in-a-csv-file-referencing-a-container-in-an-azure-blob-storage-location"></a>Acessando dados em um arquivo CSV que referencia um contêiner em um local de armazenamento de blobs do Azure   

O exemplo a seguir usa uma fonte de dados externa apontando para um contêiner (denominado `week3`) em uma conta de armazenamento do Azure.   
```tsql
CREATE EXTERNAL DATA SOURCE MyAzureInvoicesContainer
    WITH  (
        TYPE = BLOB_STORAGE,
        LOCATION = 'https://newinvoices.blob.core.windows.net/week3', 
        CREDENTIAL = UploadInvoices  
    );
```  
  
A instrução `OPENROWSET` não adiciona o nome do contêiner à descrição do arquivo:
```tsql
SELECT * FROM OPENROWSET(
   BULK  'inv-2017-01-19.csv',
   DATA_SOURCE = 'MyAzureInvoicesContainer',
   SINGLE_CLOB) AS DataFile;
```   

Usando `BULK INSERT`, não use o nome do contêiner na descrição do arquivo: 

```tsql
BULK INSERT Colors2
FROM 'inv-2017-01-19.csv'
WITH (DATA_SOURCE = 'MyAzureInvoicesContainer',
      FORMAT = 'CSV'); 
```

## <a name="see-also"></a>Consulte também   

[CRIAR UMA CREDENCIAL COM ESCOPO DE BANCO DE DADOS](../../t-sql/statements/create-database-scoped-credential-transact-sql.md)   
[CRIAR UMA FONTE DE DADOS EXTERNA](../../t-sql/statements/create-external-data-source-transact-sql.md)   
[INSERÇÃO EM MASSA](../../t-sql/statements/bulk-insert-transact-sql.md)   
[OPENROWSET](../../t-sql/functions/openrowset-transact-sql.md)   

