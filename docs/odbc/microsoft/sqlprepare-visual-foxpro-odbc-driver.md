---
title: SQLPrepare (Driver ODBC do Visual FoxPro) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLPrepare function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 0c4cb5a4-9729-4b2e-a0c6-52027b92e8fc
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 5835ddaf27d097dcfff608649f50c1f7f41a93df
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67996310"
---
# <a name="sqlprepare-visual-foxpro-odbc-driver"></a>SQLPrepare (Driver ODBC do Visual FoxPro)
> [!NOTE]  
>  Este tópico contém informações específicas de Driver ODBC do Visual FoxPro. Para obter informações gerais sobre essa função, consulte o tópico apropriado sob [referência da API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Suporte a: Completo  
  
 Conformidade com a API ODBC: Nível de núcleo  
  
 Prepara uma instrução SQL, como planejar a otimizar e execute a instrução. A instrução SQL é compilada para execução pelo [SQLExecDirect](../../odbc/microsoft/sqlexecdirect-visual-foxpro-odbc-driver.md).  
  
 Se sua tabela, exibição ou nomes de campo contiverem espaços, coloque os nomes novamente aspas simples (') marcas. Por exemplo, se seu banco de dados contiver uma tabela denominada My Table e o campo Meu campo, coloque cada elemento do identificador da seguinte maneira:  
  
```  
SELECT * FROM `My Table`.`My Field`  
```  
  
 Para obter mais informações, consulte [SQLPrepare](../../odbc/reference/syntax/sqlprepare-function.md) na *referência do programador de ODBC*.
