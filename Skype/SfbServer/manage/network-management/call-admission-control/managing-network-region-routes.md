---
title: ネットワーク地域ルートの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク地域のルートは、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域のルートが必要です。
ms.openlocfilehash: 53b6383e08196fb22784f3fcd1e8d797c9b138de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888850"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="2ac08-104">Skype for Business Server でのネットワーク領域ルートの管理</span><span class="sxs-lookup"><span data-stu-id="2ac08-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="2ac08-105">*地域のネットワーク ルート*は、ネットワーク地域のペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="2ac08-106">通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域のルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="2ac08-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="2ac08-107">これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2ac08-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="2ac08-108">この artilce の表示、作成、変更、またはネットワーク地域ルートを削除する手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="2ac08-109">ネットワーク地域のルート情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-109">View network region route information</span></span> 

<span data-ttu-id="2ac08-110">コール受付制御 (CAC) 構成内のすべての領域には、何らかの方法の他のすべての領域にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac08-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="2ac08-111">地域リンクでは、領域間の接続の帯域幅の制限を設定して、物理的なリンクを表すも、中に、ルートは、どのリンク先のパスの接続は別に 1 つの領域から走査されますを決定します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="2ac08-112">ビジネス サーバー管理シェルのビジネス サーバーのコントロール パネルまたは Skype の Skype で既存のネットワーク地域のルートを表示するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="2ac08-113">Skype のビジネス サーバーのコントロール パネルのネットワーク地域のルート情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="2ac08-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="2ac08-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ac08-115">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2ac08-116">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="2ac08-117">[**地域ルート**] ページで、表示する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="2ac08-118">のみ一度に 1 つの領域のルートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="2ac08-119">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2ac08-120">Windows PowerShell コマンドレットを使用してネットワーク地域のルート情報の表示</span><span class="sxs-lookup"><span data-stu-id="2ac08-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2ac08-121">Windows PowerShell と Get CsNetworkInterRegionRoute コマンドレットを使用してネットワーク地域のルート情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="2ac08-122">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="2ac08-123">ネットワーク地域のルート情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="2ac08-123">To view network region route information</span></span>

  - <span data-ttu-id="2ac08-124">すべてのネットワーク地域ルートに関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="2ac08-125">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="2ac08-126">詳細については、 [Get CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ac08-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="2ac08-127">作成またはネットワーク地域のルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-127">Create or modify network region routes</span></span>

<span data-ttu-id="2ac08-128">コール受付制御 (CAC) 構成内のすべての領域には、何らかの方法の他のすべての領域にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac08-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="2ac08-129">地域リンクでは、領域間の接続の帯域幅の制限を設定して、物理的なリンクを表すも、中に、ルートは、どのリンク先のパスの接続は別に 1 つの領域から走査されますを決定します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="2ac08-130">ビジネス サーバーのコントロール パネルの Skype を使用すると、ネットワーク地域のルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="2ac08-131">ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク地域ルートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="2ac08-132">作成するか、ネットワーク地域のルートを変更するには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="2ac08-133">ネットワーク地域ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="2ac08-133">To create a network region route</span></span>

1.  <span data-ttu-id="2ac08-134">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ac08-135">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2ac08-136">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="2ac08-137">[**地域ルート**] ページで [**新規**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="2ac08-138">**新しい領域のルート**の**名前**] フィールドの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="2ac08-139">この値は、ビジネスのサーバーの展開に、Skype 内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac08-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="2ac08-140">**ネットワークの領域\#1** 」ドロップ ダウン リスト、このルートによって接続される 2 つの領域のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="2ac08-141">**ネットワークの領域\#2** 」ドロップ ダウン リストで、このルートの他の地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="2ac08-142">この領域は、ネットワークの領域を選択した領域とは異なるである必要があります\#1 です。</span><span class="sxs-lookup"><span data-stu-id="2ac08-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="2ac08-143">地域リンクをルートに追加するのにには、**ネットワーク地域リンク**] リスト ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="2ac08-144">**地域リンク**] ページを表示するのには [**追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="2ac08-145">このルートに追加する地域リンクをクリックし、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="2ac08-146">個のリンクを追加またはリンクを選択し、リンクを削除する**削除**を] をクリックして [**追加**] ボタンをクリックし続けます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="2ac08-147">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="2ac08-148">ネットワーク地域ルートを変更するのには</span><span class="sxs-lookup"><span data-stu-id="2ac08-148">To modify a network region route</span></span>

1.  <span data-ttu-id="2ac08-149">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ac08-150">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2ac08-151">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="2ac08-152">[**地域ルート**] ページで、変更する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="2ac08-153">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="2ac08-154">**編集領域のルート**のこのルートによって結合された領域と、ルートに関連付けられている領域のリンクを変更できます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="2ac08-155">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="2ac08-156">既存のネットワーク地域のルートを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-156">Delete existing network region routes</span></span>

<span data-ttu-id="2ac08-157">コール受付制御 (CAC) 構成内のすべての領域には、何らかの方法の他のすべての領域にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac08-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="2ac08-158">地域リンクでは、領域間の接続の帯域幅の制限を設定して、物理的なリンクを表すも、中に、ルートは、どのリンク先のパスの接続は別に 1 つの領域から走査されますを決定します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="2ac08-159">ビジネス サーバーのコントロール パネルの Skype を使用すると、ネットワーク地域のルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="2ac08-160">ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク地域ルートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="2ac08-161">既存のネットワーク地域のルートを削除するのにには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="2ac08-162">ネットワーク地域ルートを削除するには</span><span class="sxs-lookup"><span data-stu-id="2ac08-162">To delete a network region route</span></span>

1.  <span data-ttu-id="2ac08-163">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ac08-164">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2ac08-165">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="2ac08-166">[**地域ルート**] ページで、削除する地域ルートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="2ac08-167">同時に 2 つ以上の地域ルートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2ac08-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="2ac08-168">これを行うには、CTRL キーを押し、CTRL キーを押しながら複数の地域のルートを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ac08-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="2ac08-169">または、地域のすべてのルートを選択するに **[すべて選択**] をクリックして **[編集**] メニューです。</span><span class="sxs-lookup"><span data-stu-id="2ac08-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="2ac08-170">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="2ac08-171">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac08-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="2ac08-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ac08-172">See Also</span></span>

[<span data-ttu-id="2ac08-173">Skype for Business Server でのネットワーク領域の管理</span><span class="sxs-lookup"><span data-stu-id="2ac08-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="2ac08-174">新しい-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="2ac08-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="2ac08-175">セット CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="2ac08-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="2ac08-176">削除 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="2ac08-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="2ac08-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="2ac08-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
