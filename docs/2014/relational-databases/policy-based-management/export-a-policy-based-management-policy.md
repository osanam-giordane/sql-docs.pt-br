---
title: Exportar uma política do Gerenciamento Baseado em Políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, export policy
ms.assetid: f0001b33-9078-4432-8460-496736fb325a
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: dc7067432c46e1d03323ed2a32dab84ebdf72755
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "62705322"
---
# <a name="export-a-policy-based-management-policy"></a>Exportar uma política do Gerenciamento Baseado em Políticas
  Este tópico descreve como exportar uma Política de Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
 **Neste tópico**  
  
-   **Antes de começar:**  
  
     [Segurança](#Security)  
  
-   **Para exportar uma política, usando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 Requer a associação à função PolicyAdministratorRole no banco de dados msdb.  
  
##  <a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
  
#### <a name="to-export-a-policy"></a>Para exportar uma política  
  
1.  No Pesquisador de Objetos, clique no sinal de adição para expandir o servidor que contém a Política de Gerenciamento Baseado em Políticas que você deseja exportar.  
  
2.  Clique no sinal de adição para expandir a pasta **Gerenciamento** .  
  
3.  Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.  
  
4.  Clique no sinal de adição para expandir a pasta **Políticas** .  
  
5.  Clique com o botão direito do mouse na política a ser exportada e selecione **Exportar Política**.  
  
6.  Na caixa de diálogo **Exportar Política** , digite o caminho e o nome do arquivo na barra de endereços. Como alternativa, encontra o local apropriado para o arquivo no painel de navegação na caixa de diálogo e digite o nome do arquivo XML na caixa **Nome do Arquivo** .  
  
7.  Ao concluir, clique em **Salvar**.  
  
  
