---
title: Conjunto de linhas DISCOVER_PARTITION_DIMENSION_STAT | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: bf4626b3-4d6b-4795-bb01-df335fb9c09a
caps.latest.revision: 6
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 94265a940551ed20a23aa777c033308f90d844b9
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="discoverpartitiondimensionstat-rowset"></a>Conjunto de linhas DISCOVER_PARTITION_DIMENSION_STAT
  Retorna estatísticas sobre a dimensão associada a uma partição  
  
 **Aplica-se a:** modelos de tabela, modelos multidimensionais  
  
## <a name="rowset-columns"></a>Colunas do conjunto de linhas  
 O conjunto de linhas **DISCOVER_PARTITION_DIMENSION_STAT** contém as colunas a seguir.  
  
|Nome da coluna|Indicador de tipo|Restrição|Description|  
|-----------------|--------------------|-----------------|-----------------|  
|**DATABASE_NAME**|**DBTYPE_WSTR**|Required|O nome do banco de dados.<br /><br /> Esta coluna é obrigatória na lista de restrições.|  
|**CUBE_NAME**|**DBTYPE_WSTR**|Required|O nome do cubo ou modelo tabular.<br /><br /> Esta coluna é obrigatória na lista de restrições.|  
|**NOME_GRUPO_MEDIDAS**|**DBTYPE_WSTR**|Required|O nome do grupo de medidas.<br /><br /> Esta coluna é obrigatória na lista de restrições.|  
|**NOME DA PARTIÇÃO**|**DBTYPE_WSTR**|Required|O nome da partição.<br /><br /> Esta coluna é obrigatória na lista de restrições.|  
|**DIMENSION_NAME**|**DBTYPE_WSTR**||O nome da dimensão.<br /><br /> Esta coluna é obrigatória na lista de restrições.|  
|**ATTRIBUTE_NAME**|**DBTYPE_WSTR**||O atributo de um atributo na dimensão.|  
|**ATTRIBUTE_INDEXED**|**DBTYPE_BOOL**||Quando verdadeiro, indica que o atributo está indexado; caso contrário, falso.|  
|**ATTRIBUTE_COUNT_MIN**|**DBTYPE_I8**||A contagem mínima de atributos.|  
|**ATTRIBUTE_COUNT_MAX**|**DBTYPE_I8**||A contagem máxima de atributos.|  
  
 Este conjunto de linhas do esquema não é classificado.  
  
## <a name="using-adomdnet-to-return-the-rowset"></a>Usando ADOMD.NET para retornar o conjunto de linhas  
 Ao usar ADOMD.NET e o conjunto de linhas de esquema para recuperar metadados, você pode usar o GUID ou a cadeia de caracteres para referenciar um objeto de conjunto de linhas de esquema no método GetSchemaDataSet. Para obter mais informações, consulte [Working with Schema Rowsets in ADOMD.NET](../../../analysis-services/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets.md).  
  
 A tabela a seguir fornece os valores de GUID e de cadeia de caracteres que identificam este conjunto de linhas.  
  
|Argumento|Valor|  
|--------------|-----------|  
|GUID|a07ccd8e-8148-11d0-87bb-00c04fc33942|  
|ADOMDNAME|PartitionDimensionStat|  
  
## <a name="see-also"></a>Consulte também  
 [XML for Analysis conjuntos de linhas de esquema](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  