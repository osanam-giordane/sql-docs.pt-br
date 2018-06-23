---
title: CircularString | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-spatial
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9fe06b03-d98c-4337-9f89-54da98f49f9f
caps.latest.revision: 26
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 8f8d6b042c1284dc0a0b716524f381017320306e
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36117849"
---
# <a name="circularstring"></a>CircularString
  A `CircularString` é uma coleção de zero ou mais segmentos de arco circulares contínuos. Um segmento de arco circular é um segmento curvado definido por três pontos em um plano bidimensional; o primeiro ponto não pode ser igual ao terceiro ponto. Se todos os três pontos de um segmento de arco circular forem colineares, o segmento de arco será tratado como um segmento de linha.  
  
> [!IMPORTANT]  
>  Para obter uma descrição detalhada e exemplos dos novos recursos espaciais introduzidos no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], incluindo o `CircularString` subtipo, baixe o white paper, [novos recursos espaciais no SQL Server 2012](http://go.microsoft.com/fwlink/?LinkId=226407).  
  
## <a name="circularstring-instances"></a>Instâncias CircularString  
 O desenho seguinte mostra válido `CircularString` instâncias:  
  
 ![](../../database-engine/media/5ff17e34-b578-4873-9d33-79500940d0bc.png "5ff17e34-b578-4873-9d33-79500940d0bc")  
  
### <a name="accepted-instances"></a>Instâncias aceitas  
 Um `CircularString` instância será aceita se estiver vazia ou contém um número ímpar de pontos, n, onde n > 1. O seguinte `CircularString` instâncias são aceitas.  
  
```  
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';  
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';  
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 2 0, 1 1)';  
```  
  
 `@g3` mostra que `CircularString` instância pode ser aceita, mas não é válido. A declaração da instância CircularString a seguir não é aceita. Esta declaração lança uma `System.FormatException`.  
  
```  
DECLARE @g geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1)';  
```  
  
### <a name="valid-instances"></a>Instâncias válidas  
 Uma opção válida `CircularString` instância deve estar vazia ou ter os seguintes atributos:  
  
-   Deve conter, pelo menos, um segmento de arco circular (ou seja, que tenha um mínimo de três pontos).  
  
-   O último ponto de extremidade para cada segmento de arco circular na sequência, com exceção do último segmento, deve ser o primeiro ponto de extremidade para o próximo segmento na sequência.  
  
-   Deve ter um número ímpar de pontos.  
  
-   Não pode se sobrepor a um intervalo.  
  
-   Embora `CircularString` instâncias podem conter segmentos de linha, esses segmentos de linha devem ser definidos por três pontos colineares.  
  
 O exemplo a seguir mostra um `CircularString` instâncias.  
  
```  
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';  
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';  
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1, 0 1)';  
DECLARE @g4 geometry = 'CIRCULARSTRING(1 1, 2 2, 2 2)';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(),@g4.STIsValid();  
```  
  
 Uma instância `CircularString` deve conter, pelo menos, dois segmentos de arco circulares para definir um círculo completo. Um `CircularString` instância não pode usar um segmento de arco circular único (como (1 1, 1 3, 1 1)) para definir um círculo completo. Use (1 1, 2 2, 3 1, 2 0, 1 1) para definir o círculo.  
  
 O exemplo a seguir mostra instâncias CircularString que não são válidas.  
  
```  
DECLARE @g1 geometry = 'CIRCULARSTRING(1 1, 2 0, 1 1)';  
DECLARE @g2 geometry = 'CIRCULARSTRING(0 0, 0 0, 0 0)';  
SELECT @g1.STIsValid(), @g2.STIsValid();  
```  
  
### <a name="instances-with-collinear-points"></a>Instâncias com pontos colineares  
 Nos casos a seguir, um segmento de arco circular será tratado como um segmento de linha:  
  
-   Quando todos os três pontos são colineares (por exemplo, (1 3, 4 4, 7 5)).  
  
-   Quando o primeiro ponto e o ponto mediano são os mesmos, mas o terceiro ponto é diferente (por exemplo, (1 3, 1 3, 7 5)).  
  
-   Quando o primeiro e o último pontos são os mesmos, mas o primeiro ponto é diferente (por exemplo, (1 3, 4 4, 4 4)).  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-instantiating-a-geometry-instance-with-an-empty-circularstring"></a>A. Criando uma instância de geometry com uma CircularString vazia  
 Esse exemplo mostra como criar uma instância `CircularString` vazia:  
  
```tsql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CIRCULARSTRING EMPTY');  
```  
  
### <a name="b-instantiating-a-geometry-instance-using-a-circularstring-with-one-circular-arc-segment"></a>B. Criando uma instância de geometry usando uma CircularString com um segmento de arco circular  
 O exemplo a seguir mostra como criar uma instância `CircularString` com um único segmento de arco circular (meio-círculo):  
  
```tsql  
DECLARE @g geometry;  
SET @g = geometry:: STGeomFromText('CIRCULARSTRING(2 0, 1 1, 0 0)', 0);  
SELECT @g.ToString();  
```  
  
### <a name="c-instantiating-a-geometry-instance-using-a-circularstring-with-multiple-circular-arc-segments"></a>C. Criando uma instância de geometry usando uma CircularString com vários segmentos de arco circular  
 O exemplo a seguir mostra como criar um `CircularString` instância com mais de um segmento de arco circular (círculo cheio):  
  
```tsql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CIRCULARSTRING(2 1, 1 2, 0 1, 1 0, 2 1)');  
SELECT 'Circumference = ' + CAST(@g.STLength() AS NVARCHAR(10));    
```  
  
 Isso gera a saída a seguir:  
  
```  
Circumference = 6.28319  
```  
  
 Compare a saída quando `LineString` é usada em vez de `CircularString`:  
  
```tsql  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('LINESTRING(2 1, 1 2, 0 1, 1 0, 2 1)', 0);  
SELECT 'Perimeter = ' + CAST(@g.STLength() AS NVARCHAR(10));  
```  
  
 Isso gera a saída a seguir:  
  
```  
Perimeter = 5.65685  
```  
  
 Observe que o valor para o `CircularString` exemplo estiver perto de 2 ∏, que é a circunferência real do círculo.  
  
### <a name="d-declaring-and-instantiating-a-geometry-instance-with-a-circularstring-in-the-same-statement"></a>D. Declarando e criando uma instância de geometry com uma CircularString na mesma instrução  
 Este trecho mostra como declarar e criar uma instância de `geometry` com uma `CircularString` na mesma instrução:  
  
```tsql  
DECLARE @g geometry = 'CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)';  
```  
  
### <a name="e-instantiating-a-geography-instance-with-a-circularstring"></a>E. Criando uma instância de geography com uma CircularString  
 O exemplo a seguir mostra como declarar e criar uma instância de `geography` com uma `CircularString`:  
  
```tsql  
DECLARE @g geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';  
```  
  
### <a name="f-instantiating-a-geometry-instance-with-a-circularstring-that-is-a-straight-line"></a>F. Criando uma instância de geometry com uma CircularString que é uma linha reta  
 O exemplo a seguir mostra como criar uma instância `CircularString` que é uma linha reta:  
  
```tsql  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('CIRCULARSTRING(0 0, 1 2, 2 4)', 0);  
```  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral de tipos de dados espaciais](spatial-data-types-overview.md)   
 [CompoundCurve](compoundcurve.md)   
 [MakeValid &#40;tipos de dados geography&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type)   
 [MakeValid &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type)   
 [STIsValid &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)   
 [STIsValid &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type)   
 [STLength &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)   
 [STStartPoint &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type)   
 [STEndpoint &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type)   
 [STPointN &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)   
 [STNumPoints &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type)   
 [STIsRing &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)   
 [STIsClosed &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)   
 [STPointOnSurface &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)   
 [LineString](linestring.md)  
  
  