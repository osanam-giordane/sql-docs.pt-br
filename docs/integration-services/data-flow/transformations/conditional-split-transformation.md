---
title: "Transformação de divisão condicional | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.conditionalsplittrans.f1
- sql13.dts.designer.conditionalsplittransformation.f1
helpviewer_keywords:
- Conditional Split transformation
- route rows to different outputs [Integration Services]
ms.assetid: 3f8b5825-226f-413c-ba8f-0bb931ca3770
caps.latest.revision: 51
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 4b557efa62075f7b88e6b70cf5950546444b95d8
ms.openlocfilehash: 02909ff454816119e2dfbdfeb1090d0f7e9587be
ms.contentlocale: pt-br
ms.lasthandoff: 08/19/2017

---
# <a name="conditional-split-transformation"></a>Transformação Divisão Condicional
  A transformação Divisão Condicional pode rotear linhas de dados para saídas diferentes, dependendo do conteúdo dos dados. A implementação da transformação Divisão Condicional é semelhante a uma estrutura de decisão CASE em uma linguagem de programação. A transformação avalia expressões e, com base nos resultados, direciona a linha de dados para a saída especificada. Essa transformação também fornece uma saída padrão, de forma que, se uma linha não corresponder a nenhuma expressão, ela será direcionada para a saída padrão.  
  
## <a name="configuration-of-the-conditional-split-transformation"></a>Configuração da transformação Divisão Condicional  
 É possível configurar a transformação Divisão Condicional do seguinte modo:  
  
-   Para cada condição a ser testada pela transformação, forneça uma expressão a ser avaliada pelo Booleano.  
  
-   Especifique a ordem na qual as condições são avaliadas. A ordem é importante, pois uma linha é enviada à saída correspondente para a primeira condição avaliada como true.  
  
-   Especifique a saída padrão para transformação. É necessário especificar uma saída padrão para a transformação.  
  
 Cada linha de entrada pode ser enviada a apenas uma saída, sendo esta saída a primeira condição avaliada como true. Por exemplo, as condições a seguir direcionam todas as linhas da coluna **FirstName** que começam com a letra *A* para uma saída, as linhas que começam com a letra *B* para uma saída diferente e todas as outras linhas para uma saída padrão.  
  
 Saída 1  
  
 `SUBSTRING(FirstName,1,1) == "A"`  
  
 Saída 2  
  
 `SUBSTRING(FirstName,1,1) == "B"`  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] inclui funções e operadores que podem ser usados para criar as expressões que avaliam dados de entrada e direcionar dados de saída. Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../../../integration-services/expressions/integration-services-ssis-expressions.md).  
  
 A transformação Divisão Condicional inclui a propriedade personalizada **FriendlyExpression**. Essa propriedade pode ser atualizada por uma expressão de propriedade quando o pacote é carregado. Para obter mais informações, consulte [Usar expressões de propriedade em pacotes](../../../integration-services/expressions/use-property-expressions-in-packages.md) e [Propriedades personalizadas da transformação](../../../integration-services/data-flow/transformations/transformation-custom-properties.md).  
  
 Esta transformação tem uma entrada, uma ou mais saídas e uma saída de erro.  
  
 Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.  
  
 A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente. Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:  
  
-   [Propriedades comuns](http://msdn.microsoft.com/library/51973502-5cc6-4125-9fce-e60fa1b7b796)  
  
-   [Propriedades personalizadas de Transformação](../../../integration-services/data-flow/transformations/transformation-custom-properties.md)  
  
 Para obter mais informações sobre como definir propriedades, clique em um dos seguintes tópicos:  
  
-   [Dividir um conjunto de dados por meio da transformação Divisão Condicional](../../../integration-services/data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
-   [Definir as propriedades de um componente de fluxo de dados](../../../integration-services/data-flow/set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a>Tarefas relacionadas  
 [Dividir um conjunto de dados usando a transformação divisão condicional](../../../integration-services/data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
## <a name="conditional-split-transformation-editor"></a>Editor de Transformação Divisão Condicional
  Use a caixa de diálogo **Editor de Transformação Divisão Condicional** para criar expressões, definir a ordem na qual as expressões são avaliadas e nomear as saídas de uma divisão condicional. Essa caixa de diálogo inclui funções matemáticas, de cadeia de caracteres e de data/hora e operadores que você pode usar para criar expressões. A primeira condição avaliada como verdadeira determina a saída para a qual uma linha é direcionada.  
  
> [!NOTE]  
>  A transformação Divisão Condicional direciona cada fila de entrada para uma única de saída. Se você digitar condições múltiplas, a transformação enviará cada fila à primeira saída para a qual a condição é verdadeira e desconsiderará condições subsequentes para aquela fila. Se for necessário avaliar várias condições sucessivamente, você poderá ter que concatenar transformações de Divisão Condicional múltiplas no fluxo de dados.  
  
### <a name="options"></a>Opções  
 **Order**  
 Selecione uma fila e use as teclas de seta à direita para alterar a ordem de avaliação de expressões.  
  
 **Nome de Saída**  
 Forneça um nome de saída. O padrão é uma lista numerada de casos; entretanto, você pode escolher qualquer nome exclusivo e descritivo.  
  
 **Condição**  
 Digite uma expressão ou compile uma arrastando da lista de colunas, variáveis, funções e operadores disponíveis.  
  
 O valor dessa propriedade pode ser especificado com uma expressão de propriedades.  
  
 **Tópicos relacionados**: [Expressões do Integration Services &#40;SSIS&#41;](../../../integration-services/expressions/integration-services-ssis-expressions.md), [Operadores &#40;Expressão SSIS&#41;](../../../integration-services/expressions/operators-ssis-expression.md) e [Funções &#40;Expressão SSIS&#41;](../../../integration-services/expressions/functions-ssis-expression.md)  
  
 **Nome de saída padrão**  
 Digite um nome para a saída padrão ou use o padrão.  
  
 **Configurar saída de erro**  
 Especifique como tratar os erros usando a caixa de diálogo [Configurar Saída de Erro](http://msdn.microsoft.com/library/5f8da390-fab5-44f8-b268-d8fa313ce4b9) .  
  
## <a name="see-also"></a>Consulte também  
 [Fluxo de Dados](../../../integration-services/data-flow/data-flow.md)   
 [Transformações do Integration Services](../../../integration-services/data-flow/transformations/integration-services-transformations.md)  
  
  