---
title: sys.xml_schema_collections (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.xml_schema_collections_TSQL
- sys.xml_schema_collections
- xml_schema_collections
- xml_schema_collections_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.xml_schema_collections catalog view
ms.assetid: f3f7f3dc-029f-4942-ab3c-75fa9814e40f
author: pmasl
ms.author: pelopes
ms.reviewer: mikeray
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 6ef3a2d6bca9591637223aa4f5659e42ac27c5d5
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68115049"
---
# <a name="sysxmlschemacollections-transact-sql"></a>sys.xml_schema_collections (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna uma linha por coleção de esquemas XML. Uma coleção de esquemas XML é um conjunto nomeado de definições XSD. A coleção de esquemas XML propriamente dita está contida em um esquema relacional e é identificada por um nome [!INCLUDE[tsql](../../includes/tsql-md.md)] no escopo do esquema. As seguintes tuplas são exclusivas: xml_collection_id, e schema_id e name.  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|xml_collection_id|**int**|ID da coleção de esquemas XML. Exclusiva no banco de dados.|  
|schema_id|**int**|ID do esquema relacional que contém essa coleção de esquemas XML.|  
|principal_id|**int**|ID do proprietário individual, se diferente do proprietário do esquema. Por padrão, os objetos contidos no esquema pertencem ao proprietário do esquema. No entanto, um proprietário alternativo pode ser especificado usando a instrução ALTER AUTHORIZATION para alterar a propriedade.<br /><br /> NULL = Nenhum proprietário individual alternativo.|  
|name|**sysname**|Nome da coleção de esquemas XML.|  
|create_date|**datetime**|Data em que a coleção de esquemas XML foi criada.|  
|modify_date|**datetime**|Data em que a coleção de esquemas XML foi alterada pela última vez.|  
  
## <a name="permissions"></a>Permissões  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obter mais informações, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte também  
 [Exibições de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Esquemas XML &#40;sistema de tipo XML&#41; exibições do catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/xml-schemas-xml-type-system-catalog-views-transact-sql.md)   
 [Consultando as perguntas frequentes do catálogo do sistema do SQL Server](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  
