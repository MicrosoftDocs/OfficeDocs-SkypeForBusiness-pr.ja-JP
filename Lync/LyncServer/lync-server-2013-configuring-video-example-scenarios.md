---
title: 'Lync Server 2013: ビデオの例のシナリオを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="2f2c0-102">ビデオの構成 Lync Server 2013 のシナリオの例</span><span class="sxs-lookup"><span data-stu-id="2f2c0-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f2c0-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2f2c0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2f2c0-104">Lync 2013 では、1920 x 1080 full definition (HD) ビデオとギャラリービューのビデオをサポートする新しいビデオ機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="2f2c0-105">顧客データに基づく測定値は、一般的なビデオの帯域幅が Lync 2010 に比べてわずかに増加していますが、フル HD のサポートにより、ビデオストリームの最大帯域幅が増加していることを示しています (詳細については、「メディアトラフィックネットワークの使用状況」セクション[を参照してください)。Lync Server 2013 でのメディアトラフィックのネットワーク帯域幅要件](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="2f2c0-106">そのため、管理者は、特定のユーザー (ネットワーク容量が少ない支店のユーザーなど) のビデオ帯域幅を制限したり、他のユーザー (エグゼクティブなど) に最適なビデオ品質を確保したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="2f2c0-107">次の表は、さまざまなネットワーク容量に対応したビデオを構成するための推奨される設定の一覧です。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="2f2c0-108">これらの設定により、一部のユーザーシナリオでは、高解像度のビデオの送受信が制限されます (右端の列を参照)。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="2f2c0-109">[最小] 設定では、ネットワーク帯域幅の上限が最大になったため、ギャラリーのビデオは利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="2f2c0-110">推奨されるビデオ設定</span><span class="sxs-lookup"><span data-stu-id="2f2c0-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="2f2c0-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="2f2c0-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="2f2c0-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="2f2c0-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="2f2c0-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="2f2c0-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="2f2c0-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="2f2c0-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="2f2c0-115">高品質ビデオにはビデオ解像度が期待されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f2c0-116">よく</span><span class="sxs-lookup"><span data-stu-id="2f2c0-116">Best</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-117">True</span><span class="sxs-lookup"><span data-stu-id="2f2c0-117">True</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-118">True</span><span class="sxs-lookup"><span data-stu-id="2f2c0-118">True</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-119">8000</span><span class="sxs-lookup"><span data-stu-id="2f2c0-119">8000</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-120">8000</span><span class="sxs-lookup"><span data-stu-id="2f2c0-120">8000</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-121">ピアツーピア: 最大 1920 x 1080 のビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="2f2c0-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="2f2c0-122">ギャラリービュー: 最大 2 1920 x 1080 のビデオまたは複数の小さな解像度のビデオ</span><span class="sxs-lookup"><span data-stu-id="2f2c0-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f2c0-123">Good</span><span class="sxs-lookup"><span data-stu-id="2f2c0-123">Good</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-124">True</span><span class="sxs-lookup"><span data-stu-id="2f2c0-124">True</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-125">True</span><span class="sxs-lookup"><span data-stu-id="2f2c0-125">True</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-126">2500</span><span class="sxs-lookup"><span data-stu-id="2f2c0-126">2500</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-127">2500</span><span class="sxs-lookup"><span data-stu-id="2f2c0-127">2500</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-128">ピアツーピア: 最大 1280 x 720 のビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="2f2c0-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="2f2c0-129">ギャラリービュー: 最大 5 640 x 360 解像度のビデオ</span><span class="sxs-lookup"><span data-stu-id="2f2c0-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f2c0-130">中</span><span class="sxs-lookup"><span data-stu-id="2f2c0-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-131">True</span><span class="sxs-lookup"><span data-stu-id="2f2c0-131">True</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-132">True</span><span class="sxs-lookup"><span data-stu-id="2f2c0-132">True</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-133">1000</span><span class="sxs-lookup"><span data-stu-id="2f2c0-133">1000</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-134">1000</span><span class="sxs-lookup"><span data-stu-id="2f2c0-134">1000</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-135">ピアツーピア: 最大 960 x 540 のビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="2f2c0-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="2f2c0-136">ギャラリービュー: 最大 5 424 x 240 解像度のビデオ</span><span class="sxs-lookup"><span data-stu-id="2f2c0-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f2c0-137">最低</span><span class="sxs-lookup"><span data-stu-id="2f2c0-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-138">True</span><span class="sxs-lookup"><span data-stu-id="2f2c0-138">True</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-139">False</span><span class="sxs-lookup"><span data-stu-id="2f2c0-139">False</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-140">350</span><span class="sxs-lookup"><span data-stu-id="2f2c0-140">350</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-141">350</span><span class="sxs-lookup"><span data-stu-id="2f2c0-141">350</span></span></p></td>
<td><p><span data-ttu-id="2f2c0-142">ピアツーピア: 最大 424 x 240 のビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="2f2c0-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="2f2c0-143">ギャラリービュー: 使用できません</span><span class="sxs-lookup"><span data-stu-id="2f2c0-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2f2c0-144">上の表の情報を使用して、組織内の一部のユーザーにビデオ会議機能を追加し、他のユーザーには別のビデオ解像度を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="2f2c0-145">次の例では、管理者が、最高のビデオ品質で、[エグゼクティブ] のみで利用可能な新しいビデオ機能をロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="2f2c0-146">ネットワーク容量が少ないリモート支店の従業員については、上記の表の最小設定のみが展開されます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="2f2c0-147">その他のすべての従業員については、上記の表の "良好" 設定が展開されます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="2f2c0-148">新しい機能を役員にロールアウトするために、管理者は ExecutiveVideo という名前の会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="2f2c0-149">この会議ポリシーには、次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="2f2c0-150">VideoBitRateKB が 8000 Kbps に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="2f2c0-151">TotalReceiveVideoBitRateKB が 8000 Kbps に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="2f2c0-152">AllowMultiview が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="2f2c0-153">EnableMultiviewJoin が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="2f2c0-154">支社の従業員の場合、管理者は BranchOfficeVideo という名前の会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="2f2c0-155">この会議ポリシーには、次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="2f2c0-156">VideoBitRateKB が 350 Kbps に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="2f2c0-157">TotalReceiveVideoBitRateKB が 350 Kbps に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="2f2c0-158">AllowMultiview が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="2f2c0-159">EnableMultiviewJoin が False に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="2f2c0-160">他のすべての従業員の場合、管理者は StandardVideo という名前の会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="2f2c0-161">この会議ポリシーには、次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="2f2c0-162">VideoBitRateKB が 2500 Kbps に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="2f2c0-163">TotalReceiveVideoBitRateKB が 2500 Kbps に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="2f2c0-164">AllowMultiview が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="2f2c0-165">EnableMultiviewJoin が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="2f2c0-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="2f2c0-166">管理者は、次のようにして会議ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="2f2c0-167">ExecutiveVideo 会議のポリシーが役員に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="2f2c0-168">BranchOfficeVideo 会議ポリシーは、支社のすべての従業員に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="2f2c0-169">標準ビデオ会議ポリシーは、他のすべての従業員に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="2f2c0-170">これらの会議ポリシーを割り当てると、次のユーザーエクスペリエンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="2f2c0-171">任意のユーザーサポートギャラリービューによって開催されたすべての会議。ただし、ブランチオフィスの従業員はギャラリービューを表示できません。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="2f2c0-172">2パーティまたはマルチパーティの会議では、役員は、1920 x 1080 のフル HD ビデオ (ハードウェアとネットワークリンクがサポートされている場合) を送信できます。また、他の参加者のクライアントがサポートしている 1920 x 1080 フル HD ビデオも受信できます。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="2f2c0-173">エグゼクティブ以外の従業員は、2パーティまたはマルチパーティの会議では、役員よりも低い解像度で表示されますが、解決策は引き続き有効です。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="2f2c0-174">Lync が既定のビデオウィンドウサイズで表示されている場合は、支社にいる従業員は、2パーティーの通話で優れたビデオ品質を得ることができます。ただし、Lync ウィンドウが全画面に最大化されている場合、ビデオの解像度は増加しません。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="2f2c0-175">マルチパーティ会議の場合、支店の従業員は1つのアクティブなビデオのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="2f2c0-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

