---
title: ネットワーク領域ルートの管理
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
description: ネットワーク領域ルートは、ネットワーク領域のペア間のルートを定義します。 通話受付制御の展開におけるネットワーク領域の各ペアには、ネットワーク領域ルートが必要です。
ms.openlocfilehash: 5e0c099b8c461873b96963c721d835f1ccdf4705
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817496"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="7634c-104">Skype for Business Server でのネットワーク領域ルートの管理</span><span class="sxs-lookup"><span data-stu-id="7634c-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="7634c-105">*ネットワーク領域ルート*は、ネットワーク領域のペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="7634c-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="7634c-106">通話受付制御の展開におけるネットワーク領域の各ペアには、ネットワーク領域ルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="7634c-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="7634c-107">これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7634c-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="7634c-108">ネットワーク領域ルートを表示、作成、変更、または削除するには、この artilce の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7634c-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="7634c-109">ネットワーク領域ルート情報を表示する</span><span class="sxs-lookup"><span data-stu-id="7634c-109">View network region route information</span></span> 

<span data-ttu-id="7634c-110">通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7634c-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="7634c-111">地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。</span><span class="sxs-lookup"><span data-stu-id="7634c-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="7634c-112">次の手順を使用して、Skype for Business Server コントロールパネルまたは Skype for Business Server Management Shell で既存のネットワーク領域ルートを表示します。</span><span class="sxs-lookup"><span data-stu-id="7634c-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="7634c-113">Skype for Business Server コントロールパネルのネットワーク領域ルート情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="7634c-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="7634c-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7634c-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7634c-115">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7634c-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7634c-116">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="7634c-117">[**地域ルート**] ページで、表示する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="7634c-118">表示できる地域ルートは一度に1つだけです。</span><span class="sxs-lookup"><span data-stu-id="7634c-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="7634c-119">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7634c-120">Windows PowerShell コマンドレットを使用したネットワーク領域ルート情報の表示</span><span class="sxs-lookup"><span data-stu-id="7634c-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7634c-121">ネットワーク領域のルート情報を表示するには、Windows PowerShell を使用するか、または CsNetworkInterRegionRoute コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7634c-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="7634c-122">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="7634c-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="7634c-123">ネットワーク領域ルート情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="7634c-123">To view network region route information</span></span>

  - <span data-ttu-id="7634c-124">すべてのネットワーク領域ルートに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7634c-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="7634c-125">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7634c-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="7634c-126">詳細については、「 [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7634c-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="7634c-127">ネットワーク領域ルートを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="7634c-127">Create or modify network region routes</span></span>

<span data-ttu-id="7634c-128">通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7634c-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="7634c-129">地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。</span><span class="sxs-lookup"><span data-stu-id="7634c-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="7634c-130">Skype for Business Server コントロールパネルを使用して、ネットワーク領域ルートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7634c-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="7634c-131">Skype for Business Server コントロールパネルでは、ネットワーク領域ルートの作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7634c-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="7634c-132">ネットワーク領域ルートを作成または変更するには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="7634c-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="7634c-133">ネットワーク領域ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="7634c-133">To create a network region route</span></span>

1.  <span data-ttu-id="7634c-134">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7634c-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7634c-135">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7634c-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7634c-136">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="7634c-137">[**地域ルート**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="7634c-138">[**新しい地域ルート**] で、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="7634c-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="7634c-139">この値は、Skype for Business Server の展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7634c-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="7634c-140">[ **Network region \#1** ] ドロップダウンリストから、このルートによって接続される2つの領域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7634c-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="7634c-141">[ **Network region \#2** ] ドロップダウンリストから、このルートの他の地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="7634c-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="7634c-142">この領域は、ネットワーク領域\#1 で選択した地域とは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7634c-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="7634c-143">[**ネットワークの領域のリンク**] リストボックスを使って、そのルートに地域のリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="7634c-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="7634c-144">[**追加**] ボタンをクリックして、[**地域] リンク**ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="7634c-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="7634c-145">このルートに追加する地域のリンクをクリックして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="7634c-146">[**追加**] ボタンをクリックして、さらにリンクを追加するか、リンクを選択して [**削除**] をクリックし、リンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="7634c-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="7634c-147">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="7634c-148">ネットワークの領域ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="7634c-148">To modify a network region route</span></span>

1.  <span data-ttu-id="7634c-149">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7634c-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7634c-150">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7634c-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7634c-151">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="7634c-152">[**地域ルート**] ページで、変更する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="7634c-153">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="7634c-154">[**範囲ルートの編集**] で、このルートによって参加している地域と、ルートに関連付けられている地域リンクを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7634c-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="7634c-155">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="7634c-156">既存のネットワーク領域ルートを削除する</span><span class="sxs-lookup"><span data-stu-id="7634c-156">Delete existing network region routes</span></span>

<span data-ttu-id="7634c-157">通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7634c-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="7634c-158">地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。</span><span class="sxs-lookup"><span data-stu-id="7634c-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="7634c-159">Skype for Business Server コントロールパネルを使用して、ネットワーク領域ルートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7634c-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="7634c-160">Skype for Business Server コントロールパネルでは、ネットワーク領域ルートの作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7634c-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="7634c-161">このトピックを使用して、既存のネットワーク領域ルートを削除します。</span><span class="sxs-lookup"><span data-stu-id="7634c-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="7634c-162">ネットワーク領域ルートを削除するには</span><span class="sxs-lookup"><span data-stu-id="7634c-162">To delete a network region route</span></span>

1.  <span data-ttu-id="7634c-163">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7634c-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7634c-164">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7634c-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7634c-165">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="7634c-166">[**地域ルート**] ページで、削除する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="7634c-167">複数の地域のルートを一度に削除できます。</span><span class="sxs-lookup"><span data-stu-id="7634c-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="7634c-168">これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数の領域ルートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7634c-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="7634c-169">または、すべての地域ルートを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="7634c-170">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="7634c-171">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7634c-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="7634c-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="7634c-172">See Also</span></span>

[<span data-ttu-id="7634c-173">Skype for Business Server でのネットワーク領域の管理</span><span class="sxs-lookup"><span data-stu-id="7634c-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="7634c-174">新しい (CsNetworkInterRegionRoute)</span><span class="sxs-lookup"><span data-stu-id="7634c-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="7634c-175">設定-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="7634c-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="7634c-176">CsNetworkInterRegionRoute の削除</span><span class="sxs-lookup"><span data-stu-id="7634c-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="7634c-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="7634c-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
