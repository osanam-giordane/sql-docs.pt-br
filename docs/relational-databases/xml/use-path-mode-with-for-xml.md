---
title: Usar o modo PATH com FOR XML | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PATH FOR XML mode
- characters [SQL Server], XML
- aliases [SQL Server], XML
- FOR XML clause, PATH mode
- FOR XML PATH mode
- column names [SQL Server]
- XPath queries [SQL Server]
ms.assetid: a685a9ad-3d28-4596-aa72-119202df3976
caps.latest.revision: 45
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 64b4d50fcbf13a157cf725ac7b1ab9dd328e8b07
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="use-path-mode-with-for-xml"></a>Usar o modo PATH com FOR XML
  Conforme descrito em [Construindo XML usando FOR XML](../../relational-databases/xml/for-xml-sql-server.md), o modo PATH fornece uma maneira simples de combinar elementos e atributos. O modo PATH também é uma maneira simples de introduzir aninhamento adicional para representar propriedades complexas. É possível usar consultas em modo FOR XML EXPLICIT para construir esse XML a partir de um conjunto de linhas, mas o modo PATH fornece uma alternativa simples para as consultas em modo EXPLICIT que são potencialmente trabalhosas. O modo PATH, juntamente com a capacidade de escrever consultas FOR XML aninhadas e a diretiva TYPE para retornar instâncias do tipo **xml** , permite escrever consultas com menos complexidade.  
  
 No modo PATH, os nomes ou alias de colunas são tratados como expressões XPath. Essas expressões indicam como os valores estão sendo mapeados para XML. Cada expressão XPath é um XPath relativo que fornece o tipo de item (como atributo, elemento e valor escalar) e o nome e a hierarquia do nó que será gerado em relação ao elemento de linha.  
  
 Esta seção descreve colunas de mapeamento em um conjunto de linhas em várias condições e fornece exemplos.  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Colunas sem um nome](../../relational-databases/xml/columns-without-a-name.md)  
  
-   [Colunas com um nome](../../relational-databases/xml/columns-with-a-name.md)  
  
-   [Colunas com um nome especificado como um caractere curinga](../../relational-databases/xml/columns-with-a-name-specified-as-a-wildcard-character.md)  
  
-   [Colunas com o nome de um teste de nó XPath](../../relational-databases/xml/columns-with-the-name-of-an-xpath-node-test.md)  
  
-   [Nomes de colunas com o caminho especificado como data&#40;&#41;](../../relational-databases/xml/column-names-with-the-path-specified-as-data.md)  
  
-   [Colunas que contêm um valor nulo por padrão](../../relational-databases/xml/columns-that-contain-a-null-value-by-default.md)  
  
-   [Suporte a namespace em modo PATH](../../relational-databases/xml/namespace-support-in-path-mode.md)  
  
-   [Exemplos: Usando modo PATH](../../relational-databases/xml/examples-using-path-mode.md)  
  
## <a name="see-also"></a>Consulte também  
 [Adicionar namespaces a consultas com WITH XMLNAMESPACES](../../relational-databases/xml/add-namespaces-to-queries-with-with-xmlnamespaces.md)   
 [SELECT &#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [FOR XML &#40;SQL Server&#41;](../../relational-databases/xml/for-xml-sql-server.md)  
  
  