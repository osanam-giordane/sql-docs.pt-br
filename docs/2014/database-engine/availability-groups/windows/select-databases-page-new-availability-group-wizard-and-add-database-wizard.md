---
title: Selecione a página bancos de dados (novo grupo de disponibilidade / Assistente para adicionar Assistente de banco de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.adddatabasewizard.selectdatabases.f1
- sql12.swb.newagwizard.selectdatabases.f1
ms.assetid: 929c5e15-d087-438d-b1f2-aa97c5f8bff8
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: a2c6cdeb27dfd1768c9a494497f5b2b1e0b7350a
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "62788481"
---
# <a name="select-databases-page-new-availability-group-wizard-add-database-wizard"></a>Página Selecionar bancos de dados (novo grupo de disponibilidade / Assistente para adicionar Assistente de banco de dados)
  Este tópico descreve as opções da página **Especificar Bancos de Dados** . Este tópico aplica-se ao [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] e ao [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].  
  
##  <a name="PageOptions"></a> Selecionar opções de bancos de dados  
 A grade **Bancos de dados de usuário nesta instância do SQL Server** lista todos os bancos de dados de usuário locais. As colunas são apresentadas assim:  
  
 **Nome**  
 Exibe o nome do banco de dados de usuário local.  
  
 **Tamanho**  
 Exibe o tamanho do banco de dados, se o tamanho estiver disponível para o assistente.  
  
 **Status**  
 Exibe um hiperlink cujo texto indica se um determinado banco de dados atende aos pré-requisitos para ser adicionado a um grupo de disponibilidade. Se o status for "**Atende pré-requisitos**" você poderá adicionar o banco de dados ao grupo de disponibilidade. Se um banco de dados não atender a todos os pré-requisitos, o hiperlink **Status** fornecerá uma breve explicação de por que o banco de dados não está qualificado. Para obter mais informações, clique no hiperlink.  
  
 Você pode deixar o assistente na página **Selecionar Banco de Dados** enquanto executa ações em um banco de dados para atender a um pré-requisito. Ao retornar à página **Selecionar Bancos de Dados** , clique em **Atualizar** para atualizar a grade.  
  
 **Atualizar**  
 Clique para atualizar a grade. Isso é útil depois que você executa uma ação em um banco de dados para atender a um pré-requisito.  
  
##  <a name="RelatedTasks"></a> Tarefas relacionadas  
  
-   [Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Pré-requisitos, restrições e recomendações para grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
