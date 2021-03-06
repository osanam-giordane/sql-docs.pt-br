---
title: Gerar elementos para valores NULL com o parâmetro XSINIL | Microsoft Docs
ms.custom: fresh2019may
ms.date: 05/22/2019
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, null values
- null values [SQL Server], XML
- ELEMENTS directive
- XSINIL parameter
ms.assetid: 2dbc4e48-1cae-4d83-b371-3265da9687cc
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 2373da54981ad8d3cc743214c7110bb0d49723bc
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67943142"
---
# <a name="generate-elements-for-null-values-with-the-xsinil-parameter"></a>Gerar elementos para valores NULL com o parâmetro XSINIL

[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

A diretiva **ELEMENTS** constrói XML no qual cada valor de coluna é mapeado para um elemento no XML. Por padrão, se o valor da coluna for NULL, nenhum elemento será adicionado. No entanto, com a especificação do parâmetro **XSINIL** opcional na diretiva ELEMENTS, é possível solicitar que um elemento também seja criado para o valor NULL. Nesse caso, um elemento que tenha o atributo **xsi:nil** definido como TRUE é retornado para cada valor NULL da coluna.  
  
## <a name="see-also"></a>Consulte Também

[Usar o modo RAW com FOR XML](../../relational-databases/xml/use-raw-mode-with-for-xml.md)

[Cláusula SELECT – FOR](../../t-sql/queries/select-for-clause-transact-sql.md)
