---
title: "O tamanho do pacote de rede não deve exceder 8060 Bytes | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 86db5da1-afe4-4fbb-8bf8-33cedc7e4361
caps.latest.revision: 8
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: cb2e255e501d739ddfe8f822c7c62b212aa14db8
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="network-packet-size-should-not-exceed-8060-bytes"></a>O tamanho do pacote de rede não dever exceder 8060 bytes
  Se o valor especificado para sp_configure 'network packet size' ou se o tamanho do pacote de rede de qualquer usuário que fez logon for maior que 8060, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executará operações de alocação de memória diferentes. Isso pode causar um aumento no espaço de endereço virtual de processo que não está reservado para o pool de buffers.  
  
## <a name="best-practices-recommendations"></a>Práticas Recomendadas  
 O tamanho do pacote de rede não dever exceder 8060 bytes  
  
## <a name="for-more-information"></a>Para obter mais informações  
 [Artigo 903002 da Base de Dados de Conhecimento Microsoft](http://go.microsoft.com/fwlink/?linkid=117749)  
  
## <a name="see-also"></a>Consulte também  
 [Monitorar e impor práticas recomendadas usando o Gerenciamento Baseado em Políticas](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  