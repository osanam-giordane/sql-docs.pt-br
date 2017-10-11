---
title: "Atualizado – documentos do SSMS para SQL Server | Microsoft Docs"
description: "Trechos de exibição de conteúdo atualizado com alterações recentes na documentação, para o SSMS (SQL Server Management Studio) para Microsoft SQL Server."
services: na
documentationcenter: 
author: MightyPen
manager: jhubbard
editor: 
ms.service: na
ms.topic: updart-autogen
ms.technology: database-engine
ms.custom: UpdArt.exe
ms.tgt_pltfrm: na
ms.devlang: na
ms.date: 09/27/2017
ms.author: genemi
ms.workload: ssms-sql-server-management-studio
ms.translationtype: HT
ms.sourcegitcommit: 834bba08c90262fd72881ab2890abaaf7b8f7678
ms.openlocfilehash: 15d706d713a813af8831c191aca85781a9c98472
ms.contentlocale: pt-br
ms.lasthandoff: 10/02/2017

---
# <a name="new-and-recently-updated-sql-server-management-studio-ssms-for-sql-server"></a>Novos e atualizados recentemente: SSMS (SQL Server Management Studio) para SQL Server



A Microsoft atualiza alguns de seus artigos existentes no site de documentação [Docs.Microsoft.com](http://docs.microsoft.com/) todos os dias. Este artigo exibe trechos de artigos atualizados recentemente. Links para novos artigos também podem ser listados.

Este artigo é gerado por um programa que é reexecutado periodicamente. Ocasionalmente, um trecho pode aparecer com formatação imperfeita ou como markdown do artigo de origem. Imagens nunca são exibidas aqui.

Atualizações recentes são relatadas para o intervalo de datas e o assunto a seguir:



- *Intervalo de datas das atualizações:* &nbsp; **11-09-2017** &nbsp; até &nbsp; **27-09-2017**
- *Área de assunto:* &nbsp; **SSMS (SQL Server Management Studio)**.




&nbsp;

## <a name="new-articles-created-recently"></a>Novos artigos criados recentemente

Os links a seguir direcionam para novos artigos que foram adicionados recentemente.


***Não existem novos artigos a serem listados no momento.***



&nbsp;

## <a name="updated-articles-with-excerpts"></a>Artigo atualizado com trechos

Esta seção exibe os trechos de atualizações coletados de artigos que passaram por uma atualização extensa recentemente.

Os trechos exibidos aqui aparecerão separados de seu contexto de semântico apropriado. Além disso, às vezes um trecho é separado da sintaxe de markdown importante que circunda no artigo real. Portanto, esses trechos servem apenas como orientações gerais. Os trechos só mostram a você se vale a pena clicar e visitar o artigo real conforme seus interesses.

Por essas e outras razões, não copie o código desses trechos, nem considere-os como verdade exata. Em vez disso, visite o artigo real.





&nbsp;

<a name="compactupdatedlist"/>

### <a name="compact-list-of-articles-updated-recently"></a>Lista compacta dos artigos atualizados recentemente

Essa lista compacta fornece links para todos os artigos atualizados listados na seção Trechos.

1. [Baixar o módulo do PowerShell do SQL Server](#TitleNum_1)




&nbsp;

&nbsp;

<a name="TitleNum_1"/>

### <a name="1-nbsp-download-sql-server-powershell-moduledownload-sql-server-ps-modulemd"></a>1. &nbsp; [Baixar o módulo do PowerShell do SQL Server](download-sql-server-ps-module.md)

*Atualizado: 26-09-2017* &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; 

<!-- Source markdown line 37.  ms.author= "sstein".  -->

&nbsp;


<!-- git diff --ignore-all-space --unified=0 3953870af5dca04eb3753e88a34fae69d365d6eb 10085b77284e957e34e5302975e5bc9cfd23fd0c  (PR=105  ,  Filename=download-sql-server-ps-module.md  ,  Dirpath=docs\ssms\  ,  MergeCommitSha40=ed34b77d3f23e46c7736ef96c775990261290870) -->



Se estiver como administrador e a instalação do módulo para todos os usuários do computador

> Install-Module -Name SqlServer -AllowClobber

Se não é possível executar como administrador ou instalar somente para o usuário atual

> Install-Module -Name SqlServer -Scope CurrentUser -AllowClobber

Quando as versões atualizadas do módulo SqlServer estão disponíveis, você poderá atualizar a versão usando o comando Update-Module

> Update-Module -Name SqlServer

Para exibir as versões do módulo instalado no computador, você pode usar

> Get-Module SqlServer -ListAvailable

Para usar uma versão específica do módulo em seus scripts, você pode importá-lo com

> Import-Module SqlServer -Version 21.0.17178








## <a name="similar-articles"></a>Artigos Semelhantes

<!--  HOW TO:
    Refresh this file's line items with the latest 'Count-in-Similars*' content.
    Then run Run-533-*.BAT
-->

Esta seção lista artigos muito semelhantes a artigos atualizados recentemente em outras áreas de assunto, em nosso repositório público GitHub.com: [MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs/).

#### <a name="subject-areas-which-do-have-new-or-recently-updated-articles"></a>Áreas de assunto que têm artigos novos ou atualizados recentemente

- [Novo + atualizado (0 + 1): documentos sobre o **Advanced Analytics para SQL**](../advanced-analytics/new-updated-advanced-analytics.md)
- [Novo + Atualizado (0+1): documentos sobre o **Analysis Services para SQL**](../analysis-services/new-updated-analysis-services.md)
- [Novo + Atualizado (4+1): documentos sobre o **Mecanismo de Banco de Dados para SQL**](../database-engine/new-updated-database-engine.md)
- [Novo + Atualizado (17+0): documentos sobre o **Integration Services para SQL**](../integration-services/new-updated-integration-services.md)
- [Novo + Atualizado (3+0): documentos sobre o **Linux para SQL**](../linux/new-updated-linux.md)
- [Novo + Atualizado (1+1): documentos sobre os **Bancos de Dados Relacionais para SQL**](../relational-databases/new-updated-relational-databases.md)
- [Novo + Atualizado (2+0): documentos sobre o **Reporting Services para SQL**](../reporting-services/new-updated-reporting-services.md)
- [Novo + Atualizado (0+1): documentos sobre o **SSMS (SQL Server Management Studio)**](../ssms/new-updated-ssms.md)
- [Novo + Atualizado (0+1): documentos sobre o **Transact-SQL**](../t-sql/new-updated-t-sql.md)

#### <a name="subject-areas-which-have-no-new-or-recently-updated-articles"></a>Áreas de assunto que não têm nenhum artigo novo ou atualizado recentemente

- [Novo + atualizado (0 + 0): documentos do **ADO (ActiveX Data Objects) para SQL**](../ado/new-updated-ado.md)
- [Novo + Atualizado (0 + 0): documentos de **Conexão ao SQL**](../connect/new-updated-connect.md)
- [Novo + atualizado (0 + 0): documentos do **Data Quality Services para SQL**](../data-quality-services/new-updated-data-quality-services.md)
- [Novo + atualizado (0 + 0): documentos de **Extensões DMX (Data Mining) para SQL**](../dmx/new-updated-dmx.md)
- [Novo + Atualizado (0+0): documentos sobre o **MDS (Master Data Services) para SQL**](../master-data-services/new-updated-master-data-services.md)
- [Novo + atualizado (0 + 0): documentos de **Expressão MDX para SQL**](../mdx/new-updated-mdx.md)
- [Novo + atualizado (0 + 0): documentos do **ODBC (Open Database Connectivity) para SQL**](../odbc/new-updated-odbc.md)
- [Novo + atualizado (0 + 0): documentos do **PowerShell para SQL**](../powershell/new-updated-powershell.md)
- [Novo + atualizado (0 + 0): documentos de **Exemplos para SQL**](../sample/new-updated-sample.md)
- [Novo + Atualizado (0 + 0): documentos do **Microsoft SQL Server**](../sql-server/new-updated-sql-server.md)
- [Novo + Atualizado (0 + 0): documentos do **SQL Server Data Tools (SSDT)**](../ssdt/new-updated-ssdt.md)
- [Novo + atualizado (0 + 0): documentos do **SSMA (SQL Server Migration Assistant)**](../ssma/new-updated-ssma.md)
- [Novo + Atualizado (0 + 0): documentos de **Ferramentas para SQL**](../tools/new-updated-tools.md)
- [Novo + atualizado (0 + 0): documentos do **XQuery para SQL**](../xquery/new-updated-xquery.md)


