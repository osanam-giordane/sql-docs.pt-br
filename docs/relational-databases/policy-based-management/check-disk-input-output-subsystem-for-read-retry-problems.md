---
title: Verificar o subsistema de entrada e saída de disco quanto a problemas de repetição de leitura | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 1540314e6dfe9370cd11b7638e003b5e230c32d2
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68109930"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a>Verificar o subsistema de entrada e saída de disco para problemas de repetição de leitura
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Esta regra verifica o log de eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a mensagem de erro 825. Esta mensagem indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde ler os dados do disco na primeira tentativa. Esta mensagem indica um problema grave com o subsistema de E/S do disco. Atualmente, esta mensagem não indica um problema no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Entretanto, o problema com o disco poderia causar perda de dados ou danos no banco de dados se não for resolvido.  
  
## <a name="best-practices-recommendations"></a>Práticas Recomendadas  
 As ações a seguir podem ajudar a identificar e resolver o problema subjacente no hardware:  
  
-   Revise o log de erros e o texto variável nesta mensagem para encontrar pistas que expliquem o problema.  
  
-   Verifique o sistema de disco. O problema pode estar relacionado aos discos, aos controladores de disco, aos cartões de matriz ou aos drivers de disco.  
  
-   Contate o fabricante do disco para obter os mais recentes utilitários para verificar o status do sistema do disco.  
  
-   Contate o fabricante do disco para obter as mais recentes atualizações de driver.  
  
## <a name="for-more-information"></a>Para obter mais informações  
 [MSSQLSERVER_825](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 [Fundamentos de E/S do SQL Server, Capítulo 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))  
  
  
