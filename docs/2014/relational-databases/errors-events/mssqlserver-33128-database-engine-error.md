---
title: MSSQLSERVER_33128 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 33128 (Database Engine error)
ms.assetid: 12c1096f-d120-439b-85f3-f794859503c9
caps.latest.revision: 7
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 108c49e59102814e56056ce96b3643c2cd754c76
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36115675"
---
# <a name="mssqlserver33128"></a>MSSQLSERVER_33128
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|33128|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|SEC_DEPRECATED_ALGO|  
|Texto da mensagem|A criptografia falhou. A chave usa um algoritmo substituído '%. * ls' que já não tão mais suporte.|  
  
## <a name="explanation"></a>Explicação  
 Essa mensagem ocorre ao referenciar o algoritmo de criptografia RC4 (ou RC4_128). RC4 e RC4_128 são algoritmos fracos e estão obsoletos. Use um algoritmo mais forte; por exemplo, um dos algoritmos AES.  
  
 Quando o nível de compatibilidade do banco de dados for 90 ou 100, a operação foi bem-sucedida, o evento de substituição é lançado e a mensagem aparece somente no buffer de anéis.  
  
 Quando o nível de compatibilidade do banco de dados for 110 ou superior operação foi bem-sucedida, o evento de substituição é lançado e a mensagem aparece somente no buffer de anéis. As operações de criptografia falharão, o evento de substituição será lançado e a mensagem será exibida para o usuário e aparecerá no buffer de anéis.  
  
> [!NOTE]  
>  O buffer de anéis é um componente interno que não é totalmente documentado e não deve ser usado por clientes. Mensagens do buffer de anéis são úteis ao entrar em contato com o Suporte ao Cliente do [!INCLUDE[msCoName](../../includes/msconame-md.md)]. Para exibir o buffer de anéis, consulte a exibição de gerenciamento dinâmico sys.dm_os_ring_buffers.  
  
|Estado|Description|  
|-----------|-----------------|  
|1|Uma chave RC4 é usada na função encryptbykey() interna. Função interna retorna NULL. Esta mensagem aparece somente no buffer de anéis.|  
|2|Uma chave RC4 é usada pela função decryptbykey() interna. Esta mensagem aparece somente no buffer de anéis.|  
|3|Uma chave RC4 key está sendo criptografada por uma chave simétrica. Vista pelos usuários no buffer de anéis. As chaves simétricas RC4 preteridas não podem mais ser alteradas no nível de compatibilidade 110. Tente usar chaves não RC4 para operações de criptografia. Se necessário, defina nível de compatibilidade com versões anteriores a um 90 ou 100.|  
|4|Uma chave não RC4 key está sendo criptografada por uma chave simétrica. RC4 preterida Vista pelos usuários no buffer de anéis. Modifique o aplicativo para usar chave simétricas não RC4 ou defina o nível de compatibilidade com versões anteriores para 90 ou 100.|  
|5|Uma chave RC4 está sendo descriptografia por uma chave simétrica. Esta mensagem aparece somente no buffer de anéis.|  
|6|Uma chave não RC4 está sendo descriptografada por uma chave simétrica RC4. Esta mensagem aparece somente no buffer de anéis.|  
|7|Uma chave RC4 simétrica está sendo criptografada pelo certificado. Vista pelos usuários no buffer de anéis.|  
|8|Uma chave RC4 simétrica está sendo descriptografada pelo certificado. Esta mensagem aparece somente no buffer de anéis.|  
|9|Uma chave RC4 simétrica está sendo criptografia por uma chave EKM.|  
|10|Uma chave RC4 simétrica está sendo descriptografada por uma chave EKM. Esta mensagem aparece somente no buffer de anéis.|  
  
## <a name="user-action"></a>Ação do usuário  
 Use um algoritmo mais forte; por exemplo, um dos algoritmos AES. (Recomendado)  
  
 Use ALTER DATABASE SET COMPATIBILITY_LEVEL para definir o banco de dados com o nível de compatibilidade 100. (Não recomendável.)  
  
  