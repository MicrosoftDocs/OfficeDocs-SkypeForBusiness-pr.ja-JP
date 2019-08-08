---
title: Skype for Business Server で通話の記録とエクスペリエンスデータベースの再生の詳細を手動で削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '概要: Skype for Business Server で使用されている CDR および QoE データベースからレコードを手動で削除する方法について説明します。'
ms.openlocfilehash: ba87e05dd72e5da22cfe4e01cd68be1a9fac6242
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239878"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Skype for Business Server で通話の記録とエクスペリエンスデータベースの再生の詳細を手動で削除する
 
**概要:** Skype for Business Server で使用されている CDR および QoE データベースからレコードを手動で削除する方法について説明します。
  
CDR および QoE データベースは、レコードを手動または自動で削除できます。レコードの削除は、データが古くならないようにするため、あるいはレポートをリセットして最初からやり直す必要がある場合に重要になります。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>CDR および QoE データベースからレコードを手動で削除する

管理者は、データベースから以前のレコードを自動的に削除するように通話詳細記録 (CDR) か QoE (QoE) データベース、またはその両方を構成できます。これは、指定したデータベース (CDR または QoE) で削除が有効になっており、レコードが指定した時間以上、データベース内にあると実行されます。たとえば、毎日、午前 1 時 00 分に、60 日以上経った QoE レコードが QoE データベースから削除されるように、管理者がシステムを構成できます。
  
自動的な消去に加えて、CsCdrDatabasePurge と &#x2014; という2つの新しいコマンド &#x2014; レットが Skype for Business Server に追加されました。これらのコマンドレットを使用すると、管理者はいつでも CDR と QoE データベースからレコードを手動で削除できます。 たとえば、CDR データベースから10日以上経過しているすべてのレコードを手動で消去するには、次のようなコマンドを使用できます。
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

上記のコマンドでは、両方の通話の詳細レコードと、10日以上経過した診断データレコードが atl-sql-001.litwareinc.com の監視データベースから削除されます。 (通話の詳細レコードは、ユーザー/セッションレポートです。 診断データレコードは、Skype for Business Server などのクライアントアプリケーションによってアップロードされた診断ログです。)
  
上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays と PurgeDiagnosticDataOlderThanDays の両方のパラメーターが含まれる必要があります。 ただし、これらのパラメーターを同じ値に設定する必要はありません。 たとえば、10 日より前の詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。 そのためには、PurgeCallDetailDataOlderThanDays を10、PurgeDiagnosticDataOlderThanDays を0に設定します。 次に例を示します。
  
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


