---
title: Adicionando registros | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- AddNew method [ADO]
- ADO, editing data
- editing data [ADO], AddNew method
- editing data [ADO], adding data
ms.assetid: dd34669e-6f06-403b-9241-1c85c82aecc2
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 1f4ec0934fbf75de18f460abae84b8117e99f452
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67926261"
---
# <a name="adding-records-to-a-recordset"></a>Adicionar registros a um conjunto de registros
Use o **AddNew** método para criar e inicializar um novo registro em um existente **conjunto de registros**. Você pode usar o **dá suporte a** método com um **CursorOptionEnum** valor de **adAddNew** para verificar se você pode adicionar registros a atual **doconjuntoderegistros** objeto.

 Depois de chamar o **AddNew** método, o novo registro se tornará o registro atual e permanece atual depois de chamar o **atualização** método. Se o **Recordset** objeto não oferece suporte a indicadores, você não consiga acessar o novo registro, quando você move para outro registro. Portanto, dependendo do seu tipo de cursor, você pode precisar chamar o **Requery** método para disponibilizar o novo registro.

 Se você chamar **AddNew** durante a edição do registro atual ou ao adicionar um novo registro, o ADO chama o **atualização** método para salvar qualquer altera e, em seguida, cria o novo registro.

 Esta seção contém os tópicos a seguir.

-   [Adicionando registros usando AddNew](../../../ado/guide/data/adding-records-using-addnew.md)

-   [Adicionando vários campos](../../../ado/guide/data/adding-multiple-fields.md)

-   [Determinando o modo de edição](../../../ado/guide/data/determining-edit-mode.md)

-   [Usando AddNew em modos de lote e imediatos](../../../ado/guide/data/using-addnew-in-immediate-and-batch-modes.md)
