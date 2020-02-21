---
title: 通話詳細記録と qoe (Quality of Experience) データベースを手動で削除する
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
ms.openlocfilehash: 6797d5e65f182e8a28bb442858070ffed19fcc80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Lync Server 2013 で通話詳細記録と qoe (Quality of Experience) データベースを手動で削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-07-07_

管理者は、通話詳細記録 (CDR) や QoE (Quality of Experience) データベースを構成して、データベースから古いレコードを自動的に削除することができます。これは、指定されたデータベース (CDR または QoE) に対して削除が有効になっており、指定された時間よりも長いデータベースにレコードがある場合に発生します。 たとえば、1:00 AM 管理者の毎日、qoe 60 レコードが QoE データベースから削除されるようにシステムを構成することができます。

この自動削除に加えて、Invoke-cscdrdatabasepurge と Invoke-CsQoEDatbasePurge という2つの新しいコマンドレットが、Microsoft Lync Server 2013 に追加されました。これらのコマンドレットを使用すると、管理者はいつでも CDR と QoE データベースからレコードを手動で削除できます。 たとえば、次のようなコマンドを使用すると、CDR データベースから10日以上経過したレコードをすべて手動で削除することができます。

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

上記のコマンドでは、通話詳細レコードと10日以上経過した診断データレコードの両方が、atl-sql-001.litwareinc.com 上の監視データベースから削除されます。 (通話詳細レコードは、ユーザーまたはセッションレポートです。 診断データレコードは、Lync 2013 などのクライアントアプリケーションによってアップロードされる診断ログです。)

上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays および PurgeDiagnosticDataOlderThanDays パラメーターの両方が含まれる必要があります。 しかし、これらのパラメーターを同じ値に設定する必要はありません。 たとえば、10 日より古い詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。 そのためには、Purgecalldetaildataolderthandays はを10に、PurgeDiagnosticDataOlderThanDays を0に設定します。 次に例を示します。

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

既定では、Invoke-CsCdrDatabasePurge を実行するたびに、削除する必要がある各データベース テーブルごとに、以下のようなメッセージが表示されます。

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

データベース削除が実際に行われる前に、Y (はい (Yes)) または A (すべてはい (Yes to All)) を入力する必要があります。これらの確認メッセージを表示しないようにする場合は、Invoke-CsCdrDatabasePurge の呼び出しの最後に以下のパラメーターを追加します。

    -Confirm:$False

次に例を示します。

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

このようにした場合、確認メッセージは表示されず、データベースの削除はすぐに行われます。

QoE データベースを削除するには、Invoke-CsQoEDatabasePurge コマンドレットを使用し、削除するレコードの保有期間を (日単位で) 指定します。

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

