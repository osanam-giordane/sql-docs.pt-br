---
title: Identificadores (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 1f72832fd684dd59e27ce58576a7f65fa8796347
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68074810"
---
# <a name="identifiers-dmx"></a>Identificadores (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Todos os objetos no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] deve ter um identificador. O nome de um objeto é seu identificador. Servidores, banco de dados e objetos de banco de dados, como fontes de dados, exibições de fonte de dados, cubos, dimensões e modelos de mineração, entre outros, têm identificadores.  
  
 Há duas classes de identificadores em extensões DMX:  
  
-   [Identificadores normais](#RegularIdentifiers)  
  
-   [Identificadores delimitados](#DelimitedIdentifiers)  
  
 Um identificador de objeto é criado quando o objeto é definido. O identificador é utilizado para fazer referência ao objeto. Os identificadores devem ter 100 caracteres ou menos.  
  
##  <a name="RegularIdentifiers"></a> Identificadores normais  
 Os identificadores normais em DMX respeitam as regras do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para formato de identificadores. Os identificadores normais em DMX não requerem delimitadores. A seguir, um exemplo de instrução DMX que usa um identificador normal não delimitado:  
  
```  
SELECT * FROM Clustering.CONTENT;  
```  
  
### <a name="rules-for-regular-identifiers"></a>Regras para identificadores normais  
 Estas são as regras para o formato dos identificadores normais:  
  
1.  O primeiro caractere de um identificador normal deve ser um dos seguintes:  
  
    -   Uma letra, conforme definido pelo Unicode Standard 2.0. Isso inclui caracteres latinos de a até z, de A até Z, além de caracteres de letras de outros idiomas.  
  
    -   Um sublinhado (_).  
  
2.  Os caracteres subsequentes podem ser:  
  
    -   Letras, como definido no Unicode Standard 2.0.  
  
    -   Números decimais do latim básico ou outros scripts nacionais.  
  
    -   Um sublinhado (_).  
  
3.  O identificador não deve ser uma palavra reservada DMX. As palavras reservadas fazem diferenciação entre maiúsculas e minúsculas em DMX. Para obter mais informações, consulte [palavras-chave reservadas &#40;DMX&#41;](../dmx/reserved-keywords-dmx.md).  
  
4.  O identificador não pode conter espaços inseridos nem caracteres especiais.  
  
 É preciso pôr entre colchetes todos os identificadores usados em instruções DMX que não estejam em conformidade com essas regras.  
  
##  <a name="DelimitedIdentifiers"></a> Identificadores delimitados  
 Os identificadores delimitados são postos entre colchetes ([ ]).  A seguir, um exemplo de uma instrução DMX com identificador delimitado que obedece essas regras.  
  
```  
SELECT * FROM [Marketing_Clusters].CONTENT;  
```  
  
 O identificador que não atender as regras para o formato dos identificadores normais deverá ser sempre delimitado. A seguir, é mostrado um exemplo de instrução DMX com identificador delimitado que contém um espaço:  
  
```  
SELECT * FROM [Targeted Mailing].CONTENT;  
```  
  
 Use identificadores delimitados nas seguintes situações:  
  
-   Quando palavras reservadas forem usadas em nomes de objeto ou partes de nomes de objeto.  
  
     É recomendável não usar palavras-chave reservadas como nomes de objeto. Bancos de dados que você atualizar de versões anteriores do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] podem conter identificadores que incluem palavras que não foram reservadas na versão anterior do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , mas que são palavras reservadas para[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Um identificador delimitado pode ser usado para fazer referência a um objeto assim, até que seja possível alterar o nome do objeto.  
  
-   Quando se usam caracteres que não estão listados como identificadores qualificados.  
  
     No [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], é possível usar qualquer caractere da página de código atual em um identificador delimitado; no entanto, o uso indiscriminado de caracteres especiais em um nome de objeto pode tornar as instruções DMX difíceis de ler e manter.  
  
### <a name="rules-for-delimited-identifiers"></a>Regras para identificadores delimitados  
 A seguir, são apresentadas as regras para o formato dos identificadores delimitados:  
  
1.  Os identificadores delimitados podem conter o mesmo número de caracteres dos identificadores normais (de 1 a 100 caracteres, sem incluir os caracteres delimitados).  
  
2.  O corpo de um identificador pode conter qualquer combinação de caracteres que forem usados na página de código atual, inclusive os próprios caracteres de delimitação. Se o corpo do próprio identificador contiver caracteres delimitadores, será necessária uma manipulação especial:  
  
    -   Se o corpo do identificador contiver um colchete esquerdo ([), não será necessária nenhuma manipulação especial.  
  
    -   Se o corpo do identificador contiver um colchete direito (]), será preciso especificar os colchetes direitos (]]) para representá-lo na página de código.  
  
### <a name="delimiting-identifiers-with-multiple-parts"></a>Identificadores delimitados com várias partes  
 Quando nomes de objetos qualificados forem usados, talvez seja necessário delimitar mais de um dos identificadores que compõem o nome de objeto. É preciso delimitar individualmente cada um dos identificadores.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de DMX &#40;extensões DMX&#41;](../dmx/data-mining-extensions-dmx-reference.md)   
 [Extensões de mineração de dados &#40;DMX&#41; elementos de sintaxe](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência de função](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência de operador](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência de instrução](../dmx/data-mining-extensions-dmx-statements.md)   
 [Extensões de mineração de dados &#40;DMX&#41; convenções de sintaxe](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Funções de previsão gerais &#40;DMX&#41;](../dmx/general-prediction-functions-dmx.md)   
 [Estrutura e uso de consultas de previsão DMX](../dmx/structure-and-usage-of-dmx-prediction-queries.md)   
 [Compreendendo a instrução DMX Select](../dmx/understanding-the-dmx-select-statement.md)  
  
  
