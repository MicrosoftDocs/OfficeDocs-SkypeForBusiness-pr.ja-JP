---
title: ネットワーク領域のリンク
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
description: '通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。 '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817526"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="5c99e-103">Skype for Business Server でのネットワーク領域のリンクの設定</span><span class="sxs-lookup"><span data-stu-id="5c99e-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="5c99e-104">通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="5c99e-105">この記事のセクションを使用して、newtwork region リンク情報を表示したり、netwrok region リンクを構成または削除したりします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="5c99e-106">ネットワーク領域のリンク情報を表示する</span><span class="sxs-lookup"><span data-stu-id="5c99e-106">View network region link information</span></span> 

<span data-ttu-id="5c99e-107">通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="5c99e-108">ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。</span><span class="sxs-lookup"><span data-stu-id="5c99e-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="5c99e-109">Skype for Business Server コントロールパネルを使用して、2つのネットワーク領域間の既存のリンクを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="5c99e-110">Skype for Business Server コントロールパネルでネットワーク領域のリンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="5c99e-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5c99e-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c99e-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c99e-113">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="5c99e-114">[**地域] リンク**ページで、表示する地域のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="5c99e-115">一度に表示できるのは、1つの地域のリンクに関する情報だけです。</span><span class="sxs-lookup"><span data-stu-id="5c99e-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="5c99e-116">[**編集**] メニューの [**詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5c99e-117">Windows PowerShell コマンドレットを使用してネットワーク領域のリンク情報を表示する</span><span class="sxs-lookup"><span data-stu-id="5c99e-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5c99e-118">ネットワークの領域のリンクを表示するには、Windows PowerShell を使用するか、または**CsNetworkRegionLink**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="5c99e-119">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="5c99e-120">ネットワーク領域のリンク情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="5c99e-120">To view network region link information</span></span>

  - <span data-ttu-id="5c99e-121">すべてのネットワーク領域のリンクに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="5c99e-122">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="5c99e-123">詳細については、「 [CsNetworkRegionLink の入手](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c99e-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="5c99e-124">ネットワーク領域のリンクを構成する</span><span class="sxs-lookup"><span data-stu-id="5c99e-124">Configure network region links</span></span> 

<span data-ttu-id="5c99e-125">通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="5c99e-126">ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。</span><span class="sxs-lookup"><span data-stu-id="5c99e-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="5c99e-127">Skype for Business Server コントロールパネルを使用して、2つのネットワーク領域間のリンクを定義し、これらの地域間の音声およびビデオ接続の帯域幅の制限を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="5c99e-128">ネットワーク領域のリンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="5c99e-128">To create a network region link</span></span>

1.  <span data-ttu-id="5c99e-129">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c99e-130">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c99e-131">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="5c99e-132">[**地域] リンク**ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="5c99e-133">[**新しい地域] リンク**で、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="5c99e-134">この値は、Skype for Business Server の展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c99e-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="5c99e-135">[ **Network region \#1** ] ボックスの一覧で、リンクする2つの領域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="5c99e-136">[ **Network region \#2** ] ボックスの一覧で、リンクする他の地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="5c99e-137">この領域は、ネットワーク領域\#1 で選択した地域とは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c99e-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="5c99e-138">省略これらの地域間の音声通話やビデオ通話に帯域幅の制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="5c99e-139">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="5c99e-140">ネットワーク領域のリンクを変更するには</span><span class="sxs-lookup"><span data-stu-id="5c99e-140">To modify a network region link</span></span>

1.  <span data-ttu-id="5c99e-141">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c99e-142">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c99e-143">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="5c99e-144">[**地域] リンク**ページで、変更する地域のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="5c99e-145">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5c99e-146">[**範囲の編集] リンク**では、リンクされている地域、またはこのリンクの帯域幅ポリシープロファイルを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="5c99e-147">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="5c99e-148">ネットワーク領域のリンクを削除する</span><span class="sxs-lookup"><span data-stu-id="5c99e-148">Delete network region links</span></span>

<span data-ttu-id="5c99e-149">通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="5c99e-150">ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。</span><span class="sxs-lookup"><span data-stu-id="5c99e-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="5c99e-151">Skype for Business Server コントロールパネルを使用して、2つのネットワーク領域間の既存のリンクを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="5c99e-152">ネットワーク領域のリンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="5c99e-152">To delete a network region link</span></span>

1.  <span data-ttu-id="5c99e-153">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c99e-154">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c99e-155">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="5c99e-156">[**領域のリンク**] ページで、削除する地域のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="5c99e-157">一度に複数の領域のリンクを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5c99e-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="5c99e-158">これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数の領域のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="5c99e-159">または、すべての地域リンクを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="5c99e-160">[**編集**] メニューの [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c99e-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="5c99e-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c99e-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="5c99e-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c99e-162">See Also</span></span>

[<span data-ttu-id="5c99e-163">新しい-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5c99e-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="5c99e-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5c99e-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="5c99e-165">CsNetworkRegionLink を削除する</span><span class="sxs-lookup"><span data-stu-id="5c99e-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="5c99e-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5c99e-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
