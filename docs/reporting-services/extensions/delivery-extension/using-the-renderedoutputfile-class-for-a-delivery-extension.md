---
title: "Usando a classe RenderedOutputFile para uma extensão de entrega | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- RenderedOutputFile class
- data streams [Reporting Services]
- delivery extensions [Reporting Services], data streams
ms.assetid: 8b591801-42d5-49fa-b710-bf7e6917accf
caps.latest.revision: 34
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: 35fa7b98c43bb20ef6df30f27ca74a5f2ada1792
ms.contentlocale: pt-br
ms.lasthandoff: 08/12/2017

---
# <a name="using-the-renderedoutputfile-class-for-a-delivery-extension"></a>Usando a classe RenderedOutputFile para uma extensão de entrega
  A classe de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> representa um fluxo de dados e informações sobre as propriedades associadas ao fluxo de dados. O **dados** propriedade o <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> classe é usada para representar um relatório renderizado ou um recurso de relatório como um **fluxo** objeto.  
  
 O <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> método o **relatório** retorna uma matriz de uma ou mais <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objetos que juntos constituem um único relatório renderizado. O primeiro objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> é o relatório renderizado. Qualquer outro objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> será o recurso a ser entregue junto com os dados de relatório (por exemplo, um arquivo HTML e as imagens associadas). A renderização de extensões que são extensões de renderização de fluxo único (IMAGE, PDF, MHTML e EXCEL) retornará só um objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> na matriz.  
  
 Para obter um exemplo de como usar o <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> de classe, consulte [SQL Server Reporting Services Product Samples](http://go.microsoft.com/fwlink/?LinkId=177889).  
  
## <a name="see-also"></a>Consulte também  
 [Implementando uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)   
 [Biblioteca de extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  