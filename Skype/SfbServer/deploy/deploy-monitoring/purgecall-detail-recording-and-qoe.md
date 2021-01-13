---
title: Skype for Business Server で通話詳細記録データベースと Quality of Experience データベースを手動で削除する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '概要: Skype for Business Server で使用される CDR および QoE データベースからレコードを手動で削除する方法について学習します。'
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802147"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Skype for Business Server で通話詳細記録データベースと Quality of Experience データベースを手動で削除する
 
**概要:** Skype for Business Server で使用される CDR および QoE データベースからレコードを手動で削除する方法について学習します。
  
CDR データベースと QoE データベースは、レコードを手動または自動で削除できます。 レコードの削除は、データが古くならないか、またはレポートを開始基準からリセットする必要がある場合に重要です。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>CDR および QoE データベースからレコードを手動で削除する

管理者は、通話詳細記録 (CDR) データベースや QoE (Quality of Experience) データベースを構成して、古いレコードをデータベースから自動的に削除できます。これは、指定したデータベース (CDR または QoE) に対して削除が有効になっている場合、およびデータベース内に指定した時間を超えるレコードが存在する場合に発生します。 たとえば、毎日午前 1 時に管理者がシステムを構成して、60 日以上前の QoE レコードが QoE データベースから削除される可能性があります。
  
この自動削除に加えて、Skype for Business Server &#x2014; Invoke-CsCdrDatabasePurgeとInvoke-CsQoEDatbasePurge &#x2014; 2 つの新しいコマンドレットが追加されました。これらのコマンドレットを使用すると、管理者は CDR および QoE データベースからいつでもレコードを手動で削除できます。 たとえば、CDR データベースから 10 日以上前のすべてのレコードを手動で削除するには、次のようなコマンドを使用できます。
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

前のコマンドでは、通話詳細記録と 10 日以上前の診断データ レコードの両方が、通話詳細記録の監視データベースから削除atl-sql-001.litwareinc.com。 (通話詳細レコードはユーザー/セッション レポートです。 診断データ レコードは、Skype for Business Server などのクライアント アプリケーションによってアップロードされた診断ログです)。
  
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


