---
title: Suporte internacional (Driver ODBC do Visual FoxPro) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- double-byte character sets [ODBC]
- FoxPro ODBC driver [ODBC], international support
- DBCS [ODBC]
- international support [ODBC]
- sort order [ODBC]
- collating sequences [ODBC]
- Visual FoxPro ODBC driver [ODBC], international support
ms.assetid: cd3fab32-13f1-4a86-abc4-5e18667669fc
author: MightyPen
ms.author: genemi
ms.openlocfilehash: e987c224f2d716fcab3bf898b1cb276e922e48ef
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68085501"
---
# <a name="international-support-visual-foxpro-odbc-driver"></a>Suporte internacional (Driver ODBC do Visual FoxPro)
O Driver ODBC do Microsoft Visual FoxPro dá suporte a:  
  
-   Conjuntos de caracteres de byte duplo (DBCS)  
  
-   Várias sequências de agrupamento  
  
 Uma sequência de agrupamento define a *ordem de classificação* para dados armazenados em uma tabela do Visual FoxPro ou banco de dados. Por padrão, o driver está configurado para usar as sequências de agrupamento que dão suporte a versão de idioma do seu sistema operacional.  
  
 Para obter uma lista de sequências de agrupamento com suporte, consulte [definir COLLATE](../../odbc/microsoft/set-collate-command.md).  
  
## <a name="locale"></a>localidade  
 O conjunto de informações que corresponde a um determinado idioma e país/região. Uma localidade indica as configurações específicas, como separadores decimais e ordem de classificação de caractere e formatos de hora e data.  
  
## <a name="sort-order"></a>ordem de classificação  
 Ordens de classificação incorporam as regras de classificação diferentes *localidade*s, permitindo que você classificar corretamente os dados nesses idiomas. No Visual FoxPro, a ordem de classificação atual determina os resultados das comparações de expressão de caractere e a ordem na qual os registros aparecem no indexadas ou tabelas de classificados.
