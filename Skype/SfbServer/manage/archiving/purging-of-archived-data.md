---
title: Skype for Business Server でアーカイブされたデータの削除を管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '概要: Skype for Business Server のアーカイブ データの削除を管理する方法について学習します。'
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828537"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="c3021-103">Skype for Business Server でアーカイブされたデータの削除を管理する</span><span class="sxs-lookup"><span data-stu-id="c3021-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="c3021-104">**概要:** Skype for Business Server のアーカイブ データの削除を管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="c3021-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="c3021-105">アーカイブ データベースは長期保持を目的としていないので、Skype for Business Server はアーカイブされたデータの電子検出 (検索) ソリューションを提供していないので、データを他のストレージに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3021-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="c3021-106">Skype for Business Server は、アーカイブされたデータを検索可能なトランスクリプトにエクスポートするために使用できるセッション エクスポート ツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3021-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="c3021-107">アーカイブおよびエクスポートされたデータを削除する場合を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3021-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="c3021-108">**Export-CsArchivingData** コマンドレットを使用したデータのエクスポートの詳細については [、「Skype for Business Server](export-archived-data.md)でアーカイブされたデータをエクスポートする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3021-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="c3021-109">コントロール パネルを使用してデータの削除を管理する</span><span class="sxs-lookup"><span data-stu-id="c3021-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="c3021-110">コントロール パネルを使用してアーカイブされたデータの削除を管理するには:</span><span class="sxs-lookup"><span data-stu-id="c3021-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="c3021-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c3021-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c3021-112">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c3021-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c3021-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3021-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c3021-114">アーカイブ構成の一覧で、適切なグローバル、サイト、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。その後、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3021-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="c3021-115">削除を有効にする場合は、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3021-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="c3021-116">すべてのレコードを削除する場合は、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3021-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="c3021-117">エクスポートされたデータのみを削除する場合は、[**エクスポート済みのアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3021-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="c3021-118">削除を無効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c3021-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="c3021-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3021-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="c3021-120">データを使用してデータの削除を管理Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3021-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="c3021-121">次のコマンドレットを使用して、アーカイブされたデータの削除Windows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="c3021-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="c3021-122">**EnablePurging パラメーターを指定した Set-CsArchivingConfiguration** コマンドレットを使用すると、アーカイブされたデータの削除を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c3021-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="c3021-123">**Invoke-CsArchivingDatabasePurge** を使用すると、アーカイブ データベースからレコードを手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="c3021-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="c3021-124">たとえば、次のコマンドを実行すると、アーカイブ済みのすべてのデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c3021-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="c3021-125">このコマンドを実行すると、Skype for Business Server は KeepArchivingDataForDays パラメーターに指定された値より古いアーカイブ レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="c3021-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="c3021-126">次のコマンドは **、(Export-CSArchivingData** コマンドレットを使用して) データ ファイルにエクスポートされたアーカイブ済みレコードに削除を制限します。</span><span class="sxs-lookup"><span data-stu-id="c3021-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="c3021-127">PurgeExportedArchivesOnly パラメーターを True ($True) に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3021-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="c3021-128">このコマンドを実行すると、Skype for Business Server は 2 つの条件 (1) KeepArchivingDataForDays パラメーターに指定された値より古いアーカイブ レコードのみを削除します。2) **Export-CsArchivingData** コマンドレットを使用してエクスポートされています。</span><span class="sxs-lookup"><span data-stu-id="c3021-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="c3021-129">アーカイブ レコードの自動削除を無効にするには、EnablePurging パラメーターを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="c3021-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="c3021-130">次の例では **、Invoke-CsArchivingDatabasePurge** コマンドレットを使用して、データベース上のアーカイブ データベースから 24 時間以上前のすべてのレコードを削除atl-sql-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c3021-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="c3021-131">エクスポートされていないレコードも含め、すべてのレコードが確実に削除されるには、PurgeExportedArchivesOnly パラメーターを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="c3021-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
