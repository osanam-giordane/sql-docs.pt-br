---
title: "Permissões de coleção (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [Master Data Services], permissions
- permissions [Master Data Services], collections
ms.assetid: 703e1bf5-4b4b-4830-8a5b-f979b09f677d
caps.latest.revision: 6
author: smartysanthosh
ms.author: nagavo
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 0b832a9306244210e693bde7c476269455e9b6d8
ms.openlocfilehash: ffe773af9f7ced030184ce102f221413b5a83ae4
ms.contentlocale: pt-br
ms.lasthandoff: 09/07/2017

---
# <a name="collection-permissions-master-data-services"></a>Permissões de coleção (Serviços de Dados Mestre)
  As permissões de coleção aplicam-se a todas as membros coleções de uma entidade. Você não pode dar permissão a uma coleção específica; as permissões se aplicam a todas as coleções.  
  
> [!NOTE]  
>  Essas permissões se aplicam apenas à área funcional **Explorer** da interface do usuário.  
  
|Permissão|Description|  
|----------------|-----------------|  
|**Leitura**|O usuário pode ler membros da coleção e os atributos de membro.|  
|**Criar**|O usuário pode criar membros da coleção e atribuir valores de atributo.|  
|**Update (atualizar)**|O usuário pode atualizar membros da coleção, atributos e relacionamentos|  
|**Delete (excluir)**|O usuário pode excluir os membros da coleção.|  
|**Deny**|Negar todo acesso aos membros da coleção.|  
  
 As permissões Ler, Criar, Atualizar e Excluir podem ser combinadas. Ao atribuir Criar, Atualizar e Excluir, a permissão de leitura é atribuída automaticamente.  
  
## <a name="see-also"></a>Consulte também  
 [Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](../master-data-services/assign-model-object-permissions-master-data-services.md)   
 [Coleções &#40;Master Data Services&#41;](../master-data-services/collections-master-data-services.md)   
 [Permissões de objeto de modelo &#40;Master Data Services&#41;](../master-data-services/model-object-permissions-master-data-services.md)  
  
  