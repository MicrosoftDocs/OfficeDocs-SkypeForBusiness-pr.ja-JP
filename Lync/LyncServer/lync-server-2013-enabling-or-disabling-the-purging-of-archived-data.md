---
title: 'Lync Server 2013: アーカイブされたデータの削除を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e62ff615b4e2fcf5ec10f470993f985db0363a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="f2caf-102">Lync Server 2013 でのアーカイブされたデータの削除を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f2caf-102">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2caf-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f2caf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f2caf-104">Lync Server 2013 コントロールパネルでは、アーカイブ構成を使用して、削除を有効または無効にし、削除の実装方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="f2caf-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="f2caf-105">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2caf-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="f2caf-106">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="f2caf-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f2caf-107">特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="f2caf-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="f2caf-108">アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="f2caf-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="f2caf-109">指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2caf-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2caf-110">Lync Server 2013 に所属するユーザーのアーカイブを使用するには、アーカイブポリシーを構成して、内部通信、外部通信、またはその両方のアーカイブを有効にするかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2caf-110">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="f2caf-111">既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f2caf-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="f2caf-112">ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2caf-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f2caf-113">アーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2caf-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="f2caf-114">Microsoft Exchange 統合を使用してアーカイブデータおよびファイルを Exchange 2013 サーバーに保存し、すべてのユーザーが Exchange 2013 サーバーに所属している場合は、アーカイブを展開した後に、SQL Server データベース構成を削除する必要があります。トポロジから。</span><span class="sxs-lookup"><span data-stu-id="f2caf-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="f2caf-115">これを行うには、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2caf-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="f2caf-116">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でのアーカイブデータベースオプションの変更</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2caf-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="f2caf-117">アーカイブの削除を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="f2caf-117">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="f2caf-118">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f2caf-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2caf-119">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2caf-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2caf-120">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2caf-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2caf-121">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2caf-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="f2caf-122">アーカイブ構成の一覧で、適切なグローバル、サイト、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。その後、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f2caf-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="f2caf-123">削除を有効にする場合は、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f2caf-123">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="f2caf-124">すべてのレコードを削除する場合は、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2caf-124">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="f2caf-125">エクスポートされたデータのみを削除する場合は、[**エクスポート済みのアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2caf-125">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="f2caf-126">削除を無効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f2caf-126">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="f2caf-127">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2caf-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f2caf-128">Windows PowerShell コマンドレットを使用してアーカイブデータの削除を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f2caf-128">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f2caf-129">アーカイブデータの自動削除を有効または無効にするには、Windows PowerShell と**set-csarchivingconfiguration**コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="f2caf-129">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="f2caf-130">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="f2caf-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f2caf-131">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2caf-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="f2caf-132">すべてのアーカイブデータの削除を有効にするには</span><span class="sxs-lookup"><span data-stu-id="f2caf-132">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="f2caf-133">すべてのアーカイブ データの削除を有効化するには、**EnablePurging** プロパティを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2caf-133">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="f2caf-134">例:</span><span class="sxs-lookup"><span data-stu-id="f2caf-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="f2caf-135">このコマンドを実行すると、 **KeepArchivingDataForDays**プロパティに指定された値よりも古いすべてのアーカイブレコードが Lync Server によって削除されます。</span><span class="sxs-lookup"><span data-stu-id="f2caf-135">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="f2caf-136">エクスポートされたアーカイブデータのみを削除できるようにするには</span><span class="sxs-lookup"><span data-stu-id="f2caf-136">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="f2caf-137">[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)コマンドレットを使用して、データファイルにエクスポートされたレコードをアーカイブするように削除を制限するには、PurgeExportedArchivesOnly プロパティを True ($True) に設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="f2caf-137">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="f2caf-138">例:</span><span class="sxs-lookup"><span data-stu-id="f2caf-138">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="f2caf-139">このコマンドを実行すると、Lync Server は、2つの条件を満たすレコードのアーカイブのみを削除します。 1) は、 **KeepArchivingDataForDays**プロパティに指定された値よりも古いものです。および 2) は、 **export-csarchivingdata**コマンドレットを使用してエクスポートされています。</span><span class="sxs-lookup"><span data-stu-id="f2caf-139">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="f2caf-140">すべてのアーカイブデータの削除を無効にするには</span><span class="sxs-lookup"><span data-stu-id="f2caf-140">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="f2caf-141">アーカイブ レコードの自動削除を無効化するには、**EnablePurging** プロパティを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2caf-141">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="f2caf-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f2caf-142">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="f2caf-143">アーカイブデータを削除するためのその他のオプションを含む詳細については、 [set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2caf-143">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2caf-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2caf-144">See Also</span></span>


[<span data-ttu-id="f2caf-145">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="f2caf-145">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="f2caf-146">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</span><span class="sxs-lookup"><span data-stu-id="f2caf-146">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="f2caf-147">組織、サイト、およびプールの Lync Server 2013 でのアーカイブ構成オプションの管理</span><span class="sxs-lookup"><span data-stu-id="f2caf-147">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

