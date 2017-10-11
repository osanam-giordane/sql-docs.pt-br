---
title: Como FOR JSON converte tipos de dados do SQL Server para tipos de dados JSON (SQL Server) | Microsoft Docs
ms.custom:
- SQL2016_New_Updated
ms.date: 07/07/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-json
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FOR JSON, data type conversion
ms.assetid: da356f06-efd0-4ea3-8157-77395bf790d7
caps.latest.revision: 11
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 9045ebe77cf2f60fecad22672f3f055d8c5fdff2
ms.openlocfilehash: d866cc385b2c44d4594f4d4f8249df6f84ac48f2
ms.contentlocale: pt-br
ms.lasthandoff: 07/31/2017

---
# <a name="how-for-json-converts-sql-server-data-types-to-json-data-types-sql-server"></a>Como FOR JSON converte tipos de dados do SQL Server para tipos de dados JSON (SQL Server)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  A cláusula **FOR JSON** usa as regras a seguir para converter os tipos de dados do SQL Server em tipos JSON na saída JSON.  
  
|Categoria|Tipo de dados do SQL Server|Tipo de dados JSON|  
|--------------|--------------|---------------|  
|Tipos de cadeia de caracteres e caracteres|char, nchar, varchar, nvarchar|cadeia de caracteres|  
|Tipos numéricos|int, bigint, float, decimal, numeric|number|  
|Tipo de Bit|bit|Booliano (verdadeiro ou falso)|  
|Tipos de data e hora|date, datetime, datetime2, time, datetimeoffset|cadeia de caracteres|  
|Tipos binários|varbinary, binary, image, timestamp, rowversion|Cadeia de caracteres codificada em BASE64|  
|Tipos CLR|geometria, geografia, outros tipos CLR|Sem suporte. Estes tipos retornam um erro.<br /><br /> Na instrução SELECT, use CAST ou CONVERT ou use um método ou propriedade CLR para converter os dados de origem em um tipo de dados do SQL Server que pode ser convertido com êxito em um tipo JSON. Por exemplo, use **STAsText()** para o tipo de geometria ou **ToString()** para qualquer tipo CLR. O tipo do valor de saída JSON é derivado do tipo de retorno da conversão aplicada na instrução SELECT.|  
|Outros tipos|uniqueidentifier, money|cadeia de caracteres|  

## <a name="learn-more-about-the-built-in-json-support-in-sql-server"></a>Saiba mais sobre o suporte interno a JSON no SQL Server  
Para ver várias soluções específicas, casos de uso e recomendações, consulte as [postagens no blog sobre o suporte interno a JSON](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) no SQL Server e no Banco de Dados SQL do Azure, publicadas por Jovan Popovic, gerente de programas da Microsoft.
  
## <a name="see-also"></a>Consulte também  
 [Formatar os resultados da consulta como JSON com o FOR JSON &#40;SQL Server&#41;](../../relational-databases/json/format-query-results-as-json-with-for-json-sql-server.md)  
  
  
