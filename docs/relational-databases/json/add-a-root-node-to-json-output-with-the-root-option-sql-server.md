---
title: "Adicionar um nó raiz à saída JSON com a opção ROOT (SQL Server) | Microsoft Docs"
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
- ROOT (FOR JSON)
ms.assetid: b9afa74a-f59f-483e-a178-42be2e9882c9
caps.latest.revision: 16
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 9045ebe77cf2f60fecad22672f3f055d8c5fdff2
ms.openlocfilehash: 58948fd1977e2094b1469ab92ac1debf0e7f4b2e
ms.contentlocale: pt-br
ms.lasthandoff: 07/31/2017

---
# <a name="add-a-root-node-to-json-output-with-the-root-option-sql-server"></a>Adicionar um nó raiz à saída JSON com a opção ROOT (SQL Server)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Para adicionar um único elemento de nível superior à saída JSON da cláusula **FOR JSON** , especifique a opção **ROOT** .  
  
 Se você não especificar a opção **ROOT** , a saída JSON não incluirá um elemento raiz.  
  
## <a name="examples"></a>Exemplos  
 A tabela a seguir mostra a saída da cláusula **FOR JSON** com e sem a opção **ROOT** .  
  
 Os exemplos na tabela a seguir pressupõem que o argumento *RootName* opcional esteja vazio. Se você fornecer um nome para o elemento raiz, esse valor substituirá o valor **root** nos exemplos.  
  
 Sem a opção **ROOT**  
  
```json  
{  
   <<json properties>>  
}  
```  
  
```json  
[  
   <<json array elements>>  
]  
```  
  
 Com a opção **ROOT**  
  
```json  
{   
  "root": {  
   <<json properties>>  
 }  
}  
```  
  
```json  
{   
  "root": [  
   << json array elements >>  
  ]  
}  
```  
  
 Veja outro exemplo de uma cláusula **FOR JSON** com a opção **ROOT** . Este exemplo especifica um valor para o argumento *RootName* opcional.  
  
 **Consulta**  
  
```sql  
SELECT TOP 5   
       BusinessEntityID As Id,  
       FirstName, LastName,  
       Title As 'Info.Title',  
       MiddleName As 'Info.MiddleName'  
   FROM Person.Person  
   FOR JSON PATH, ROOT('info')
```  
  
 **Resultado**  
  
```json  
{
    "info": [{
        "Id": 1,
        "FirstName": "Ken",
        "LastName": "Sánchez",
        "Info": {
            "MiddleName": "J"
        }
    }, {
        "Id": 2,
        "FirstName": "Terri",
        "LastName": "Duffy",
        "Info": {
            "MiddleName": "Lee"
        }
    }, {
        "Id": 3,
        "FirstName": "Roberto",
        "LastName": "Tamburello"
    }, {
        "Id": 4,
        "FirstName": "Rob",
        "LastName": "Walters"
    }, {
        "Id": 5,
        "FirstName": "Gail",
        "LastName": "Erickson",
        "Info": {
            "Title": "Ms.",
            "MiddleName": "A"
        }
    }]
}
```  
  
 **Resultado (sem raiz)**  
  
```json  
[{
    "Id": 1,
    "FirstName": "Ken",
    "LastName": "Sánchez",
    "Info": {
        "MiddleName": "J"
    }
}, {
    "Id": 2,
    "FirstName": "Terri",
    "LastName": "Duffy",
    "Info": {
        "MiddleName": "Lee"
    }
}, {
    "Id": 3,
    "FirstName": "Roberto",
    "LastName": "Tamburello"
}, {
    "Id": 4,
    "FirstName": "Rob",
    "LastName": "Walters"
}, {
    "Id": 5,
    "FirstName": "Gail",
    "LastName": "Erickson",
    "Info": {
        "Title": "Ms.",
        "MiddleName": "A"
    }
}]
```  

## <a name="learn-more-about-the-built-in-json-support-in-sql-server"></a>Saiba mais sobre o suporte interno a JSON no SQL Server  
Para ver várias soluções específicas, casos de uso e recomendações, consulte as [postagens no blog sobre o suporte interno a JSON](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) no SQL Server e no Banco de Dados SQL do Azure, publicadas por Jovan Popovic, gerente de programas da Microsoft.
 
## <a name="see-also"></a>Consulte também  
 [Cláusula FOR &#40;Transact-SQL&#41;](../../t-sql/queries/select-for-clause-transact-sql.md)  
  
  
