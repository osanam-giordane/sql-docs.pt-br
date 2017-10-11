---
title: Suporte para tipos de dados (Driver ODBC do Visual FoxPro) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual FoxPro ODBC driver [ODBC], data types
- FoxPro ODBC driver [ODBC], data types
- data types [ODBC], Visual FoxPro ODBC driver
ms.assetid: ab529cc6-d157-4b35-b6f9-6ffd09af098c
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: caf58413946e51ae8575b8d068e4a516316eb090
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="supported-data-types-visual-foxpro-odbc-driver"></a>Tipos de dados com suporte (Driver ODBC do Visual FoxPro)
A lista de tipos de dados com suporte pelo driver são apresentados por meio da API do ODBC e no Microsoft Query.  
  
## <a name="data-types-in-c-applications"></a>Tipos de dados em aplicativos C  
 Você pode obter uma lista de tipos de dados suportados pelo Driver ODBC para Visual FoxPro, usando o [SQLGetTypeInfo](../../odbc/microsoft/sqlgettypeinfo-visual-foxpro-odbc-driver.md) função em aplicativos C ou C++.  
  
## <a name="data-types-in-applications-using-microsoft-query"></a>Tipos de dados em aplicativos que usam o Microsoft Query  
 Se seu aplicativo usa o Microsoft Query para criar uma nova tabela em uma fonte de dados do Visual FoxPro, Microsoft Query exibe o **nova definição de tabela** caixa de diálogo. Em **campo Descrição**, o **tipo** caixa listas [tipos de dados de campo do Visual FoxPro](../../odbc/microsoft/visual-foxpro-field-data-types.md)representado pelos caracteres únicos.