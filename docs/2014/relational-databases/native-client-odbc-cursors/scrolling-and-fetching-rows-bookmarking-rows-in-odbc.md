---
title: Indicando linhas em ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- ODBC cursors, scrolling rows
- bookmarks [ODBC]
ms.assetid: 9cfcd243-c9d4-4c2a-abc4-399dbabe5f6b
caps.latest.revision: 30
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7f2d19fe6cf79e11c11a5e6c5c4839ae35788353
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36012037"
---
# <a name="bookmarking-rows-in-odbc"></a>Indicando linhas em ODBC
  Um indicador é um valor usado para identificar uma linha de dados. O significado do valor de indicador só é conhecido para o driver ou a fonte de dados. Por exemplo, ele poderá ser tão simples quanto um número de linha ou tão complexo quanto um endereço de disco. Em ODBC, o aplicativo solicita um indicador para uma linha específica, armazena-o e transmite-o novamente ao cursor para que retorne à linha.  
  
 Ao buscar linhas com [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), um aplicativo pode usar um indicador como uma base para selecionar a linha inicial. Esta é uma forma de endereçamento absoluto porque não depende da posição atual do cursor. Para rolar até uma linha marcada, o aplicativo chama **SQLFetchScroll** com um *FetchOrientation* de SQL_FETCH_BOOKMARK. Esta operação usa o indicador apontado pelo atributo da opção SQL_ATTR_FETCH_BOOKMARK_PTR. Retorna o conjunto de linhas que inicia com a linha identificada por esse indicador. Um aplicativo pode especificar um deslocamento para esta operação é o *FetchOffset* argumento da chamada para **SQLFetchScroll**. Quando um deslocamento é especificado, a primeira linha do conjunto de linhas retornado é determinada adicionando o número no argumento FetchOffset ao número da linha identificada pelo indicador. O driver ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client apenas dá suporte a indicadores em cursores estáticos e do conjunto de chaves. Se um cursor dinâmico for solicitado quando indicadores forem definidos, um cursor do conjunto de chaves será aberto no lugar.  
  
 Indicadores também podem ser usados com o **SQLBulkOperations** função para executar operações em um conjunto de linhas que iniciam no indicador.  
  
## <a name="see-also"></a>Consulte também  
 [Rolagem e busca de linhas](../native-client-ole-db-rowsets/fetching-rows.md)  
  
  