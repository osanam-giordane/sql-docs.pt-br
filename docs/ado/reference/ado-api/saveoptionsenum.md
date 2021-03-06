---
title: SaveOptionsEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- SaveOptionsEnum
helpviewer_keywords:
- SaveOptionsEnum enumeration [ADO]
ms.assetid: 59339100-6e29-48d1-aea3-6873796d186b
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 807a8d7e5757a2caf76f100a1ae51c4a8a3f4e98
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67931146"
---
# <a name="saveoptionsenum"></a>SaveOptionsEnum
Especifica se um arquivo deve ser criado ou substituído quando salvar uma [Stream](../../../ado/reference/ado-api/stream-object-ado.md) objeto. Os valores podem ser **adSaveCreateNotExist** ou **adSaveCreateOverWrite**...  
  
|Constante|Valor|Descrição|  
|--------------|-----------|-----------------|  
|**adSaveCreateNotExist**|1|Padrão. Cria um novo arquivo se o arquivo especificado o *FileName* parâmetro ainda não existir.|  
|**adSaveCreateOverWrite**|2|Substitui o arquivo com os dados da aberto no momento **Stream** do objeto, se o arquivo especificado pela *Filename* parâmetro já existe. Se o arquivo especificado pela *Filename* parâmetro não existe, um novo arquivo é criado.|  
  
## <a name="adowfc-equivalent"></a>Equivalente do ADO/WFC  
 Essas constantes não têm equivalentes do ADO/WFC.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Método SaveToFile](../../../ado/reference/ado-api/savetofile-method.md)
