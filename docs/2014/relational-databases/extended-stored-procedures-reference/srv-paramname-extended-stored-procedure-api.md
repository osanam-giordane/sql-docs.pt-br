---
title: srv_paramname (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramname
ms.assetid: 1a53d707-7b06-49cc-a0df-ac727cfe953f
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 8a5eca5aef966d205ef550b05eff2d7055e4cb28
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "63127175"
---
# <a name="srvparamname-extended-stored-procedure-api"></a>srv_paramname (API de procedimento armazenado estendido)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Em vez disso, use a Integração CLR.  
  
 Retorna o nome de um parâmetro de chamada de procedimento armazenado remoto.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
DBCHAR * srv_paramname (  
SRV_PROC * srvproc,intn, int *len );  
```  
  
## <a name="arguments"></a>Argumentos  
 *srvproc*  
 É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto). A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.  
  
 *n*  
 Indica o número do parâmetro. O primeiro parâmetro é 1.  
  
 *len*  
 Fornece um ponteiro para uma variável `int` que contém o comprimento, em bytes, do nome do parâmetro. Se *len* for NULL, o tamanho do nome do parâmetro do procedimento armazenado remoto não será retornado.  
  
## <a name="returns"></a>Retorna  
 Um ponteiro para uma cadeia de caracteres com terminação nula que contém o nome do parâmetro. O tamanho do nome do parâmetro é armazenado em *len*. Se não houver *n*-ésimo parâmetro nem um procedimento armazenado remoto, será retornado NULL, *len* será definido como -1 e uma mensagem de erro informativa será enviada. Se o nome do parâmetro for o NULL, *len* será definido como 0 e uma cadeia de caracteres vazia que termina em nulo será retornada.  
  
## <a name="remarks"></a>Comentários  
 Essa função obtém o nome de um parâmetro de chamada de procedimento armazenado remoto. Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome). Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro. O manipulador SRV_RPC ainda é chamado, mas aparece como se não houvesse parâmetros e **srv_rpcparams** retorna 0.  
  
> [!IMPORTANT]  
>  Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção. Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).  
  
## <a name="see-also"></a>Consulte também  
 [srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
