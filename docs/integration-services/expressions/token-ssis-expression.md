---
title: "TOKEN (expressão SSIS) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9fdd06bf-5bc9-445c-95bf-709e0ca5989b
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: ff578d1f2ba584c64e471fa9514c6fa76e581d8e
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="token--ssis-expression"></a>TOKEN (expressão SSIS)
  Retorna um token (subcadeia de caracteres) de uma cadeia de caracteres com base nos delimitadores especificados, que separam os tokens na cadeia de caracteres, e o número do token que denota qual token deve ser retornado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
TOKEN(character_expression, delimiter_string, occurrence)  
```  
  
## <a name="arguments"></a>Argumentos  
 *character_expression*  
 Uma cadeia de caracteres que contém tokens separados por delimitadores.  
  
 *delimiter_string*  
 Uma cadeia de caracteres que contém caracteres delimitadores. Por exemplo, "; ," contém três caracteres delimitadores ponto e vírgula, um espaço em branco e uma vírgula.  
  
 *ocorrência*  
 Um inteiro assinado ou não assinado que especifica o token a ser retornado. Por exemplo, se você especificar 3 como um valor para esse parâmetro, o terceiro token da cadeia de caracteres será retornado.  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_WSTR  
  
## <a name="remarks"></a>Comentários  
 Essa função divide a cadeia de caracteres < character_expression > em um conjunto de tokens separados pelos delimitadores especificados na < delimiter_string > e, em seguida, retorna o enésimo token onde N é o número de ocorrência do token especificado pelo \<ocorrência > parâmetro. Consulte a seção Exemplos para obter os usos dessa função.  
  
 Os comentários a seguir se aplicam à função TOKEN:  
  
-   A cadeia de caracteres delimitadores pode conter um ou mais caracteres delimitadores.  
  
-   Se o valor de \<ocorrência > parâmetro for maior do que o número total de tokens na cadeia de caracteres, a função retornará NULL.  
  
-   Delimitadores à esquerda são ignorados.  
  
-   TOKEN funciona apenas com o tipo de dados DT_WSTR. Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido no tipo de dados DT_WSTR antes de TOKEN executar sua operação. Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.  
  
-   TOKEN retornará um resultado nulo se character_expression for nula.  
  
-   É possível usar variáveis e colunas como valores de todos os argumentos da expressão.  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 No exemplo a seguir, a função TOKEN retorna "a". A cadeia de caracteres "a little white dog" tem 4 tokens "a", "little", "white", "dog" separadas pelo delimitador " " (caractere de espaço). O segundo argumento, uma cadeia de caracteres delimitadora, especifica apenas um delimitador, o caractere de espaço, a ser usado na divisão da cadeia de caracteres de entrada em tokens. O último argumento, 1, especifica o primeiro token a ser retornado. O primeiro token é "a" nesta cadeia de caracteres de exemplo.  
  
```  
TOKEN("a little white dog"," ",1)  
```  
  
 No exemplo a seguir, a função TOKEN retorna "dog". A cadeia de caracteres delimitadores neste exemplo contém cinco delimitadores. A cadeia de caracteres de entrada contém quatro tokens: “a”, “little”, “white”, “dog”.  
  
```  
TOKEN("a:little|white dog","| ,.:",4)  
```  
  
 No exemplo a seguir, a função TOKEN retorna "" (uma cadeia de caracteres vazia) porque não há 99 tokens na cadeia de caracteres.  
  
```  
TOKEN("a little white dog"," ",99)  
```  
  
 No exemplo a seguir, a função TOKEN retorna uma cadeia de caracteres completa. A função analisa a cadeia de caracteres de entrada para verificar se há delimitadores e, como não há, ela adiciona a cadeia de caracteres inteira como o primeiro token.  
  
```  
TOKEN("a little white dog","|",1)  
```  
  
 No exemplo a seguir, a função TOKEN retorna "a". Ela ignora todos os caracteres de espaço à esquerda.  
  
```  
TOKEN("        a little white dog", " ", 1)  
```  
  
 No exemplo a seguir, a função TOKEN retorna o ano de uma cadeia de caracteres de data.  
  
```  
TOKEN("2009/01/01", "/"), 1  
```  
  
 No exemplo a seguir, a função TOKEN retorna o nome do arquivo do caminho especificado. Por exemplo, se o valor de User::Path for "c:\arquivos de programas\data\myfile.txt", a função TOKEN retornará "myfile.txt." A função TOKENCOUNT retorna 4 e a função TOKEN função retorna o 4º token, "myfile.txt".  
  
```  
TOKEN(@[User::Path], "\\", TOKENCOUNT(@[User::Path], "\\"))  
```  
  
## <a name="see-also"></a>Consulte também  
 [Funções &#40; Expressão do SSIS &#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  