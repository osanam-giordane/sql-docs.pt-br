---
title: "Usar a saída FOR JSON no SQL Server e em aplicativos cliente (SQL Server) | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 06/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-json
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FOR JSON, using in client apps
- FOR JSON, using in SQL Server
ms.assetid: 302e5397-b499-4ea3-9a7f-c24ccad698eb
caps.latest.revision: 12
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 9045ebe77cf2f60fecad22672f3f055d8c5fdff2
ms.openlocfilehash: 1fa05e61c8c057141eceee65c5c1da39c5d4200e
ms.contentlocale: pt-br
ms.lasthandoff: 07/31/2017

---
# <a name="use-for-json-output-in-sql-server-and-in-client-apps-sql-server"></a>Usar a saída FOR JSON no SQL Server e em aplicativos cliente (SQL Server)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

Os exemplos a seguir demonstram algumas maneiras de usar a cláusula **FOR JSON** ou sua saída JSON em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou em aplicativos cliente.  
  
## <a name="use-for-json-output-in-sql-server-variables"></a>Use a saída FOR JSON em variáveis do SQL Server  
A saída da cláusula FOR JSON é do tipo NVARCHAR(MAX), portanto pode ser atribuída a qualquer variável, conforme mostrado no exemplo a seguir.  
  
```sql  
DECLARE @x NVARCHAR(MAX) = (SELECT TOP 10 * FROM Sales.SalesOrderHeader FOR JSON AUTO)  
```  
  
## <a name="use-for-json-output-in-sql-server-user-defined-functions"></a>Usar a saída FOR JSON em funções definidas pelo usuário do SQL Server  
 Você pode criar funções definidas pelo usuário que formate conjuntos de resultados como JSON e retornam essa saída JSON. O exemplo a seguir cria uma função definida pelo usuário que busca linhas de detalhes de um pedido de vendas e formata como uma matriz JSON.  
  
```sql  
CREATE FUNCTION GetSalesOrderDetails(@salesOrderId int)  
 RETURNS NVARCHAR(MAX)  
AS  
BEGIN  
   RETURN (SELECT UnitPrice, OrderQty  
           FROM Sales.SalesOrderDetail  
           WHERE SalesOrderID = @salesOrderId  
           FOR JSON AUTO)  
END
```  
  
 Você pode usar essa função em um lote ou consulta, como mostrado no exemplo a seguir.  
  
```sql  
DECLARE @x NVARCHAR(MAX) = dbo.GetSalesOrderDetails(43659)

PRINT dbo.GetSalesOrderDetails(43659)

SELECT TOP 10
  H.*, dbo.GetSalesOrderDetails(H.SalesOrderId) AS Details
FROM Sales.SalesOrderHeader H
```  
  
## <a name="merge-parent-and-child-data-into-a-single-table"></a>Mesclar dados pai e filho em uma única tabela  
No exemplo a seguir, cada conjunto de linhas filho é formatado como uma matriz JSON. A matriz JSON torna-se o valor da coluna Detalhes na tabela pai.  
  
```sql  
SELECT TOP 10 SalesOrderId, OrderDate,  
      (SELECT TOP 3 UnitPrice, OrderQty  
         FROM Sales.SalesOrderDetail D  
         WHERE H.SalesOrderId = D.SalesOrderID  
         FOR JSON AUTO) AS Details  
INTO SalesOrder  
FROM Sales.SalesOrderHeader H  
```  
  
## <a name="update-the-data-in-json-columns"></a>Atualizar os dados nas colunas JSON  
 O exemplo a seguir demonstra que você pode atualizar o valor das colunas que contêm texto JSON.  
  
```sql  
UPDATE SalesOrder  
SET Details =  
     (SELECT TOP 1 UnitPrice, OrderQty  
       FROM Sales.SalesOrderDetail D  
       WHERE D.SalesOrderId = SalesOrder.SalesOrderId  
      FOR JSON AUTO 
```  
  
## <a name="use-for-json-output-in-a-c-client-app"></a>Use a saída JSON em um aplicativo cliente C#  
 O exemplo a seguir mostra como recuperar a saída JSON de uma consulta em um objeto StringBuilder em um aplicativo cliente C#. Suponha que a variável `queryWithForJson` contém o texto de uma instrução SELECT com uma cláusula FOR JSON.  
  
```csharp  
var queryWithForJson = "SELECT ... FOR JSON";
var conn = new SqlConnection("<connection string>");
var cmd = new SqlCommand(queryWithForJson, conn);
conn.Open();
var jsonResult = new StringBuilder();
var reader = cmd.ExecuteReader();
if (!reader.HasRows)
{
    jsonResult.Append("[]");
}
else
{
    while (reader.Read())
    {
        jsonResult.Append(reader.GetValue(0).ToString());
    }
}
```  

## <a name="learn-more-about-the-built-in-json-support-in-sql-server"></a>Saiba mais sobre o suporte interno a JSON no SQL Server  
Para ver várias soluções específicas, casos de uso e recomendações, consulte as [postagens no blog sobre o suporte interno a JSON](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) no SQL Server e no Banco de Dados SQL do Azure por Jovan Popovic, gerente de programas da Microsoft.
 
## <a name="see-also"></a>Consulte também  
 [Formatar os resultados da consulta como JSON com o FOR JSON &#40;SQL Server&#41;](../../relational-databases/json/format-query-results-as-json-with-for-json-sql-server.md)  
  
  
