---
title: 'Lição 2: Preparando a pasta de instantâneo | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f286cde9-c0d0-43ef-b7ba-53c3cbb8906c
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: 5ec45b0a29f9f4c8fb1e6a9b683e47797f194885
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "62721017"
---
# <a name="lesson-2-preparing-the-snapshot-folder"></a>Lição 2: Preparando a pasta de instantâneo
  Nesta lição, você aprenderá a configurar a pasta do instantâneo, usada para criar e armazenar o instantâneo de publicação.  
  
### <a name="to-create-a-share-for-the-snapshot-folder-and-assign-permissions"></a>Para criar um compartilhamento para a pasta de instantâneo e atribuir permissões  
  
1.  No Windows Explorer, vá para a pasta de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . O local padrão é C:\Arquivos de Programa\Microsoft SQL Server\MSSQL.X\MSSQL\Data.  
  
2.  Crie uma nova pasta chamada **repldata**.  
  
3.  Clique com o botão direito do mouse nessa pasta e clique em **Propriedades**.  
  
4.  Na guia **Compartilhamento** da caixa de diálogo **Propriedades de repldata** , clique em **Compartilhar**.  
  
5.  Na caixa de diálogo **Compartilhamento de Arquivos** , clique em **Compartilhar**e clique em **Concluído**.  
  
6.  Na guia **Segurança** , clique em **Editar**.  
  
7.  Na caixa de diálogo **Permissões** , clique em **Adicionar**. Na caixa de texto **Selecionar Usuário, Computadores, Conta de Serviço ou Grupos**, digite o nome da conta do Snapshot Agent criado na Lição 1, como \<_Machine_Name>_ **\repl_snapshot**, em que \<*Machine_Name>* é o nome do Publicador. Clique em **Verificar Nomes**e em **OK**.  
  
8.  Repita a etapa anterior para adicionar permissões para o Agente de Distribuição, como \<_Machine_Name>_ **\repl_distribution** e para o Agente de Mesclagem, como \<_Machine_Name>_ **\repl_merge**.  
  
9. Verifique se as permissões a seguir são permitidas:  
  
    -   repl_snapshot - Controle total  
  
    -   repl_distribution - Leitura  
  
    -   repl_merge - Leitura  
  
10. Clique em **OK** para fechar a caixa de diálogo **Propriedades de repldata** e criar o compartilhamento de repldata.  
  
## <a name="next-steps"></a>Próximas etapas  
 Você configurou com êxito o compartilhamento da pasta de instantâneo. A seguir, você configurará a distribuição. Confira [Lição 3: Configurando a distribuição](lesson-3-configuring-distribution.md).  
  
## <a name="see-also"></a>Consulte também  
 [Proteger uma pasta de instantâneo](security/secure-the-snapshot-folder.md)  
  
  
