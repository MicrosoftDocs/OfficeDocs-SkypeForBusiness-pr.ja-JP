---
title: 通話の記録とエクスペリエンスデータベースの品質を手動で削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50d7de2fdb63b9152731214edeff3bf9c03aa634
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Lync Server 2013 で通話の記録とエクスペリエンスデータベースの記録を手動で削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-07-07_

管理者は、データベースから以前のレコードを自動的に削除するように通話詳細記録 (CDR) か QoE (QoE) データベース、またはその両方を構成できます。これは、指定したデータベース (CDR または QoE) で削除が有効になっており、レコードが指定した時間以上、データベース内にあると実行されます。たとえば、毎日、午前 1 時 00 分に、60 日以上経った QoE レコードが QoE データベースから削除されるように、管理者がシステムを構成できます。

自動パージに加えて、CsCdrDatabasePurge とという2つの新しいコマンドレットが、Microsoft Lync Server 2013 に追加されています。これらのコマンドレットを使用すると、管理者はいつでも CDR と QoE データベースからレコードを手動で削除できます。 たとえば、CDR データベースから10日以上経過しているすべてのレコードを手動で消去するには、次のようなコマンドを使用できます。

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

上記のコマンドでは、両方の通話の詳細レコードと、10日以上経過した診断データレコードが atl-sql-001.litwareinc.com の監視データベースから削除されます。 (通話の詳細レコードは、ユーザー/セッションレポートです。 診断データレコードは、Lync 2013 などのクライアントアプリケーションによってアップロードされた診断ログです。)

上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays と PurgeDiagnosticDataOlderThanDays の両方のパラメーターが含まれる必要があります。 ただし、これらのパラメーターを同じ値に設定する必要はありません。 たとえば、10 日より前の詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。 そのためには、PurgeCallDetailDataOlderThanDays を10、PurgeDiagnosticDataOlderThanDays を0に設定します。 次に例を示します。

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

既定では、Invoke-CsCdrDatabasePurge を実行するたびに、削除する必要がある各データベース テーブルごとに、以下のようなメッセージが表示されます。

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

データベース削除が実際に行われる前に、Y (はい) または A (すべてはい) を入力する必要があります。これらの確認メッセージを表示しないようにする場合は、Invoke-CsCdrDatabasePurge の呼び出しの最後に以下のパラメーターを追加します。

    -Confirm:$False

例:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

この操作を実行すると、確認メッセージは表示されず、データベースの削除がすぐに実行されます。

QoE データベースを削除するには、Invoke-CsQoEDatabasePurge コマンドレットを使用し、削除するレコードの保有期間を (日単位で) 指定します。

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

