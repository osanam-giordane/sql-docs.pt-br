---
title: Gerenciando Assemblies de integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- database objects [CLR integration], assemblies
- common language runtime [SQL Server], assemblies
- assemblies [CLR integration], managing
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 1e65bb5c651862a82d78faede158234d20392c1c
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "62919689"
---
# <a name="managing-clr-integration-assemblies"></a>Gerenciando assemblies de integração CLR
  O código gerenciado é compilado e implantado em unidades chamadas de assembly. Um assembly é empacotado como uma DLL ou um arquivo executável (.exe). Um arquivo executável pode ser executado sozinho, mas uma DLL precisa ser hospedada em um aplicativo existente. Assemblies DLL gerenciados podem ser carregados no e hospedados por [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)]. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o banco de dados usando a instrução CREATE ASSEMBLY, antes que possa ser carregado no processo e usado. Os assemblies também podem ser atualizados de uma versão mais recente usando a instrução ALTER ASSEMBLY ou removidos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a instrução DROP ASSEMBLY.  
  
 As informações do assembly são armazenadas na tabela `sys.assembly_files` no banco de dados em que o assembly foi instalado. A tabela `sys.assembly_files` contém as colunas a seguir:  
  
|coluna|Descrição|  
|------------|-----------------|  
|assembly_id|O identificador definido para o assembly. Este número é atribuído a todos os objetos relacionados ao mesmo assembly.|  
|nome|O nome do objeto.|  
|file_id|Um número que identifica cada objeto, com o primeiro objeto associado a um determinado `assembly_id` recebendo o valor de 1. Se vários objetos forem associados ao mesmo `assembly_id`, cada valor `file_id` subsequente será incrementado em 1.|  
|content|A representação hexadecimal do assembly ou arquivo.|  
  
## <a name="in-this-section"></a>Nesta seção  
 [Criando um assembly](creating-an-assembly.md)  
 Discute a criação de assemblies SAFE, EXTERNAL_ACCESS e UNSAFE CLR no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 [Alterando um assembly](altering-an-assembly.md)  
 Descreve a atualização de assemblies CLR no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 [Descarte de um assembly](dropping-an-assembly.md)  
 Discute o descarte de assemblies CLR do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Consulte também  
 [Segurança da integração CLR](../security/clr-integration-security.md)   
 [Segurança de acesso do código da integração CLR](../security/clr-integration-code-access-security.md)  
  
  
