---
title: ネットワーク地域ルートの管理
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
description: ネットワーク地域ルートでは、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。
ms.openlocfilehash: c91f46ff45dd50f638cdb4f256fb93f2d33781ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118556"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="c9d25-104">Skype for Business Server でのネットワーク領域ルートの管理</span><span class="sxs-lookup"><span data-stu-id="c9d25-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="c9d25-105">\*\* ネットワーク地域ルートでは、ネットワーク地域のペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="c9d25-106">通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9d25-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="c9d25-107">これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c9d25-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="c9d25-108">ネットワーク地域ルートを表示、作成、変更、または削除するには、この artilce の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="c9d25-109">ネットワーク地域のルート情報を表示する</span><span class="sxs-lookup"><span data-stu-id="c9d25-109">View network region route information</span></span> 

<span data-ttu-id="c9d25-110">通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d25-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="c9d25-111">地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="c9d25-112">Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルの既存のネットワーク地域ルートを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c9d25-113">Skype for Business Server コントロール パネルでネットワーク地域のルート情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="c9d25-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c9d25-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c9d25-115">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c9d25-116">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域ルート] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c9d25-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c9d25-117">[**地域ルート**] ページで、変更する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="c9d25-118">一度に表示できる地域ルートは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="c9d25-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="c9d25-119">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c9d25-120">ネットワーク地域のルート情報を表示する (Windows PowerShellコマンドレットを使用)</span><span class="sxs-lookup"><span data-stu-id="c9d25-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c9d25-121">ネットワーク地域のルート情報は、ネットワーク と Windows PowerShellコマンドレットをGet-CsNetworkInterRegionRouteできます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="c9d25-122">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c9d25-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="c9d25-123">ネットワーク地域のルート情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="c9d25-123">To view network region route information</span></span>

  - <span data-ttu-id="c9d25-124">すべてのネットワーク地域ルートに関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="c9d25-125">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="c9d25-126">詳細については、[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9d25-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="c9d25-127">ネットワーク地域ルートの作成または変更</span><span class="sxs-lookup"><span data-stu-id="c9d25-127">Create or modify network region routes</span></span>

<span data-ttu-id="c9d25-128">通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d25-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="c9d25-129">地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="c9d25-130">Skype for Business Server コントロール パネルを使用して、ネットワーク地域のルートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="c9d25-131">Skype for Business Server コントロール パネルから、ネットワーク地域ルートを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="c9d25-132">このトピックでは、ネットワーク地域ルートの作成または変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="c9d25-133">ネットワーク地域ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="c9d25-133">To create a network region route</span></span>

1.  <span data-ttu-id="c9d25-134">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c9d25-135">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c9d25-136">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域ルート] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c9d25-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c9d25-137">[**地域ルート**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="c9d25-138">[**新しい地域ルート**] で、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="c9d25-139">この値は、Skype for Business Server 展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d25-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="c9d25-140">[ネットワーク **領域 \# 1]** ドロップダウン リストから、このルートで接続する 2 つの領域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="c9d25-141">[ネットワーク **領域 \# 2]** ドロップダウン リストから、このルートの他の領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="c9d25-142">この領域は、ネットワーク領域 1 で選択した地域とは異なる \# 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d25-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="c9d25-p107">[**ネットワーク地域リンク**] リスト ボックスを使用して、地域リンクをルートに追加します。 [**追加**] ボタンをクリックし、[**地域リンク**] ページを表示します。 このルートに追加する地域リンクをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="c9d25-146">[**追加**] ボタンのクリックを続けて、さらにリンクを追加できます。また、リンクを選択して [**削除**] をクリックすると、リンクを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="c9d25-147">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="c9d25-148">ネットワーク地域ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="c9d25-148">To modify a network region route</span></span>

1.  <span data-ttu-id="c9d25-149">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c9d25-150">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c9d25-151">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域ルート] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c9d25-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c9d25-152">[**地域ルート**] ページで、変更する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="c9d25-153">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c9d25-154">[**地域ルートの編集**] で、このルートが接続する地域やこのルートに関連付ける地域リンクを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="c9d25-155">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="c9d25-156">既存のネットワーク地域ルートの削除</span><span class="sxs-lookup"><span data-stu-id="c9d25-156">Delete existing network region routes</span></span>

<span data-ttu-id="c9d25-157">通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d25-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="c9d25-158">地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="c9d25-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="c9d25-159">Skype for Business Server コントロール パネルを使用して、ネットワーク地域のルートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="c9d25-160">Skype for Business Server コントロール パネルから、ネットワーク地域ルートを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="c9d25-161">このトピックを使用して、既存のネットワーク地域ルートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="c9d25-162">ネットワーク地域ルートを削除するには</span><span class="sxs-lookup"><span data-stu-id="c9d25-162">To delete a network region route</span></span>

1.  <span data-ttu-id="c9d25-163">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c9d25-164">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9d25-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c9d25-165">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域ルート] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c9d25-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c9d25-166">[**地域ルート**] ページで、削除する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="c9d25-p109">1 つ以上の地域ルートを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のルートを選択します。また、すべての地域ルートを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="c9d25-170">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="c9d25-171">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d25-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="c9d25-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9d25-172">See Also</span></span>

[<span data-ttu-id="c9d25-173">Skype for Business Server でのネットワーク領域の管理</span><span class="sxs-lookup"><span data-stu-id="c9d25-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="c9d25-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c9d25-174">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="c9d25-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c9d25-175">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="c9d25-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c9d25-176">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="c9d25-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c9d25-177">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Get-CsNetworkInterRegionRoute)