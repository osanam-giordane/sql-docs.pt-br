---
title: "O rastreamento dinâmico | Microsoft Docs"
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
- tracing options [ODBC], dynamic
- dynamic tracing [ODBC]
ms.assetid: ebe58a83-a7b0-4747-86c8-2af2940471ef
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: af9d893b751e085361b50259f1d751cdeded3b39
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="dynamic-tracing"></a>Rastreamento dinâmico
O rastreamento pode ser habilitado ou desabilitado em qualquer ponto em um aplicativo executado. Isso permite que um aplicativo rastrear qualquer número de chamadas de função.  
  
 A variável **ODBCSharedTraceFlag** é definido para habilitar o rastreamento dinamicamente. Essa variável é compartilhada entre todas as cópias em execução do Gerenciador de Driver. Se qualquer aplicativo define essa variável, o rastreamento está habilitado para todos os aplicativos ODBC em execução no momento. Para ativar o rastreamento desativado quando o rastreamento dinâmico está habilitado, um aplicativo chama **SQLSetConnectAttr** para definir SQL_ATTR_TRACE como SQL_TRACE_OFF. Essa chamada ativará o rastreamento para o aplicativo somente. Aplicativos que estão vinculados com Odbc32.lib podem modificar o uso dessa variável. Dados de rastreamento podem ser exibidos em uma janela em tempo real, em vez do arquivo de rastreamento, que deve ser aberta após a sessão do ODBC. Controles podem ser adicionados à tela do aplicativo para ativar ou desativar o rastreamento no será.  
  
 O rastreamento DLL acompanha o ODBC 3*. x* não é thread-safe. Não há garantia de que o arquivo de log é gravado corretamente se o rastreamento global é habilitado (a variável **ODBCSharedTraceFlag** é definido) e mais de um aplicativo grava o arquivo de rastreamento ao mesmo tempo. Essa condição não retorna um erro.