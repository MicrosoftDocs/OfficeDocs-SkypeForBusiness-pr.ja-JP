---
title: 'Lync Server 2013: ネットワーク地域リンクの作成'
description: 'Lync Server 2013: ネットワーク地域リンクを作成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6510d252ac1534a3a8e9f14d56acc8d0d8b60a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553943"
---
# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="740dc-103">Lync Server 2013 でのネットワーク地域リンクの作成</span><span class="sxs-lookup"><span data-stu-id="740dc-103">Create network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="740dc-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="740dc-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="740dc-p101">ネットワーク内の地域は、物理的な WAN 接続を経由してリンクされます。 *ネットワーク地域リンク*は、通話受付管理 (CAC) 用に構成された 2 つの地域間のリンクを作成し、これらの地域間の音声トラフィックとビデオ トラフィックに帯域幅制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="740dc-p101">Regions within a network are linked through physical WAN connectivity. A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="740dc-107">ネットワーク地域リンクの使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="740dc-107">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="740dc-108">新しい-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="740dc-108">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="740dc-109">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="740dc-109">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="740dc-110">設定-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="740dc-110">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="740dc-111">-CsNetworkRegionLink の削除</span><span class="sxs-lookup"><span data-stu-id="740dc-111">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="740dc-112">トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。</span><span class="sxs-lookup"><span data-stu-id="740dc-112">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="740dc-113">これらの地域リンクは、「計画」のドキュメントの「地域リンクの帯域幅情報の表」に記載されているように、WAN 帯域幅によって制限されます。「計画」のドキュメントの「 [Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="740dc-113">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="740dc-114">Lync Server 管理シェルを使用して、ネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="740dc-114">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="740dc-115">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="740dc-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="740dc-p103">New-CsNetworkRegionLink コマンドレットを実行して、地域リンクを作成し、適切な帯域幅ポリシー プロファイルを適用します。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="740dc-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="740dc-118">Lync Server コントロール パネルを使用して、ネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="740dc-118">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="740dc-119">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="740dc-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="740dc-120">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="740dc-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="740dc-121">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="740dc-121">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="740dc-122">[**地域リンク**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="740dc-122">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="740dc-123">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="740dc-123">Click **New**.</span></span>

5.  <span data-ttu-id="740dc-124">[**新しい地域リンク**] ページで、[**名前**] をクリックし、ネットワーク地域リンクの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="740dc-124">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="740dc-125">[ **ネットワーク地域 \# 1**] をクリックし、一覧でネットワーク地域2にリンクするネットワーク地域をクリックし \# ます。</span><span class="sxs-lookup"><span data-stu-id="740dc-125">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="740dc-126">[ **ネットワーク地域 \# 2**] をクリックし、一覧でネットワーク地域1にリンクするネットワーク地域をクリックし \# ます。</span><span class="sxs-lookup"><span data-stu-id="740dc-126">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="740dc-127">オプションで、[**帯域幅ポリシー**] をクリックし、ネットワーク地域リンクに適用する帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="740dc-127">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="740dc-128">帯域幅ポリシーは、ネットワーク地域リンクの帯域幅に制約があり、そのリンクのメディア トラフィックを CAC を使用して操作する場合に限り、適用します。</span><span class="sxs-lookup"><span data-stu-id="740dc-128">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="740dc-129">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="740dc-129">Click **Commit**.</span></span>

10. <span data-ttu-id="740dc-130">他の地域についての設定を二間してステップ 4 ～ 9 を繰り返し、ご使用のトポロジのネットワーク地域リンクの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="740dc-130">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
