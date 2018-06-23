---
title: Arquitetura do lado do cliente e do servidor formatação XML (SQLXML 4.0) | Microsoft Docs
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
- providers [SQLXML], XML formatting architecture
- SQLOLEDB provider
- client-side XML formatting
- data providers [SQLXML], XML formatting architecture
- SQLNCLI, XML
- server-side XML formatting
- SQL Server Native Client, XML
- SQLXMLOLEDB Provider, XML formatting architecture
ms.assetid: 52440d9e-89fd-4c15-a008-a1ea99f41387
caps.latest.revision: 31
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 589ca305ee7fe492dd5342ab184b37abcfb5d2ec
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36009717"
---
# <a name="architecture-of-client-side-and-server-side-xml-formatting-sqlxml-40"></a>Arquitetura de formatação XML no lado do cliente e no lado do servidor (SQLXML 4.0)
  A ilustração a seguir mostra a arquitetura de formatação XML no lado do servidor.  
  
 ![Arquitetura de formatação XML no lado do servidor. ] (../../../database-engine/dev-guide/media/serversidexml.gif "Formatação de arquitetura de XML no lado do servidor.")  
  
 Neste exemplo, o comando especificado no cliente é enviado ao servidor. O servidor gera um documento XML e o retorna ao cliente. Nesse caso, o servidor tem uma instância de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Com a formatação XML no lado do servidor, você pode usar o provedor SQLXMLOLEDB ou o provedor SQLOLEDB.  O provedor SQLXMLOLEDB usa Sqlxml4.dll que é incluído no SQLXML 4.0. Quando você usa o provedor SQLOLEDB, por padrão obtém a funcionalidade do SQLXML fornecida pela Sqlxmlx.dll, incluída com o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows ou MDAC (Microsoft Data Access Components) 2.6 ou posterior. Para usar Sqlxml4.dll com SQLOLEDB, você deve definir a propriedade de versão do SQLXML para "SQLXML.4.0" no objeto de Conexão de SQLOLEDB. Em todo caso, o servidor gera o documento XML e o envia ao cliente.  
  
> [!NOTE]  
>  As consultas e os diagramas de atualização XPath são analisados no cliente. Para obter a funcionalidade do diagrama de atualização ou do modelo XPath no SQLXML 4.0, use Sqlxml4.dll.  
  
 A ilustração a seguir mostra a arquitetura da formatação XML no lado do cliente.  
  
 ![Arquitetura de formatação XML no lado do cliente. ] (../../../database-engine/dev-guide/media/clientsidexml.gif "Formatação de arquitetura de XML no lado do cliente.")  
  
 Neste exemplo, o cliente usa o provedor SQLXMLOLEDB. Na cadeia de conexão, a propriedade de provedor de dados deve ser definida como SQLOLEDB. (Esse é o único valor aceito no SQLXML 4.0.) O comando executado no cliente é enviado ao servidor. O conjunto de linhas gerado no servidor é enviado ao cliente. A formatação do documento XML do conjunto de linhas é executada no cliente.  
  
 No SQLXML 4.0, tanto o provedor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) como o SQLOLEDB podem ser usados como o provedor de dados. Você pode acessar potencialmente qualquer fonte de dados. Contanto que a consulta retorne um único conjunto de linhas, a transformação XML pode ser aplicada no cliente.  
  
  