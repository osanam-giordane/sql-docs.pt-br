---
title: Extensão de servidores centrais de gerenciamento do SQL Server
titleSuffix: Azure Data Studio
description: Instalar e usar a extensão de servidores centrais de gerenciamento do SQL Server (versão prévia) para o Studio de dados do Azure
ms.custom: seodec18
ms.date: 06/06/2019
ms.reviewer: alayu; sstein
ms.prod: sql
ms.technology: azure-data-studio
ms.topic: conceptual
author: yualan
ms.author: alayu
ms.openlocfilehash: 03edfc5b6d95c5cd6497d96d7014641f3032fb84
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67959200"
---
# <a name="sql-server-central-management-servers-extension-preview"></a>Extensão de Servidores de Gerenciamento Central do SQL Server (versão prévia)
A extensão de servidores centrais de gerenciamento permite aos usuários armazenar uma lista de instâncias do SQL Server que é organizado em um ou mais grupos. As ações executadas usando um grupo CMS agir em todos os servidores no grupo de servidores.

Essa experiência está atualmente em visualização inicial. Relatar problemas e solicitações de recursos [aqui](https://github.com/microsoft/azuredatastudio/issues).

![Extensão CMS](media/sql-server-cms-extension/cms-list.png)

## <a name="install-the-sql-server-central-management-servers-extension"></a>Instalar a extensão de servidores centrais de gerenciamento do SQL Server

1. Para abrir o Gerenciador de extensões e acessar as **extensões** disponíveis, selecione o ícone de extensões ou selecione extensões no menu **Exibição**.
2. Selecione uma extensão disponível para exibir seus detalhes.
1. Selecione a extensão desejada (SQL Server Central Management Servers) e **instalar** -lo.

### <a name="how-do-i-start-central-management-servers"></a>Como começar a servidores de gerenciamento Central?
 Servidores centrais de gerenciamento podem ser exibidos clicando no ícone de conexões (Ctrl/Cmd + G). Na primeira vez que você baixe a extensão, o modo de exibição CMS será minimizado e abri-lo clicando em **servidores de gerenciamento Central**

## <a name="next-steps"></a>Próximas etapas
Para saber mais conceitualmente sobre servidores de gerenciamento Central, [você pode ler mais aqui.](https://docs.microsoft.com/sql/ssms/register-servers/create-a-central-management-server-and-server-group)


