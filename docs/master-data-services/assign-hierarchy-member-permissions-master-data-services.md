---
title: "Atribuir permissões de membro de hierarquia (Master Data Services) | Microsoft Docs"
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
- permissions [Master Data Services], assigning member permissions
- members [Master Data Services], assigning permissions
ms.assetid: e1b8b46a-7cd1-4a7d-9345-dd7df081e145
caps.latest.revision: 7
author: smartysanthosh
ms.author: nagavo
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 0b832a9306244210e693bde7c476269455e9b6d8
ms.openlocfilehash: ab447d35def70cd31f34806294de568c243e6d11
ms.contentlocale: pt-br
ms.lasthandoff: 09/07/2017

---
# <a name="assign-hierarchy-member-permissions-master-data-services"></a>Atribuir permissões de membro de hierarquia (Master Data Services)
  Atribua permissões a membros de hierarquia para conceder aos usuários ou grupos o acesso para exibir dados na área funcional **Explorer** do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].  
  
 As permissões de membro de hierarquia são opcionais. Elas fornecem granularidade adicional às permissões de objeto de modelo, que são obrigatórias.  
  
## <a name="prerequisites"></a>Pré-requisitos  
 Para executar esse procedimento:  
  
-   Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-assign-hierarchy-member-permissions"></a>Para atribuir permissões de membro de hierarquia  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.  
  
2.  Na página **Usuários** ou **Grupos** , selecione a linha do usuário ou grupo que deseja editar.  
  
3.  Clique em **Editar usuário selecionado**.  
  
4.  Clique na guia **Membros da Hierarquia** .  
  
5.  Na lista **Modelo** , selecione um modelo.  
  
6.  Na lista **Versão** , selecione uma versão.  
  
7.  Na lista **Hierarquia** , selecione uma hierarquia.  
  
8.  Clique em **Editar**.  
  
9. Expanda a árvore e clique no nó de hierarquia ao qual deseja atribuir permissões.  
  
10. No menu, selecione uma combinação das permissões **Criar**, **Ler, Atualizar** e **Excluir** ou **Negar** .  
  
11. Clique em **Salvar**.  
  
    > [!NOTE]  
    >  As permissões de membro de hierarquia não entram em vigor imediatamente. Consulte [Aplicar permissões de membros imediatamente &#40;Master Data Services&#41;](../master-data-services/immediately-apply-member-permissions-master-data-services.md) para obter mais informações.  
  
## <a name="see-also"></a>Consulte também  
 [Excluir permissões de membro de hierarquia &#40;Master Data Services&#41;](../master-data-services/delete-hierarchy-member-permissions-master-data-services.md)   
 [Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](../master-data-services/assign-model-object-permissions-master-data-services.md)   
 [Permissões de membro de hierarquia &#40;Master Data Services&#41;](../master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  