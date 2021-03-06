---
title: Método getHoldability (SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 4508d90f-c3c4-4eac-8001-fb0b93b66734
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 57bf0cfc206319bf6afcb09435e8787499266c0c
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67982919"
---
# <a name="getholdability-method-sqlserverresultset"></a>Método getHoldability (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera a suspensão do objeto [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public int getHoldability()  
```  
  
## <a name="return-value"></a>Valor retornado  
 Um valor **int** que contém um dos seguintes níveis de suspensão:  
  
 HOLD_CURSORS_OVER_COMMIT  
  
 CLOSE_CURSORS_AT_COMMIT  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Esse método de é especificado pelo método getholdabilidade na interface java. Sql. ResultSet.  
  
 Para definir a suspensão do conjunto de resultados, os aplicativos podem usar o método [setHoldability](../../../connect/jdbc/reference/setholdability-method-sqlserverconnection.md) da classe [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md). Depois que o método [setHoldability](../../../connect/jdbc/reference/setholdability-method-sqlserverconnection.md) for chamado, o objeto de instrução e seu objeto de conjunto de resultados forem criados e a instrução for executada, talvez o aplicativo precise alterar a suspensão novamente.  
  
 Nos cursores de servidor, quando conectados ao SQL Server 2005 ou posterior, a definição da suspensão afetará apenas a suspensão dos novos conjuntos de resultados que ainda serão criados nessa conexão. Porém, com o SQL Server 2000, a definição da colocação em espera afetará a colocação em espera dos conjuntos de resultados existentes e dos novos conjuntos de resultados que ainda serão criados nessa conexão.  
  
 Quando a suspensão é redefinida e o método de é chamado no objeto de conjunto de resultados criado anteriormente, o valor retornado por esse método pode ser diferente do valor de manutenção retornado pelos seguintes métodos: Statement. getResultSetHoldability , Connection. getholdabilidade ou DatabaseMetaData. getResultSetHoldability.  
  
## <a name="see-also"></a>Consulte Também  
 [Membros de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Classe SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
