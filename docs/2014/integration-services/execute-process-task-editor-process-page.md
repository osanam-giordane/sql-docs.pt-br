---
title: Execute o Editor da tarefa de processo (página processo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executeprocesstask.process.f1
helpviewer_keywords:
- Execute Process Task Editor
ms.assetid: 0fc22406-e79b-47a4-a7e4-108d4ce6202f
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: fa799404777f8f0ef0a8a07a81c8c7961c636004
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66059026"
---
# <a name="execute-process-task-editor-process-page"></a>Execute Process Task Editor (Process Page)
  Use a página **Processo** da caixa de diálogo **Editor da Tarefa Executar Processo** , para configurar as opções que executam o processo. As opções incluem o executável a ser utilizado, seu local, argumentos do prompt de comando e as variáveis que fornecem entrada e capturam a saída.  
  
 Para obter informações sobre essa tarefa, consulte [Execute Process Task](control-flow/execute-process-task.md).  
  
## <a name="options"></a>Opções  
 **RequireFullFileName**  
 Indique se a tarefa deve falhar se o executável não for localizado no local especificado.  
  
 **Executável**  
 Digite o nome do executável a utilizar.  
  
 **Argumentos**  
 Forneça argumentos do prompt de comando.  
  
 **WorkingDirectory**  
 Digite o caminho da pasta que contém o executável ou clique no botão Procurar **(…)** e localize a pasta.  
  
 **StandardInputVariable**  
 Selecione a variável para fornecer a entrada ao processo ou clique em \<**Nova variável...** > para criar uma nova variável:  
  
 **Tópicos relacionados:**  [Adicionar Variável](../../2014/integration-services/add-variable.md)  
  
 **StandardOutputVariable**  
 Selecione uma variável para capturar a saída do processo ou clique em \<**Nova variável...** > para criar uma nova variável.  
  
 **StandardErrorVariable**  
 Selecione uma variável para capturar a saída de erro do processador ou clique em \<**Nova variável...** > para criar uma nova variável.  
  
 **FailTaskIfReturnCodeIsNotSuccessValue**  
 Indique se a tarefa deve falhar caso o código de saída do processo seja diferente do valor especificado em **SuccessValue**.  
  
 **SuccessValue**  
 Especifique o valor retornado pelo executável para indicar êxito. Por padrão, esse valor está definido como **0**.  
  
 **TimeOut**  
 Especifique o número de segundos em que o processo pode ser executado. Um valor **0** indica que não é usado nenhum valor de tempo limite e o processo é executado até ser concluído ou até ocorrer um erro.  
  
 **TerminateProcessAfterTimeOut**  
 Indique se o processo é forçado a terminar após o tempo limite especificado pela opção **TimeOut** . Esta opção só estará disponível se **TimeOut** não for **0**.  
  
 **WindowStyle**  
 Especifique o estilo de janela no qual executar o processo.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Página Expressões](expressions/expressions-page.md)  
  
  
