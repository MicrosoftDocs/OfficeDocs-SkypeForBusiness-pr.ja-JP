---
title: 'Lync Server 2013: 特定のサイトまたはプールのアーカイブを管理するためのアーカイブ構成の作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b0495a15d19adba9ac21fb7817347a16b78bc13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="44c9b-102">Lync Server 2013 でアーカイブ構成を作成して、特定のサイトまたはプールのアーカイブを管理する</span><span class="sxs-lookup"><span data-stu-id="44c9b-102">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44c9b-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="44c9b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="44c9b-104">Lync Server 2013 コントロールパネルでは、アーカイブ構成を使って、展開でのアーカイブの実装方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="44c9b-104">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="44c9b-105">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="44c9b-106">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="44c9b-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="44c9b-107">作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。</span><span class="sxs-lookup"><span data-stu-id="44c9b-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="44c9b-108">アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="44c9b-109">アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」をご覧ください。「計画ドキュメント、展開ドキュメント、または操作のドキュメントでの[Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c9b-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44c9b-110">アーカイブを使用するには、内部通信のアーカイブを有効にするか、外部通信を有効にするか、または Lync Server 2013 を使用しているユーザーに対してアーカイブを有効にするかを指定するようにアーカイブポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44c9b-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="44c9b-111">既定では、内部または外部の通信でアーカイブは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="44c9b-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="44c9b-112">すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開に適したアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44c9b-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="44c9b-113">アーカイブを有効にする方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c9b-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="44c9b-114">Microsoft Exchange 統合を使用して Exchange 2013 サーバー上のアーカイブデータとファイルを保存し、すべてのユーザーが Exchange 2013 サーバー上にある場合は、アーカイブを展開した後に、SQL Server データベースの構成を削除する必要があります。を選びます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="44c9b-115">この操作を行うには、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44c9b-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="44c9b-116">詳細については、「運用ドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でアーカイブデータベースのオプションを変更する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c9b-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="44c9b-117">サイトまたはプールのアーカイブ構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="44c9b-117">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="44c9b-118">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44c9b-119">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="44c9b-120">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44c9b-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="44c9b-121">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="44c9b-122">[**アーカイブ構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="44c9b-122">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="44c9b-123">サイトアーカイブ構成を作成するには、[**サイトの構成**] をクリックし、[**サイトの選択**] でアーカイブ用に構成するサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-123">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="44c9b-124">プールのアーカイブ構成を作成するには、[**プールの構成**] をクリックし、[**プールの選択**] で、アーカイブ用に構成するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="44c9b-124">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="44c9b-125">[**新しいアーカイブ設定**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="44c9b-125">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="44c9b-126">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-126">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="44c9b-127">IM セッションと Web 会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-127">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="44c9b-128">ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-128">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="44c9b-129">[**新しいアーカイブ設定**] で、次の操作も実行します。</span><span class="sxs-lookup"><span data-stu-id="44c9b-129">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="44c9b-130">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-130">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="44c9b-131">アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-131">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="44c9b-132">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="44c9b-132">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="44c9b-133">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="44c9b-133">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="44c9b-134">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-134">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="44c9b-135">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44c9b-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="44c9b-136">Windows PowerShell コマンドレットを使用してアーカイブ構成設定を作成する</span><span class="sxs-lookup"><span data-stu-id="44c9b-136">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="44c9b-137">アーカイブ構成設定は、Windows PowerShell と CsArchivingConfiguration コマンドレットを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-137">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="44c9b-138">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="44c9b-139">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c9b-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="44c9b-140">サイトのアーカイブ構成設定の新しいコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="44c9b-140">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="44c9b-141">次のコマンドを実行すると、レドモンドのサイト用に新しいアーカイブ構成設定のコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-141">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="44c9b-142">IM アーカイブのみを許可するアーカイブ構成設定の新しいコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="44c9b-142">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="44c9b-143">前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-143">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="44c9b-144">異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。</span><span class="sxs-lookup"><span data-stu-id="44c9b-144">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="44c9b-145">たとえば、インスタントメッセージングセッションのアーカイブを許可する既定のアーカイブ構成設定のコレクションを作成するには、次のようなコマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44c9b-145">For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="44c9b-146">アーカイブ構成設定の作成時に複数のプロパティ値を指定するには</span><span class="sxs-lookup"><span data-stu-id="44c9b-146">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="44c9b-p108">複数のパラメーターを含めることにより複数のプロパティ値を変更できます。たとえば、次のコマンドを実行すると、インスタント メッセージング セッションをアーカイブし、アーカイブ サービスのインスタント メッセージング サービスをブロックして使用不可にする新しい設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="44c9b-p108">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="44c9b-149">詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c9b-149">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44c9b-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="44c9b-150">See Also</span></span>


[<span data-ttu-id="44c9b-151">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="44c9b-151">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="44c9b-152">組織、サイト、およびプールの Lync Server 2013 でアーカイブ構成オプションを管理する</span><span class="sxs-lookup"><span data-stu-id="44c9b-152">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

