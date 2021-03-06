---
title: Níveis de conformidade do SQL | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- conformance levels [ODBC], SQL
- SQL conformance levels [ODBC]
- data sources [ODBC], conformance levels
- ODBC drivers [ODBC], conformance levels
ms.assetid: 3529df2c-a09b-4c16-9c60-eae7a06d903a
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 7862b2e3a86c6d98a51c73ecb470d59bcfe29dc9
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68107517"
---
# <a name="sql-conformance-levels"></a>Níveis de conformidade SQL
O nível de gramática de SQL-92 com suporte por um driver é indicado pelo valor retornado por uma chamada para **SQLGetInfo** com o tipo de informação SQL_SQL_CONFORMANCE. Isso indica se o driver está de acordo com os níveis de entrada, Transitional FIPS, intermediário ou completo definidos no SQL-92.  
  
 Todos os drivers ODBC devem dar suporte a gramática SQL mínima descrita em [gramática SQL mínima](../../../odbc/reference/appendixes/sql-minimum-grammar.md) no Apêndice c: Gramática SQL. Essa gramática é um subconjunto do nível de entrada do SQL-92. Drivers podem oferecer suporte ao SQL adicional e ser compatível com o nível de entrada do SQL-92, intermediário ou completo ou o FIPS 127-2 nível de transição. Drivers que estão em conformidade para um determinado nível de SQL-92 ou FIPS 127-2 podem oferecer suporte a recursos adicionais em qualquer um dos níveis mais altos ainda não ser totalmente compatível com a esse nível. Para determinar se um recurso tem suporte, um aplicativo deve chamar **SQLGetInfo** com o tipo de informações apropriadas. O nível de conformidade de um recurso do SQL é descrito no tipo de informações correspondentes. (Consulte a [SQLGetInfo](../../../odbc/reference/syntax/sqlgetinfo-function.md) descrição da função.)
