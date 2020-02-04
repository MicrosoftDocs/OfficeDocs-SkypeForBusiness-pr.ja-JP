---
title: 'Lync Server 2013: ネットワーク領域リンクを作成する'
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
ms.openlocfilehash: f40b9d569cbc571fe931a53b6f399b6273efd055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="d184b-102">Lync Server 2013 でネットワークの地域リンクを作成する</span><span class="sxs-lookup"><span data-stu-id="d184b-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d184b-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d184b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d184b-104">ネットワーク内の地域は、物理的な WAN 接続を経由してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="d184b-104">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="d184b-105">[*ネットワーク領域] リンク*は、通話受付制御 (CAC) 用に構成された2つの領域間のリンクを作成し、これらの地域間の音声とビデオのトラフィックの帯域幅の制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="d184b-105">A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="d184b-106">ネットワーク領域へのリンクの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d184b-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="d184b-107">新しい-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="d184b-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="d184b-108">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="d184b-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="d184b-109">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="d184b-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="d184b-110">CsNetworkRegionLink を削除する</span><span class="sxs-lookup"><span data-stu-id="d184b-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="d184b-111">トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。</span><span class="sxs-lookup"><span data-stu-id="d184b-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="d184b-112">計画ドキュメントの「 [Lync Server 2013 で通話受付制御の要件を収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)する」で説明されているように、これらの地域リンクはそれぞれ WAN の帯域幅によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="d184b-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="d184b-113">Lync Server 管理シェルを使用してネットワーク領域のリンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="d184b-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="d184b-114">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d184b-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d184b-115">New-CsNetworkRegionLink コマンドレットを実行して、地域リンクを作成し、適切な帯域幅ポリシー プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="d184b-115">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="d184b-116">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="d184b-116">For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="d184b-117">Lync Server コントロールパネルを使用してネットワーク領域のリンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="d184b-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d184b-118">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d184b-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d184b-119">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d184b-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="d184b-120">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d184b-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="d184b-121">[**地域リンク**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d184b-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="d184b-122">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d184b-122">Click **New**.</span></span>

5.  <span data-ttu-id="d184b-123">[**新しい地域リンク**] ページで、[**名前**] をクリックし、ネットワーク地域リンクの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d184b-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="d184b-124">[**ネットワーク領域\#1**] をクリックし、ネットワーク領域\#2 にリンクさせるリストのネットワーク領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d184b-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="d184b-125">[**ネットワーク領域\#2**] をクリックし、ネットワーク領域\#1 にリンクさせるリスト内のネットワーク領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d184b-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="d184b-126">オプションで、[**帯域幅ポリシー**] をクリックし、ネットワーク地域リンクに適用する帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d184b-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="d184b-127">帯域幅ポリシーは、ネットワーク地域リンクの帯域幅に制約があり、そのリンクのメディア トラフィックを CAC を使用して操作する場合に限り、適用します。</span><span class="sxs-lookup"><span data-stu-id="d184b-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="d184b-128">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d184b-128">Click **Commit**.</span></span>

10. <span data-ttu-id="d184b-129">他の地域についての設定でステップ 4 ～ 9 を繰り返し、ご使用のトポロジのネットワーク地域リンクの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="d184b-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
