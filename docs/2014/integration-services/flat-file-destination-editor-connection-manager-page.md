---
title: Editor de destino (página Gerenciador de Conexão) do arquivo simples | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledestadapter.connection.f1
helpviewer_keywords:
- Flat File Destination Editor
ms.assetid: b01571fa-bc19-4742-8eed-ac163172a919
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 429ba1f8a12a4bd574a8304d18311a6e6e4efc79
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66058703"
---
# <a name="flat-file-destination-editor-connection-manager-page"></a>Editor de Destino de Arquivo Simples (página Gerenciador de Conexões)
  Use a página do **Gerenciador de Conexões** da caixa de diálogo do **Editor de Destino de Arquivo Simples** para selecionar a conexão de arquivo simples do destino e especificar se irá substituir ou anexar ao arquivo de destino existente. O destino de arquivo simples grava dados em um arquivo de texto. Esse arquivo de texto pode ser em formato delimitado, de largura fixa, de largura fixa com delimitador de linha ou em formato irregular à direita.  
  
 Para saber mais sobre o destino de Arquivo Simples, consulte [Flat File Destination](data-flow/flat-file-destination.md).  
  
## <a name="options"></a>Opções  
 **Gerenciador de conexões de arquivo simples**  
 Selecione um gerenciador de conexões existente usando a caixa de listagem ou crie uma nova conexão clicando em **Novo**.  
  
 **Nova**  
 Crie uma nova conexão utilizando as caixas de diálogo **Formato de Arquivo Simples** e **Editor do Gerenciador de Conexões de Arquivos Simples** .  
  
 Além dos formatos padrão de arquivo simples: delimitado, de largura fixa e irregular à direita, a caixa de diálogo **Formato de Arquivo Simples** tem uma quarta opção, **Largura fixa com delimitadores de linha**. Esta opção representa um caso especial do formato irregular à direita no qual o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] adiciona uma coluna fictícia como a coluna final de dados. Essa coluna fictícia assegura que a coluna final tenha uma largura fixa.  
  
 A opção **Largura fixa com delimitadores de linha** não está disponível no **Editor do Gerenciador de Conexões de Arquivos Simples**. Se necessário, você pode emular esta opção no editor. Para emular esta opção, na página **Geral** do **Editor do Gerenciador de Conexões de Arquivos Simples**, em **Formato**, selecione **Irregular à direita**. Na página **Avançado** do editor, adicione uma nova coluna fictícia como a coluna final de dados.  
  
 **Substituir dados no arquivo**  
 Indique se irá substituir um arquivo existente ou acrescentar dados a ele.  
  
 **Cabeçalho**  
 Digite um bloco de texto a ser inserido no arquivo antes que qualquer dado seja gravado. Use esta opção para incluir informações adicionais, como cabeçalhos de coluna.  
  
 **Visualização**  
 Visualize os resultados usando a caixa de diálogo **Exibição de Dados** . A visualização pode exibir até 200 linhas.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor de Destino de Arquivo Simples &#40;Página Mapeamentos&#41;](../../2014/integration-services/flat-file-destination-editor-mappings-page.md)  
  
  
