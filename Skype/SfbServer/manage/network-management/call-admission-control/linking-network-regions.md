---
title: ネットワークの領域をリンクします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを構成することができます。 '
ms.openlocfilehash: 30d4a020826b24c3615ce059809645481466efc3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888353"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="9e9fd-103">Skype for Business Server でのネットワーク領域のリンクの設定</span><span class="sxs-lookup"><span data-stu-id="9e9fd-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="9e9fd-104">呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="9e9fd-105">Newtwork 領域のリンク情報を表示または構成するネットワーク地域リンクを削除するには、この資料のセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="9e9fd-106">ネットワーク地域リンク情報の表示</span><span class="sxs-lookup"><span data-stu-id="9e9fd-106">View network region link information</span></span> 

<span data-ttu-id="9e9fd-107">呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="9e9fd-108">ネットワーク内の領域は、物理的なワイド エリア ネットワーク (WAN) 接続を介してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="9e9fd-109">ビジネス サーバーのコントロール パネルの Skype を使用するには 2 つのネットワーク領域間の既存のリンクを表示するのには。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="9e9fd-110">Skype のビジネス サーバーのコントロール パネルの地域のネットワーク リンクを表示するのには</span><span class="sxs-lookup"><span data-stu-id="9e9fd-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9e9fd-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9e9fd-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9e9fd-113">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域のリンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="9e9fd-114">[**地域リンク**] ページで、表示する領域のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="9e9fd-115">のみ、一度に 1 つの領域のリンク情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="9e9fd-116">**[編集**] メニュー**の詳細を表示**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9e9fd-117">Windows PowerShell コマンドレットを使用してネットワーク地域リンク情報の表示</span><span class="sxs-lookup"><span data-stu-id="9e9fd-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9e9fd-118">Windows PowerShell と**Get CsNetworkRegionLink**コマンドレットを使用してネットワーク地域リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="9e9fd-119">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="9e9fd-120">ネットワーク地域リンク情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="9e9fd-120">To view network region link information</span></span>

  - <span data-ttu-id="9e9fd-121">すべてのネットワーク地域リンクに関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="9e9fd-122">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="9e9fd-123">詳細については、 [Get CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="9e9fd-124">ネットワーク地域リンクを構成します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-124">Configure network region links</span></span> 

<span data-ttu-id="9e9fd-125">呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="9e9fd-126">ネットワーク内の領域は、物理的なワイド エリア ネットワーク (WAN) 接続を介してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="9e9fd-127">ビジネス サーバーのコントロール パネルの Skype を使用するには 2 つのネットワーク領域間のリンクを定義し、これらの領域間でのオーディオおよびビデオ接続の帯域幅の制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="9e9fd-128">ネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="9e9fd-128">To create a network region link</span></span>

1.  <span data-ttu-id="9e9fd-129">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9e9fd-130">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9e9fd-131">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域のリンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="9e9fd-132">[**地域リンク**] ページで [**新規**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="9e9fd-133">**新しい地域リンク**] で **[名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="9e9fd-134">この値は、ビジネスのサーバーの展開に、Skype 内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="9e9fd-135">**ネットワークの領域\#1** 」ドロップ ダウン リスト、リンクする 2 つの領域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="9e9fd-136">**ネットワークの領域\#2** 」ドロップ ダウン リストで、リンクするその他の地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="9e9fd-137">この領域は、ネットワークの領域を選択した領域とは異なるである必要があります\#1 です。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="9e9fd-138">(省略可能)これらの領域の間のオーディオまたはビデオ通話に帯域幅の制限を配置する場合は、**帯域幅ポリシー**のドロップダウン リストから、帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="9e9fd-139">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="9e9fd-140">ネットワーク地域リンクを変更するのには</span><span class="sxs-lookup"><span data-stu-id="9e9fd-140">To modify a network region link</span></span>

1.  <span data-ttu-id="9e9fd-141">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9e9fd-142">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9e9fd-143">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域のリンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="9e9fd-144">[**地域リンク**] ページで、変更する地域リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="9e9fd-145">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9e9fd-146">**地域リンクの編集**] で、リンクされている地域やこのリンクの帯域幅ポリシーのプロファイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="9e9fd-147">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="9e9fd-148">ネットワーク地域リンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-148">Delete network region links</span></span>

<span data-ttu-id="9e9fd-149">呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="9e9fd-150">ネットワーク内の領域は、物理的なワイド エリア ネットワーク (WAN) 接続を介してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="9e9fd-151">ビジネス サーバーのコントロール パネルの Skype を使用するには 2 つのネットワーク領域間の既存のリンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="9e9fd-152">ネットワーク地域リンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="9e9fd-152">To delete a network region link</span></span>

1.  <span data-ttu-id="9e9fd-153">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9e9fd-154">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9e9fd-155">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域のリンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="9e9fd-156">[**地域リンク**] ページで、削除する地域リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="9e9fd-157">一度に複数の地域のリンクを削除できます。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="9e9fd-158">これを行うには、CTRL キーを押し、CTRL キーを押しながら複数の地域のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="9e9fd-159">または、地域のすべてのリンクを選択するに<STRONG>[すべて選択</STRONG>] をクリックして<STRONG>[編集</STRONG>] メニューです。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="9e9fd-160">**[編集**] メニューから [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="9e9fd-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e9fd-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="9e9fd-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e9fd-162">See Also</span></span>

[<span data-ttu-id="9e9fd-163">新しい-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9e9fd-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="9e9fd-164">セット CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9e9fd-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="9e9fd-165">削除 CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9e9fd-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="9e9fd-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9e9fd-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
