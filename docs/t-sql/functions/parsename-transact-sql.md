---
title: PARSENAME (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- PARSENAME_TSQL
- PARSENAME
dev_langs:
- TSQL
helpviewer_keywords:
- PARSENAME function
- parsing [SQL Server], PARSENAME function
- names [SQL Server], objects
- objects [SQL Server], names
- part of object names [SQL Server]
ms.assetid: abf34f99-9ee9-460b-85b2-930ca5c4b5ae
caps.latest.revision: 38
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 63065dcee0d1f7784e7be396273785f741ef44c7
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="parsename-transact-sql"></a>PARSENAME (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all_md](../../includes/tsql-appliesto-ss2012-all-md.md)]

  Retorna a parte especificada de um nome de objeto. As partes de um objeto que podem ser recuperadas são o nome do objeto, o nome do proprietário, o nome do banco de dados e o nome do servidor.  
  
> [!NOTE]  
>  A função PARSENAME não indica se existe um objeto pelo nome especificado. PARSENAME apenas retorna a parte especificada do nome de objeto especificado.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
PARSENAME ( 'object_name' , object_piece )   
```  
  
## <a name="arguments"></a>Argumentos  
 '*object_name*'  
 É o nome do objeto para o qual a parte de objeto especificada deve ser recuperada. *object_name* é **sysname**. Este parâmetro é um nome de objeto opcionalmente qualificado. Se todas as partes do nome do objeto forem qualificadas, esse nome poderá ter quatro partes: o nome do servidor, o nome do banco de dados, o nome do proprietário e o nome do objeto.  
  
 *object_piece*  
 É a parte do objeto a ser retornada. *object_piece* é do tipo **int**e pode ter estes valores:  
  
 1 = Nome do objeto  
  
 2 = Nome do esquema  
  
 3 = Nome do banco de dados  
  
 4 = Nome do servidor  
  
## <a name="return-types"></a>Tipos de retorno  
 **nchar**  
  
## <a name="remarks"></a>Comentários  
 PARSENAME retornará o NULL se uma das seguintes condições for verdadeira:  
  
-   O *object_name* ou *object_piece* é NULL.  
  
-   Um erro de sintaxe ocorre.  
  
 A parte do objeto solicitado tem um comprimento de 0 e não é válido [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identificador. Um nome de objeto de comprimento zero processa o nome qualificado completo como não válido.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir usa `PARSENAME` para retornar informações sobre a tabela `Person` no banco de dados `AdventureWorks2012`.  
  
```  
USE AdventureWorks2012;  
SELECT PARSENAME('AdventureWorks2012..Person', 1) AS 'Object Name';  
SELECT PARSENAME('AdventureWorks2012..Person', 2) AS 'Schema Name';  
SELECT PARSENAME('AdventureWorks2012..Person', 3) AS 'Database Name';  
SELECT PARSENAME('AdventureWorks2012..Person', 4) AS 'Server Name';  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```
Object Name
------------------------------
Person

(1 row(s) affected)

Schema Name
------------------------------
(null)

(1 row(s) affected)

Database Name
------------------------------
AdventureWorks2012

(1 row(s) affected)

Server Name
------------------------------
(null)

(1 row(s) affected)
 ```
 
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 O exemplo a seguir usa `PARSENAME` para retornar informações sobre a tabela `Person` no banco de dados `AdventureWorks2012`.  
  
```  
-- Uses AdventureWorks  
  
SELECT PARSENAME('AdventureWorksPDW2012.dbo.DimCustomer', 1) AS 'Object Name';  
SELECT PARSENAME('AdventureWorksPDW2012.dbo.DimCustomer', 2) AS 'Schema Name';  
SELECT PARSENAME('AdventureWorksPDW2012.dbo.DimCustomer', 3) AS 'Database Name';  
SELECT PARSENAME('AdventureWorksPDW2012.dbo.DimCustomer', 4) AS 'Server Name';  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
```
Object Name
------------------------------
DimCustomer

(1 row(s) affected)

Schema Name
------------------------------
dbo

(1 row(s) affected)

Database Name
------------------------------
AdventureWorksPDW2012

(1 row(s) affected)

Server Name
------------------------------
(null)

(1 row(s) affected)
```
  
## <a name="see-also"></a>Consulte também  
 [ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)   
 [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)   
 [Funções do sistema &#40; Transact-SQL &#41;](../../relational-databases/system-functions/system-functions-for-transact-sql.md)  
  
  

