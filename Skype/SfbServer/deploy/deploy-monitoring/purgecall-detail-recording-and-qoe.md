---
title: Skype for Business Server 2015 での通話詳細記録および QoE (Quality of Experience) データベースの手動での削除
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '概要: は、CDR およびビジネス サーバー 2015 の Skype で使用される QoE データベースからレコードを手動で削除する方法について説明します。'
ms.openlocfilehash: 805bf72b3d4846bb00d3c3772b033242976cd7c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="94062-103">Skype for Business Server 2015 での通話詳細記録および QoE (Quality of Experience) データベースの手動での削除</span><span class="sxs-lookup"><span data-stu-id="94062-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="94062-104">**の概要:**CDR およびビジネス サーバー 2015 の Skype で使用される QoE データベースからレコードを手動で削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94062-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="94062-p101">CDR および QoE データベースは、レコードを手動または自動で削除できます。レコードの削除は、データが古くならないようにするため、あるいはレポートをリセットして最初からやり直す必要がある場合に重要になります。</span><span class="sxs-lookup"><span data-stu-id="94062-p101">The CDR and QoE databases can be manually or automatically purged of records. Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="94062-107">CDR および QoE データベースからレコードを手動で削除する</span><span class="sxs-lookup"><span data-stu-id="94062-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="94062-p102">管理者は、データベースから以前のレコードを自動的に削除するように通話詳細記録 (CDR) か QoE (QoE) データベース、またはその両方を構成できます。これは、指定したデータベース (CDR または QoE) で削除が有効になっており、レコードが指定した時間以上、データベース内にあると実行されます。たとえば、毎日、午前 1 時 00 分に、60 日以上経った QoE レコードが QoE データベースから削除されるように、管理者がシステムを構成できます。</span><span class="sxs-lookup"><span data-stu-id="94062-p102">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time. For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="94062-110">だけでなく、自動削除、2 つの新しいコマンドレット & #x やり取りできます。呼び出す CsCdrDatabasePurge を呼び出す CsQoEDatbasePurge & #x やり取りできます。ビジネス サーバー 2015; の Skype に追加されましたこれらのコマンドレットでは、いつでも、CDR および QoE データベースからレコードを手動で削除する管理者を使用できます。</span><span class="sxs-lookup"><span data-stu-id="94062-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server 2015; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="94062-111">たとえば、10 日以上のすべてのレコードを手動で削除する CDR データベースから古いを使用できますコマンドのようになります。</span><span class="sxs-lookup"><span data-stu-id="94062-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="94062-112">上記のコマンドでは、詳細レコード、および診断データのレコードが 10 日は、atl の sql-001.litwareinc.com の監視のデータベースから削除されたより古いを呼び出す両方。(呼び出しの詳細レコードは、ユーザーまたはセッションのレポートです。</span><span class="sxs-lookup"><span data-stu-id="94062-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com. (Call detail records are user/session reports.</span></span> <span data-ttu-id="94062-113">診断データ レコードは、診断ログの Skype ビジネス サーバー 2015 のクライアント アプリケーションによってアップロードされた)。</span><span class="sxs-lookup"><span data-stu-id="94062-113">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server 2015.)</span></span>
  
<span data-ttu-id="94062-114">上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays と PurgeDiagnosticDataOlderThanDays の両方のパラメーターが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94062-114">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="94062-115">ただし、これらのパラメーターを同じ値に設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="94062-115">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="94062-116">たとえば、10 日より前の詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。</span><span class="sxs-lookup"><span data-stu-id="94062-116">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="94062-117">10 と PurgeDiagnosticDataOlderThanDays に PurgeCallDetailDataOlderThanDays を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="94062-117">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="94062-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="94062-118">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="94062-119">既定では、Invoke-CsCdrDatabasePurge を実行するたびに、削除する必要がある各データベース テーブルごとに、以下のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="94062-119">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
```
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="94062-p106">データベース削除が実際に行われる前に、Y (はい) または A (すべてはい) を入力する必要があります。これらの確認メッセージを表示しないようにする場合は、Invoke-CsCdrDatabasePurge の呼び出しの最後に以下のパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="94062-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```
-Confirm:$False
```

<span data-ttu-id="94062-122">例:</span><span class="sxs-lookup"><span data-stu-id="94062-122">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="94062-123">この操作を実行すると、確認メッセージは表示されず、データベースの削除がすぐに実行されます。</span><span class="sxs-lookup"><span data-stu-id="94062-123">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="94062-124">QoE データベースを削除するには、Invoke-CsQoEDatabasePurge コマンドレットを使用し、削除するレコードの保有期間を (日単位で) 指定します。</span><span class="sxs-lookup"><span data-stu-id="94062-124">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


