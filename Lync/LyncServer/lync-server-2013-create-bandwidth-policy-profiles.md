---
title: 'Lync Server 2013: 帯域幅ポリシープロファイルの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 579bd9a2131a177fbece81bdbceec343e73edc89
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="52b20-102">Lync Server 2013 での帯域幅ポリシープロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="52b20-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52b20-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="52b20-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="52b20-p101">*帯域幅ポリシー*は、リアルタイムのオーディオおよびビデオのモダリティについて、帯域幅使用量の制限を定義します。 帯域幅ポリシーは*帯域幅ポリシーのプロファイル*に適用され、帯域幅ポリシーのプロファイルは通話受付管理のために複数のネットワーク サイトに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="52b20-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="52b20-106">CAC の展開にどの程度の帯域幅制限を設定するかに関するガイドラインについては、「計画」のドキュメントの「 [Lync Server 2013 での通話受付管理の要件の定義](lync-server-2013-defining-your-requirements-for-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52b20-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="52b20-107">帯域幅ポリシーおよびポリシープロファイルの使用の詳細については、「Lync Server Management Shell」のドキュメントの次のコマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="52b20-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="52b20-108">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="52b20-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="52b20-109">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="52b20-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="52b20-110">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="52b20-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="52b20-111">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="52b20-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="52b20-112">次の手順で作成されるポリシーの例は、オーディオ トラフィック全体、個々のオーディオ セッション、ビデオ トラフィック全体、および個々のビデオ セッションに制限を設けます。</span><span class="sxs-lookup"><span data-stu-id="52b20-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="52b20-113">たとえば、5Mb\_のリンク帯域幅ポリシープロファイルは次の制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="52b20-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="52b20-114">オーディオ リミット: 2,000 kbps</span><span class="sxs-lookup"><span data-stu-id="52b20-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="52b20-115">オーディオ セッション リミット: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="52b20-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="52b20-116">ビデオ リミット: 1,400 kbps</span><span class="sxs-lookup"><span data-stu-id="52b20-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="52b20-117">ビデオ セッション リミット: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="52b20-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="52b20-p103">オーディオ セッション リミットの最小値は 40 kbps です。 ビデオ セッション リミットの最小値は 100 kbps です。</span><span class="sxs-lookup"><span data-stu-id="52b20-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="52b20-120">管理シェルを使用して帯域幅ポリシー プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="52b20-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="52b20-121">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="52b20-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="52b20-p104">作成する帯域幅ポリシーのプロファイルごとに、New-CsNetworkBandwidthPolicyProfile コマンドレットを実行します。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="52b20-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="52b20-124">Lync Server コントロール パネルを使用して帯域幅ポリシーのプロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="52b20-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="52b20-125">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52b20-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="52b20-126">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52b20-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="52b20-127">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52b20-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="52b20-128">[**ポリシーのプロファイル**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52b20-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="52b20-129">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52b20-129">Click **New**.</span></span>

5.  <span data-ttu-id="52b20-130">[**新しいポリシーのプロファイル**] ページで、[**名前**] をクリックし、帯域幅ポリシー プロファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="52b20-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="52b20-131">[**オーディオ リミット**] をクリックし、すべてのオーディオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="52b20-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="52b20-132">[**オーディオ セッション リミット**] をクリックし、個々のオーディオ セッションに対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="52b20-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="52b20-133">[**ビデオ リミット**] をクリックし、すべてのビデオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="52b20-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="52b20-134">[**ビデオ セッション リミット**] をクリックし、個々のビデオ セッションに対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="52b20-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="52b20-135">必要に応じて、[**説明**] をクリックし、この帯域幅ポリシーのプロファイルを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="52b20-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="52b20-136">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52b20-136">Click **Commit**.</span></span>

12. <span data-ttu-id="52b20-137">トポロジの帯域幅ポリシーのプロファイル作成を完了するには、ステップ 4 ～ 11 を繰り返して、他の帯域幅ポリシーのプロファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="52b20-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

