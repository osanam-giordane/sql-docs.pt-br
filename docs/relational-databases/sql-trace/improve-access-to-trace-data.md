---
title: Aprimorar o acesso aos dados de rastreamento | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Profiler [SQL Server Profiler], space
- SQL Server Profiler, space
- space [SQL Server], SQL Server Profiler
ms.assetid: c260c000-fd53-4831-993f-df6894f3228b
caps.latest.revision: 14
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: c20ce109f48cf8791ddb3116258c52b0d3ba70e8
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="improve-access-to-trace-data"></a>Aprimorar o acesso aos dados de rastreamento
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] usa o espaço no diretório **temp** para aprimorar o acesso aos dados de rastreamento. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] exige, pelo menos, 10 MB (megabytes) de espaço livre. Se o espaço livre cair abaixo de 10 MB enquanto você estiver usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], todas as funções do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] serão interrompidas.  
  
 Quando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] usar o espaço no diretório **temp** , este uso de espaço pode fazer o diretório **temp** crescer rapidamente. Para evitar problemas com a expansão de arquivos, você pode colocar o diretório **temp** em uma unidade que não é unidade de sistema alterando o valor da variável de ambiente TEMP.  
  
 O procedimento a seguir descreve como alterar o valor da variável de ambiente TEMP na maioria dos sistemas operacionais Microsoft Windows. Para obter mais informações sobre como definir variáveis de ambiente, consulte a documentação de seu sistema operacional Windows.  
  
### <a name="to-change-the-temp-environment-variable-in-windows-operating-systems"></a>Para alterar a variável de ambiente TEMP em sistemas operacionais Windows  
  
1.  No menu **Iniciar** , escolha **Painel de Controle**e clique em **Sistema**.  
  
2.  Na caixa de diálogo **Propriedades do Sistema** , clique na guia **Avançado** e clique em **Variáveis de Ambiente**.  
  
3.  Role para baixo a lista de **Variáveis do sistema**, selecione a linha que corresponde à variável **TEMP** e clique em **Editar**.  
  
4.  Na caixa de diálogo **Editar Variável do Sistema** , insira o caminho e o nome da unidade e diretório em que você deseja que o diretório **temp** esteja localizado.  
  
5.  Clique em **OK** para salvar a alteração.  
  
## <a name="see-also"></a>Consulte também  
 [Iniciar o SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md)   
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  