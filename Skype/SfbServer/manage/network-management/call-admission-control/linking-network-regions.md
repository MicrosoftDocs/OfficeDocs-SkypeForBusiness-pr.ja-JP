---
title: ネットワーク地域のリンク
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
description: '通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。 '
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816467"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="1991e-103">Skype for Business Server でのネットワーク領域のリンクの設定</span><span class="sxs-lookup"><span data-stu-id="1991e-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="1991e-104">通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="1991e-105">この記事のセクションを使用して、新しい作業領域リンク情報を表示したり、netwrok 地域リンクを構成または削除したりします。</span><span class="sxs-lookup"><span data-stu-id="1991e-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="1991e-106">ネットワーク地域リンク情報の表示</span><span class="sxs-lookup"><span data-stu-id="1991e-106">View network region link information</span></span> 

<span data-ttu-id="1991e-107">通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="1991e-108">ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="1991e-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="1991e-109">Skype for Business Server コントロール パネルを使用して、2 つのネットワーク地域間の既存のリンクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1991e-110">Skype for Business Server コントロール パネルでネットワーク地域リンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="1991e-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1991e-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1991e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1991e-112">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1991e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1991e-113">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[地域リンク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1991e-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="1991e-114">[**地域リンク**] ページで、表示する地域リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1991e-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="1991e-115">一度に情報を表示できる地域リンクは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="1991e-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="1991e-116">[**編集**] メニューの [**詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1991e-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1991e-117">次のコマンドレットを使用してネットワーク地域Windows PowerShell表示する</span><span class="sxs-lookup"><span data-stu-id="1991e-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1991e-118">ネットワーク地域リンクを表示するには、Windows PowerShell **Get-CsNetworkRegionLink コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="1991e-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="1991e-119">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="1991e-120">ネットワーク地域リンク情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="1991e-120">To view network region link information</span></span>

  - <span data-ttu-id="1991e-121">すべてのネットワーク地域リンクに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1991e-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="1991e-122">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="1991e-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="1991e-123">詳細については、「[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1991e-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="1991e-124">ネットワーク地域リンクを構成する</span><span class="sxs-lookup"><span data-stu-id="1991e-124">Configure network region links</span></span> 

<span data-ttu-id="1991e-125">通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="1991e-126">ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="1991e-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="1991e-127">Skype for Business Server コントロール パネルを使用して、2 つのネットワーク地域間のリンクを定義し、これらの地域間の音声接続とビデオ接続の帯域幅制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="1991e-128">ネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="1991e-128">To create a network region link</span></span>

1.  <span data-ttu-id="1991e-129">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1991e-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1991e-130">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1991e-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1991e-131">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[地域リンク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1991e-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="1991e-132">[地域リンク **] ページで、[** 新規] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1991e-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="1991e-133">[ **新しい地域リンク] で**、[名前] フィールドに値 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="1991e-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="1991e-134">この値は、Skype for Business Server 展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1991e-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="1991e-135">[ **ネットワーク地域 \# 1]** ドロップダウン リストから、リンクする 2 つの地域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="1991e-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="1991e-136">[ **ネットワーク地域 \# 2]** ドロップダウン リストから、リンクする他の地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="1991e-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="1991e-137">この地域は、ネットワーク地域 1 で選択した地域とは異なる \# 必要があります。</span><span class="sxs-lookup"><span data-stu-id="1991e-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="1991e-138">(省略可能)これらの地域間の音声通話またはビデオ通話に帯域幅制限を設定する場合は、[帯域幅ポリシー] ドロップダウン リストから帯域幅ポリシー プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1991e-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="1991e-139">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1991e-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="1991e-140">ネットワーク地域リンクを変更するには</span><span class="sxs-lookup"><span data-stu-id="1991e-140">To modify a network region link</span></span>

1.  <span data-ttu-id="1991e-141">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1991e-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1991e-142">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1991e-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1991e-143">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[地域リンク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1991e-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="1991e-144">[地域 **リンク] ページ** で、変更する地域リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1991e-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="1991e-145">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1991e-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1991e-146">[ **地域リンクの** 編集] では、リンクされている地域またはこのリンクの帯域幅ポリシー プロファイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="1991e-147">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1991e-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="1991e-148">ネットワーク地域リンクを削除する</span><span class="sxs-lookup"><span data-stu-id="1991e-148">Delete network region links</span></span>

<span data-ttu-id="1991e-149">通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="1991e-150">ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="1991e-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="1991e-151">Skype for Business Server コントロール パネルを使用して、2 つのネットワーク地域間の既存のリンクを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1991e-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="1991e-152">ネットワーク地域リンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="1991e-152">To delete a network region link</span></span>

1.  <span data-ttu-id="1991e-153">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1991e-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1991e-154">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1991e-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1991e-155">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[地域リンク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1991e-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="1991e-156">[**地域リンク**] ページで、削除する地域リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1991e-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="1991e-p107">1 つ以上の地域リンクを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数の地域リンクを選択します。また、すべての地域リンクを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1991e-p107">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="1991e-160">[**編集**] メニューの [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1991e-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="1991e-161">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1991e-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="1991e-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="1991e-162">See Also</span></span>

[<span data-ttu-id="1991e-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1991e-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="1991e-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1991e-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="1991e-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1991e-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="1991e-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1991e-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
