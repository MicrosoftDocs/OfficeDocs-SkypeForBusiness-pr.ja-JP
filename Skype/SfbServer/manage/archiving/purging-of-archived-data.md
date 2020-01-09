---
title: Skype for Business Server でアーカイブデータの削除を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '概要: Skype for Business Server のアーカイブデータの削除を管理する方法について説明します。'
ms.openlocfilehash: f168f7fe744ef388de246cbcd2dd9de0fc2ef805
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991612"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="e76eb-103">Skype for Business Server でアーカイブデータの削除を管理する</span><span class="sxs-lookup"><span data-stu-id="e76eb-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="e76eb-104">**概要:** Skype for Business Server のアーカイブデータの削除を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e76eb-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="e76eb-105">アーカイブデータベースは、長期間の保存のためのものではありません。また、Skype for Business Server では、アーカイブデータの電子的な探索 (検索) ソリューションを提供していないため、データを他のストレージに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e76eb-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="e76eb-106">Skype for Business Server には、アーカイブデータを検索可能なトランスクリプトにエクスポートするために使用できるセッションエクスポートツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e76eb-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="e76eb-107">アーカイブされたデータやエクスポートされたデータをいつ削除するかを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e76eb-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="e76eb-108">**CsArchivingData**コマンドレットを使用してデータをエクスポートする方法について詳しくは、「 [Skype for business Server にアーカイブデータをエクスポート](export-archived-data.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e76eb-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="e76eb-109">コントロール パネルを使用してデータの削除を管理する</span><span class="sxs-lookup"><span data-stu-id="e76eb-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="e76eb-110">コントロール パネルを使用してデータの削除を管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e76eb-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="e76eb-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e76eb-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="e76eb-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e76eb-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e76eb-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e76eb-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e76eb-114">アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e76eb-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="e76eb-115">削除を有効にする場合は、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e76eb-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="e76eb-116">すべてのレコードを削除する場合は、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e76eb-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="e76eb-117">エクスポートされたデータのみを削除する場合は、[**エクスポート済みのアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e76eb-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="e76eb-118">削除を無効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e76eb-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="e76eb-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e76eb-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="e76eb-120">Windows PowerShell を使用したデータの削除を管理する</span><span class="sxs-lookup"><span data-stu-id="e76eb-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="e76eb-121">アーカイブされたデータの削除は、次の Windows PowerShell コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="e76eb-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="e76eb-122">**Set-CsArchivingConfiguration** コマンドレットで EnablePurging パラメーターを指定すると、アーカイブされたデータの削除を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e76eb-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="e76eb-123">**Invoke-CsArchivingDatabasePurge** を使用すると、アーカイブ データベースからレコードを手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="e76eb-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="e76eb-124">たとえば、次のコマンドを使用するとアーカイブされている全データの削除を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e76eb-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="e76eb-125">このコマンドを実行すると、Skype for Business Server は、KeepArchivingDataForDays パラメーターに指定された値よりも古いすべてのアーカイブレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="e76eb-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="e76eb-126">次のコマンドは、データファイルにエクスポートされた ( **CSArchivingData**コマンドレットを使用して) アーカイブされたレコードの削除を制限します。</span><span class="sxs-lookup"><span data-stu-id="e76eb-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="e76eb-127">PurgeExportedArchivesOnly パラメーターを True ($True) に設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e76eb-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="e76eb-128">このコマンドを実行すると、Skype for Business Server は、2つの条件を満たすレコードのみを消去します。 1) は、KeepArchivingDataForDays パラメーターに指定された値よりも古いものです。and、2) **CsArchivingData**コマンドレットを使用してエクスポートされている。</span><span class="sxs-lookup"><span data-stu-id="e76eb-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="e76eb-129">アーカイブ レコードの自動削除を無効にするには、EnablePurging パラメーターを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e76eb-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="e76eb-130">次の例では、 **CsArchivingDatabasePurge**コマンドレットを使用して、atl-sql-001.contoso.com のアーカイブデータベースから24時間以上経過したレコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="e76eb-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="e76eb-131">該当するレコードが、エクスポートされていないレコードも含めてすべて確実に削除されるようにするために、PurgeExportedArchivesOnly パラメーターを False ($False) に設定しています。</span><span class="sxs-lookup"><span data-stu-id="e76eb-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
