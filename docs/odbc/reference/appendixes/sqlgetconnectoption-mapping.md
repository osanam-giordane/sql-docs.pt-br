---
title: Mapeamento SQLGetConnectOption | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLGetConnectOption
- SQLGetConnectOption function [ODBC], mapping
ms.assetid: e3792fe4-a955-473a-a297-c1b2403660c4
author: MightyPen
ms.author: genemi
ms.openlocfilehash: d0533a0ee616d4097793eca46c7d45a269142737
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68086406"
---
# <a name="sqlgetconnectoption-mapping"></a>Mapeamento SQLGetConnectOption
Quando um aplicativo chama **SQLGetConnectOption** por meio de ODBC *3.x* driver, a chamada para  
  
```  
SQLGetConnectOption(hdbc, fOption, pvParam)   
```  
  
 é mapeado da seguinte maneira:  
  
-   Se *fOption* indica uma opção de conexão definidas pelo ODBC que retorna uma cadeia de caracteres, as chamadas de Gerenciador de Driver  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, BufferLength, NULL)  
    ```  
  
-   Se *fOption* indica uma opção de conexão definidas pelo ODBC que retorna um valor inteiro de 32 bits, as chamadas de Gerenciador de Driver  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, 0, NULL)  
    ```  
  
-   Se *fOption* indica uma opção de instrução definidos pelo driver, as chamadas de Gerenciador de Driver  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, BufferLength, NULL)  
    ```  
  
 Nos três casos anteriores, o *ConnectionHandle* argumento é definido como o valor na *hdbc*, o *atributo* argumento é definido como o valor em *fOption* e o *ValuePtr* argumento é definido como o mesmo valor de *pvParam*.  
  
 Para obter opções de conexão de cadeia de caracteres definidas pelo ODBC, o Gerenciador de Driver define o *BufferLength* argumento na chamada para **SQLGetConnectAttr** para o tamanho máximo predefinido (SQL_MAX_OPTION_STRING_LENGTH); para uma opção de conexão não cadeia de caracteres, *BufferLength* é definido como 0.  
  
 Para um ODBC *3.x* driver, o Gerenciador de Driver não verifica se *opção* está entre SQL_CONN_OPT_MIN e SQL_CONN_OPT_MAX ou é maior que SQL_CONNECT_OPT_DRVR_START. O driver deve verificar a validade dos valores de opção.
