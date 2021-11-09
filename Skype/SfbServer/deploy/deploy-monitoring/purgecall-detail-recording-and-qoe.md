---
title: 通話の詳細記録と Quality of Experience データベースを手動で削除Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '概要: CDR と、ユーザーが使用する QoE データベースからレコードを手動で削除するSkype for Business Server。'
ms.openlocfilehash: edaeb5d34fefe1ea8f50da4d7bb4bb31c94c62b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851601"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>通話の詳細記録と Quality of Experience データベースを手動で削除Skype for Business Server
 
**概要:** CDR と、ユーザーが使用する QoE データベースからレコードを手動で削除するSkype for Business Server。
  
CDR データベースと QoE データベースは、レコードを手動または自動的に削除できます。 レコードの削除は、データが古くならないか、または開始基準からレポートをリセットする必要がある場合に重要な場合があります。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>CDR データベースと QoE データベースからレコードを手動で削除する

管理者は、データベースから古いレコードを自動的に削除するために、通話詳細記録 (CDR) データベースまたは QoE データベースを構成できます。これは、指定されたデータベース (CDR または QoE) に対して削除が有効になっている場合と、指定した時間より長いデータベース内にレコードがある場合に発生します。 たとえば、毎日午前 1 時に管理者がシステムを構成して、60 日を超える QoE レコードが QoE データベースから削除される可能性があります。
  
この自動削除に加えて、2 つの新しいコマンドレット&#x2014; Invoke-CsCdrDatabasePurge、Invoke-CsQoEDatbasePurge &#x2014;に追加Skype for Business Server。これらのコマンドレットを使用すると、管理者は CDR データベースと QoE データベースからいつでもレコードを手動で削除できます。 たとえば、CDR データベースから 10 日以上前のすべてのレコードを手動で削除するには、次のようなコマンドを使用できます。
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

前のコマンドでは、10 日を超える通話詳細レコードと診断データ レコードの両方が、atl-sql-001.litwareinc.com の監視データベースから削除されます。 (通話詳細レコードはユーザー/セッション レポートです。 診断データ レコードは、クライアント アプリケーションによってアップロードされた診断ログ (Skype for Business Server)。)
  
上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays および PurgeDiagnosticDataOlderThanDays パラメーターの両方が含まれる必要があります。 しかし、これらのパラメーターを同じ値に設定する必要はありません。 たとえば、10 日より古い詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。 これを行うには、PurgeCallDetailDataOlderThanDays を 10 に、PurgeDiagnosticDataOlderThanDays を 0 に設定します。 次に例を示します。
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

既定では、Invoke-CsCdrDatabasePurge を実行するたびに、削除する必要がある各データベース テーブルごとに、以下のようなメッセージが表示されます。
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

データベース削除が実際に行われる前に、Y (はい (Yes)) または A (すべてはい (Yes to All)) を入力する必要があります。これらの確認メッセージを表示しないようにする場合は、Invoke-CsCdrDatabasePurge の呼び出しの最後に以下のパラメーターを追加します。
  
```powershell
-Confirm:$False
```

次に例を示します。
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

このようにした場合、確認メッセージは表示されず、データベースの削除はすぐに行われます。
  
QoE データベースを削除するには、Invoke-CsQoEDatabasePurge コマンドレットを使用し、削除するレコードの保有期間を (日単位で) 指定します。
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


