---
title: Conexão de contexto | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context connections [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- context [CLR integration]
ms.assetid: 67dd1925-d672-4986-a85f-bce4fe832ef7
caps.latest.revision: 13
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a95f4c4b190f37674290588714fc3e7b0c6582a5
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36117445"
---
# <a name="context-connection"></a>Conexão de contexto
  O problema de acesso a dados internos é um cenário bastante comum. Ou seja, você deseja acessar o mesmo servidor no qual sua função ou seu procedimento armazenado CLR (Common Language Runtime) está em execução. Uma opção é criar uma conexão usando `System.Data.SqlClient.SqlConnection`, especificar uma cadeia de conexão que aponta para o servidor local e abrir a conexão. Isso exige a especificação de credenciais para fazer logon. A conexão está em uma sessão do banco de dados diferente do procedimento armazenado ou da função, pode ter opções `SET` diferentes, está em uma transação separada, não vê suas tabelas temporárias e assim por diante. Se código da função ou do procedimento armazenado gerenciado estiver em execução no processo do SQL Server, isso ocorrerá porque alguém se conectou a esse servidor e executou uma instrução SQL para invocá-lo. Provavelmente, você deseja que o procedimento armazenado ou a função seja executado no contexto dessa conexão, juntamente com sua transação, opções `SET` e assim por diante. Isto é chamado de conexão de contexto.  
  
 A conexão de contexto permite executar instruções Transact-SQL no mesmo contexto em que seu código foi invocado pela primeira vez. Para obter a conexão de contexto, use a palavra-chave de cadeia de conexão "context connection", como no exemplo a seguir:  
  
 [C#]  
  
```  
using(SqlConnection connection = new SqlConnection("context connection=true"))   
{  
    connection.Open();  
    // Use the connection  
}  
```  
  
 [Visual Basic]  
  
```  
Using connection as new SqlConnection("context connection=true")  
    connection.Open()  
    ' Use the connection  
End Using  
  
```  
  
## <a name="in-this-section"></a>Nesta seção  
 [Regular vs. Conexões de contexto](context-connections-vs-regular-connections.md)  
 Descreve as diferenças entre conexões normais e de contexto.  
  
 [Restrições em conexões comuns e de contexto](context-connections-and-regular-connections-restrictions.md)  
 Descreve as restrições em conexões normais e de contexto.  
  
  