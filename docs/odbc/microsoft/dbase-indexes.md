---
title: Índices do dBASE | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- DBase indexes [ODBC]
- DBase driver [ODBC], indexes
ms.assetid: fdfa56f5-e324-4ec2-9267-fdf95ab99373
author: MightyPen
ms.author: genemi
ms.openlocfilehash: d9a0a57c3dce920c6d5fbc2510932066cb5a2659
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68096365"
---
# <a name="dbase-indexes"></a>Índices do dBASE
O driver ODBC do dBASE automaticamente abre e atualiza os arquivos de índice do dBASE IV. Você deve usar o **Selecionar índices** caixa de diálogo exibida por meio do administrador de fonte de dados o ODBC para associar arquivos do dBASE III. ndx arquivos dBASE.  
  
 As seguintes limitações se aplicam à criação de índices do dBASE:  
  
-   Todos os nomes de coluna devem ser válidos.  
  
-   Todas as colunas devem ser no mesmo crescente ou decrescente.  
  
-   O comprimento de uma coluna de texto deve ser menor que 100 bytes.  
  
-   Se houver mais de uma coluna, todas as colunas devem ser colunas de texto e a soma dos tamanhos da coluna deve ser menor que 100 bytes.  
  
-   Campos de memorando não podem ser indexados.  
  
-   Um índice não deve ser especificado para o conjunto atual de campos (ou seja, os índices duplicados não são permitidos).  
  
-   O nome do índice deve corresponder a convenção de nomenclatura de índice do dBASE. dBASE III requer que cada índice esteja em um arquivo separado, cada um com uma extensão. ndx. DBASE IV, os índices são criados como nomes de marca são armazenados em um arquivo. MDX único. O arquivo. MDX tem o mesmo nome base do arquivo de banco de dados (por exemplo, Emp. MDX é o arquivo de índice para o banco de EMP).  
  
-   dBASE define um índice exclusivo como um em que apenas um registro de um conjunto de valores de chave idênticos é adicionado ao índice.
