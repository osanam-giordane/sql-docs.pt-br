---
title: TYPE_ID (Transact-SQL) | Microsoft Docs
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
- TYPE_ID
- TYPE_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- IDs [SQL Server], types
- TYPE_ID function
- type IDs [SQL Server]
- data types [SQL Server], IDs
ms.assetid: 647d17ef-b878-4922-b446-56642322ebad
caps.latest.revision: 42
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a90c27d9d5d599a607306641958c1dcbc94aec79
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="typeid-transact-sql"></a>TYPE_ID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retorna o ID de um nome de tipo de dados especificado.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
TYPE_ID ( [ schema_name ] type_name )   
```  
  
## <a name="arguments"></a>Argumentos  
 *type_name*  
 É o nome do tipo de dados. *type_name* é do tipo **nvarchar**. *type_name* pode ser um sistema ou definido pelo usuário tipo.  
  
## <a name="return-types"></a>Tipos de retorno  
 **int**  
  
## <a name="exceptions"></a>Exceções  
 Retornará NULL em caso de erro ou se um chamador não tiver permissão para exibir o objeto.  
  
 No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], um usuário só pode exibir os metadados de itens protegíveis de sua propriedade ou para os quais ele tenha permissão concedida. Isso significa que as funções internas que emitem metadados, como TYPE_ID, poderão retornar NULL se o usuário não tiver nenhuma permissão para o objeto. Para obter mais informações, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="remarks"></a>Comentários  
 TYPE_ID retorna NULL se o nome do tipo não for válido ou se o chamador não tiver permissão suficiente para fazer referência ao tipo.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-looking-up-the-type-id-values-for-single--and-two-part-type-names"></a>A. Pesquisando os valores TYPE ID para nomes de tipo de uma e duas partes  
 O exemplo a seguir retorna o ID do tipo para nomes de tipo de uma e duas partes.  
  
```  
USE tempdb;  
GO  
CREATE TYPE NewType FROM int;  
GO  
CREATE SCHEMA NewSchema;  
GO  
CREATE TYPE NewSchema.NewType FROM int;  
GO  
SELECT TYPE_ID('NewType') AS [1 Part Data Type ID],  
       TYPE_ID('NewSchema.NewType') AS [2 Part Data Type ID];  
GO  
```  
  
### <a name="b-looking-up-the-type-id-of-a-system-data-type"></a>B. Pesquisando o TYPE ID de um tipo de dados de sistema  
 O exemplo a seguir retorna o `TYPE ID` do tipo de dados de sistema `datetime`.  
  
```  
SELECT TYPE_NAME(TYPE_ID('datetime')) AS [TYPE_NAME]  
    ,TYPE_ID('datetime') AS [TYPE_ID];  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="c-looking-up-the-type-id-of-a-system-data-type"></a>C: consultando a ID de tipo de um tipo de dados do sistema  
 O exemplo a seguir retorna o `TYPE ID` do tipo de dados de sistema `datetime`.  
  
```  
SELECT TYPE_NAME(TYPE_ID('datetime')) AS typeName,   
    TYPE_ID('datetime') AS typeID FROM table1;  
```  
  
## <a name="see-also"></a>Consulte também  
 [TYPE_NAME &#40; Transact-SQL &#41;](../../t-sql/functions/type-name-transact-sql.md)   
 [TYPEPROPERTY &#40; Transact-SQL &#41;](../../t-sql/functions/typeproperty-transact-sql.md)   
 [sys.types &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-types-transact-sql.md)   
 [Funções de metadados &#40; Transact-SQL &#41;](../../t-sql/functions/metadata-functions-transact-sql.md)  
  
  

