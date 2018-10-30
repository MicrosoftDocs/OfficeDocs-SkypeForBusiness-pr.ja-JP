---
title: 通話詳細記録および QoE (Quality of Experience) データベースの手動での削除
TOCTitle: 通話詳細記録および QoE (Quality of Experience) データベースの手動での削除
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48271810
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 通話詳細記録および QoE (Quality of Experience) データベースの手動での削除

 

_**トピックの最終更新日:** 2014-07-07_

以前のセクションで説明したように、管理者は、データベースから古いレコードを自動的に削除するように通話詳細記録 (CDR) か QoE (QoE) データベース、またはその両方を構成できます。これは、指定したデータベース (CDR または QoE) で削除が有効にされ、レコードが指定した時間以上、データベース内にあった場合に行われます。たとえば、毎日、午前 1 時 00 分に、60 日以上経った QoE レコードが QoE データベースから削除されるように、管理者がシステムを構成できます。

自動的な削除に加えて、2 つの新しいコマンドレット、Invoke-CsCdrDatabasePurge と Invoke-CsQoEDatbasePurge が Microsoft Lync Server 2013 に追加されました。これらのコマンドレットにより、管理者は CDR および QoE データベースからいつでも手動でレコードを削除できます。たとえば、CDR データベースから 10 日以上経ったすべてのレコードを手動で削除するには、以下のようなコマンドを使用できます。

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

前述のコマンドは、監視データベース atl-sql-001.litwareinc.com から、10 日以上経過した通話詳細記録と診断データ レコードの両方を削除します。(通話詳細記録はユーザー/セッション レポートを表します。診断データ レコードは Lync 2013 のようなクライアント アプリケーションによってアップロードされた診断ログです。)

上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays および PurgeDiagnosticDataOlderThanDays パラメーターの両方が含まれる必要があります。しかし、これらのパラメーターを同じ値に設定する必要はありません。たとえば、10 日より古い詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。これを行うには、PurgeCallDetailDataOlderThanDays を 10、PurgeDiagnosticDataOlderThanDays を 0 に設定します。次に例を示します。

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

既定では、Invoke-CsCdrDatabasePurge を実行するたびに、削除する必要がある各データベース テーブルごとに、以下のようなメッセージが表示されます。

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

データベース削除が実際に行われる前に、Y (はい (Yes)) または A (すべてはい (Yes to All)) を入力する必要があります。これらの確認メッセージを表示しないようにする場合は、Invoke-CsCdrDatabasePurge の呼び出しの最後に以下のパラメーターを追加します。

    -Confirm:$False

次に例を示します。

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

このようにした場合、確認メッセージは表示されず、データベースの削除はすぐに行われます。

QoE データベースを削除するには、Invoke-CsQoEDatabasePurge コマンドレットを使用し、削除するレコードの保有期間を (日単位で) 指定します。

    Invoke-CsQoEDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

