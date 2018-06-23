---
title: Identidade e controle de acesso (Replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- access controls [SQL Server replication]
- security [SQL Server replication], identity and access control
- authentication [SQL Server replication]
- identity [Replication]
ms.assetid: 4da0e793-1ee4-4f69-a80b-45c6732a238d
caps.latest.revision: 7
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 88eab53d0d0d65397ce92182275a1dfbd27d0370
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36115397"
---
# <a name="identity-and-access-control-replication"></a>Identidade e controle de acesso (Replicação)
  A autenticação é o processo pelo qual uma entidade (geralmente um computador neste contexto) verifica se outra entidade, também chamada *principal*, (geralmente um outro computador ou um usuário) é quem ou o que diz ser. A autorização é o processo pelo qual um principal autenticado obtém acesso aos recursos, como um arquivo no sistema de arquivos ou  uma tabela no banco de dados.  
  
 A segurança de replicação usa a autenticação e a autorização para controlar o acesso aos objetos de banco de dados replicados e aos computadores e agentes envolvidos no processamento de replicação. Isso é realizado por meio de três mecanismos:  
  
-   Segurança do agente  
  
     O modelo de segurança do agente de replicação permite um controle refinado das contas nas quais os agentes de replicação executam e efetuam conexões. Para obter informações detalhadas sobre o modelo de segurança do agente, consulte [Replication Agent Security Model](replication-agent-security-model.md). Para mais informações sobre como definir logons e senhas para os agentes, consulte [Gerenciar logons e senhas na Replicação](manage-logins-and-passwords-in-replication.md).  
  
-   Funções de administração  
  
     Certifique-se de que  o servidor e as funções do banco de dados corretos sejam usados na configuração, manutenção e processamento da replicação. Para obter mais informações, consulte [Security Role Requirements for Replication](security-role-requirements-for-replication.md).  
  
-   A lista de acesso à publicação (PAL)  
  
     Conceda acesso a publicações por meio da PAL. A PAL funciona de modo semelhante à lista de controle de acesso do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows. Quando um Assinante se conecta ao Publicador ou ao Distribuidor e solicita acesso à publicação, as informações de autenticação passadas pelo agente são verificadas de acordo com a PAL. Para mais informações e melhores práticas para a PAL, consulte [Proteger o Publicador](secure-the-publisher.md).  
  
## <a name="filtering-published-data"></a>Filtrando dados publicados  
 Além de usar a autenticação e a autorização para controlar o acesso aos dados e objetos replicados, a replicação inclui duas opções para controlar quais dados estão disponíveis no Assinante: a filtragem de colunas e a filtragem de linhas. Para mais informações sobre filtragem, consulte [Filtrar dados publicados](../publish/filter-published-data.md).  
  
 Ao definir um artigo, você pode publicar apenas as colunas que são necessárias para a publicação e omitir as desnecessárias ou aquelas que contêm dados confidenciais. Por exemplo, quando publicar a tabela **Customer** do banco de dados Adventure Works para os representantes de vendas em atuação na área, você pode omitir a coluna **AnnualSales** , que talvez seja importante apenas para os executivos da empresa.  
  
 A filtragem de dados publicados restringe o acesso aos dados e permite que você especifique os dados disponíveis no Assistente. Por exemplo, você pode filtrar a tabela **Customer** para que os parceiros da corporação recebam apenas as informações sobre os clientes cuja coluna **ShareInfo** tenha um valor de "sim." Para a replicação de mesclagem, haverá considerações de segurança se você usar um filtro com parâmetros que inclua HOST_NAME(). Para obter mais detalhes, consulte a seção "Filtragem com HOST_NAME ()" em [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).  
  
## <a name="see-also"></a>Consulte também  
 [Segurança e proteção &#40;Replicação&#41;](security-and-protection-replication.md)   
 [Visão geral da segurança &#40;Replicação&#41;](security-overview-replication.md)   
 [Ameaça e mitigação de vulnerabilidade &#40;Replicação&#41;](threat-and-vulnerability-mitigation-replication.md)  
  
  