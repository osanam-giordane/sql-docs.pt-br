---
title: Usando os serviços de informações da Internet da Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC driver for Oracle [ODBC], IIS
- internet information services [ODBC]
- IIS [ODBC]
ms.assetid: 3328f2f1-b34a-472f-82cf-ad49768ff061
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 9e531149af21facd80e9e6ddab19a76c3bdc0fa6
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68088143"
---
# <a name="using-microsoft-internet-information-services"></a>Usar os Serviços de Informações da Internet da Microsoft
> [!IMPORTANT]  
>  Este recurso será removido em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Em vez disso, use o driver ODBC fornecido pela Oracle.  
  
 Se você tiver dificuldade para se conectar de dentro de um script do IIS (especialmente se você receber um erro ou um 12641), adicione a seguinte linha ao arquivo SQLNET:  
  
```  
SQLNET.AUTHENTICATION_SERVICES = (none)  
```  
  
 Isso desabilitará os serviços de rede segura para que você pode se conectar usando a autenticação anônima.
