---
title: 'Erro do servidor de Internet: Acesso negado | Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- access denied error in RDS [ADO]
ms.assetid: e5b43cfa-da8d-430d-a2ab-5443dda47a16
author: MightyPen
ms.author: genemi
ms.openlocfilehash: adbfc4e56c49447d88fb354d1e67c2c5e3e30b71
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67922623"
---
# <a name="internet-server-error-access-denied"></a>Erro do servidor de Internet: Acesso negado
Se você receber esse erro, isso normalmente significa que o Microsoft Internet Information Services (IIS) retornou o status a seguir:  
  
 HTTP_STATUS_DENIED 401  
  
 Verifique se os diretórios acessados pelo IIS tem as permissões apropriadas. RDS podem se comunicar com um servidor Web IIS em execução em qualquer um dos três modos de autenticação de senha: Anonymous, Basic ou desafio/resposta do NT (chamada autenticação integrada do Windows no Windows 2000). Além disso, o servidor Web deve ter permissões para o computador de origem de dados se ele for um computador com Windows NT/Windows 2000.  
  
> [!IMPORTANT]
>  Começando com o Windows 8 e Windows Server 2012, os componentes de servidor RDS não estão mais incluídos no sistema operacional Windows (consulte o Windows 8 e [manual de compatibilidade do Windows Server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obter mais detalhes). Componentes de cliente RDS serão removidos em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Devem ser migrados para aplicativos que usam o RDS [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="see-also"></a>Consulte também  
 [Conceitos básicos do RDS](../../../ado/guide/remote-data-service/rds-fundamentals.md)




