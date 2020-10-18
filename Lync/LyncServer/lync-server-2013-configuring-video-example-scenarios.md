---
title: 'Lync Server 2013: ビデオサンプルシナリオの構成'
description: 'Lync Server 2013: ビデオサンプルシナリオの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625899887926de9afe2e6ff94df70ab725c0190a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575143"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="9a5a3-103">Lync Server 2013 のビデオサンプルシナリオの構成</span><span class="sxs-lookup"><span data-stu-id="9a5a3-103">Configuring video example scenarios for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a5a3-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9a5a3-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9a5a3-105">Lync 2013 は、1920 x 1080 完全高品位 (HD) ビデオおよびギャラリービューのビデオをサポートする新しいビデオ機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-105">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="9a5a3-106">お客様のデータに基づく測定値は、一般的なビデオ帯域幅が Lync 2010 に比べてわずかに増加しましたが、フル HD サポートのために最大ビデオストリーム帯域幅が増加しています。詳細については、「 [media traffic for media トラッフィック In Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)」の「Media Traffic network Usage」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-106">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="9a5a3-107">そのため、管理者は特定のユーザー (ネットワークの容量が少ない支社のユーザーなど) のビデオ帯域幅を制限したり、他のユーザー (エグゼクティブなど) に最適なビデオ品質を確保するために役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-107">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="9a5a3-108">次の表に、さまざまなネットワーク容量に対してビデオを構成する際に推奨される設定の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-108">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="9a5a3-109">これらの設定により、一部のユーザーシナリオでは、より高解像度のビデオを送受信することができなくなります (右端の列を参照)。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-109">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="9a5a3-110">最小値を設定すると、最大受信ネットワーク帯域幅が少ないため、ギャラリーのビデオが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-110">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="9a5a3-111">推奨されるビデオ設定</span><span class="sxs-lookup"><span data-stu-id="9a5a3-111">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="9a5a3-112">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="9a5a3-112">AllowMultiView</span></span></th>
<th><span data-ttu-id="9a5a3-113">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="9a5a3-113">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="9a5a3-114">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="9a5a3-114">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="9a5a3-115">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="9a5a3-115">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="9a5a3-116">良好な品質のビデオに必要なビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="9a5a3-116">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a5a3-117">高</span><span class="sxs-lookup"><span data-stu-id="9a5a3-117">Best</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-118">True</span><span class="sxs-lookup"><span data-stu-id="9a5a3-118">True</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-119">True</span><span class="sxs-lookup"><span data-stu-id="9a5a3-119">True</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-120">8000</span><span class="sxs-lookup"><span data-stu-id="9a5a3-120">8000</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-121">8000</span><span class="sxs-lookup"><span data-stu-id="9a5a3-121">8000</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-122">ピアツーピア: 最大 1920 x 1080 ビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="9a5a3-122">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="9a5a3-123">ギャラリービュー: 最大 2 1920 x 1080 ビデオまたは複数の解像度のビデオ</span><span class="sxs-lookup"><span data-stu-id="9a5a3-123">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a5a3-124">Good</span><span class="sxs-lookup"><span data-stu-id="9a5a3-124">Good</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-125">True</span><span class="sxs-lookup"><span data-stu-id="9a5a3-125">True</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-126">True</span><span class="sxs-lookup"><span data-stu-id="9a5a3-126">True</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-127">2500</span><span class="sxs-lookup"><span data-stu-id="9a5a3-127">2500</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-128">2500</span><span class="sxs-lookup"><span data-stu-id="9a5a3-128">2500</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-129">ピアツーピア: 最大 1280 x 720 ビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="9a5a3-129">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="9a5a3-130">ギャラリービュー: 最大 5 640 x 360 解像度のビデオ</span><span class="sxs-lookup"><span data-stu-id="9a5a3-130">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a5a3-131">中</span><span class="sxs-lookup"><span data-stu-id="9a5a3-131">Medium</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-132">True</span><span class="sxs-lookup"><span data-stu-id="9a5a3-132">True</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-133">True</span><span class="sxs-lookup"><span data-stu-id="9a5a3-133">True</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-134">1000</span><span class="sxs-lookup"><span data-stu-id="9a5a3-134">1000</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-135">1000</span><span class="sxs-lookup"><span data-stu-id="9a5a3-135">1000</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-136">ピアツーピア: 最大 960 x 540 ビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="9a5a3-136">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="9a5a3-137">ギャラリービュー: 最大 5 424 x 240 解像度のビデオ</span><span class="sxs-lookup"><span data-stu-id="9a5a3-137">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a5a3-138">最小値</span><span class="sxs-lookup"><span data-stu-id="9a5a3-138">Minimum</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-139">True</span><span class="sxs-lookup"><span data-stu-id="9a5a3-139">True</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-140">False</span><span class="sxs-lookup"><span data-stu-id="9a5a3-140">False</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-141">350</span><span class="sxs-lookup"><span data-stu-id="9a5a3-141">350</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-142">350</span><span class="sxs-lookup"><span data-stu-id="9a5a3-142">350</span></span></p></td>
<td><p><span data-ttu-id="9a5a3-143">ピアツーピア: 最大 424 x 240 ビデオ解像度</span><span class="sxs-lookup"><span data-stu-id="9a5a3-143">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="9a5a3-144">ギャラリービュー: 使用不可</span><span class="sxs-lookup"><span data-stu-id="9a5a3-144">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a5a3-145">前の表に記載されている情報を使用して、新しい HD ビデオおよびギャラリービューのビデオ会議機能を組織の一部のユーザーに展開する一方で、他のユーザーがさまざまなビデオ解像度を使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-145">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="9a5a3-146">次の例では、管理者は、エグゼクティブのみが利用できる最高のビデオ品質で新しいビデオ機能をロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-146">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="9a5a3-147">ネットワークの容量が少ないリモートブランチオフィスの従業員の場合、上記の表の最小設定のみが展開されます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-147">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="9a5a3-148">他のすべての従業員の場合、上記の表にある "Good" 設定が展開されます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-148">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="9a5a3-149">エグゼクティブに新機能をロールアウトするために、管理者は ExecutiveVideo という名前の会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-149">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="9a5a3-150">この会議ポリシーには、次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-150">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="9a5a3-151">VideoBitRateKB は 8000 Kbps に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-151">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="9a5a3-152">TotalReceiveVideoBitRateKB は 8000 Kbps に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-152">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="9a5a3-153">AllowMultiview が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="9a5a3-153">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="9a5a3-154">EnableMultiviewJoin が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="9a5a3-154">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="9a5a3-155">ブランチオフィスの従業員の場合、管理者は BranchOfficeVideo という名前の会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-155">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="9a5a3-156">この会議ポリシーには、次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-156">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="9a5a3-157">VideoBitRateKB は 350 Kbps に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-157">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="9a5a3-158">TotalReceiveVideoBitRateKB は 350 Kbps に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-158">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="9a5a3-159">AllowMultiview が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="9a5a3-159">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="9a5a3-160">EnableMultiviewJoin が False に設定されている</span><span class="sxs-lookup"><span data-stu-id="9a5a3-160">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="9a5a3-161">他のすべての従業員の場合、管理者は StandardVideo という名前の会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-161">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="9a5a3-162">この会議ポリシーには、次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-162">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="9a5a3-163">VideoBitRateKB は 2500 Kbps に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-163">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="9a5a3-164">TotalReceiveVideoBitRateKB は 2500 Kbps に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-164">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="9a5a3-165">AllowMultiview が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="9a5a3-165">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="9a5a3-166">EnableMultiviewJoin が True に設定されている</span><span class="sxs-lookup"><span data-stu-id="9a5a3-166">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="9a5a3-167">管理者は、次のように会議ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-167">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="9a5a3-168">ExecutiveVideo 会議ポリシーが役職者に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-168">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="9a5a3-169">BranchOfficeVideo 会議ポリシーは、ブランチオフィスのすべての従業員に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-169">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="9a5a3-170">StandardVideo 会議ポリシーは、他のすべての従業員に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-170">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="9a5a3-171">これらの会議ポリシーの割り当てによって、次のようなユーザーの環境が発生します。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-171">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="9a5a3-172">任意のユーザーによって開催されたすべての会議はギャラリービューをサポートしますが、ブランチオフィスの従業員はギャラリービューを利用できません。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-172">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="9a5a3-173">2パーティまたはマルチパーティの会議の場合、エグゼクティブは 1920 x 1080 フル HD ビデオを送信できます。ハードウェアとネットワークリンクがサポートしている場合は、他の参加者のクライアントがサポートしている 1920 x 1080 フル HD ビデオを受信できます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-173">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="9a5a3-174">エグゼクティブではない従業員は、2者またはマルチパーティの会議では、エグゼクティブよりも低い解像度で表示されますが、適切な解決策を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-174">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="9a5a3-175">Lync が既定のビデオウィンドウサイズを表示すると、ブランチオフィスの従業員は、2者間通話で優れたビデオ品質を得ることができます。ただし、Lync ウィンドウが全画面表示に最大化されている場合は、ビデオ解像度は上がりません。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-175">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="9a5a3-176">マルチパーティ会議では、ブランチオフィスの従業員には1つのアクティブなビデオのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a5a3-176">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

