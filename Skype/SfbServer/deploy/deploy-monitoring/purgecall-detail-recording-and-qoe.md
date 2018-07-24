---
title: ビジネス サーバーの通話詳細記録と Skype で高品質なエクスペリエンスのデータベースを手動で削除します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '概要: は、CDR および QoE データベース Skype ビジネス サーバーの使用からのレコードを手動で削除する方法について説明します。'
ms.openlocfilehash: 14218bbc6af3d05cba3c9886da70ab7155d05159
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006083"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>ビジネス サーバーの通話詳細記録と Skype で高品質なエクスペリエンスのデータベースを手動で削除します。
 
**の概要:** CDR および QoE データベース Skype ビジネス サーバーの使用からのレコードを手動で削除する方法について説明します。
  
CDR および QoE データベースは、レコードを手動または自動で削除できます。レコードの削除は、データが古くならないようにするため、あるいはレポートをリセットして最初からやり直す必要がある場合に重要になります。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>CDR および QoE データベースからレコードを手動で削除する

管理者は、データベースから以前のレコードを自動的に削除するように通話詳細記録 (CDR) か QoE (QoE) データベース、またはその両方を構成できます。これは、指定したデータベース (CDR または QoE) で削除が有効になっており、レコードが指定した時間以上、データベース内にあると実行されます。たとえば、毎日、午前 1 時 00 分に、60 日以上経った QoE レコードが QoE データベースから削除されるように、管理者がシステムを構成できます。
  
だけでなく、自動削除、2 つの新しいコマンドレット & #x やり取りできます。呼び出す CsCdrDatabasePurge を呼び出す CsQoEDatbasePurge & #x やり取りできます。ビジネス サーバの Skype に追加されましたこれらのコマンドレットでは、いつでも、CDR および QoE データベースからレコードを手動で削除する管理者を使用できます。 たとえば、10 日以上のすべてのレコードを手動で削除する CDR データベースから古いを使用できますコマンドのようになります。
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

上記のコマンドでは、詳細レコード、および診断データのレコードが 10 日は、atl の sql-001.litwareinc.com の監視のデータベースから削除されたより古いを呼び出す両方。 (呼び出しの詳細レコードは、ユーザーまたはセッションのレポートです。 診断データ レコードは、診断ログの Skype ビジネス サーバーのクライアント アプリケーションによってアップロードされた)。
  
上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays と PurgeDiagnosticDataOlderThanDays の両方のパラメーターが含まれる必要があります。 ただし、これらのパラメーターを同じ値に設定する必要はありません。 たとえば、10 日より前の詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。 10 と PurgeDiagnosticDataOlderThanDays に PurgeCallDetailDataOlderThanDays を 0 に設定します。 次に例を示します。
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

既定では、Invoke-CsCdrDatabasePurge を実行するたびに、削除する必要がある各データベース テーブルごとに、以下のようなメッセージが表示されます。
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

データベース削除が実際に行われる前に、Y (はい) または A (すべてはい) を入力する必要があります。これらの確認メッセージを表示しないようにする場合は、Invoke-CsCdrDatabasePurge の呼び出しの最後に以下のパラメーターを追加します。
  
```
-Confirm:$False
```

例:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

この操作を実行すると、確認メッセージは表示されず、データベースの削除がすぐに実行されます。
  
QoE データベースを削除するには、Invoke-CsQoEDatabasePurge コマンドレットを使用し、削除するレコードの保有期間を (日単位で) 指定します。
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


