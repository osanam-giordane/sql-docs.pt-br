---
title: Dispositivo de backup (página Conteúdo de Mídia) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: backup-restore
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql13.swb.backupdevice.contents.f1
ms.assetid: 5fc7bd22-b6d8-4af1-8a58-2e7d0b994d08
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c877ffb5bb15836f21a6a37c7cd8ccb22b27cc10
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67987766"
---
# <a name="backup-device-media-contents-page"></a>Dispositivo de backup (página Conteúdo da Mídia)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Use a caixa de diálogo **Dispositivo de Backup** para exibir as informações de backup. As informações descrevem o dispositivo, a mídia, o conjunto de mídias e o conjunto ou conjuntos de backups.  
  
 **Para usar o SQL Server Management Studio para exibir o conteúdo de um dispositivo de backup**  
  
-   [Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a>Opções  
 Exiba as informações das mídias individuais, conjunto de mídias e os conjuntos de backup.  
  
 **Mídia**  
 Um disco ou um conjunto de fitas nos quais as informações de backup estão armazenadas.  
  
 **Sequência de mídia**  
 Relaciona o número de sequência de mídia; o número de sequência familiar e o identificador de espelhos, se houver. Todas as mídias físicas de backup são marcadas com o número de sequência da mídia que indica a ordem de utilização da mídia. A mídia inicial de backup é identificada com 1, a segunda (a primeira fita de continuação) é identificada com 2, e assim por diante. Quando o conjunto de backup é restaurado, os números sequenciais das mídias garantem que o operador que estiver restaurando o backup esteja montando a mídia correta na ordem apropriada.  
  
 **Criado em**  
 Exibe a data e a hora da criação do conjunto de mídias.  
  
 **Conjunto de mídias**  
 Um conjunto de mídias é uma coleção ordenada de mídias de backup no qual uma ou mais operações de backup foram gravadas usando um número constante de dispositivos de backup.  
  
 **Nome**  
 Exibe o nome do conjunto de mídias, se houver.  
  
 **Descrição**  
 Exibe a descrição do conjunto de mídias, se houver.  
  
 **Contagem de família de mídia**  
 Exibe o número de famílias no conjunto de mídias. Cada conjunto de mídias é uma coleção de uma ou mais famílias de mídias. Toda a saída de um determinado dispositivo de backup único (ou grupo de dispositivos de backup espelhados) forma uma única família de mídias. Cada conjunto de mídias contém uma família para cada dispositivo separado (ou grupo de dispositivos espelhados); por exemplo, se um conjunto de mídias utiliza dois dispositivos de backup não espelhados, o mesmo terá duas famílias de mídias.  
  
 **Conjuntos de backup**  
 Exibe as informações sobre o conjunto ou conjuntos de backup incluídos na mídia. Um conjunto de backup é o resultado de uma operação de backup bem-sucedida cujo conteúdo é distribuído entre as mídias em um conjunto de dispositivos de backup.  
  
|Cabeçalho|Valores|  
|------------|------------|  
|**Nome**|O nome do conjunto de backup.|  
|**Tipo**|O objeto de backup: Banco de dados, Arquivo ou *\<blank>* (para logs de transação).|  
|**Componente**|O tipo de backup realizado: Total, Diferencial ou Log de Transações.|  
|**Servidor**|O nome da instância de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que realizou a operação de backup.|  
|**Backup de banco de dados**|O nome do banco de dados cujo backup foi efetuado.|  
|**Posição**|A posição do conjunto de backup no volume.|  
|**Data**|A data e hora da conclusão da operação de backup, apresentadas na configuração regional do cliente.|  
|**Tamanho**|O tamanho do conjunto de backup em bytes.|  
|**Nome do Usuário**|O nome do usuário que realizou a operação de backup.|  
|**Validade**|A data e hora de validade do conjunto de backup.|  
  
##  <a name="RelatedTasks"></a> Tarefas relacionadas  
  
-   [Definir um dispositivo de backup lógico para um arquivo de disco &#40;SQL Server&#41;](../../relational-databases/backup-restore/define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [Definir um dispositivo de backup lógico para uma unidade de fita &#40;SQL Server&#41;](../../relational-databases/backup-restore/define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [Especificar um disco ou fita como destino de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [Excluir um dispositivo de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/delete-a-backup-device-sql-server.md)  
  
-   [Definir a data de validade em um backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [Exibir os dados e arquivos de log em um conjunto de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [Restaurar um backup de um dispositivo &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Dispositivos de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-devices-sql-server.md)   
 [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
