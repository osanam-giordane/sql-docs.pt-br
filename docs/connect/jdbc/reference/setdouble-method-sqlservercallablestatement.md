---
title: Método SetDouble (SQLServerCallableStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerCallableStatement.setDouble
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: c054bb84-1292-4b70-b574-2ae189cd4e68
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 2b103bae2e7de26997545d0158ec2e3c440a0c59
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68213689"
---
# <a name="setdouble-method-sqlservercallablestatement"></a>Método setDouble (SQLServerCallableStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define o parâmetro designado como o valor **double** fornecido.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void setDouble(java.lang.String sCol,  
                      double d)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *sCol*  
  
 Uma **String** que contém o nome do parâmetro.  
  
 *d*  
  
 Um valor **duplo** .  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Esse método setDouble é especificado pelo método setDouble na interface java.sql.CallableStatement.  
  
## <a name="see-also"></a>Consulte Também  
 [Membros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Classe SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
