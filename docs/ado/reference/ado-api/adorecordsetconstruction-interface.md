---
title: Interface ADORecordsetConstruction | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ADORecordsetConstruction
helpviewer_keywords:
- ADORecordsetConstruction interface [ADO]
ms.assetid: 08386eba-f1f7-4879-8ffd-8733930ecb2f
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 1e1d14255acd4cc7f18abea1c494353ef970903c
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67920792"
---
# <a name="adorecordsetconstruction-interface"></a>Interface ADORecordsetConstruction
O **ADORecordsetConstruction** interface é usada para construir o ADO **conjunto de registros** objeto a partir de um banco de dados OLE **conjunto de linhas** objeto em um aplicativo C/C++.  
  
 Esta interface dá suporte as seguintes propriedades:  
  
## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|[Capítulo](../../../ado/reference/ado-api/chapter-property-ado.md)|Leitura/gravação.<br />Obtém/define um banco de dados OLE **capítulo** objeto de/nesse ADO **Recordset** objeto.|  
|[RowPosition](../../../ado/reference/ado-api/rowposition-property-ado.md)|Leitura/gravação.<br />Obtém/define um banco de dados OLE **RowPosition** objeto de/nesse ADO **Recordset** objeto.|  
|[Rowset](../../../ado/reference/ado-api/rowset-property-ado.md)|Leitura/gravação.<br />Obtém/define um banco de dados OLE **conjunto de linhas** objeto de/nesse ADO **Recordset** objeto.|  
  
## <a name="methods"></a>Métodos  
 nenhuma.  
  
## <a name="events"></a>Events  
 nenhuma.  
  
## <a name="remarks"></a>Comentários  
 Dado um banco de dados OLE **conjunto de linhas** objeto (`pRowset`), a construção de ADO **conjunto de registros** objeto (`adoRs`) de valores para as três operações básicas a seguir:  
  
1.  Criar um ADO **Recordset** objeto:  
  
    ```  
    Recordset20Ptr adoRs;  
    adoRs.CreateInstance(__uuidof(Recordset));  
    ```  
  
2.  Consulta a **IADORecordsetConstruction** interface sobre o **conjunto de registros** objeto:  
  
    ```  
    adoRecordsetConstructionPtr adoRsConstruct=NULL;  
    adoRs->QueryInterface(__uuidof(ADORecordsetConstruction),  
                         (void**)&adoRsConstruct);  
    ```  
  
3.  Chame o `IADORecordsetConstruction::put_Rowset` método de propriedade para definir o banco de dados OLE `Rowset` objeto ADO `Recordset` objeto:  
  
    ```  
    IUnknown *pUnk=NULL;  
    pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);  
    adoRsConstruct->put_Rowset(pUnk);  
    ```  
  
 O resultante `adoRs` objeto agora representa o ADO **conjunto de registros** objeto construído a partir do OLE DB **conjunto de linhas** objeto.  
  
 Também é possível construir um ADO **conjunto de registros** objeto a partir de um banco de dados OLE **capítulo** ou **RowPosition** objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Versão:** O ADO 2.0 e posterior  
  
 **Biblioteca:** msado15.dll  
  
 **UUID:** 00000283-0000-0010-8000-00AA006D2EA4  
  
## <a name="see-also"></a>Consulte também  
 [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)   
 [Propriedade Rowset (ADO)](../../../ado/reference/ado-api/rowset-property-ado.md)
