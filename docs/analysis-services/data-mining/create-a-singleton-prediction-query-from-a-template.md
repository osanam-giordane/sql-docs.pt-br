---
title: "Criar uma consulta de previsão Singleton a partir de um modelo | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- singleton query predictions [DMX]
ms.assetid: e0a68ab0-bece-4d25-b464-47f1719302e6
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: c54b65567095408f66c01d22b7f39d839ae939b2
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="create-a-singleton-prediction-query-from-a-template"></a>Criar uma consulta de previsão singleton a partir de um modelo
  Uma consulta singleton é útil quando você tem um modelo a ser usado para previsão, mas não deseja mapeá-lo para um conjunto de dados de entrada externo ou fazer previsões em massa. Uma consulta singleton permite oferecer um valor ou valores ao modelo e ver instantaneamente o valor previsto.  
  
 Por exemplo, a consulta DMX a seguir representa uma consulta singleton no modelo de email de destino, TM_Decision_Tree.  
  
```  
SELECT * FROM [TM_Decision_tree] ;  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 O procedimento a seguir descreve como usar o Gerenciador de Modelos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para criar rapidamente esta consulta.  
  
### <a name="to-open-the-analysis-services-templates-in-sql-server-management-studio"></a>Para abrir os modelos de Analysis Services no SQL Server Management Studio  
  
1.  No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Gerenciador de Modelos**.  
  
2.  Clique no ícone de cubo para abrir os modelos de **Analysis Server**.  
  
### <a name="to-open-a-prediction-query-template"></a>Para abrir um modelo de consulta de previsão  
  
1.  Em **Explorador de Modelos**, na lista de modelos de Analysis Server, expanda **DMX**e **Consultas de Previsão**.  
  
2.  Clique duas vezes em **Previsão Singleton**.  
  
3.  Na caixa de diálogo **Conectar ao Analysis Services** , digite o nome do servidor que tem a instância de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém o modelo de mineração a ser consultado.  
  
4.  Clique em **Conectar**.  
  
5.  O modelo é aberto no banco de dados especificado, junto com um Pesquisador de Objetos do modelo de mineração que contém as funções de mineração de dados e uma lista de estruturas de mineração de dados e modelos relacionados.  
  
### <a name="to-customize-the-singleton-query-template"></a>Para personalizar o modelo de consulta singleton  
  
1.  No modelo, clique na lista suspensa **Bancos de Dados Disponíveis** e selecione uma instância de Analysis Service na lista.  
  
2.  Na lista **Modelo de Mineração** , selecione o modelo de mineração que deseja consultar.  
  
     A lista de colunas no modelo de mineração é exibida no painel **Metadados** do pesquisador de objetos.  
  
3.  No menu **Consulta** , selecione **Especificar Valores para Parâmetros de Modelo**.  
  
4.  Na linha **lista de seleção** , digite * para retornar todas as colunas ou digite uma lista delimitada por vírgulas das colunas e expressões para retornar colunas específicas.  
  
     Se você digitar *, a coluna de previsão será retornada, junto com qualquer coluna para a qual você fornece novos valores na etapa 6.  
  
     Para o exemplo de código mostrado no início desse tópico, a linha **lista de seleção** foi definida como *.  
  
5.  Na linha **modelo de mineração** , digite o nome do modelo de mineração da lista de modelos de mineração exibidos no **Explorador de Objetos**.  
  
     Para o exemplo de código mostrado no início desse tópico, a linha **modelo de mineração** foi definido como nome, **TM_Decision_Tree**.  
  
6.  Na linha **valor** , digite o novo valor de dados para os quais você deseja fazer uma previsão.  
  
     Para o exemplo de código no início desse tópico, a linha **valor** foi definida como **2** para prever o comportamento de compras de bicicletas com base no número de crianças em casa.  
  
7.  Na linha **coluna** , digite o nome da coluna no modelo de mineração para o qual os novos dados devem ser mapeados.  
  
     Para o exemplo de código mostrado no início desse tópico, a linha **coluna** foi definida como **Número de Crianças em Casa**.  
  
    > [!NOTE]  
    >  Quando você usa a caixa de diálogo **Especificar Valores para Parâmetros de Modelo** , você não tem que adicionar colchetes ao redor do nome da coluna. Os colchetes serão adicionados automaticamente para você.  
  
8.  Deixe o **alias de entrada** como **t**.  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. No painel de texto de consulta, localize a pequena curva vermelha sob a vírgula e a elipse que indica um erro de sintaxe. Exclua a elipse e adicione qualquer condição de consulta adicional desejada. Se você não quiser adicionar nenhuma outra condição, exclua a vírgula.  
  
     Para o exemplo de código mostrado no início desse tópico, a condição de consulta adicional foi definida como **'45' como [Idade]**.  
  
11. Clique em **Executar**.  
  
## <a name="see-also"></a>Consulte também  
 [Criando previsões &#40;Tutorial básico de Data Mining&#41;](http://msdn.microsoft.com/library/a8410ed2-bb98-4d51-a9eb-b239be1201c2)  
  
  