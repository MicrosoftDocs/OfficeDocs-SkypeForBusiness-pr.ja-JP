---
title: サイトの通話受付制御の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '[ネットワークサイト] は、通話受付制御 (CAC)、E9、および media バイパスの展開の各ネットワーク領域内の事業所または場所です。'
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817516"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="e4b6c-103">Skype for Business Server でのサイトの通話受付管理サービスの管理</span><span class="sxs-lookup"><span data-stu-id="e4b6c-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="e4b6c-104">[ネットワークサイト] は、通話受付制御 (CAC)、E9、および media バイパスの展開の各ネットワーク領域内の事業所または場所です。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="e4b6c-105">この記事の手順を使用して、ネットワークサイトの通話受付制御を構成します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="e4b6c-106">ネットワークサイトリンクを構成する</span><span class="sxs-lookup"><span data-stu-id="e4b6c-106">Configure network site links</span></span>

<span data-ttu-id="e4b6c-107">通話受付制御 (CAC) 構成では、直接リンクされているサイト間の帯域幅の制限を定義するネットワーク間ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="e4b6c-108">ネットワークサイトが直接リンクを共有している場合、オーディオおよびビデオ接続の帯域幅の制限は、これら2つのサイト間で定義できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="e4b6c-109">Skype for Business Server コントロールパネルを使ってネットワークサイトポリシーを構成することはできません。これは、Skype for Business Server 管理シェルからコマンドレットを使用することによってのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e4b6c-110">Skype for Business Server 管理シェルからネットワークサイトリンク (ネットワーク間ポリシーとも呼ばれます) の作成、変更、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="e4b6c-111">ネットワークサイトのリンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="e4b6c-111">To create a network site link</span></span>

1.  <span data-ttu-id="e4b6c-112">Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="e4b6c-113">Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。次に、[skype **for business server**] をクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="e4b6c-114">コマンドプロンプトで、次のコマンドを入力します。これは、構成に対して有効な値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="e4b6c-115">この例では、Reno とポートランドのネットワーク\_サイト間の帯域幅の制限を設定する Reno ポートランドという名前の新しいネットワークサイトリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="e4b6c-116">このコマンドを実行する前に、ネットワークサイトと帯域幅ポリシーのプロファイルが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="e4b6c-117">パラメーターの詳細については、「 [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="e4b6c-118">ネットワークサイトリンクに適用できる帯域幅ポリシープロファイルの一覧を取得するには、 **CsNetworkBandwidthPolicyProfile**コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="e4b6c-119">詳細については、「 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="e4b6c-120">ネットワークサイトのリンクを変更するには</span><span class="sxs-lookup"><span data-stu-id="e4b6c-120">To modify a network site link</span></span>

1.  <span data-ttu-id="e4b6c-121">Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="e4b6c-122">Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。次に、[skype **for business server**] をクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="e4b6c-123">指定のネットワークサイトリンクのプロパティを変更するには、 **CsNetworkInterSitePolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="e4b6c-124">いずれか (または両方) または接続されたサイトを変更することができます。また、リンクに関連付けられている帯域幅ポリシープロファイルを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="e4b6c-125">Reno\_ポートランドという名前のサイトリンクの帯域幅ポリシープロファイルを変更する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="e4b6c-126">パラメーターの詳細については、「 [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="e4b6c-127">ネットワークサイトのリンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="e4b6c-127">To delete a network site link</span></span>

1.  <span data-ttu-id="e4b6c-128">Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="e4b6c-129">Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。次に、[skype **for business server**] をクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="e4b6c-130">ネットワークサイトへのリンクを削除するには、 **CsNetworkInterSitePolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="e4b6c-131">次の例では、\_Reno ポートランドネットワークサイトのリンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="e4b6c-132">パラメーターの詳細については、「 [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="e4b6c-133">ネットワークサイトの情報を表示する</span><span class="sxs-lookup"><span data-stu-id="e4b6c-133">View network site information</span></span>

<span data-ttu-id="e4b6c-134">[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="e4b6c-135">ネットワークサイトの情報は、Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e4b6c-136">Skype for Business Server コントロールパネルでネットワークサイトの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="e4b6c-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="e4b6c-137">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4b6c-138">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e4b6c-139">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="e4b6c-140">[**サイト**] ページで、表示するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="e4b6c-141">一度に1つのサイトの情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="e4b6c-142">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e4b6c-143">Windows PowerShell コマンドレットを使用したネットワークサイト情報の表示</span><span class="sxs-lookup"><span data-stu-id="e4b6c-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e4b6c-144">ネットワークサイトの情報を表示するには、Windows PowerShell を使用するか、または CsNetworkSite コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="e4b6c-145">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="e4b6c-146">ネットワークサイトの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="e4b6c-146">To view network site information</span></span>

  - <span data-ttu-id="e4b6c-147">すべてのネットワークサイトに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="e4b6c-148">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="e4b6c-149">詳細については、「 [CsNetworkSite site](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) 」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="e4b6c-150">ネットワークサイトを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e4b6c-150">Create or modify network sites</span></span> 

<span data-ttu-id="e4b6c-151">[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="e4b6c-152">Skype for Business Server コントロールパネルを使用して、サイトを構成し、それらを地域に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="e4b6c-153">たとえば、北米向けのネットワーク領域は、シカゴ、Redmond、バンクーバーなどのネットワークサイトに関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="e4b6c-154">サイト内のすべてのサイトに対して、CAC ネットワークサイトを作成する必要があります。このサイトには帯域幅の制限がありません。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="e4b6c-155">Skype for Business Server コントロールパネルから、ネットワークサイトの作成、変更、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="e4b6c-156">ネットワークサイトを作成または変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="e4b6c-157">ネットワークサイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="e4b6c-157">To create a network site</span></span>

1.  <span data-ttu-id="e4b6c-158">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4b6c-159">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e4b6c-160">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="e4b6c-161">[**サイト**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="e4b6c-162">[**新しいサイト**] の [**名前**] フィールドに、このサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="e4b6c-163">サイト名は、Skype for Business Server の展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="e4b6c-164">[ **Region** ] ドロップダウンリストで、このサイトに関連付けるネットワーク領域を選びます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="e4b6c-165">省略このサイトへの音声通話またはビデオ通話に帯域幅の制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから適切な設定を使用して、帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="e4b6c-166">利用可能な帯域幅ポリシープロファイルの詳細を表示したり、新しい帯域幅ポリシープロファイルを作成したりするには、**ネットワーク構成**グループの [**ポリシー Profil** ] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="e4b6c-167">詳細については、「[ネットワーク帯域幅ポリシープロファイルを管理する](managing-network-bandwidth-policy-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="e4b6c-168">省略このサイトの場所の設定を指定する場合は、[**場所のポリシー** ] ドロップダウンリストから場所のポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="e4b6c-169">位置情報ポリシーは、特定の拡張 9-1-1 (E9) およびクライアントの場所の設定をサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="e4b6c-170">利用可能な位置情報ポリシーの詳細を表示するか、[**ネットワーク構成**] グループの [**場所のポリシー** ] ページから新しい場所ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="e4b6c-171">省略[**説明**] フィールドに値を入力して、このサイトについて、名前だけでは表現できない詳細情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="e4b6c-172">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="e4b6c-173">新しいネットワークサイトを作成する場合は、**関連するサブネット**テーブルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="e4b6c-174">サブネットを作成または変更するときに、サブネットをサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="e4b6c-175">詳細については、「[ネットワークサブネットを管理する](managing-network-subnets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="e4b6c-176">ネットワークサイトを変更するには</span><span class="sxs-lookup"><span data-stu-id="e4b6c-176">To modify a network site</span></span>

1.  <span data-ttu-id="e4b6c-177">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4b6c-178">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e4b6c-179">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="e4b6c-180">[**サイト**] ページで、変更するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="e4b6c-181">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e4b6c-182">[**サイトの編集**] ページでは、サイトに関連付けられている説明、地域、帯域幅ポリシーのプロファイル、および場所のポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="e4b6c-183">詳細については、「[ネットワークサイトを作成する」を](#to-create-a-network-site)参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="e4b6c-184">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-184">Click **Commit**.</span></span>

<span data-ttu-id="e4b6c-185">このページでは、**関連するサブネット**テーブルを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="e4b6c-186">関連付けられたサブネットの一覧は参照用に提供されるため、サイトの設定を変更したときに影響を受けるサブネットを認識できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="e4b6c-187">既存のネットワークサイトを削除する</span><span class="sxs-lookup"><span data-stu-id="e4b6c-187">Delete an existing network site</span></span>

<span data-ttu-id="e4b6c-188">[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="e4b6c-189">Skype for Business Server コントロールパネルを使用して、サイトを構成し、それらを地域に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="e4b6c-190">たとえば、北米向けのネットワーク領域は、シカゴ、Redmond、バンクーバーなどのネットワークサイトに関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="e4b6c-191">サイト内のすべてのサイトに対して、CAC ネットワークサイトを作成する必要があります。このサイトには帯域幅の制限がありません。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="e4b6c-192">Skype for Business Server コントロールパネルから、ネットワークサイトの作成、変更、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="e4b6c-193">既存のネットワークサイトを削除するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="e4b6c-194">ネットワークサイトの作成または変更の詳細については、「[サイトの通話受付制御を管理する](managing-call-admission-control-for-sites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="e4b6c-195">ネットワークサイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="e4b6c-195">To delete a network site</span></span>

1.  <span data-ttu-id="e4b6c-196">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4b6c-197">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e4b6c-198">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="e4b6c-199">[**サイト**] ページで、削除するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="e4b6c-200">一度に複数のサイトを削除できます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="e4b6c-201">この操作を行うには、ctrl キーを押しながら複数のサイトを選び、CTRL キーを押しながら選択します。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="e4b6c-202">または、すべてのサイトを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="e4b6c-203">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="e4b6c-204">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="e4b6c-205">ネットワークサイトがネットワークサブネットに関連付けられている場合は、そのサイトを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="e4b6c-206">サブネットに関連付けられているサイトを削除しようとすると、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="e4b6c-207">サイトがいずれかのサブネットに関連付けられているかどうかを確認するには、サイトをクリックし、[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4b6c-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="e4b6c-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4b6c-208">See Also</span></span>


[<span data-ttu-id="e4b6c-209">新規-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e4b6c-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="e4b6c-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e4b6c-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="e4b6c-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e4b6c-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="e4b6c-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e4b6c-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="e4b6c-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="e4b6c-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="e4b6c-214">新しい-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="e4b6c-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="e4b6c-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="e4b6c-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="e4b6c-216">CsNetworkSite の削除</span><span class="sxs-lookup"><span data-stu-id="e4b6c-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="e4b6c-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="e4b6c-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
