---
title: Catalog. move_environment (banco de dados SSISDB) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: b3fb5242-3c4c-4a87-b3e5-beb22fbab053
caps.latest.revision: 14
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: e08328e0baccaa9098d8647b50c6133de2504912
ms.contentlocale: pt-br
ms.lasthandoff: 09/26/2017

---
# <a name="catalogmoveenvironment-ssisdb-database"></a>catalog.move_environment (Banco de Dados SSISDB)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Move um ambiente de uma pasta para outra no catálogo do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
## <a name="syntax"></a>Sintaxe  
  
```tsql  
move_environment [ @source_folder = ] source_folder  
    , [ @environment_name = ] environment_name  
    , [ @destination_folder = ] destination_folder  
```  
  
## <a name="arguments"></a>Argumentos  
 [ @source_folder =] *source_folder*  
 O nome da pasta de origem onde o ambiente reside antes da movimentação. O *source_folder* é **nvarchar (128)**.  
  
 [ @environment_name =] *environment_name*  
 O nome do ambiente que deve ser movido. O *environment_name* é **nvarchar (128)**.  
  
 [ @destination_folder =] *destination_folder*  
 O nome da pasta de destino onde o ambiente reside após a movimentação. O *destination_folder* é **nvarchar (128)**.  
  
## <a name="return-code-value"></a>Valor do código de retorno  
 0 (êxito)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Nenhuma  
  
## <a name="permissions"></a>Permissões  
 Este procedimento armazenado exige uma das seguintes permissões:  
  
-   Permissões READ e MODIFY no ambiente  
  
-   Associação de **ssis_admin** função de banco de dados  
  
-   Associação de **sysadmin** função de servidor  
  
## <a name="errors-and-warnings"></a>Erros e avisos  
 A lista a seguir descreve algumas condições que podem gerar um erro ou um aviso:  
  
-   O ambiente não existe na pasta de origem  
  
-   A pasta de destino já tem um ambiente com o mesmo nome  
  
-   O usuário não tem as permissões apropriadas  
  
## <a name="remarks"></a>Comentários  
 As referências de ambiente de projetos não seguem o ambiente durante a movimentação. As referências de ambiente devem ser atualizadas de forma correspondente. Esse procedimento armazenado terá êxito mesmo que as referências de ambiente sejam desfeitas pela movimentação de um ambiente. As referências de ambiente devem ser atualizadas depois da conclusão desse procedimento armazenado.  
  
> [!NOTE]  
>  Um projeto pode ter referências de ambiente relativas ou absolutas. As referências relativas fazem referência ao ambiente pelo nome. Essas referências requerem que o ambiente resida na mesma pasta do projeto. As referências absolutas fazem referência ao ambiente por nome e pasta. Essas referências fazem referência a ambientes que residam em uma pasta diferente da pasta do projeto.  
  
  