---
title: ビジネス サーバーの Skype でのアーカイブ ・ データの削除を管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '概要: は、Skype のビジネス サーバーのアーカイブ ・ データのパージを管理する方法を説明します。'
ms.openlocfilehash: fce7c8214eddd55736a54b960d57053a88cdc859
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997945"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="5313e-103">ビジネス サーバーの Skype でのアーカイブ ・ データの削除を管理します。</span><span class="sxs-lookup"><span data-stu-id="5313e-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="5313e-104">**の概要:** ビジネス サーバー用の Skype のアーカイブ ・ データのパージを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5313e-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="5313e-105">アーカイブ データベースは、長期的な保存は、ありませんし、Skype のビジネス サーバー ソリューションが提供されない、(検索) を電子的証拠開示アーカイブ ・ データは、データを他のストレージに移動する必要があるため。</span><span class="sxs-lookup"><span data-stu-id="5313e-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="5313e-106">ビジネス サーバー用の Skype は、アーカイブ ・ データを検索可能なトラン スクリプトにエクスポートするのには使用できるセッション エクスポート ツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="5313e-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="5313e-107">アーカイブされたデータやエクスポートされたデータをいつ削除するかを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5313e-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="5313e-108">**.Eml という**コマンドレットを使用してデータをエクスポートする方法の詳細については、 [Skype のビジネス サーバーでアーカイブされたデータをエクスポートする](export-archived-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5313e-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="5313e-109">コントロール パネルを使用してデータの削除を管理する</span><span class="sxs-lookup"><span data-stu-id="5313e-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="5313e-110">コントロール パネルを使用してデータの削除を管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5313e-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="5313e-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5313e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5313e-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5313e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5313e-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5313e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="5313e-114">アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5313e-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="5313e-115">削除を有効にする場合は、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5313e-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="5313e-116">すべてのレコードを削除する場合は、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5313e-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="5313e-117">エクスポートされたデータのみを削除する場合は、[**エクスポート済みのアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5313e-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="5313e-118">削除を無効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5313e-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="5313e-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5313e-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="5313e-120">Windows PowerShell を使用したデータの削除を管理する</span><span class="sxs-lookup"><span data-stu-id="5313e-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="5313e-121">アーカイブされたデータの削除は、次の Windows PowerShell コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="5313e-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="5313e-122">**Set-CsArchivingConfiguration** コマンドレットで EnablePurging パラメーターを指定すると、アーカイブされたデータの削除を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5313e-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="5313e-123">**Invoke-CsArchivingDatabasePurge** を使用すると、アーカイブ データベースからレコードを手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="5313e-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="5313e-124">たとえば、次のコマンドを使用するとアーカイブされている全データの削除を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5313e-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="5313e-125">このコマンドを実行すると、Skype のビジネス サーバーは KeepArchivingDataForDays パラメーターに指定された値より古いすべてのアーカイブのレコードをパージします。</span><span class="sxs-lookup"><span data-stu-id="5313e-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="5313e-126">次のコマンドは、( **.eml という**コマンドレットを使用して) でのデータ ファイルにエクスポートされたアーカイブされた記録の削除を制限します。</span><span class="sxs-lookup"><span data-stu-id="5313e-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="5313e-127">True ($True) に、PurgeExportedArchivesOnly パラメーターを設定することもあります。</span><span class="sxs-lookup"><span data-stu-id="5313e-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="5313e-128">このコマンドを実行すると、Skype ビジネス サーバーの 2 つの条件を満たすレコードをアーカイブにのみパージされます: 1) KeepArchivingDataForDays パラメーターに指定した値よりも古い2) **.eml という**コマンドレットを使用してエクスポートされました。</span><span class="sxs-lookup"><span data-stu-id="5313e-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="5313e-129">アーカイブ レコードの自動削除を無効にするには、EnablePurging パラメーターを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="5313e-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="5313e-130">次の例では、atl の sql-001.contoso.com のアーカイブ データベースから 24 時間を超えるすべてのレコードを削除するのに**呼び出し CsArchivingDatabasePurge**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5313e-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="5313e-131">該当するレコードが、エクスポートされていないレコードも含めてすべて確実に削除されるようにするために、PurgeExportedArchivesOnly パラメーターを False ($False) に設定しています。</span><span class="sxs-lookup"><span data-stu-id="5313e-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```