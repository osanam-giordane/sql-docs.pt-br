---
title: Elemento de banco de dados para servidor (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 5817a6d32ff94aaba7e4c0a573e6cd6a5fd586dc
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68116925"
---
# <a name="database-element-for-server-dta"></a>Elemento de banco de dados para servidor (DTA)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Especifica o banco de dados que deseja ajustar em um servidor específico.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum.|  
|Valor padrão|Nenhuma.|  
|Ocorrência|Exigido uma ou mais vezes por elemento **Server** .|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elementos|  
|------------------|--------------|  
|Elemento pai|[Elemento Server &#40;DTA&#41;](../../tools/dta/server-element-dta.md)|  
|Elementos filho|[Elemento Name para Database &#40;DTA&#41;](../../tools/dta/name-element-for-database-dta.md)<br /><br /> [Elemento Schema para Database &#40;DTA&#41;](../../tools/dta/schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a>Remarks  
 Esse elemento tem o nome **DatabaseDetailsTypecomplexType** no Esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados. Não confunda este elemento **Database** com aquele cujo pai raiz é o elemento **Configuration**. Para obter mais informações, veja [Elemento Database para configuração &#40;DTA&#41;](../../tools/dta/database-element-for-configuration-dta.md).  
  
## <a name="example"></a>Exemplo  
 Para obter um exemplo de uso desse elemento **Database** , veja [Elemento Server &#40;DTA&#41;](../../tools/dta/server-element-dta.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
