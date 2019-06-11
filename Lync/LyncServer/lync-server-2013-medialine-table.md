---
title: 'Lync Server 2013: MediaLine テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="c99f2-102">Lync Server 2013 の MediaLine テーブル</span><span class="sxs-lookup"><span data-stu-id="c99f2-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c99f2-103">_**最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="c99f2-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="c99f2-104">各レコードは1つのメディアラインを表します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-104">Each record represents one media line.</span></span> <span data-ttu-id="c99f2-105">(1 つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c99f2-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="c99f2-106">1つのオーディオとビデオ (A/V) セッションには通常、1つのオーディオメディアラインと1つのビデオメディアラインが含まれていますが、会議デバイスが使用されている場合や、[ギャラリー] ビューを使用している場合は、2つのビデオメディア線が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c99f2-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c99f2-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c99f2-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c99f2-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c99f2-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c99f2-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c99f2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c99f2-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c99f2-114"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="c99f2-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-116">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-116">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-117">Primary</span><span class="sxs-lookup"><span data-stu-id="c99f2-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="c99f2-118"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="c99f2-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="c99f2-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c99f2-121">Primary</span><span class="sxs-lookup"><span data-stu-id="c99f2-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="c99f2-122">0はメインオーディオ、1はメインビデオ、2はパノラマビデオ、3はアプリケーション/デスクトップ共有です。</span><span class="sxs-lookup"><span data-stu-id="c99f2-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="c99f2-123">このラベルは、1つのセッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c99f2-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="c99f2-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-126">この列は存在しますが、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="c99f2-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="c99f2-127">メディアラインに使用される接続に関する情報は、CallerConnectivityICE 列と CalleeConnectivityICE 列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="c99f2-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-129">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-130">「Bits フラグ」で説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="c99f2-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="c99f2-131">詳細については、「ダウンロード可能な<em>エクスペリエンス監視サーバープロトコルの仕様</em>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99f2-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-133">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-134">CallerIceWarningFlags と同じですが、呼び出し先側でも同じです。</span><span class="sxs-lookup"><span data-stu-id="c99f2-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="c99f2-135">詳細については、「ダウンロード可能な<em>エクスペリエンス監視サーバープロトコルの仕様</em>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99f2-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-136"><strong>セキュリティ</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="c99f2-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-138">使用されているセキュリティプロファイル。</span><span class="sxs-lookup"><span data-stu-id="c99f2-138">The security profile in use.</span></span> <span data-ttu-id="c99f2-139">0は NONE、1は SRTP、2は V1 です。</span><span class="sxs-lookup"><span data-stu-id="c99f2-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="c99f2-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-142">0は UDP、1は TCP です。</span><span class="sxs-lookup"><span data-stu-id="c99f2-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-144">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-144">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-145">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-146">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-146">IP Address of the caller.</span></span> <span data-ttu-id="c99f2-147">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99f2-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-149">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-150">発信者によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="c99f2-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-152">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-152">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-153"> 外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-154">発信者のサブネット。</span><span class="sxs-lookup"><span data-stu-id="c99f2-154">The subnet of the caller.</span></span> <span data-ttu-id="c99f2-155">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99f2-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-157">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-158">1: 発信者がエンタープライズネットワーク内にあることを示します。0は、呼び出し元がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-160">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-160">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-161">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-162">発信者の mac アドレス。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="c99f2-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-164">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-164">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-165">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-166">発信者が使用した Lync Server A/V Edge サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="c99f2-167">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99f2-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-169">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-170">発信者によって、A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="c99f2-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-172">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-172">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-173">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-174">発信者によって使用されるデバイスをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="c99f2-174">Capture device used by the caller.</span></span> <span data-ttu-id="c99f2-175"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c99f2-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-177">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-177">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-178">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-179">発信者によって使われるレンダリングデバイス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-179">Render device used by caller.</span></span> <span data-ttu-id="c99f2-180"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c99f2-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-182">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-182">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-183">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-184">発信者のキャプチャデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="c99f2-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-186">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-186">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-187">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-188">発信者のレンダリングデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="c99f2-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="c99f2-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c99f2-191">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-192">発信者がネットワークに接続した方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="c99f2-193">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="c99f2-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="c99f2-194">一般的な値は、有線接続の場合は0、WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="c99f2-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-196">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-196">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-197">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-198">ワイヤレスが使用されている場合は、発信者の BSSID。</span><span class="sxs-lookup"><span data-stu-id="c99f2-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="c99f2-199"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="c99f2-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-201">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-202">発信者のリンク。</span><span class="sxs-lookup"><span data-stu-id="c99f2-202">The caller's link.</span></span> <span data-ttu-id="c99f2-203">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="c99f2-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-205">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="c99f2-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-206">発信者のエンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="c99f2-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-208">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-208">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-209">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-210">通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-210">IP Address of the call receiver.</span></span> <span data-ttu-id="c99f2-211">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99f2-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-213">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-214">通話レシーバーで使用されているポート。</span><span class="sxs-lookup"><span data-stu-id="c99f2-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-216">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-216">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-217">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-218">呼び出し先のサブネット。</span><span class="sxs-lookup"><span data-stu-id="c99f2-218">Subnet of callee.</span></span> <span data-ttu-id="c99f2-219">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99f2-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-221">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-222">1: 通話受信者が企業ネットワーク内にあることを意味する0は、通話レシーバーがネットワークの外側にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-224">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-224">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-225">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-226">呼び出し先 Mac アドレス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-226">Callee Mac address.</span></span> <span data-ttu-id="c99f2-227"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c99f2-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-229">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-229">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-230">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-231">通話レシーバーによって使用される A/V エッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="c99f2-232">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99f2-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-234">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-235">通話レシーバーによって、A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="c99f2-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-236"><strong>Calleecapdev</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-237">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-237">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-238">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-239">通話レシーバーによって使用されるデバイスをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="c99f2-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="c99f2-240"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c99f2-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-241"><strong>Calle・ Enderdev</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-242">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-242">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-243">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-244">通話レシーバーによって使用されるレンダリングデバイス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-244">Render device used by the call receiver.</span></span> <span data-ttu-id="c99f2-245"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c99f2-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-246"><strong>Calleecapdevdriver</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-247">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-247">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-248">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-249">通話レシーバーのキャプチャデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="c99f2-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="c99f2-250"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="c99f2-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c99f2-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c99f2-253">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-254">通話レシーバーのレンダリングデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="c99f2-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="c99f2-255"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="c99f2-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="c99f2-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c99f2-258">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-259">呼び出し先がネットワークに接続された方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="c99f2-260">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="c99f2-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="c99f2-261">一般的な値は、有線接続の場合は0、WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="c99f2-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-263">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-263">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-264">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-265">ワイヤレスが使用されている場合は、呼び出し先の BSSID。</span><span class="sxs-lookup"><span data-stu-id="c99f2-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="c99f2-266"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="c99f2-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-268">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-269">通話レシーバーのリンク。1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="c99f2-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-271">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="c99f2-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-272">通話受信側エンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="c99f2-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-274">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c99f2-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-275">オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="c99f2-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-277">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-278">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side stream に適用される実際の帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="c99f2-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="c99f2-279">これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c99f2-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="c99f2-280">これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</span><span class="sxs-lookup"><span data-stu-id="c99f2-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-282">smallint</span><span class="sxs-lookup"><span data-stu-id="c99f2-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-283">これは、適用される帯域幅の上限のソースです。</span><span class="sxs-lookup"><span data-stu-id="c99f2-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="c99f2-284">帯域幅の制限の対象となる場所について説明します ("Policy Server"、"TURN Server"、"モダリティ" など)。</span><span class="sxs-lookup"><span data-stu-id="c99f2-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="c99f2-285"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c99f2-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-286"><strong>[発信者]</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-287">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-288">呼び出し元からのメトリックが受信されたかどうかを示します。1は yes で、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="c99f2-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-289"><strong>[呼び出し先]</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-290">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c99f2-291">通話レシーバーからのメトリックが受信されたかどうかを示します。1は yes で、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="c99f2-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-293">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-294">レポートがセッションの一部であるか、セッション全体であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="c99f2-295">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-297">bit</span><span class="sxs-lookup"><span data-stu-id="c99f2-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-298">通話が低品質通話 (1) または良好コール (0) として分類されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="c99f2-299">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="c99f2-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-302">発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="c99f2-303">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="c99f2-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c99f2-306">発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c99f2-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="c99f2-307">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-309">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-309">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-310">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-311">通話を発信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="c99f2-312">NAT (ネットワークアドレス変換) を使用している組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="c99f2-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="c99f2-313">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-315">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-315">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-316">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-317">通話を発信したユーザーによって採用された WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="c99f2-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="c99f2-318">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-320">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-320">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-321">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-322">通話を発信したユーザーによって採用された WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="c99f2-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="c99f2-323">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-325">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-325">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-326">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-327">通話を受信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c99f2-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="c99f2-328">NAT (ネットワークアドレス変換) を使用している組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="c99f2-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="c99f2-329">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c99f2-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-331">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-331">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-332">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-333">通話を受信したユーザーによって採用された WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="c99f2-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="c99f2-334">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c99f2-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c99f2-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c99f2-336">int</span><span class="sxs-lookup"><span data-stu-id="c99f2-336">int</span></span></p></td>
<td><p><span data-ttu-id="c99f2-337">外部</span><span class="sxs-lookup"><span data-stu-id="c99f2-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c99f2-338">通話を受信したユーザーが使用する WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="c99f2-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="c99f2-339">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c99f2-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

