---
title: MSSQLSERVER_2570 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 63adadd3dda40dc520e2152eab1a461dfe69958a
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68023030"
---
# <a name="mssqlserver2570"></a>MSSQLSERVER_2570
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|2570|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|DBCC_COLUMN_VALUE_OUT_OF_RANGE|  
|Texto da mensagem|Página P_ID, slot S_ID na ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE). O valor de coluna COLUMN_NAME está fora do intervalo para tipo de dados "DATATYPE". Atualize a coluna para um valor válido.|  
  
## <a name="explanation"></a>Explicação  
O valor de coluna contido na coluna especificada está fora do intervalo de valores possíveis para o tipo de dados da coluna.  
  
## <a name="user-action"></a>Ação do usuário  
O erro não é reparável. Atualize a coluna com um valor que esteja dentro do intervalo para o tipo de dados da coluna e execute o comando novamente.  Para obter mais informações, consulte o artigo [923247](https://support.microsoft.com/kb/923247) da Base de Dados de Conhecimento.  
  
## <a name="see-also"></a>Consulte Também  
[UPDATE &#40;Transact-SQL&#41;](~/t-sql/queries/update-transact-sql.md)  
[Tipos de dados &#40;Transact-SQL&#41;](~/t-sql/data-types/data-types-transact-sql.md)  
  
