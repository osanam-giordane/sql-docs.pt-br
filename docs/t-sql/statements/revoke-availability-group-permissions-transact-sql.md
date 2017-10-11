---
title: "Permissões de grupo de disponibilidade REVOKE (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], permissions
- REVOKE statement, availability groups
- revoking permissions, [SQL Server], availability groups
- permissions [SQL Server], availability group
ms.assetid: 02c77378-a36d-4286-9235-d8867a2b92ad
caps.latest.revision: 10
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 1573f866cec3105cde4eeab59c230ede46144ac3
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="revoke-availability-group-permissions-transact-sql"></a>Permissões de grupo de disponibilidade REVOKE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Revoga permissões em um grupo de disponibilidade AlwaysOn. 
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
REVOKE [ GRANT OPTION FOR ] permission  [ ,...n ]   
    ON AVAILABILITY GROUP :: availability_group_name  
    { FROM | TO } < server_principal >  [ ,...n ]  
    [ CASCADE ]  
    [ AS SQL_Server_login ]   
  
<server_principal> ::=   
        SQL_Server_login  
    | SQL_Server_login_from_Windows_login   
    | SQL_Server_login_from_certificate   
    | SQL_Server_login_from_AsymKey  
```  
  
## <a name="arguments"></a>Argumentos  
 *permissão*  
 Especifica uma permissão que pode ser revogada em um grupo de disponibilidade. Para obter uma lista de permissões, consulte a seção Comentários mais adiante neste tópico.  
  
 NO grupo de disponibilidade **::***availability_group_name*  
 Especifica o grupo de disponibilidade no qual a permissão está sendo revogada. O qualificador de escopo (**::**) é necessária.  
  
 {DO | PARA} \<server_principal > especifica o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logon para o qual a permissão está sendo revogada.  
  
 *SQL_Server_login*  
 Especifica o nome de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 *SQL_Server_login_from_Windows_login*  
 Especifica o nome de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criado a partir de um logon do Windows.  
  
 *SQL_Server_login_from_certificate*  
 Especifica o nome de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mapeado para um certificado.  
  
 *SQL_Server_login_from_AsymKey*  
 Especifica o nome de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mapeado para uma chave assimétrica.  
  
 GRANT OPTION  
 Indica que o direito de conceder a permissão especificada a outros principais será revogado. A permissão em si não será revogada.  
  
> [!IMPORTANT]  
>  Se a entidade de segurança tiver a permissão especificada sem a opção GRANT, a própria permissão será revogada.  
  
 CASCADE  
 Indica que a permissão que está sendo revogada também é revogada de outros principais aos quais ela foi concedida ou negada por esse principal.  
  
> [!IMPORTANT]  
>  A revogação em cascata de uma permissão WITH GRANT OPTION concedida revogará as opções GRANT e DENY dessa permissão.  
  
 AS *SQL_Server_login*  
 Especifica o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a partir do qual o principal que executa esta consulta deriva seu direito de revogar a permissão.  
  
## <a name="remarks"></a>Comentários  
 As permissões no escopo do servidor podem ser revogadas somente quando o banco de dados atual é **mestre**.  
  
 Informações sobre grupos de disponibilidade estão visíveis no [availability_groups &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-availability-groups-transact-sql.md) exibição do catálogo. Informações sobre permissões de servidor são visíveis no [server_permissions](../../relational-databases/system-catalog-views/sys-server-permissions-transact-sql.md) exibição de catálogo e obter informações sobre as entidades de servidor é visível no [sys. server_principals](../../relational-databases/system-catalog-views/sys-server-principals-transact-sql.md) exibição do catálogo.  
  
 Um grupo de disponibilidade é um nível de servidor protegível. As permissões mais específicas e limitadas que podem ser revogadas em um grupo de disponibilidade são listadas na tabela a seguir, junto com as permissões mais gerais que as incluem implicitamente.  
  
|Permissão de grupo de disponibilidade|Implícito na permissão de grupo de disponibilidade|Implícito na permissão de servidor|  
|-----------------------------------|----------------------------------------------|----------------------------------|  
|ALTER|CONTROL|ALTER ANY AVAILABILITY GROUP|  
|CONNECT|CONTROL|CONTROL SERVER|  
|CONTROL|CONTROL|CONTROL SERVER|  
|TAKE OWNERSHIP|CONTROL|CONTROL SERVER|  
|VIEW DEFINITION|CONTROL|VIEW ANY DEFINITION|  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão CONTROL no grupo de disponibilidade ou a permissão ALTER ANY AVAILABILITY GROUP no servidor.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-revoking-view-definition-permission-on-an-availability-group"></a>A. Revogando a permissão VIEW DEFINITION em um grupo de disponibilidade  
 O exemplo a seguir revoga a permissão `VIEW DEFINITION` no grupo de disponibilidade `MyAg` para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logon `ZArifin`.  
  
```  
USE master;  
REVOKE VIEW DEFINITION ON AVAILABILITY GROUP::MyAg TO ZArifin;  
GO  
```  
  
### <a name="b-revoking-take-ownership-permission-with-the-cascade"></a>B. Revogando a permissão TAKE OWNERSHIP com CASCADE  
 O exemplo a seguir revoga a permissão `TAKE OWNERSHIP` no grupo de disponibilidade `MyAg` para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usuário `PKomosinski` e de todas as entidades de segurança às quais o `PKomosinski` concedeu TAKE OWNERSHIP em MyAg.  
  
```  
USE master;  
REVOKE TAKE OWNERSHIP ON AVAILABILITY GROUP::MyAg TO PKomosinski   
    CASCADE;  
GO  
```  
  
### <a name="c-revoking-a-previously-granted-with-grant-option-clause"></a>C. Revogando uma cláusula WITH GRANT OPTION previamente concedida  
 Se uma permissão foi concedida usando WITH GRANT OPTION, use REVOKE GRANT OPTION FOR... Para remover WITH GRANT OPTION. O exemplo a seguir concede a permissão e remove a parte de WITH GRANT da permissão.  
  
```  
USE master;  
GRANT CONTROL ON AVAILABILITY GROUP::MyAg TO PKomosinski   
    WITH GRANT OPTION;  
GO  
REVOKE GRANT OPTION FOR CONTROL ON AVAILABILITY GROUP::MyAg TO PKomosinski  
CASCADE  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Permissões de grupo de disponibilidade GRANT &#40; Transact-SQL &#41;](../../t-sql/statements/grant-availability-group-permissions-transact-sql.md)   
 [Negar permissões de grupo de disponibilidade &#40; Transact-SQL &#41;](../../t-sql/statements/deny-availability-group-permissions-transact-sql.md)   
 [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](../../t-sql/statements/create-availability-group-transact-sql.md)   
 [sys. availability_groups &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-availability-groups-transact-sql.md)   
 [Exibições de catálogo de grupos de disponibilidade AlwaysOn &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/always-on-availability-groups-catalog-views-transact-sql.md)   
 [Permissões &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [Entidades &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)  
  
  

