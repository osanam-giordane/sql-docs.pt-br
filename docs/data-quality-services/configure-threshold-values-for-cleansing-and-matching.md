---
title: "Configurar valores de limite para limpeza e correspondência | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- data-quality-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dqs.admin.config.general.f1
helpviewer_keywords:
- cleansing,threshold value
- cleansing threshold values
- matching,threshold value
ms.assetid: d2305409-7115-45a4-8f60-1213c0a47368
caps.latest.revision: 9
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d577ae93726810251bdd92438fed4b26f1f4bd39
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="configure-threshold-values-for-cleansing-and-matching"></a>Configurar valores de limite para limpeza e correspondência
  Este tópico descreve como configurar valores de limite que serão usados durante a limpeza auxiliada por computador e as atividades correspondentes no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 É necessário ter a função dqs_administrator no banco de dados DQS_MAIN para configurar esses valores de limite.  
  
##  <a name="Configure"></a> Configurando os valores de limite  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Executar o aplicativo Data Quality Client](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Configuração**.  
  
3.  Em seguida, clique na guia **Configurações Gerais** . Essa guia permite a você especificar os valores de limite para a limpeza, bem como as atividades de correspondência.  
  
4.  Para especificar valores de limote para a atividade de limpeza, especifique os valores apropriados nas seguintes caixas na área **Limpeza Interativa** :  
  
    -   **Pontuação mínima para sugestões**: a pontuação mínima ou o nível de confiança que será usado pelo DQS para sugerir substitutos para um valor durante o processo de limpeza auxiliada por computador. Insira um valor na notação decimal do valor percentual correspondente. Por exemplo, digite 0,75 para 75%. Esse valor deve ser inferior ou igual ao valor especificado na caixa **Pontuação mínima para correções automáticas** . O valor padrão é 0,7.  
  
    -   **Pontuação mínima para correções automáticas**: a pontuação mínima ou o nível de confiança que será usado pelo DQS para corrigir automaticamente um valor durante o processo de limpeza auxiliada por computador. Insira um valor na notação decimal do valor percentual correspondente. Por exemplo, insira 0,9 para 90%. O valor padrão é 0,8.  
  
5.  Para especificar um valor de limite para a atividade de correspondência, especifique um valor na caixa **Pontuação mínima de registro** na área **Correspondência** . Esse valor significa a pontuação mínima para um registro a ser considerado como uma correspondência para outro registro. O valor padrão é 80%.  
  
6.  Clique em **Fechar**.  
  
  