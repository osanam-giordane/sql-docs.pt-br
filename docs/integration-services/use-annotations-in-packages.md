---
title: "Usar anotações em pacotes | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- self-documenting packages
- adding annotations
- annotations [Integration Services]
ms.assetid: 48c8ed9a-b10d-490c-9ba7-4b77aa44e3dd
caps.latest.revision: 42
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: dabeecf1a4e2715bf4ccd214ac21ff3311f27411
ms.contentlocale: pt-br
ms.lasthandoff: 09/26/2017

---
# <a name="use-annotations-in-packages"></a>Usar anotações em pacotes
  O [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer fornece anotações, que você pode usar para fazer pacotes de autodocumentação e mais fáceis de entender e manter. Você pode adicionar anotações ao fluxo de controle, fluxo de dados e superfícies de design do manipulador de eventos do [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer. As anotações podem conter qualquer tipo de texto e são úteis para adicionar rótulos, comentários e outras informações descritivas para um pacote. As anotações são um recurso de tempo de design apenas. Por exemplo, elas não são gravadas nos logs.  
  
 Quando você pressiona ENTER, o texto é quebrado para a próxima linha. A caixa de anotação automaticamente aumenta de tamanho à medida que você adiciona linhas de texto. As anotações de pacote são persistidas como texto não criptografado na seção CDATA do arquivo de pacote.  
  
 Para obter mais informações sobre as alterações ao formato do arquivo de pacote, consulte [Formato do pacote SSIS](http://msdn.microsoft.com/library/cfe0e5dc-5be3-4222-b721-fe83665edd94).  
  
 Quando você salva o pacote, o [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer salva as anotações no pacote.  
  
## <a name="add-an-annotation-to-a-package"></a>Adicionar uma anotação a um pacote  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote no qual deseja adicionar uma anotação.  
  
2.  No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.  
  
3.  No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique com o botão direito do mouse em qualquer lugar da superfície de design da guia **Fluxo de Controle**, **Fluxo de Dados**, ou **Manipulador de Eventos** e clique em **Adicionar Anotação**. Um bloco de texto aparece na superfície de design da guia.  
  
4.  Adicionar texto.  
  
    > [!NOTE]  
    >  Se você não adicionar nenhum texto, o bloco de texto será removido ao se clicar fora do bloco.  
  
5.  Para alterar o tamanho ou o formato do texto na anotação, clique com o botão direito do mouse na anotação e clique em **Definir Fonte da Anotação de Texto**.  
  
6.  Para adicionar uma linha adicional de texto, pressione ENTER.  
  
     A caixa de anotação automaticamente aumenta de tamanho à medida que você adiciona linhas de texto.  
  
7.  Para adicionar uma anotação a um grupo, clique com o botão direito do mouse na anotação e clique em **Grupo**.  
  
8.  Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Tudo**.  