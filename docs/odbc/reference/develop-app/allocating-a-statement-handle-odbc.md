---
title: Alocando um identificador de instrução ODBC | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQL statements [ODBC], statement handles
- statement handles [ODBC]
- allocating statement handles [ODBC]
- handles [ODBC], statement
ms.assetid: 4ce3b446-34ab-46dc-96e5-f40ec95c267e
author: MightyPen
ms.author: genemi
ms.openlocfilehash: d50b0a31aed4935c805ca30620575ccff70d4a0b
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68077213"
---
# <a name="allocating-a-statement-handle-odbc"></a>Alocar um identificador de instrução ODBC
Antes do aplicativo pode executar uma instrução, ele deve alocar um identificador de instrução da seguinte maneira:  
  
1.  O aplicativo declara uma variável do tipo HSTMT. Em seguida, ele chama **SQLAllocHandle** e passa o endereço dessa variável, o identificador da conexão de alocação a instrução e a opção de SQL_HANDLE_STMT. Por exemplo:  
  
    ```  
    SQLHSTMT hstmt1;  
  
    SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
    ```  
  
2.  O Gerenciador de Driver aloca uma estrutura na qual armazenar informações sobre a instrução e chama **SQLAllocHandle** no driver com a opção de SQL_HANDLE_STMT.  
  
3.  O driver aloca sua própria estrutura na qual armazenar informações sobre a instrução e retorna o identificador de instrução de driver para o Gerenciador de Driver.  
  
4.  O Gerenciador de Driver retorna o identificador de instrução do Gerenciador de Driver para o aplicativo na variável de aplicativo.  
  
 O identificador de instrução identifica qual instrução a ser usada ao chamar funções ODBC. Para obter mais informações sobre identificadores de instrução, consulte [identificadores de instrução](../../../odbc/reference/develop-app/statement-handles.md).
