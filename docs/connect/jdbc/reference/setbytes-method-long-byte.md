---
title: Método setBytes (Long, Byte) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerBlob.setBytes (long.byte[])
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ffb8f107-0f9d-4410-957f-62b718e1e872
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 02c8e541b237cbf72fc2b3da3ed5c2b0759b0eb2
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67974914"
---
# <a name="setbytes-method-long-byte"></a>Método setBytes (long, byte[])
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Grava a matriz de bytes fornecida no BLOB iniciando na posição determinada e, em seguida, retorna o número de bytes gravados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public int setBytes(long pos,  
                    byte[] bytes)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *pos*  
  
 A posição (baseada em 1) no BLOB em que a gravação de dados é iniciada.  
  
 *bytes*  
  
 A matriz de bytes a ser gravada no BLOB.  
  
## <a name="return-value"></a>Valor retornado  
 Um valor **long** que especifica o número de bytes gravados.  
  
## <a name="exceptions"></a>Exceções  
 java.sql.SQLException  
  
## <a name="remarks"></a>Remarks  
 Esse método setBytes é especificado pelo método setBytes na interface java.sql.Blob.  
  
 Os dados são substituídos iniciando na posição especificada e podem ultrapassar o comprimento inicial do BLOB. A especificação de valores posição+1 acrescentará bytes. A transmissão de um valor posição+2 ou maior (ou zero ou menos) lançará um erro de posição. A transmissão de uma matriz de **byte** de comprimento zero retornará zero, pois nenhum byte foi gravado.  
  
## <a name="see-also"></a>Consulte Também  
 [Método &#40;setBytes SQLServerBlob&#41;](../../../connect/jdbc/reference/setbytes-method-sqlserverblob.md)   
 [Métodos SQLServerBlob](../../../connect/jdbc/reference/sqlserverblob-methods.md)   
 [Membros de SQLServerBlob](../../../connect/jdbc/reference/sqlserverblob-members.md)   
 [Classe SQLServerBlob](../../../connect/jdbc/reference/sqlserverblob-class.md)  
  
  
