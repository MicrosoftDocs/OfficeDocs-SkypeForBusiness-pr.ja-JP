---
title: 'Lync Server 2013: ネットワーク地域を作成または変更する'
description: 'Lync Server 2013: ネットワーク地域を作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a149a668f64df804d2631243d9bb63401bd8a284
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562233"
---
# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="66084-103">Lync Server 2013 でネットワーク地域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="66084-103">Create or modify a network region in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66084-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="66084-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="66084-105">*ネットワーク地域* は、通話受付管理、E9-1-1、およびメディアバイパスの構成で使用されるネットワークハブまたはバックボーンです。</span><span class="sxs-lookup"><span data-stu-id="66084-105">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="66084-106">ネットワーク地域を作成または変更するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="66084-106">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="66084-107">たとえば、1つの音声機能に対してネットワーク地域が既に作成されている場合、新しいネットワーク地域を作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも同じネットワーク地域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="66084-107">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="66084-108">ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="66084-108">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="66084-109">たとえば、E9-1-1 用のネットワーク地域を作成していて、通話受付管理を展開する場合は、ネットワーク地域定義を変更して中央サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66084-109">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="66084-110">詳細については、「 [Lync Server 2013 での CAC のネットワーク地域の構成](lync-server-2013-configure-network-regions-for-cac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66084-110">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66084-111">ネットワーク地域の定義で機能固有の要件については、すべてその機能の「展開」のトピックで説明されています。</span><span class="sxs-lookup"><span data-stu-id="66084-111">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="66084-112">ネットワーク地域の使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66084-112">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="66084-113">新しい-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="66084-113">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="66084-114">取得-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="66084-114">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="66084-115">設定-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="66084-115">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="66084-116">-CsNetworkRegion の削除</span><span class="sxs-lookup"><span data-stu-id="66084-116">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="66084-117">ネットワーク地域の作成</span><span class="sxs-lookup"><span data-stu-id="66084-117">Create a Network Region</span></span>

<span data-ttu-id="66084-118">通話受付管理、E9-1-1、またはメディア バイパスで使用できるネットワーク地域を作成します。</span><span class="sxs-lookup"><span data-stu-id="66084-118">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="66084-119">Lync Server 管理シェルを使用してネットワーク地域を作成するには</span><span class="sxs-lookup"><span data-stu-id="66084-119">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="66084-120">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="66084-121">New-CsNetworkRegion コマンドレットを実行してネットワーク地域を作成します。</span><span class="sxs-lookup"><span data-stu-id="66084-121">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="66084-122">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="66084-122">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="66084-123">この例では、サイト ID が CHICAGO の中央サイトと関連付けられた "NorthAmerica" というネットワーク地域を作成しました。</span><span class="sxs-lookup"><span data-stu-id="66084-123">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="66084-124">トポロジでのネットワーク地域の作成を完了するには、ネットワーク地域ごとの設定値を使用してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="66084-124">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="66084-125">Lync Server コントロールパネルを使用してネットワーク地域を作成するには</span><span class="sxs-lookup"><span data-stu-id="66084-125">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="66084-126">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="66084-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="66084-127">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66084-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="66084-128">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-128">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="66084-129">[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-129">Click **Region**.</span></span>

4.  <span data-ttu-id="66084-130">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-130">Click **New**.</span></span>

5.  <span data-ttu-id="66084-131">[**新しい地域**] ページで、[**名前**] をクリックしてネットワーク地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="66084-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="66084-132">[**中央サイト**] をクリックし、リストにある中央サイトを 1 つクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-132">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="66084-133">オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="66084-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="66084-134">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-134">Click **Commit**.</span></span>

9.  <span data-ttu-id="66084-135">トポロジでのネットワーク地域の作成を完了するには、その他の地域の設定値を使用してステップ 4 ～ 8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="66084-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="66084-136">ネットワーク地域の変更</span><span class="sxs-lookup"><span data-stu-id="66084-136">Modify a Network Region</span></span>

<span data-ttu-id="66084-137">既存のネットワーク地域の設定を変更して、基本地域情報に対する変更、または新しい機能で必要な変更に対応します。</span><span class="sxs-lookup"><span data-stu-id="66084-137">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="66084-138">Lync Server 管理シェルを使用してネットワーク地域を変更するには</span><span class="sxs-lookup"><span data-stu-id="66084-138">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="66084-139">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="66084-140">Set-CsNetworkRegion コマンドレットを実行して、既存のネットワーク地域を変更します。</span><span class="sxs-lookup"><span data-stu-id="66084-140">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="66084-141">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="66084-141">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="66084-p103">この例では、説明を変更することにより、(このトピックの前半で説明した手順を使用して作成した) "NorthAmerica" という既存のネットワーク地域に変更を加えました。 "NorthAmerica" 地域の説明があった場合、このコマンドはここでの値で地域の説明を上書きします。説明が設定されていない場合、このコマンドは説明を設定します。</span><span class="sxs-lookup"><span data-stu-id="66084-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="66084-144">その他のネットワーク地域を変更するには、その他の地域の設定値を使用してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="66084-144">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="66084-145">Lync Server コントロールパネルを使用してネットワーク地域を変更するには</span><span class="sxs-lookup"><span data-stu-id="66084-145">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="66084-146">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="66084-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="66084-147">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66084-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="66084-148">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-148">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="66084-149">[**地域**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-149">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="66084-150">表で、変更するネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-150">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="66084-151">[**編集**] をクリックして、[**詳細の表示...**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-151">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="66084-152">[**地域の編集**] ページで、このネットワーク地域の設定の値を必要に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="66084-152">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="66084-153">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66084-153">Click **Commit**.</span></span>

8.  <span data-ttu-id="66084-154">ネットワーク地域の変更を完了するには、他の地域の設定値を使用してステップ 4 ～ 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="66084-154">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

