---
title: COMPRESS (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 10/11/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- COMPRESS
- COMPRESS_TSQL
helpviewer_keywords:
- COMPRESS function
ms.assetid: c2bfe9b8-57a4-48b4-b028-e1a3ed5ece88
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6fd94c5062e0f268e902c69c154834430bf9e6f4
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67943128"
---
# <a name="compress-transact-sql"></a>COMPRESS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-asdw-xxx-md.md)]

Esta função compacta a expressão de entrada usando o algoritmo GZIP. A função retorna uma matriz de bytes do tipo **varbinary(max)** .
  
![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Sintaxe  
  
```sql
COMPRESS ( expression )  
```  
  
## <a name="arguments"></a>Argumentos  
*expressão*  
Um

* **binary(***n***)**
* **char(***n***)**
* **nchar(***n***)**
* **nvarchar(max)**
* **nvarchar(***n***)**
* **varbinary(max)**
* **varbinary(***n***)**
* **varchar(max)**

ou em

* **varchar(***n***)**

expressão. Para saber mais, veja [Expressões &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md).
  
## <a name="return-types"></a>Tipos de retorno
**varbinary(max)** representa o conteúdo compactado da entrada.
  
## <a name="remarks"></a>Remarks  
Dados compactados não podem ser indexados.
  
A função `COMPRESS` compacta os dados de expressão de entrada. É necessário invocar essa função para cada seção de dados a ser compactada. Veja [Compactação de dados](../../relational-databases/data-compression/data-compression.md) para saber mais sobre a compactação de dados automática durante o armazenamento no nível de linha ou página.
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-compress-data-during-the-table-insert"></a>A. Compactar dados durante a inserção de tabela  
O seguinte exemplo mostra como compactar dados inseridos em uma tabela:
  
```sql
INSERT INTO player (name, surname, info )  
VALUES (N'Ovidiu', N'Cracium',   
        COMPRESS(N'{"sport":"Tennis","age": 28,"rank":1,"points":15258, turn":17}'));  
  
INSERT INTO player (name, surname, info )  
VALUES (N'Michael', N'Raheem', compress(@info));  
```  
  
### <a name="b-archive-compressed-version-of-deleted-rows"></a>B. Arquivar a versão compactada de linhas excluídas  
Primeiro, essa instrução exclui registros antigos do player da tabela `player`. Para economizar espaço, em seguida, armazena os registros na tabela `inactivePlayer`, em um formato compactado.
  
```sql
DELETE FROM player  
OUTPUT deleted.id, deleted.name, deleted.surname, deleted.datemodifier, COMPRESS(deleted.info)   
INTO dbo.inactivePlayers
WHERE datemodified < @startOfYear; 
```  
  
## <a name="see-also"></a>Confira também
[Funções de cadeia de caracteres &#40;Transact-SQL&#41;](../../t-sql/functions/string-functions-transact-sql.md)  
[DECOMPRESS &#40;Transact-SQL&#41;](../../t-sql/functions/decompress-transact-sql.md)
  
  
