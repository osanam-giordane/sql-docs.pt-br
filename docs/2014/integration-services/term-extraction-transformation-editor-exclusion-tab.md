---
title: Editor de transformação extração de termos (guia exclusão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.dts.designer.termextraction.inclusionexclusion.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 90110d95-fd97-4542-9cda-832c86606130
caps.latest.revision: 27
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: fc7ff9ebc47db5a460113330f7b950e783359d59
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36116928"
---
# <a name="term-extraction-transformation-editor-exclusion-tab"></a>Editor de Transformação Extração de Termos (guia Exclusão)
  Use a guia **Exclusão** da caixa de diálogo do **Editor de Transformação Extração de Termos** para definir uma conexão com uma tabela de exclusão e especificar as colunas que contêm termos de exclusão.  
  
 Para saber mais sobre a transformação Extração de Termos, consulte [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).  
  
## <a name="options"></a>Opções  
 **Usar termos de exclusão**  
 Indique se devem ser excluídos termos específicos durante uma extração de termos especificando uma coluna que contém termos de exclusão. Você deve especificar as seguintes propriedades de origem caso opte por excluir termos.  
  
 **Gerenciador de conexões OLE DB**  
 Selecione um gerenciador de conexões OLE DB existente ou crie uma nova conexão clicando em **Novo**.  
  
 **Nova**  
 Crie uma nova conexão com um banco de dados usando a caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** .  
  
 **Tabela ou exibição**  
 Selecione a tabela ou exibição que contém os termos de exclusão.  
  
 **Coluna**  
 Selecione a coluna na tabela ou exibição que contém os termos de exclusão.  
  
 **Configurar Saída de Erro**  
 Use a caixa de diálogo [Configurar Saída de Erro](../../2014/integration-services/configure-error-output.md) para especificar tratamento de erro em linhas que causam erros.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor de transformação extração de termos &#40;guia extração de termos&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md)   
 [Editor de transformação extração de termos &#40;guia Avançado&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md)   
 [Transformação Pesquisa de Termos](data-flow/transformations/lookup-transformation.md)  
  
  