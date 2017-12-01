---
title: sp_marksubscriptionvalidation (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- sp_marksubscriptionvalidation
- sp_marksubscriptionvalidation_TSQL
helpviewer_keywords: sp_marksubscriptionvalidation
ms.assetid: e68fe0b9-5993-4880-917a-b0f661f8459b
caps.latest.revision: "21"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9b6286a062e41741145962cf123041812b6d366c
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="spmarksubscriptionvalidation-transact-sql"></a>sp_marksubscriptionvalidation (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Marca a transação aberta atual para ser uma transação de validação do nível de assinatura para o assinante especificado. Esse procedimento armazenado é executado no Publicador, no banco de dados publicador.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_marksubscriptionvalidation [ @publication = ] 'publication'  
        , [ @subscriber = ] 'subscriber'  
        , [ @destination_db = ] 'destination_db'  
    [ , [ @publisher = ] 'publisher' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@publication** =] **'***publicação***'**  
 É o nome da publicação. *publicação* é **sysname**, sem padrão.  
  
 [  **@subscriber** =] **'***assinante***'**  
 É o nome do Assinante. *assinante* é sysname, sem padrão.  
  
 [  **@destination_db=**] **'***destination_db***'**  
 É o nome do banco de dados de destino. *destination_db* é **sysname**, sem padrão.  
  
 [  **@publisher=** ] **'***publicador***'**  
 Especifica um não[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publicador. *publicador* é **sysname**, com um padrão NULL.  
  
> [!NOTE]  
>  *publicador* não deve ser usado para uma publicação que pertence a um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publicador.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Comentários  
 **sp_marksubscriptionvalidation** é usado em replicação transacional.  
  
 **sp_marksubscriptionvalidation** não oferecer suporte a não[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assinantes.  
  
 Para não -[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] editores, não é possível executar **sp_marksubscriptionvalidation** de dentro de uma transação explícita. Isso porque transações explícitas não têm suporte em conexão de servidor vinculada usada para acessar o Editor.  
  
 **sp_marksubscriptionvalidation** deve ser usado junto com [sp_article_validation &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-article-validation-transact-sql.md), especificando um valor de **1** para *subscription_level*e pode ser usado com outras chamadas **sp_marksubscriptionvalidation** para marcar o transação aberta atual para outros assinantes.  
  
## <a name="permissions"></a>Permissões  
 Somente membros do **sysadmin** função de servidor fixa ou **db_owner** pode executar a função de banco de dados fixa **sp_marksubscriptionvalidation**.  
  
## <a name="example"></a>Exemplo  
 A consulta seguinte pode ser aplicada ao banco de dados de publicação para publicar comandos de validação de nível de assinatura. Esses comandos são retirados pelos Distribution Agents de Assinantes especificados. Observe que a primeira transação valida o artigo '**art1**', enquanto a segunda transação valida'**art2**'. Observe também que as chamadas para **sp_marksubscriptionvalidation** e [sp_article_validation &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-article-validation-transact-sql.md) foram encapsuladas em uma transação. É recomendável somente uma chamada para [sp_article_validation &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-article-validation-transact-sql.md) por transação. Isso ocorre porque [sp_article_validation &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-article-validation-transact-sql.md) mantém um bloqueio de tabela compartilhada na tabela de origem para a duração da transação. A transação deve ser curta para maximizar simultaneidade.  
  
```  
begin tran  
  
exec sp_marksubscriptionvalidation @publication = 'pub1',  
 @subscriber = 'Sub', @destination_db = 'SubDB'  
  
exec sp_marksubscriptionvalidation @publication = 'pub1',  
 @subscriber = 'Sub2', @destination_db = 'SubDB'  
  
exec sp_article_validation @publication = 'pub1', @article = 'art1',  
 @rowcount_only = 0, @full_or_fast = 0, @shutdown_agent = 0,  
 @subscription_level = 1  
  
commit tran  
  
begin tran  
  
exec sp_marksubscriptionvalidation @publication = 'pub1',  
 @subscriber = 'Sub', @destination_db = 'SubDB'  
  
exec sp_marksubscriptionvalidation @publication = 'pub1',  
 @subscriber = 'Sub2', @destination_db = 'SubDB'  
  
exec sp_article_validation @publication = 'pub1', @article = 'art2',  
 @rowcount_only = 0, @full_or_fast = 0, @shutdown_agent = 0,  
 @subscription_level = 1  
  
commit tran  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Validar os dados replicados](../../relational-databases/replication/validate-replicated-data.md)  
  
  