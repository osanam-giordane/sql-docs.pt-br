---
title: catalog.master_properties (Banco de dados SSISDB) | Microsoft Docs
ms.custom: ''
ms.date: 12/16/2016
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 00bfa716-5390-48e3-b30c-d954d5e0be47
author: janinezhang
ms.author: janinez
ms.openlocfilehash: 537b9a1d1b0fb84ba26c56aeb2f897d268bb2d03
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68104837"
---
# <a name="catalogmasterproperties-ssisdb-database"></a>catalog.master_properties (Banco de dados SSISDB)

[!INCLUDE[ssis-appliesto](../../includes/ssis-appliesto-ssvrpluslinux-asdb-asdw-xxx.md)]


[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

Exibe as propriedades do Mestre do Scale Out [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].

|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|property_name|**nvarchar(256)**|O nome da propriedade mestre de expansão.|  
|property_value|**nvarchar(max)**|O valor da propriedade mestre de expansão.|

## <a name="remarks"></a>Remarks
Esta exibição mostra uma linha para cada propriedade mestre de expansão. As propriedades mostradas por esta exibição incluem o seguinte:

|Nome da propriedade|Descrição|  
|-------------------|-----------------| 
|**CLUSTER_LOGDB_SERVER**|O SQL Server no qual banco de dados está localizado.|
|**LAST_ONLINE_TIME**|A última vez em que o Mestre do Scale Out esteve online.|
|**MACHINE_IP**|O IP do computador.|
|**MACHINE_NAME**|O nome do computador.|
|**MASTER_ADDRESS**|O ponto de extremidade do Mestre do Scale Out.|
|**MASTER_SERVICE_PORT**|A porta no ponto de extremidade do Mestre do Scale Out.|
|**SSLCERT_THUMBPRINT**|A impressão digital do certificado do Mestre do Scale Out.|

## <a name="permissions"></a>Permissões
Todos os membros da função de banco de dados público têm permissão de leitura para esta exibição. 
