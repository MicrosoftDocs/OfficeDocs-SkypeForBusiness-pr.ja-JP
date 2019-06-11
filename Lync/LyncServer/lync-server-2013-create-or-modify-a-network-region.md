---
title: 'Lync Server 2013: ネットワークの領域を作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a9b7a8adbb4ca4c0853aa7013662433701201d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="a8824-102">Lync Server 2013 でネットワークの領域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="a8824-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8824-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a8824-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a8824-104">*ネットワーク領域*とは、通話受付制御、E9-1、メディアバイパスの構成で使用されるネットワークハブまたはバックボーンのことです。</span><span class="sxs-lookup"><span data-stu-id="a8824-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="a8824-105">ネットワーク領域を作成または変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8824-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="a8824-106">たとえば、1つの音声機能のネットワーク領域を既に作成している場合は、新しいネットワークの領域を作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも、同じネットワーク領域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8824-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="a8824-107">ただし、機能固有の設定を適用するために、ネットワーク地域に関する既存の定義に変更を加える必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="a8824-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="a8824-108">たとえば、E9-1-1 用のネットワーク地域を作成し (この場合は関連付けられた中央サイトは必要ありません)、次に通話受付管理を展開する場合は、中央サイトを指定するためにネットワーク地域の定義を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8824-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="a8824-109">詳細については、「 [Lync Server 2013 で CAC のネットワーク領域を構成する](lync-server-2013-configure-network-regions-for-cac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8824-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8824-110">ネットワーク領域定義の機能固有の要件については、この機能の展開に関するトピックで説明されています。</span><span class="sxs-lookup"><span data-stu-id="a8824-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="a8824-111">ネットワーク領域の操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8824-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a8824-112">新しい CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a8824-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="a8824-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a8824-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="a8824-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a8824-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="a8824-115">CsNetworkRegion の削除</span><span class="sxs-lookup"><span data-stu-id="a8824-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="a8824-116">ネットワークの領域を作成する</span><span class="sxs-lookup"><span data-stu-id="a8824-116">Create a Network Region</span></span>

<span data-ttu-id="a8824-117">通話受付制御、E9、またはメディアバイパスで使用できるネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8824-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="a8824-118">Lync Server Management Shell を使用してネットワークの領域を作成するには</span><span class="sxs-lookup"><span data-stu-id="a8824-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="a8824-119">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a8824-120">New-CsNetworkRegion コマンドレットを実行してネットワーク地域を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8824-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="a8824-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a8824-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="a8824-122">この例では、サイト ID が CHICAGO の中央サイトに関連付けられた "NorthAmerica" というネットワーク地域を作成しました。</span><span class="sxs-lookup"><span data-stu-id="a8824-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="a8824-123">トポロジでのネットワーク地域の作成を完了するには、ネットワーク地域ごとの設定値を使用してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a8824-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="a8824-124">Lync Server コントロールパネルを使ってネットワークの領域を作成するには</span><span class="sxs-lookup"><span data-stu-id="a8824-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a8824-125">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a8824-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a8824-126">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a8824-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a8824-127">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a8824-128">[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-128">Click **Region**.</span></span>

4.  <span data-ttu-id="a8824-129">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-129">Click **New**.</span></span>

5.  <span data-ttu-id="a8824-130">[**新しい地域**] ページで、[**名前**] をクリックしてネットワーク地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8824-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="a8824-131">[**中央サイト**] をクリックし、リストにある中央サイトを 1 つクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="a8824-132">オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8824-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="a8824-133">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="a8824-134">トポロジでのネットワーク地域の作成を完了するには、その他の地域の設定値を使用してステップ 4 ～ 8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a8824-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="a8824-135">ネットワークの領域を変更する</span><span class="sxs-lookup"><span data-stu-id="a8824-135">Modify a Network Region</span></span>

<span data-ttu-id="a8824-136">既存のネットワーク領域の設定を変更して、新しい機能によって必要とされる基本領域の情報や変更に対応します。</span><span class="sxs-lookup"><span data-stu-id="a8824-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="a8824-137">Lync Server 管理シェルを使用してネットワークの領域を変更するには</span><span class="sxs-lookup"><span data-stu-id="a8824-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="a8824-138">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a8824-139">Set-CsNetworkRegion コマンドレットを実行して、既存のネットワーク地域を変更します。</span><span class="sxs-lookup"><span data-stu-id="a8824-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="a8824-140">例:</span><span class="sxs-lookup"><span data-stu-id="a8824-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="a8824-p103">この例では、説明を変更することにより、(このトピックの前半で説明した手順を使用して作成した) "NorthAmerica" という既存のネットワーク地域に変更を加えました。"NorthAmerica" 地域の説明があった場合、このコマンドはここでの値で地域の説明を上書きします。説明が設定されていない場合、このコマンドは説明を設定します。</span><span class="sxs-lookup"><span data-stu-id="a8824-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="a8824-143">その他のネットワーク地域を変更するには、その他の地域の設定値を使用してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a8824-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="a8824-144">Lync Server コントロールパネルを使用してネットワークの領域を変更するには</span><span class="sxs-lookup"><span data-stu-id="a8824-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a8824-145">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a8824-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a8824-146">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a8824-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a8824-147">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a8824-148">[**地域**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="a8824-149">表で、変更するネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="a8824-150">[**編集**] をクリックして、[**詳細の表示...**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="a8824-151">[**地域の編集**] ページで、このネットワーク地域の設定の値を必要に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="a8824-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="a8824-152">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8824-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="a8824-153">ネットワーク地域の変更を完了するには、他の地域の設定値を使用してステップ 4 ～ 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a8824-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

