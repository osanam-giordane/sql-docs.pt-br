---
title: Criar faturas e formulários com listas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.date: 03/07/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-design
ms.topic: conceptual
ms.assetid: c33231a5-b3a8-42e4-95bc-d05bdf2222f5
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b8ec0531056ea1a4ae3ff1850baed21dfb61df8e
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "65581505"
---
# <a name="create-invoices-and-forms-with-lists-report-builder-and-ssrs"></a>Criar faturas e formulários com listas (Construtor de Relatórios e SSRS)
  Uma região de dados de lista se repete a cada grupo ou linha no conjunto de dados de relatório paginado do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] . Uma lista pode ser usada para criar relatórios ou formulários de forma livre, como faturas, ou em conjunto com outras regiões de dados. É possível definir listas que contenham qualquer número de itens de relatório. Uma lista pode ser aninhada wit  
  
 Para começar a trabalhar rapidamente com listas, consulte [Tutorial: criando um relatório de formato livre &#40;Construtor de Relatórios&#41;](../../reporting-services/tutorial-creating-a-free-form-report-report-builder.md).  
  
> [!NOTE]  
>  É possível publicar listas separadamente de um relatório como partes do relatório. Leia mais sobre [Partes de relatório (Construtor de Relatórios e SSRS)](../../reporting-services/report-design/report-parts-report-builder-and-ssrs.md).  
  
##  <a name="AddingList"></a> Adicionando uma lista ao relatório  
 Adicione uma lista à superfície de design usando a guia Inserir ou a faixa de opções. Por padrão, inicialmente a lista contém uma única célula em uma linha associada ao grupo de detalhes.  
  
 ![Item de relatório Nova Lista na área de design](../../reporting-services/report-design/media/rs-listtemplatenew.gif "Item de relatório Nova Lista na área de design")  
  
 Quando você seleciona uma lista na superfície de design, os identificadores de linha e de coluna são exibidos, conforme mostra a figura a seguir.  
  
 ![Nova Lista adicionada por meio da Caixa de Ferramentas, selecionada](../../reporting-services/report-design/media/rs-listtemplatenewselected.gif "Nova Lista adicionada por meio da Caixa de Ferramentas, selecionada")  
  
 A lista inicial é um modelo baseado na região de dados tablix. Após a inclusão de uma lista, você pode aprimorar o design alterando o conteúdo ou a aparência da lista, com a especificação de expressões de filtro, de classificação ou de grupo, ou com a alteração da forma de exibição da lista nas páginas do relatório. Para obter mais informações, consulte [Controlando a exibição da região de dados Tablix em uma página do relatório &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/controlling-the-tablix-data-region-display-on-a-report-page.md). Embora a lista comece com uma única coluna e linha, é possível continuar desenvolvendo o design da lista, adicionando grupos aninhados ou adjacentes de linhas ou de colunas ou linhas detalhadas adicionais. Para obter mais informações, consulte [Explorando a flexibilidade de uma região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/exploring-the-flexibility-of-a-tablix-data-region-report-builder-and-ssrs.md).  
  
  
##  <a name="DisplayingLayout"></a> Exibindo dados em um layout de forma livre  
 Para organizar dados de relatório em um layout de forma livre, e não em uma grade, é possível adicionar uma lista à superfície de design. Arraste campos do painel de dados do relatório para a célula. Por padrão, a célula contém um retângulo que funciona como um contêiner. Mova todos os campos do contêiner até obter o design desejado. Use as linhas de ajuste exibidas quando você arrasta caixas de texto no contêiner de retângulo para ajudar você a alinhar as bordas vertical e horizontalmente. Remova o espaço em branco indesejado, ajustando o tamanho da célula. Para obter mais informações, consulte [Alterar a altura da linha ou a largura da coluna &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/change-row-height-or-column-width-report-builder-and-ssrs.md).  
  
 A seguinte figura mostra uma lista que exibe informações sobre uma ordem, inclusive os campos: Data, Ordem, Quantidade, Produto, LineTotal e uma imagem.  
  
 ![Lista no modo de exibição de Design, quatro campos e uma imagem](../../reporting-services/report-design/media/rs-basiclistformdesign.gif "Lista no modo de exibição de Design, quatro campos e uma imagem")  
  
 Em Visualização, a lista se repete para exibir os dados de campo no formato sem forma, como mostrado na seguinte figura:  
  
 ![Visualização da lista com quatro campos e uma imagem](../../reporting-services/report-design/media/rs-basiclistformpreview.gif "Visualização da lista com quatro campos e uma imagem")  
  
> [!NOTE]  
>  As exibições de linhas pontilhadas dessas figuras são incluídas para mostrar o layout sem forma de cada valor. Normalmente, você não usaria linhas pontilhadas em um relatório de produção.  
  
  
##  <a name="DisplayingGrouping"></a> Exibindo dados com um nível de agrupamento  
 Como uma lista fornece um contêiner automaticamente, é possível usar uma lista para exibir dados agrupados com várias exibições. Para alterar a lista padrão e especificar um grupo, edite o grupo Detalhes, especifique um nome novo e uma expressão de grupo.  
  
 Por exemplo, você pode inserir uma tabela e um gráfico que mostram exibições diferentes do mesmo conjunto de dados. É possível adicionar um grupo à lista para que os itens de relatório aninhados se repitam uma vez para todos os valores do grupo. A seguinte figura mostra uma lista agrupada por categoria de produto. Observe que não há nenhuma linha detalhada. Duas tabelas são aninhadas lado a lado na lista. A primeira tabela exibe as subcategorias com vendas totais. A segunda exibe a categoria agrupada por área geográfica, com um gráfico que mostra a distribuição das subcategorias.  
  
 ![Uma lista com duas tabelas, uma com um gráfico aninhado](../../reporting-services/report-design/media/rs-basiclistgroupdesign.gif "Uma lista com duas tabelas, uma com um gráfico aninhado")  
  
 Em Visualização, a tabela exibe vendas totais de todas as subcategorias de bicicletas, e a tabela ao lado exibe a divisão das vendas por área geográfica. Usando uma expressão para especificar a cor do plano de fundo da tabela e uma paleta personalizada do gráfico, a primeira tabela também fornece a legenda das cores do gráfico.  
  
 ![Visualização, duas tabelas, uma com um gráfico aninhado](../../reporting-services/report-design/media/rs-basiclistgrouppreview.gif "Visualização, duas tabelas, uma com um gráfico aninhado")  
  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/report-builder-functions-aggregate-functions-reference.md)   
 [Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)  
  
  
