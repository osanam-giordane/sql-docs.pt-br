---
title: 'C para SQL: Bit | Microsoft Docs'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- converting data from c to SQL types [ODBC], bit
- bit data type [ODBC]
- data conversions from C to SQL types [ODBC], bit
ms.assetid: 267c9fa9-599e-4ee6-b51b-0cae43f09183
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 8cc5e26b30816d0989dca90566a1a5de008b71c7
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68019426"
---
# <a name="c-to-sql-bit"></a>C para SQL: bit
O identificador para o tipo de dados ODBC C bit é:  
  
 SQL_C_BIT  
  
 A tabela a seguir mostra o ODBC SQL para o qual os dados de C de bit podem ser convertidos de tipos de dados. Para obter uma explicação das colunas e os termos na tabela, consulte [conversão de dados do C para tipos de dados SQL](../../../odbc/reference/appendixes/converting-data-from-c-to-sql-data-types.md).  
  
|Identificador de tipo SQL|Teste|SQLSTATE|  
|-------------------------|----------|--------------|  
|SQL_CHAR SQL_VARCHAR<br /><br /> SQL_LONGVARCHAR<br /><br /> SQL_WCHAR SQL_WVARCHAR<br /><br /> SQL_WLONGVARCHAR|Nenhum|n/d|  
|SQL_DECIMAL SQL_NUMERIC<br /><br /> SQL_TINYINT SQL_SMALLINT<br /><br /> SQL_INTEGER SQL_BIGINT<br /><br /> SQL_REAL SQL_FLOAT<br /><br /> SQL_DOUBLE|Nenhum|n/d|  
|SQL_BIT|Nenhum|n/d|  
  
 O driver ignora o valor de comprimento/indicador ao converter dados de tipo de dados bit C e pressupõe que o tamanho do buffer de dados é o tamanho do tipo de dados bit C. O valor de comprimento/indicador é passado a *StrLen_or_Ind* argumento na **SQLPutData** e no buffer especificado com o *StrLen_or_IndPtr* argumento **SQLBindParameter**. O buffer de dados é especificado com o *DataPtr* argumento **SQLPutData** e o *ParameterValuePtr* argumento em **SQLBindParameter**.
