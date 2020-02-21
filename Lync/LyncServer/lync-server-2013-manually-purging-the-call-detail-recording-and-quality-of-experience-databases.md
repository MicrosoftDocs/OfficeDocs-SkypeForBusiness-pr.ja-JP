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

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="a2060-102">Lync Server 2013 で通話詳細記録と qoe (Quality of Experience) データベースを手動で削除する</span><span class="sxs-lookup"><span data-stu-id="a2060-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2060-103">_**トピックの最終更新日:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="a2060-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="a2060-104">管理者は、通話詳細記録 (CDR) や QoE (Quality of Experience) データベースを構成して、データベースから古いレコードを自動的に削除することができます。これは、指定されたデータベース (CDR または QoE) に対して削除が有効になっており、指定された時間よりも長いデータベースにレコードがある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a2060-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="a2060-105">たとえば、1:00 AM 管理者の毎日、qoe 60 レコードが QoE データベースから削除されるようにシステムを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a2060-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="a2060-106">この自動削除に加えて、Invoke-cscdrdatabasepurge と Invoke-CsQoEDatbasePurge という2つの新しいコマンドレットが、Microsoft Lync Server 2013 に追加されました。これらのコマンドレットを使用すると、管理者はいつでも CDR と QoE データベースからレコードを手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="a2060-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="a2060-107">たとえば、次のようなコマンドを使用すると、CDR データベースから10日以上経過したレコードをすべて手動で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a2060-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="a2060-108">上記のコマンドでは、通話詳細レコードと10日以上経過した診断データレコードの両方が、atl-sql-001.litwareinc.com 上の監視データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2060-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="a2060-109">(通話詳細レコードは、ユーザーまたはセッションレポートです。</span><span class="sxs-lookup"><span data-stu-id="a2060-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="a2060-110">診断データレコードは、Lync 2013 などのクライアントアプリケーションによってアップロードされる診断ログです。)</span><span class="sxs-lookup"><span data-stu-id="a2060-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="a2060-111">上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays および PurgeDiagnosticDataOlderThanDays パラメーターの両方が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2060-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="a2060-112">しかし、これらのパラメーターを同じ値に設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a2060-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="a2060-113">たとえば、10 日より古い詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。</span><span class="sxs-lookup"><span data-stu-id="a2060-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="a2060-114">そのためには、Purgecalldetaildataolderthandays はを10に、PurgeDiagnosticDataOlderThanDays を0に設定します。</span><span class="sxs-lookup"><span data-stu-id="a2060-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="a2060-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a2060-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="a2060-116">既定では、Invoke-CsCdrDatabasePurge を実行するたびに、削除する必要がある各データベース テーブルごとに、以下のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2060-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="a2060-p105">データベース削除が実際に行われる前に、Y (はい (Yes)) または A (すべてはい (Yes to All)) を入力する必要があります。これらの確認メッセージを表示しないようにする場合は、Invoke-CsCdrDatabasePurge の呼び出しの最後に以下のパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2060-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="a2060-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a2060-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="a2060-120">このようにした場合、確認メッセージは表示されず、データベースの削除はすぐに行われます。</span><span class="sxs-lookup"><span data-stu-id="a2060-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="a2060-121">QoE データベースを削除するには、Invoke-CsQoEDatabasePurge コマンドレットを使用し、削除するレコードの保有期間を (日単位で) 指定します。</span><span class="sxs-lookup"><span data-stu-id="a2060-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

