---
title: Propriedades personalizadas do destino do SQL Server | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b736aa6d-c154-44a0-be08-f25733fca1d9
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d29337e20ed16ab60fc3ec55968a351dc527e2c6
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="sql-server-destination-custom-properties"></a>Propriedades personalizadas do destino SQL Server
  O destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tem propriedades personalizadas e propriedades comuns a todos os componentes de fluxo de dados.  
  
 A tabela a seguir descreve as propriedades personalizadas do destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Todas as propriedades são de leitura/gravação.  
  
|Nome da propriedade|Tipo de Dados|Description|  
|-------------------|---------------|-----------------|  
|AlwaysUseDefaultCodePage|Booliano|Força o uso do valor da propriedade DefaultCodePage. O valor padrão dessa propriedade é **False**.|  
|BulkInsertCheckConstraints|Booliano|Um valor que especifica se a inserção em massa verifica restrições. O valor padrão dessa propriedade é **True**.|  
|BulkInsertFireTriggers|Booliano|Um valor que especifica se a inserção em massa aciona gatilhos em tabelas. O valor padrão dessa propriedade é **False**.|  
|BulkInsertFirstRow|Integer|Um valor que especifica a primeira linha a ser inserida. O valor padrão dessa propriedade é **-1**, que indica que nenhum valor foi atribuído|  
|BulkInsertKeepIdentity|Booliano|Um valor que especifica se podem ser inseridos valores em colunas de identidade. O valor padrão dessa propriedade é **False**.|  
|BulkInsertKeepNulls|Booliano|Um valor que especifica se a inserção em massa mantém valores Nulos. O valor padrão dessa propriedade é **False**.|  
|BulkInsertLastRow|Integer|Um valor que especifica a última linha a ser inserida. O valor padrão dessa propriedade é **-1**, que indica que nenhum valor foi atribuído.|  
|BulkInsertMaxErrors|Integer|Um valor que especifica o número de erros que podem ocorrer antes que a inserção em massa seja interrompida. O valor padrão dessa propriedade é **-1**, que indica que nenhum valor foi atribuído.|  
|BulkInsertOrder|Cadeia de caracteres|Os nomes das colunas de classificação. Cada coluna pode ser classificada em ordem crescente ou decrescente. Se forem usadas várias colunas de classificação, os nomes de coluna serão separados por vírgulas.|  
|BulkInsertTableName|Cadeia de caracteres|A tabela ou exibição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no banco de dados para o qual os dados são copiados.|  
|BulkInsertTablock|Booliano|Um valor que especifica se a tabela é bloqueada durante a inserção em massa. O valor padrão dessa propriedade é **True**.|  
|DefaultCodePage|Integer|A página de código a ser usada quando informações de página de código não estão disponíveis na fonte de dados.|  
|MaxInsertCommitSize|Integer|Um valor que especifica o número máximo de linhas a serem inseridas em um lote. Quando o valor é zero, todas as linhas são inseridas em um único lote.|  
|Tempo Limite|Integer|Um valor que especifica a duração em segundos da espera do destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] até a conclusão, se não houver dados disponíveis para inserção. O valor 0 significa que não há tempo limite para o destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . O valor padrão dessa propriedade é 30.|  
  
 A entrada e as colunas de entrada do destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não têm nenhuma propriedade personalizada.  
  
 Para obter mais informações, consulte [Destino do SQL Server](../../integration-services/data-flow/sql-server-destination.md).  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades comuns](http://msdn.microsoft.com/library/51973502-5cc6-4125-9fce-e60fa1b7b796)  
  
  