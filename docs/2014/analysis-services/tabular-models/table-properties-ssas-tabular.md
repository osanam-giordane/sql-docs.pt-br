---
title: Propriedades (SSAS Tabular) da tabela | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 97d6731c5e85c3b37facc7172ecacbd2c7c74176
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2019
ms.locfileid: "66066468"
---
# <a name="table-properties-ssas-tabular"></a>Propriedades da tabela (SSAS tabular)
  Este tópico descreve as propriedades do modelo de tabela. As propriedades descritas aqui são diferentes daquelas na caixa de diálogo Editar Propriedades de Tabela, que definem quais colunas da origem são importadas.  
  
 Seções neste tópico:  
  
-   [Propriedades da tabela](#bkmk_properties)  
  
-   [Para definir as configurações de propriedade de tabela](#bkmk_config_prop)  
  
##  <a name="bkmk_properties"></a> Propriedades da tabela  
 **Basic**  
  
|Propriedade|Configuração padrão|Descrição|  
|--------------|---------------------|-----------------|  
|**Nome da conexão**|\<nome da conexão >|O nome da conexão à fonte de dados da tabela.<br /><br /> Para editar a conexão, clique no botão.|  
|**Oculto**|Falso|Especifica se a tabela é ocultada das listas de campo de cliente de relatório.|  
|**Partições**||As partições para a tabela não podem ser exibidas na janela **Propriedades** . Para exibir, criar ou editar partições, clique no botão para abrir o Gerenciador de Partições.|  
|**Dados de origem**||Os dados de origem da tabela não podem ser exibidos na janela **Propriedades** . Para exibir ou editar os dados de origem, clique no botão para abrir a caixa de diálogo Editar Propriedades da Tabela.|  
|**Descrição da tabela**||Uma descrição de texto da tabela.<br /><br /> No [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], se um usuário final colocar o cursor sobre esta tabela na lista de campos, a descrição aparecerá como uma dica de ferramenta.|  
|**Nome da tabela**|\<nome amigável >|Especifica o nome amigável da tabela. O nome da tabela pode ser especificado quando uma tabela é importada com o uso do Assistente de Importação de Tabela ou a qualquer momento após a importação. O nome da tabela no modelo pode ser diferente da tabela associada na origem. O nome amigável da tabela aparece na lista de campos do aplicativo cliente de relatório e no banco de dados modelo no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].|  
  
 **Propriedades de relatório**  
  
 Para obter descrições detalhadas e informações de configuração das propriedades de relatório, consulte [Propriedades de relatório do Power View &#40;SSAS de Tabela&#41;](properties-ssas-tabular.md).  
  
|Propriedade|Configuração padrão|Descrição|  
|--------------|---------------------|-----------------|  
|**Conjunto de Campos Padrão**|||  
|Comportamento de tabela|||  
  
###  <a name="bkmk_config_prop"></a> Para definir as configurações de propriedade de tabela  
  
1.  No designer de modelos, na Exibição de Dados, clique em uma tabela (guia) ou, na Exibição de Diagrama, clique em um cabeçalho de tabela.  
  
2.  Na janela **Propriedades** , clique em uma propriedade e digite um valor ou clique no botão para obter opções de configuração adicionais.  
  
  
