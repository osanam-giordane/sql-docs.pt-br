---
title: Tipos de dados com suporte (SSAS Tabular) | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 92993f7b-7243-4aec-906d-0b0379798242
caps.latest.revision: 16
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a60cc3c2782abed53a8064f80bcdbe01921826cc
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="data-types-supported-ssas-tabular"></a>Tipos de dados com suporte (SSAS tabular)
  Este artigo descreve os tipos de dados que podem ser usados em modelos tabulares e discute a conversão implícita de tipos de dados quando dados são calculados ou usados em uma fórmula DAX (Data Analysis Expressions).  
  
 Este artigo inclui as seções a seguir:  
  
-   [Tipos de dados usados em modelos tabulares](#bkmk_data_types)  
  
-   [Conversão implícita e explícita de tipos de dados em fórmulas DAX](#bkmk_implicit)  
  
-   [Manipulação de espaços em branco, cadeias de caracteres vazias e valores zero](#bkmk_hand_blanks)  
  
##  <a name="bkmk_data_types"></a> Tipos de dados usados em modelos tabulares  
 Há suporte para os seguintes tipos de dados. Quando você importa dados ou usa um valor em uma fórmula, mesmo quando a fonte de dados original contém um tipo de dados diferente, os dados serão convertidos em um dos tipos de dados a seguir. Valores que resultam de fórmulas também usam esses tipos de dados.  
  
 Em geral, esses tipos de dados são implementados para permitir cálculos precisos em colunas calculadas e, para consistência, as mesmas restrições se aplicam ao resto dos dados no modelo.  
  
 Os formatos usados para números, moeda, datas e horas devem seguir o formato da localidade especificada no cliente usado para trabalhar com dados de modelo. É possível usar as opções de formatação do modelo para controlar a forma como o valor é exibido.  
  
||||  
|-|-|-|  
|**Tipo de dados em modelo**|**Tipos de dados em DAX**|**Description**|  
|Número Inteiro|Um valor inteiro de 64 bits (oito bytes)*<br /><br /> Observação:<br />         As fórmulas DAX não dão suporte aos tipos de dados que são muito pequenos para conter o valor mínimo relacionado na descrição.|Números sem casas decimais. Inteiros podem ser números positivos ou negativos, mas devem ser números inteiros entre -9.223.372.036.854.775.808 (-2^63) e 9.223.372.036.854.775.807 (2^63-1).|  
|Número Decimal|Um número real de 64 bits (oito bytes)*<br /><br /> Observação:<br />         As fórmulas DAX não dão suporte aos tipos de dados que são muito pequenos para conter o valor mínimo relacionado na descrição.|Números reais são números que podem ter casas decimais. Os números reais abrangem uma grande variedade de valores:<br /><br /> Valores negativos de -1,79E +308 a -2,23E -308<br /><br /> Zero<br /><br /> Valores positivos de 2,23E -308 a 1,79E + 308<br /><br /> No entanto, o número de dígitos significativos está limitado a 17 dígitos decimais.|  
|Boolean|Boolean|Um valor True ou False.|  
|Texto|Cadeia de caracteres|Uma cadeia de caracteres de dados de caractere Unicode. Podem ser cadeias de caracteres, números ou datas representados em um formato de texto.|  
|Data|Data/hora|Datas e horas em uma representação de data-hora aceita.<br /><br /> As datas válidas são todas as datas depois de 1º de março de 1900.|  
|Moeda|Moeda|O tipo de dados de moeda permite valores entre -922.337.203.685.477,5808 e 922.337.203.685.477,5807 com quatro dígitos decimais de precisão fixa.|  
|N/A|Em branco|Um espaço em branco é um tipo de dados no DAX que representa e substitui nulos SQL. É possível criar um espaço em branco usando a função BLANK e testar se há espaços em branco usando a função lógica, ISBLANK.|  
  
 \* Se você tentar importar dados que tenham valores numéricos muito grandes, poderá haver falha na importação com o seguinte erro:  
  
 Erro de banco de dados na memória: O '\<nome da coluna >' coluna do '\<nome da tabela >' tabela contém um valor de ' 1.7976931348623157e + 308', que não é suportado. A operação foi cancelada.  
  
 Esse erro ocorre porque o designer de modelos usa esse valor para representar nulos. Os valores na lista a seguir são sinônimos do valor nulo mencionado anterior:  
  
||  
|-|  
|Value|  
|9223372036854775807|  
|-9223372036854775808|  
|1,7976931348623158e+308|  
|2,2250738585072014e-308|  
  
 Você deve remover o valor dos dados e tentar importá-los novamente.  
  
> [!NOTE]  
>  Você não pode importar de uma coluna de **varchar(max)** que contém um comprimento da cadeia de caracteres de mais de 131.072 caracteres.  
  
### <a name="table-data-type"></a>Tipo de dados de tabela  
 Além disso, a DAX usa um tipo de dados *table* . Esse tipo de dados é usado pela DAX em muitas funções, como agregações e cálculos de inteligência de hora. Algumas funções exigem uma referência a uma tabela; outras retornam uma tabela que pode ser usada como entrada para outras funções. Em algumas funções que exigem uma tabela como entrada, você pode especificar uma expressão avaliada para uma tabela; para algumas funções, uma referência a uma tabela base é necessária. Para obter informações sobre os requisitos de funções específicas, consulte [Referência de função DAX](http://msdn.microsoft.com/en-us/4dbb28a1-dd1a-4fca-bcd5-e90f74864a7b).  
  
##  <a name="bkmk_implicit"></a> Conversão implícita e explícita de tipos de dados em fórmulas DAX
  
 Cada função DAX tem requisitos específicos quanto aos tipos de dados que são usados como entradas e saídas. Por exemplo, algumas funções exigem inteiros para alguns argumentos e datas para outros; outras funções exigem texto ou tabelas.  
  
 Se os dados na coluna especificada como um argumento forem incompatíveis com o tipo de dados exigido pela função, em muitos casos DAX retornará um erro. Entretanto, sempre que possível, DAX tentará converter implicitamente os dados no tipo de dados exigido. Por exemplo:  
  
-   Você pode digitar um número, por exemplo "123", como uma cadeia de caracteres. O DAX analisará a cadeia de caracteres e tentará especificá-la como um tipo de dados numérico.  
  
-   Você pode adicionar TRUE + 1 e obter o resultado 2, pois TRUE é implicitamente convertido no número 1 e a operação 1+1 é executada.  
  
-   Se você adicionar valores em duas colunas e um valor for representado como texto ("12") e o outro como um número (12), o DAX converterá implicitamente a cadeia de caracteres em um número e, em seguida, adicionará para um resultado numérico. A seguinte expressão retorna 44: = "22" + 22  
  
-   Se você tentar concatenar dois números, o suplemento do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] vai apresentá-los como cadeias de caracteres e, em seguida, concatená-los. A seguinte expressão retorna "1234": = 12 & 34  
  
 A tabela a seguir resume as conversões implícitas de tipo de dados executadas em fórmulas. Em geral, o designer de modelos semânticos se comporta como o Microsoft Excel e executa conversões implícitas sempre que possível quando exigido pela operação especificada.  
  
### <a name="table-of-implicit-data-conversions"></a>Tabela de conversões implícitas de dados  
 O tipo de conversão executada é determinado pelo operador, que converte os valores exigidos antes de executar a operação solicitada. Estas tabelas listam os operadores e indicam a conversão que é executada em cada tipo de dados na coluna quando ele é emparelhado com o tipo de dados na linha de interseção.  
  
> [!NOTE]  
>  Tipos de dados de texto não são incluídos nestas tabelas. Quando um número é representado como em um formato de texto, em alguns casos, o designer de modelos tentará determinar o tipo de número e representá-lo como um número.  
  
#### <a name="addition-"></a>Adição (+)  
  
||||||  
|-|-|-|-|-|  
|Operador (+)|INTEGER|Moeda|REAL|Data/hora|  
|INTEGER|INTEGER|Moeda|REAL|Data/hora|  
|Moeda|Moeda|Moeda|REAL|Data/hora|  
|REAL|REAL|REAL|REAL|Data/hora|  
|Data/hora|Data/hora|Data/hora|Data/hora|Data/hora|  
  
 Por exemplo, se um número real for usado em uma operação de adição com dados de moeda, os dois valores serão convertidos em REAL, e o resultado será retornado como REAL.  
  
#### <a name="subtraction--"></a>Subtração (-)  
 Na tabela a seguir, o cabeçalho da linha é o minuendo (lado esquerdo) e o cabeçalho da coluna é o subtraendo (lado direito).  
  
||||||  
|-|-|-|-|-|  
|Operador (-)|INTEGER|Moeda|REAL|Data/hora|  
|INTEGER|INTEGER|Moeda|REAL|REAL|  
|Moeda|Moeda|Moeda|REAL|REAL|  
|REAL|REAL|REAL|REAL|REAL|  
|Data/hora|Data/hora|Data/hora|Data/hora|Data/hora|  
  
 Por exemplo, se uma data for usada em uma operação de subtração com qualquer outro tipo de dados, os dois valores serão convertidos em datas, e o valor de retorno também será uma data.  
  
> [!NOTE]  
>  Os modelos tabulares também dão suporte ao operador unário, - (negativo), mas esse operador não altera o tipo de dados do operando.  
  
#### <a name="multiplication-"></a>Multiplicação (*)  
  
||||||  
|-|-|-|-|-|  
|Operador (*)|INTEGER|Moeda|REAL|Data/hora|  
|INTEGER|INTEGER|Moeda|REAL|INTEGER|  
|Moeda|Moeda|REAL|Moeda|Moeda|  
|REAL|REAL|Moeda|REAL|REAL|  
  
 Por exemplo, se um inteiro for combinado com um número real em uma operação de multiplicação, os dois números serão convertidos em números reais, e o valor de retorno também será REAL.  
  
#### <a name="division-"></a>Divisão (/)  
 Na tabela a seguir, o cabeçalho da linha é o numerador e o cabeçalho da coluna é o denominador.  
  
||||||  
|-|-|-|-|-|  
|Operador (/)<br /><br /> (Linha/coluna)|INTEGER|Moeda|REAL|Data/hora|  
|INTEGER|REAL|Moeda|REAL|REAL|  
|Moeda|Moeda|REAL|Moeda|REAL|  
|REAL|REAL|REAL|REAL|REAL|  
|Data/hora|REAL|REAL|REAL|REAL|  
  
 Por exemplo, se um inteiro for combinado com um valor de moeda em uma operação de divisão, os dois valores serão convertidos em números reais, e o resultado também será um número real.  
  
#### <a name="comparison-operators"></a>Operadores de comparação  
Há suporte para apenas um conjunto limitado de combinações de tipo de dados mistos para operações de comparação. Para obter mais informações, consulte [Referência de operador DAX](https://msdn.microsoft.com/library/ee634237.aspx).  
  
## <a name="bkmk_hand_blanks"></a> Manipulação de espaços em branco, cadeias de caracteres vazias e valores zero  
 A tabela a seguir resume as diferenças entre DAX e o Microsoft Excel, com relação ao modo como espaços em branco são tratados.  
  
||||  
|-|-|-|  
|Expressão|DAX|Excel|  
|BLANK + BLANK|Em branco|0 (zero)|  
|BLANK +5|5|5|  
|BLANK * 5|Em branco|0 (zero)|  
|5/BLANK|Infinity|Erro|  
|0/BLANK|NaN|Erro|  
|BLANK/BLANK|Em branco|Erro|  
|FALSE OR BLANK|FALSE|FALSE|  
|FALSE AND BLANK|FALSE|FALSE|  
|TRUE OR BLANK|TRUE|TRUE|  
|TRUE AND BLANK|FALSE|TRUE|  
|BLANK OR BLANK|Em branco|Erro|  
|BLANK AND BLANK|Em branco|Erro|  
  
 Para obter detalhes sobre como uma determinada função ou operador manipula espaços em branco, consulte os tópicos individuais de cada função DAX, na seção, [Referência de função DAX](http://msdn.microsoft.com/en-us/4dbb28a1-dd1a-4fca-bcd5-e90f74864a7b).  
  
## <a name="see-also"></a>Consulte também  
 [Fontes de dados &#40;SSAS de Tabela&#41;](../../analysis-services/tabular-models/data-sources-ssas-tabular.md)   
 [Importar dados &#40;SSAS de Tabela&#41;](http://msdn.microsoft.com/library/6617b2a2-9f69-433e-89e0-4c5dc92982cf)  
  
  