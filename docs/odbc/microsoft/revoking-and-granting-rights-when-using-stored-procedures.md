---
title: Revogando e concedendo direitos ao usar procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [ODBC], ODBC driver for Oracle
- ODBC driver for Oracle [ODBC], stored procedures
ms.assetid: 24070039-03ab-4623-a681-6308802eb399
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 91fcf722554fe1840465329e707c792a6bbab6db
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67987957"
---
# <a name="revoking-and-granting-rights-when-using-stored-procedures"></a>Revogar e conceder direitos ao usar procedimentos armazenados
> [!IMPORTANT]  
>  Este recurso será removido em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Em vez disso, use o driver ODBC fornecido pela Oracle.  
  
 O Microsoft ODBC Driver for Oracle retorna a seguinte mensagem de erro quando os direitos de usuário são concedidos e revogados, em seguida, em uma tabela acessada por um procedimento armazenado:  
  
 SQL_ERROR=-1  
  
 szErrorMsg = "[Microsoft] [driver ODBC para Oracle] o número errado de parâmetros"  
  
 szErrorMsg = "[Microsoft] [driver ODBC para Oracle] sintaxe ou violação de acesso"  
  
 A chamada para a função Oracle OCI Odessp() falha nesse cenário, mas é necessária para implementar os parâmetros padrão. Depois que as permissões de tabela subjacentes são modificadas, o procedimento armazenado deve ser recompilado antes de executá-la novamente.
