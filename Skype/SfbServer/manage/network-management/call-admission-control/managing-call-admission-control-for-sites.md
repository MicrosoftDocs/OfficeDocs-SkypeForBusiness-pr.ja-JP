---
title: サイトの通話受付管理の管理
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
description: ネットワーク サイトは、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスが展開される各ネットワーク地域内のオフィスまたは拠点です。
ms.openlocfilehash: 0b339f15e53dd94bda655884f70c041f9da9e5a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118566"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="4b9ae-103">Skype for Business Server でのサイトの通話受付管理サービスの管理</span><span class="sxs-lookup"><span data-stu-id="4b9ae-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="4b9ae-104">ネットワーク サイトは、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスが展開される各ネットワーク地域内のオフィスまたは拠点です。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="4b9ae-105">この記事の手順を使用して、ネットワーク サイトの通話受付管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="4b9ae-106">ネットワーク サイト リンクの構成</span><span class="sxs-lookup"><span data-stu-id="4b9ae-106">Configure network site links</span></span>

<span data-ttu-id="4b9ae-107">通話受付管理 (CAC) 構成内に、直接リンクされているサイト間の帯域幅制限を定義するネットワークサイト間ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="4b9ae-108">ネットワーク サイトが直接リンクを共有している場合、これらの 2 つのサイト間にオーディオ接続およびビデオ接続の帯域幅制限を定義できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="4b9ae-109">Skype for Business Server コントロール パネルを使用してネットワーク サイト ポリシーを構成することはできません。これは、Skype for Business Server 管理シェルのコマンドレットを使用する場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="4b9ae-110">Skype for Business Server 管理シェルからネットワーク サイト リンク (ネットワークサイト間ポリシーとも呼ばれる) を作成、変更、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="4b9ae-111">ネットワーク サイト リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="4b9ae-111">To create a network site link</span></span>

1.  <span data-ttu-id="4b9ae-112">Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="4b9ae-113">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="4b9ae-114">コマンド プロンプトで、使用している構成で有効な値に置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="4b9ae-115">次の使用例は、Reno とポートランドのネットワーク サイト間の帯域幅制限を設定する、Reno Portland という名前の新しいネットワーク サイト \_ リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="4b9ae-116">ネットワーク サイトと帯域幅ポリシーのプロファイルが、このコマンドを実行する前に既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="4b9ae-117">パラメーターの詳細については [、「New-CsNetworkInterSitePolicy」を参照してください](/powershell/module/skype/New-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="4b9ae-118">ネットワーク サイト リンクに適用できる帯域幅ポリシーのプロファイルの一覧を取得するには、**Get-CsNetworkBandwidthPolicyProfile** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="4b9ae-119">詳細については [、「Get-CsNetworkBandwidthPolicyProfile」を参照してください](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="4b9ae-120">ネットワーク サイト リンクを変更するには</span><span class="sxs-lookup"><span data-stu-id="4b9ae-120">To modify a network site link</span></span>

1.  <span data-ttu-id="4b9ae-121">Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="4b9ae-122">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="4b9ae-123">特定のネットワーク サイト リンクのプロパティを変更するには、**Set-CsNetworkInterSitePolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="4b9ae-124">接続されたサイトの一方 (または両方) を変更したり、リンクに関連付けられた帯域幅ポリシーのプロファイルを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="4b9ae-125">Reno Portland という名前のサイト リンクの帯域幅ポリシー プロファイルを変更する例を \_ 次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="4b9ae-126">パラメーターの詳細については [、「Set-CsNetworkInterSitePolicy」を参照してください](/powershell/module/skype/Set-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="4b9ae-127">ネットワーク サイト リンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="4b9ae-127">To delete a network site link</span></span>

1.  <span data-ttu-id="4b9ae-128">Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="4b9ae-129">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="4b9ae-130">ネットワーク サイト リンクを削除するには、**Remove-CsNetworkInterSitePolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="4b9ae-131">次の例では、Reno \_ Portland ネットワーク サイト リンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="4b9ae-132">パラメーターの詳細については [、「Remove-CsNetworkInterSitePolicy」を参照してください](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="4b9ae-133">ネットワーク サイト情報の表示</span><span class="sxs-lookup"><span data-stu-id="4b9ae-133">View network site information</span></span>

<span data-ttu-id="4b9ae-134">ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="4b9ae-135">ネットワーク サイト情報は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルで表示できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="4b9ae-136">Skype for Business Server コントロール パネルでネットワーク サイト情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="4b9ae-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4b9ae-137">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b9ae-138">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b9ae-139">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サイト] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="4b9ae-140">[**サイト**] ページで、表示するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4b9ae-141">一度に表示できるのは 1 つのサイトの情報だけです。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="4b9ae-142">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4b9ae-143">コマンドレットを使用したネットワーク サイト情報Windows PowerShell表示する</span><span class="sxs-lookup"><span data-stu-id="4b9ae-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4b9ae-144">ネットワーク サイトの情報を表示するには、Windows PowerShellコマンドレットをGet-CsNetworkSiteします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="4b9ae-145">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="4b9ae-146">ネットワーク サイトの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="4b9ae-146">To view network site information</span></span>

  - <span data-ttu-id="4b9ae-147">すべてのネットワーク サイトに関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="4b9ae-148">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="4b9ae-149">詳細については、[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-149">For more information, see the help topic for the [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="4b9ae-150">ネットワーク サイトを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="4b9ae-150">Create or modify network sites</span></span> 

<span data-ttu-id="4b9ae-151">ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="4b9ae-152">Skype for Business Server コントロール パネルを使用してサイトを構成し、それらを地域に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="4b9ae-153">たとえば、北アメリカのネットワーク地域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="4b9ae-154">CAC ネットワーク サイトは、サイトに帯域幅制限がない場合でも、組織内の各サイトに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="4b9ae-155">Skype for Business Server コントロール パネルから、ネットワーク サイトを作成、変更、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="4b9ae-156">ネットワーク サイトを作成または変更するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="4b9ae-157">ネットワーク サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="4b9ae-157">To create a network site</span></span>

1.  <span data-ttu-id="4b9ae-158">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b9ae-159">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b9ae-160">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サイト] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="4b9ae-161">[**サイト**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="4b9ae-162">[**新しいサイト**] で、[**名前**] フィールドにサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4b9ae-163">サイト名は、Skype for Business Server 展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="4b9ae-164">[**地域**] ドロップダウン リストで、このサイトに関連付けるネットワーク地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="4b9ae-165">(オプション) このサイトに対する音声またはビデオ通話に帯域幅制限を設定する場合は、[**帯域幅ポリシー**] ドロップダウン リストで該当する設定値を備える帯域幅ポリシー プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4b9ae-166">ネットワーク構成グループの [ポリシー プロファイル] ページで、使用可能な帯域幅ポリシー プロファイルの詳細を表示するか、新しい帯域幅ポリシー プロファイル **を作成** できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="4b9ae-167">詳細については、「 [ネットワーク帯域幅ポリシー プロファイルの管理」を参照してください](managing-network-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="4b9ae-168">(オプション) このサイトに、場所に関する設定を提供する場合は、[**場所のポリシー**] ドロップダウン リストで場所のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4b9ae-169">場所のポリシーは、特定の Enhanced 9-1-1 (E9-1-1) とクライアントの場所に関連する設定をサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="4b9ae-170">[**ネットワーク構成**] グループの [**場所のポリシー**] ページでは、利用可能な場所のポリシーの詳細を表示したり、新しい場所のポリシーを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="4b9ae-171">(オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサイトの詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="4b9ae-172">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4b9ae-173">新しいネットワーク サイトを作成するとき、[**関連付けられたサブネット**] テーブルは使用しません。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="4b9ae-174">サブネットの作成または変更時に、サブネットをサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="4b9ae-175">詳細については、「ネットワーク サブネット [の管理」を参照してください](managing-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="4b9ae-176">ネットワーク サイトを変更するには</span><span class="sxs-lookup"><span data-stu-id="4b9ae-176">To modify a network site</span></span>

1.  <span data-ttu-id="4b9ae-177">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b9ae-178">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b9ae-179">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サイト] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="4b9ae-180">[**サイト**] ページで、変更するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="4b9ae-181">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4b9ae-182">[**サイトの編集**] ページでは、サイトに関連付けられた、説明、地域、帯域幅ポリシー プロファイル、および場所のポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="4b9ae-183">詳細については、「上記の [ネットワーク サイトを作成するには」を参照](#to-create-a-network-site) してください。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="4b9ae-184">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-184">Click **Commit**.</span></span>

<span data-ttu-id="4b9ae-p114">このページの [**関連付けられたサブネット**] テーブルを変更することはできません。 関連付けられたサブネットの一覧は、参照のために用意されており、サイトの設定を変えるとどのサブネットが影響を受けるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="4b9ae-187">既存のネットワーク サイトを削除する</span><span class="sxs-lookup"><span data-stu-id="4b9ae-187">Delete an existing network site</span></span>

<span data-ttu-id="4b9ae-188">ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="4b9ae-189">Skype for Business Server コントロール パネルを使用してサイトを構成し、それらを地域に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="4b9ae-190">たとえば、北アメリカのネットワーク地域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="4b9ae-191">CAC ネットワーク サイトは、サイトに帯域幅制限がない場合でも、組織内の各サイトに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="4b9ae-192">Skype for Business Server コントロール パネルから、ネットワーク サイトを作成、変更、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="4b9ae-193">既存のネットワーク サイトを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="4b9ae-194">ネットワーク サイトの作成または変更の詳細については、「サイトの通話受付管理の管理 [」を参照してください](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="4b9ae-195">ネットワーク サイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="4b9ae-195">To delete a network site</span></span>

1.  <span data-ttu-id="4b9ae-196">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b9ae-197">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b9ae-198">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サイト] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="4b9ae-199">[**サイト**] ページで、削除するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4b9ae-p116">1 つ以上のサイトを一度に削除できます。 これを実行するには、Ctrl キーを押しながら、複数のサイトを選択します。 また、すべてのサイトを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="4b9ae-203">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="4b9ae-204">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="4b9ae-p117">ただし、ネットワーク サイトがネットワーク サブネットに関連付けられている場合は、サイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラー メッセージが表示されます。 サイトがサブネットに関連付けられているかどうかを確認するには、そのサイトをクリックして、[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9ae-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="4b9ae-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b9ae-208">See Also</span></span>


[<span data-ttu-id="4b9ae-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4b9ae-209">New-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="4b9ae-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4b9ae-210">Set-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="4b9ae-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4b9ae-211">Remove-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="4b9ae-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4b9ae-212">Get-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="4b9ae-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4b9ae-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="4b9ae-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4b9ae-214">New-CsNetworkSite</span></span>](/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="4b9ae-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4b9ae-215">Set-CsNetworkSite</span></span>](/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="4b9ae-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4b9ae-216">Remove-CsNetworkSite</span></span>](/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="4b9ae-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4b9ae-217">Get-CsNetworkSite</span></span>](/powershell/module/skype/Get-CsNetworkSite)