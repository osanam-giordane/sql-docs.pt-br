---
title: "Exportar informações de servidor registrado (SQL Server Management Studio) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.exportregisteredservers.f1
helpviewer_keywords:
- Registered Servers [SQL Server], exporting
- exporting registered server information
- transferring registered server information
ms.assetid: b65e168f-b6bf-489c-b8ad-3b8644acf0b6
caps.latest.revision: 27
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 5db067d5a2fe5bbf9953484c9a999ed7b1fcddae
ms.openlocfilehash: 384095b7fc904f9e8d57cb3d71a1bd074900c86a
ms.contentlocale: pt-br
ms.lasthandoff: 07/31/2017

---
# <a name="export-registered-server-information-sql-server-management-studio"></a>Exportar informações de servidor registrado (SQL Server Management Studio)
  Este tópico descreve como salvar e exportar informações de servidor registrado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]e distribuí-las para outros empregados ou servidores. É possível usar esse recurso de exportação para apresentar uma interface com o usuário consistente em computadores múltiplos.  
  
 Exportar e, depois, importar os arquivos de Servidores Registrados permite que você configure facilmente vários computadores com os mesmos servidores em Servidores Registrados. Isso é útil quando se gerencia um grande número de servidores de computadores em diversos locais ou quando você deseja configurar um usuário menos experiente com configurações de conexão básica.  
  
> [!NOTE]  
>  Os registros de servidores que usam a autenticação do SQL Server armazenam senhas por usuário. Depois de exportar e importar os registros de servidores, os usuários devem digitar a senha para cada servidor quando se conectarem pela primeira vez, armazenando as senhas em suas listas de servidores registrados. Isso não é necessário para servidores registrados que usam a autenticação do Windows.  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-export-registered-server-information"></a>Para exportar informações de servidor registrado  
  
1.  Em Servidores Registrados, clique com o botão direito do mouse em um grupo de servidores e clique em **Exportar**.  
  
    > [!NOTE]  
    >  Você pode exportar um servidor individual, toda a árvore de servidores registrados ou um subconjunto da árvore de servidores registrados.  
  
2.  Na caixa de diálogo **Exportar Servidores Registrados** , faça as seguintes seleções:  
  
     **Grupo de servidor**  
     Especifique o grupo de servidor que será exportado. Exporte todos os servidores registrados, servidores registrados em um grupo de servidores específicos ou um único servidor registrado para o arquivo de exportação. A funcionalidade de exportação é recursiva; por exemplo, se o grupo de servidores A contiver o grupo de servidores B, e o grupo de servidores B contiver os grupos de servidores C e D, a exportação do grupo de servidores A exportará todas as entradas em A, B, C e D.  
  
     O grupo de servidores exibe somente os grupos da árvore atual de servidores registrados.  
  
     **Arquivo de exportação**  
     Digite o nome do arquivo de exportação na caixa de texto ou use o botão Procurar (**...**) para localizar um arquivo de exportação no computador cliente. Se você selecionar um arquivo existente, a informação de servidor registrado será anexada ao arquivo. Use a extensão .regsrvr. Se você quiser que as informações do servidor registrado estejam disponíveis para outros usuários ou outro computador, você poderá salvar o arquivo na rede. Outros usuários podem acessar o arquivo e podem importar parte ou todas as informações do servidor registrado. Se você selecionar um arquivo existente como o arquivo de exportação, o conteúdo do arquivo será substituído pelas informações de registro do servidor.  
  
     **Não inclua nomes de usuário e senhas no arquivo de exportação**  
     Exclua nomes de usuário ao exportar o arquivo.  
  
    > [!IMPORTANT]  
    >  Embora os arquivos de exportação sejam criptografados, se nomes de usuários e senhas da autenticação do SQL Server forem incluídas no arquivo, o acesso ao arquivo deve ser cuidadosamente controlado. Portanto, os nomes de usuários e senhas são excluídos do arquivo de exportação por padrão.  
  
## <a name="see-also"></a>Consulte também  
 [Importar informações de servidor registrado &#40;SQL Server Management Studio&#41;](../../tools/sql-server-management-studio/import-registered-server-information-sql-server-management-studio.md)   
 [Criar um novo servidor registrado &#40;SQL Server Management Studio&#41;](../../tools/sql-server-management-studio/create-a-new-registered-server-sql-server-management-studio.md)  
  
  