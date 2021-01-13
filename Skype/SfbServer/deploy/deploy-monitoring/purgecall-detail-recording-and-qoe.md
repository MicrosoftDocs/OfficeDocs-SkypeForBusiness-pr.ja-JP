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
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="2d51e-103">Skype for Business Server で通話詳細記録データベースと Quality of Experience データベースを手動で削除する</span><span class="sxs-lookup"><span data-stu-id="2d51e-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="2d51e-104">**概要:** Skype for Business Server で使用される CDR および QoE データベースからレコードを手動で削除する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="2d51e-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="2d51e-105">CDR データベースと QoE データベースは、レコードを手動または自動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="2d51e-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="2d51e-106">レコードの削除は、データが古くならないか、またはレポートを開始基準からリセットする必要がある場合に重要です。</span><span class="sxs-lookup"><span data-stu-id="2d51e-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="2d51e-107">CDR および QoE データベースからレコードを手動で削除する</span><span class="sxs-lookup"><span data-stu-id="2d51e-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="2d51e-108">管理者は、通話詳細記録 (CDR) データベースや QoE (Quality of Experience) データベースを構成して、古いレコードをデータベースから自動的に削除できます。これは、指定したデータベース (CDR または QoE) に対して削除が有効になっている場合、およびデータベース内に指定した時間を超えるレコードが存在する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2d51e-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="2d51e-109">たとえば、毎日午前 1 時に管理者がシステムを構成して、60 日以上前の QoE レコードが QoE データベースから削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d51e-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="2d51e-110">この自動削除に加えて、Skype for Business Server &#x2014; Invoke-CsCdrDatabasePurgeとInvoke-CsQoEDatbasePurge &#x2014; 2 つの新しいコマンドレットが追加されました。これらのコマンドレットを使用すると、管理者は CDR および QoE データベースからいつでもレコードを手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="2d51e-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="2d51e-111">たとえば、CDR データベースから 10 日以上前のすべてのレコードを手動で削除するには、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d51e-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="2d51e-112">前のコマンドでは、通話詳細記録と 10 日以上前の診断データ レコードの両方が、通話詳細記録の監視データベースから削除atl-sql-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="2d51e-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="2d51e-113">(通話詳細レコードはユーザー/セッション レポートです。</span><span class="sxs-lookup"><span data-stu-id="2d51e-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="2d51e-114">診断データ レコードは、Skype for Business Server などのクライアント アプリケーションによってアップロードされた診断ログです)。</span><span class="sxs-lookup"><span data-stu-id="2d51e-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="2d51e-115">上に示すように、Invoke-CsCdrDatabasePurge コマンドレットを実行するときは、PurgeCallDetaiDataOlderThanDays および PurgeDiagnosticDataOlderThanDays パラメーターの両方が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d51e-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="2d51e-116">しかし、これらのパラメーターを同じ値に設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2d51e-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="2d51e-117">たとえば、10 日より古い詳細通話記録を削除する一方で、すべての診断データ レコードをデータベースに残すことはできます。</span><span class="sxs-lookup"><span data-stu-id="2d51e-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="2d51e-118">これを行うには、PurgeCallDetailDataOlderThanDays を 10 に、PurgeDiagnosticDataOlderThanDays を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d51e-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="2d51e-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d51e-119">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="2d51e-120">既定では、Invoke-CsCdrDatabasePurge を実行するたびに、削除する必要がある各データベース テーブルごとに、以下のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d51e-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="2d51e-p106">データベース削除が実際に行われる前に、Y (はい (Yes)) または A (すべてはい (Yes to All)) を入力する必要があります。これらの確認メッセージを表示しないようにする場合は、Invoke-CsCdrDatabasePurge の呼び出しの最後に以下のパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="2d51e-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```powershell
-Confirm:$False
```

<span data-ttu-id="2d51e-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d51e-123">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="2d51e-124">このようにした場合、確認メッセージは表示されず、データベースの削除はすぐに行われます。</span><span class="sxs-lookup"><span data-stu-id="2d51e-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="2d51e-125">QoE データベースを削除するには、Invoke-CsQoEDatabasePurge コマンドレットを使用し、削除するレコードの保有期間を (日単位で) 指定します。</span><span class="sxs-lookup"><span data-stu-id="2d51e-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


