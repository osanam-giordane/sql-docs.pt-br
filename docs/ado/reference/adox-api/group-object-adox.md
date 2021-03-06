---
title: Grupo de objeto (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Group
helpviewer_keywords:
- group object [ADOX]
ms.assetid: 55ef0ade-68ea-4da5-8aa5-4cd27d1f6d1e
author: MightyPen
ms.author: genemi
ms.openlocfilehash: b4b3de5f445ddd09bf7d069b0b93d82c6f8de978
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67966218"
---
# <a name="group-object-adox"></a>Objeto Group (ADOX)
Representa uma conta de grupo que tenha permissões de acesso dentro de um banco de dados protegido.  
  
## <a name="remarks"></a>Comentários  
 O [grupos](../../../ado/reference/adox-api/groups-collection-adox.md) coleção de uma [catálogo](../../../ado/reference/adox-api/catalog-object-adox.md) representa as contas de grupo de todas as do catálogo. O **grupos** coleção para uma [usuário](../../../ado/reference/adox-api/user-object-adox.md) representa somente o grupo ao qual o usuário pertence.  
  
 Com as propriedades, coleções e métodos de um **grupo** do objeto, você pode:  
  
-   Identificar o grupo com o [nome](../../../ado/reference/adox-api/name-property-adox.md) propriedade.  
  
-   Determinar se um grupo tem ler, gravar ou excluir as permissões com o [GetPermissions](../../../ado/reference/adox-api/getpermissions-method-adox.md) e [SetPermissions](../../../ado/reference/adox-api/setpermissions-method-adox.md) métodos.  
  
-   Acessar as contas de usuário que têm associações no grupo com o [usuários](../../../ado/reference/adox-api/users-collection-adox.md) coleção.  
  
-   Acessar propriedades específicas do provedor com o [propriedades](../../../ado/reference/ado-api/properties-collection-ado.md) coleção.  
  
 Esta seção contém o tópico a seguir.  
  
-   [Propriedades, Métodos e Eventos do objeto Group](../../../ado/reference/adox-api/group-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte também  
 [Coleção Groups (ADOX)](../../../ado/reference/adox-api/groups-collection-adox.md)   
 [Coleção Users (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)
