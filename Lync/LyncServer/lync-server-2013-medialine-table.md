---
title: 'Lync Server 2013: MediaLine テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="4ffae-102">Lync Server 2013 の MediaLine テーブル</span><span class="sxs-lookup"><span data-stu-id="4ffae-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ffae-103">_**最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="4ffae-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="4ffae-104">各レコードは1つのメディアラインを表します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-104">Each record represents one media line.</span></span> <span data-ttu-id="4ffae-105">(1 つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ffae-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="4ffae-106">1つのオーディオとビデオ (A/V) セッションには通常、1つのオーディオメディアラインと1つのビデオメディアラインが含まれていますが、会議デバイスが使用されている場合や、[ギャラリー] ビューを使用している場合は、2つのビデオメディア線が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4ffae-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ffae-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4ffae-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4ffae-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4ffae-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4ffae-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ffae-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4ffae-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4ffae-114"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4ffae-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-116">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-116">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-117">Primary</span><span class="sxs-lookup"><span data-stu-id="4ffae-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="4ffae-118"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4ffae-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ffae-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ffae-121">Primary</span><span class="sxs-lookup"><span data-stu-id="4ffae-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="4ffae-122">0はメインオーディオ、1はメインビデオ、2はパノラマビデオ、3はアプリケーション/デスクトップ共有です。</span><span class="sxs-lookup"><span data-stu-id="4ffae-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="4ffae-123">このラベルは、1つのセッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffae-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ffae-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-126">この列は存在しますが、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="4ffae-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4ffae-127">メディアラインに使用される接続に関する情報は、CallerConnectivityICE 列と CalleeConnectivityICE 列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="4ffae-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-129">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-130">「Bits フラグ」で説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="4ffae-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="4ffae-131">詳細については、「ダウンロード可能な<em>エクスペリエンス監視サーバープロトコルの仕様</em>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffae-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-133">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-134">CallerIceWarningFlags と同じですが、呼び出し先側でも同じです。</span><span class="sxs-lookup"><span data-stu-id="4ffae-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="4ffae-135">詳細については、「ダウンロード可能な<em>エクスペリエンス監視サーバープロトコルの仕様</em>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffae-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-136"><strong>セキュリティ</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ffae-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-138">使用されているセキュリティプロファイル。</span><span class="sxs-lookup"><span data-stu-id="4ffae-138">The security profile in use.</span></span> <span data-ttu-id="4ffae-139">0は NONE、1は SRTP、2は V1 です。</span><span class="sxs-lookup"><span data-stu-id="4ffae-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ffae-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-142">0は UDP、1は TCP です。</span><span class="sxs-lookup"><span data-stu-id="4ffae-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-144">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-144">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-145">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-146">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-146">IP Address of the caller.</span></span> <span data-ttu-id="4ffae-147">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffae-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-149">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-150">発信者によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="4ffae-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-152">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-152">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-153"> 外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-154">発信者のサブネット。</span><span class="sxs-lookup"><span data-stu-id="4ffae-154">The subnet of the caller.</span></span> <span data-ttu-id="4ffae-155">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffae-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-157">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-158">1: 発信者がエンタープライズネットワーク内にあることを示します。0は、呼び出し元がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-160">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-160">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-161">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-162">発信者の mac アドレス。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="4ffae-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-164">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-164">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-165">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-166">発信者が使用した Lync Server A/V Edge サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="4ffae-167">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffae-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-169">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-170">発信者によって、A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="4ffae-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-172">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-172">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-173">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-174">発信者によって使用されるデバイスをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="4ffae-174">Capture device used by the caller.</span></span> <span data-ttu-id="4ffae-175"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4ffae-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-177">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-177">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-178">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-179">発信者によって使われるレンダリングデバイス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-179">Render device used by caller.</span></span> <span data-ttu-id="4ffae-180"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4ffae-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-182">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-182">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-183">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-184">発信者のキャプチャデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4ffae-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-186">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-186">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-187">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-188">発信者のレンダリングデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4ffae-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ffae-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ffae-191">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-192">発信者がネットワークに接続した方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="4ffae-193">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="4ffae-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="4ffae-194">一般的な値は、有線接続の場合は0、WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="4ffae-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-196">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-196">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-197">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-198">ワイヤレスが使用されている場合は、発信者の BSSID。</span><span class="sxs-lookup"><span data-stu-id="4ffae-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="4ffae-199"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="4ffae-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-201">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-202">発信者のリンク。</span><span class="sxs-lookup"><span data-stu-id="4ffae-202">The caller's link.</span></span> <span data-ttu-id="4ffae-203">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="4ffae-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-205">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4ffae-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-206">発信者のエンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="4ffae-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-208">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-208">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-209">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-210">通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-210">IP Address of the call receiver.</span></span> <span data-ttu-id="4ffae-211">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffae-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-213">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-214">通話レシーバーで使用されているポート。</span><span class="sxs-lookup"><span data-stu-id="4ffae-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-216">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-216">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-217">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-218">呼び出し先のサブネット。</span><span class="sxs-lookup"><span data-stu-id="4ffae-218">Subnet of callee.</span></span> <span data-ttu-id="4ffae-219">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffae-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-221">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-222">1: 通話受信者が企業ネットワーク内にあることを意味する0は、通話レシーバーがネットワークの外側にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-224">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-224">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-225">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-226">呼び出し先 Mac アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-226">Callee Mac address.</span></span> <span data-ttu-id="4ffae-227"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4ffae-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-229">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-229">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-230">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-231">通話レシーバーによって使用される A/V エッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="4ffae-232">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffae-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-234">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-235">通話レシーバーによって、A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="4ffae-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-236"><strong>Calleecapdev</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-237">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-237">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-238">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-239">通話レシーバーによって使用されるデバイスをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="4ffae-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="4ffae-240"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4ffae-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-241"><strong>Calle・ Enderdev</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-242">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-242">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-243">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-244">通話レシーバーによって使用されるレンダリングデバイス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-244">Render device used by the call receiver.</span></span> <span data-ttu-id="4ffae-245"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4ffae-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-246"><strong>Calleecapdevdriver</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-247">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-247">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-248">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-249">通話レシーバーのキャプチャデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="4ffae-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="4ffae-250"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="4ffae-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ffae-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ffae-253">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-254">通話レシーバーのレンダリングデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="4ffae-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="4ffae-255"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="4ffae-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ffae-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ffae-258">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-259">呼び出し先がネットワークに接続された方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="4ffae-260">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="4ffae-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="4ffae-261">一般的な値は、有線接続の場合は0、WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="4ffae-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-263">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-263">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-264">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-265">ワイヤレスが使用されている場合は、呼び出し先の BSSID。</span><span class="sxs-lookup"><span data-stu-id="4ffae-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="4ffae-266"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="4ffae-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-268">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-269">通話レシーバーのリンク。1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="4ffae-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-271">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4ffae-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-272">通話受信側エンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="4ffae-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-274">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4ffae-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-275">オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="4ffae-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-277">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-278">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side stream に適用される実際の帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="4ffae-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="4ffae-279">これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffae-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="4ffae-280">これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</span><span class="sxs-lookup"><span data-stu-id="4ffae-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-282">smallint</span><span class="sxs-lookup"><span data-stu-id="4ffae-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-283">これは、適用される帯域幅の上限のソースです。</span><span class="sxs-lookup"><span data-stu-id="4ffae-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="4ffae-284">帯域幅の制限の対象となる場所について説明します ("Policy Server"、"TURN Server"、"モダリティ" など)。</span><span class="sxs-lookup"><span data-stu-id="4ffae-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="4ffae-285"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4ffae-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-286"><strong>[発信者]</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-287">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-288">呼び出し元からのメトリックが受信されたかどうかを示します。1は yes で、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="4ffae-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-289"><strong>[呼び出し先]</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-290">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ffae-291">通話レシーバーからのメトリックが受信されたかどうかを示します。1は yes で、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="4ffae-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-293">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-294">レポートがセッションの一部であるか、セッション全体であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="4ffae-295">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-297">bit</span><span class="sxs-lookup"><span data-stu-id="4ffae-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-298">通話が低品質通話 (1) または良好コール (0) として分類されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="4ffae-299">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="4ffae-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-302">発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="4ffae-303">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ffae-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffae-306">発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4ffae-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="4ffae-307">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-309">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-309">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-310">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-311">通話を発信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="4ffae-312">NAT (ネットワークアドレス変換) を使用している組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="4ffae-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="4ffae-313">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-315">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-315">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-316">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-317">通話を発信したユーザーによって採用された WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="4ffae-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="4ffae-318">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-320">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-320">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-321">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-322">通話を発信したユーザーによって採用された WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="4ffae-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="4ffae-323">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-325">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-325">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-326">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-327">通話を受信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ffae-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="4ffae-328">NAT (ネットワークアドレス変換) を使用している組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="4ffae-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="4ffae-329">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffae-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-331">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-331">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-332">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-333">通話を受信したユーザーによって採用された WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="4ffae-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="4ffae-334">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffae-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="4ffae-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffae-336">int</span><span class="sxs-lookup"><span data-stu-id="4ffae-336">int</span></span></p></td>
<td><p><span data-ttu-id="4ffae-337">外部</span><span class="sxs-lookup"><span data-stu-id="4ffae-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffae-338">通話を受信したユーザーが使用する WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="4ffae-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="4ffae-339">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ffae-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

