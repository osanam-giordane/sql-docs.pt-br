---
title: Adicionar trechos de Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 901c7995-8eb5-4d12-8bb0-de0a922b48f8
caps.latest.revision: 9
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: b82d956905d55afb597a0dc4e31d299eebdc4309
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36005663"
---
# <a name="add-transact-sql-snippets"></a>Adicionar trechos de Transact-SQL
  Você pode adicionar seus próprios trechos de código Transact-SQL ao conjunto de trechos predefinidos incluídos em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="creating-a-transact-sql-snippet-file"></a>Criando um arquivo de trecho Transact-SQL  
 A primeira parte da criação de um trecho de código do [!INCLUDE[tsql](../../includes/tsql-md.md)] é criar um arquivo XML com o texto do seu trecho de código. O arquivo deve ter uma extensão .snippet e atender as requisitos do [Esquema de trechos de código](http://go.microsoft.com/fwlink/?LinkId=207504). Defina a linguagem do trecho como SQL.  
  
 Você pode usar os trechos predefinidos fornecidos com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como exemplos. Para encontrar os trechos predefinidos, abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selecione o menu **Ferramentas** e clique em **Gerenciador de Trechos de Código**. Selecione **SQL** na caixa de listagem **Linguagem** ; o caminho para os trechos do [!INCLUDE[tsql](../../includes/tsql-md.md)] será exibido na caixa **Local** .  
  
## <a name="registering-the-code-snippet"></a>Registrando o trecho de código  
 Após criar o arquivo de trecho, use o Gerenciador de Trechos de Código para registrar o trecho com o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. Você pode adicionar uma pasta que contém vários trechos ou importar trechos individuais para a pasta **Meus Trechos de Código** .  
  
## <a name="procedures"></a>Procedimentos  
  
#### <a name="adding-a-snippet-folder"></a>Adicionando uma pasta de trechos  
  
1.  Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
2.  Selecione o menu **Ferramentas** e clique em **Gerenciador de Trechos de Código**.  
  
3.  Clique no botão **Adicionar** .  
  
4.  Navegue até a pasta que contém seus trechos de código e clique no botão **Selecionar Pasta** .  
  
#### <a name="importing-a-snippet"></a>Importando um trecho  
  
1.  Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
2.  Selecione o menu **Ferramentas** e clique em **Gerenciador de Trechos de Código**.  
  
3.  Clique no botão **Importar** .  
  
4.  Navegue até a pasta que contém seu trecho, clique no arquivo .snippet e clique em **Abrir** .  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria um `TRY-CATCH` trecho com surround e o importa para [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
1.  Cole o código a seguir no bloco de notas e salve como um arquivo chamado TryCatch.snippet.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
    <_locDefinition xmlns="urn:locstudio">  
        <_locDefault _loc="locNone" />  
        <_locTag _loc="locData">Title</_locTag>  
        <_locTag _loc="locData">Description</_locTag>  
        <_locTag _loc="locData">Author</_locTag>  
        <_locTag _loc="locData">ToolTip</_locTag>  
       <_locTag _loc="locData">Default</_locTag>  
    </_locDefinition>  
    <CodeSnippet Format="1.0.0">  
    <Header>  
    <Title>TryCatch</Title>  
                            <Shortcut></Shortcut>  
    <Description>Example Snippet for Try-Catch.</Description>  
    <Author>SQL Server Books Online Example</Author>  
    <SnippetTypes>  
                                    <SnippetType>SurroundsWith</SnippetType>  
    </SnippetTypes>  
    </Header>  
    <Snippet>  
    <Declarations>  
                                    <Literal>  
                                    <ID>CatchCode</ID>  
                                    <ToolTip>Code to handle the caught error</ToolTip>  
                                    <Default>CatchCode</Default>  
                                    </Literal>  
    </Declarations>  
    <Code Language="SQL"><![CDATA[  
    BEGIN TRY  
  
    $selected$ $end$  
  
    END TRY  
    BEGIN CATCH  
  
    $CatchCode$  
  
    END CATCH;  
    ]]>  
    </Code>  
    </Snippet>  
    </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
2.  Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
3.  Selecione o menu **Ferramentas** e clique em **Gerenciador de Trechos de Código**.  
  
4.  Clique no botão **Importar** .  
  
5.  Navegue até a pasta que contém TryCatch.snippet, clique no arquivo TryCatch.snippet e clique em **Abrir** . Você não deve ter um trecho TryCatch na pasta **Meus Trechos de Código** .  
  
## <a name="see-also"></a>Consulte também  
 [Inserir trechos cercados com o Transact-SQL](insert-surround-with-transact-sql-snippets.md)  
  
  