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
ms.openlocfilehash: edf0e216d90af0d32a0e700661a653a13028e01a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="654ad-102">Lync Server 2013 の MediaLine テーブル</span><span class="sxs-lookup"><span data-stu-id="654ad-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="654ad-103">_**トピックの最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="654ad-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="654ad-104">各レコードは1つのメディアラインを表します。</span><span class="sxs-lookup"><span data-stu-id="654ad-104">Each record represents one media line.</span></span> <span data-ttu-id="654ad-105">(1 つのオーディオセッションには、通常1つのオーディオメディア回線が含まれています。</span><span class="sxs-lookup"><span data-stu-id="654ad-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="654ad-106">通常、1つの音声ビデオ (A/V) セッションには1つのオーディオメディア行と1つのビデオメディア回線が含まれますが、会議デバイスが使用されている場合や、ギャラリービューが使用されている場合は、セッションに2つのビデオメディア回線が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="654ad-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654ad-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="654ad-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="654ad-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="654ad-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654ad-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-112">日付型</span><span class="sxs-lookup"><span data-stu-id="654ad-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="654ad-113">Primary</span><span class="sxs-lookup"><span data-stu-id="654ad-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="654ad-114"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-116">int</span><span class="sxs-lookup"><span data-stu-id="654ad-116">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-117">Primary</span><span class="sxs-lookup"><span data-stu-id="654ad-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="654ad-118"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="654ad-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="654ad-121">Primary</span><span class="sxs-lookup"><span data-stu-id="654ad-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="654ad-122">0はメインオーディオ、1はメインビデオ、2はパノラマビデオ、3はアプリケーション/デスクトップ共有です。</span><span class="sxs-lookup"><span data-stu-id="654ad-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="654ad-123">このラベルは、1つのセッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="654ad-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="654ad-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-126">この列は存在しますが、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="654ad-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="654ad-127">メディアラインに使用される接続に関する情報は、CallerConnectivityICE および CalleeConnectivityICE の各列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-129">int</span><span class="sxs-lookup"><span data-stu-id="654ad-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-130">「Bits フラグ」で説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="654ad-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="654ad-131">詳細については、「 <em>Qexperience Monitoring Server Protocol Specification</em>」を参照してください。ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="654ad-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-133">int</span><span class="sxs-lookup"><span data-stu-id="654ad-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-134">CallerIceWarningFlags と同じですが、呼び出し先側で行います。</span><span class="sxs-lookup"><span data-stu-id="654ad-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="654ad-135">詳細については、「 <em>Qexperience Monitoring Server Protocol Specification</em>」を参照してください。ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="654ad-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-136"><strong>セキュリティ</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="654ad-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-138">使用されているセキュリティプロファイル。</span><span class="sxs-lookup"><span data-stu-id="654ad-138">The security profile in use.</span></span> <span data-ttu-id="654ad-139">0 は NONE、1 は SRTP、2 は V1 です。</span><span class="sxs-lookup"><span data-stu-id="654ad-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="654ad-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-142">0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="654ad-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-144">int</span><span class="sxs-lookup"><span data-stu-id="654ad-144">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-145">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-146">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="654ad-146">IP Address of the caller.</span></span> <span data-ttu-id="654ad-147">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654ad-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-149">int</span><span class="sxs-lookup"><span data-stu-id="654ad-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-150">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="654ad-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-152">int</span><span class="sxs-lookup"><span data-stu-id="654ad-152">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-153"> 外部</span><span class="sxs-lookup"><span data-stu-id="654ad-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-154">発信者のサブネット。</span><span class="sxs-lookup"><span data-stu-id="654ad-154">The subnet of the caller.</span></span> <span data-ttu-id="654ad-155">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654ad-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-157">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-158">1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="654ad-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-160">int</span><span class="sxs-lookup"><span data-stu-id="654ad-160">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-161">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-162">発信者の mac アドレス。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-164">int</span><span class="sxs-lookup"><span data-stu-id="654ad-164">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-165">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-166">発信者が使用する Lync Server の音声ビデオエッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="654ad-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="654ad-167">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654ad-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-169">int</span><span class="sxs-lookup"><span data-stu-id="654ad-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-170">発信者が音声ビデオエッジサービスで使用するポートです。</span><span class="sxs-lookup"><span data-stu-id="654ad-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-172">int</span><span class="sxs-lookup"><span data-stu-id="654ad-172">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-173">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-174">発信者によって使用されるキャプチャデバイス。</span><span class="sxs-lookup"><span data-stu-id="654ad-174">Capture device used by the caller.</span></span> <span data-ttu-id="654ad-175"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-177">int</span><span class="sxs-lookup"><span data-stu-id="654ad-177">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-178">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-179">発信者によって使用されるレンダーデバイス。</span><span class="sxs-lookup"><span data-stu-id="654ad-179">Render device used by caller.</span></span> <span data-ttu-id="654ad-180"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-182">int</span><span class="sxs-lookup"><span data-stu-id="654ad-182">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-183">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-184">発信者のキャプチャデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-186">int</span><span class="sxs-lookup"><span data-stu-id="654ad-186">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-187">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-188">発信者のレンダーデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="654ad-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="654ad-191">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-192">発信者がネットワークに接続した方法を示します。</span><span class="sxs-lookup"><span data-stu-id="654ad-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="654ad-193">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="654ad-194">一般的な値は、有線接続の場合は、1つの WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="654ad-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-196">int</span><span class="sxs-lookup"><span data-stu-id="654ad-196">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-197">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-198">発信者の BSSID (ワイヤレスが使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="654ad-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="654ad-199"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="654ad-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-201">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-202">発信者のリンク。</span><span class="sxs-lookup"><span data-stu-id="654ad-202">The caller's link.</span></span> <span data-ttu-id="654ad-203">1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="654ad-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-205">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="654ad-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-206">発信者のエンドポイントのネットワークリンクの速度 (単位は bps)。</span><span class="sxs-lookup"><span data-stu-id="654ad-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-208">int</span><span class="sxs-lookup"><span data-stu-id="654ad-208">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-209">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-210">通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="654ad-210">IP Address of the call receiver.</span></span> <span data-ttu-id="654ad-211">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654ad-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-213">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-214">通話受信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="654ad-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-216">int</span><span class="sxs-lookup"><span data-stu-id="654ad-216">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-217">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-218">呼び出し先のサブネット。</span><span class="sxs-lookup"><span data-stu-id="654ad-218">Subnet of callee.</span></span> <span data-ttu-id="654ad-219">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654ad-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-221">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-222">1は、通話受信者がエンタープライズネットワーク内にあることを意味します。0は、通話受信者がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="654ad-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-224">int</span><span class="sxs-lookup"><span data-stu-id="654ad-224">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-225">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-226">呼び出し先 Mac アドレス。</span><span class="sxs-lookup"><span data-stu-id="654ad-226">Callee Mac address.</span></span> <span data-ttu-id="654ad-227"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-229">int</span><span class="sxs-lookup"><span data-stu-id="654ad-229">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-230">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-231">通話受信者が使用する音声ビデオエッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="654ad-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="654ad-232">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654ad-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-234">int</span><span class="sxs-lookup"><span data-stu-id="654ad-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-235">通話受信者が使用する音声ビデオエッジサービスのポート。</span><span class="sxs-lookup"><span data-stu-id="654ad-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-236"><strong>Calleecapのアーキテクチャ開発</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-237">int</span><span class="sxs-lookup"><span data-stu-id="654ad-237">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-238">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-239">通話レシーバーによって使用されるキャプチャデバイス。</span><span class="sxs-lookup"><span data-stu-id="654ad-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="654ad-240"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-242">int</span><span class="sxs-lookup"><span data-stu-id="654ad-242">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-243">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-244">呼び出しレシーバーによって使用されるレンダリングデバイス。</span><span class="sxs-lookup"><span data-stu-id="654ad-244">Render device used by the call receiver.</span></span> <span data-ttu-id="654ad-245"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-246"><strong>Calleecapアーキテクチャ Devdriver</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-247">int</span><span class="sxs-lookup"><span data-stu-id="654ad-247">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-248">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-249">通話受信者のキャプチャデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="654ad-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="654ad-250"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="654ad-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="654ad-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="654ad-253">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-254">呼び出しレシーバーのレンダーデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="654ad-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="654ad-255"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="654ad-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="654ad-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="654ad-258">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-259">呼び出し先がネットワークに接続された方法を示します。</span><span class="sxs-lookup"><span data-stu-id="654ad-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="654ad-260">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="654ad-261">一般的な値は、有線接続の場合は、1つの WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="654ad-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-263">int</span><span class="sxs-lookup"><span data-stu-id="654ad-263">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-264">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-265">ワイヤレスが使用されている場合は、呼び出し先の BSSID。</span><span class="sxs-lookup"><span data-stu-id="654ad-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="654ad-266"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="654ad-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-268">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-269">通話受信者のリンク。1は仮想プライベートネットワーク (VPN)、0は非 VPN。</span><span class="sxs-lookup"><span data-stu-id="654ad-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-271">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="654ad-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-272">通話受信者のエンドポイントのネットワークリンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="654ad-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-274">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="654ad-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-275">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="654ad-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-277">int</span><span class="sxs-lookup"><span data-stu-id="654ad-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-278">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された、特定の送信側ストリームに適用される実際の帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="654ad-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="654ad-279">帯域幅の推定値に基づいて、有効な帯域幅を低くすることができるため、これを効果的な帯域幅と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="654ad-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="654ad-280">これは基本的に、送信ストリームが帯域幅の見積もりによって課される制限を受けることができる最大帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="654ad-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-282">smallint</span><span class="sxs-lookup"><span data-stu-id="654ad-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-283">適用されている帯域幅キャップのソースです。</span><span class="sxs-lookup"><span data-stu-id="654ad-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="654ad-284">帯域幅制限の対象となる場所 ("Policy Server"、"TURN Server"、"モダリティ" など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="654ad-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="654ad-285"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="654ad-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-287">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-288">発信者からの指標を受信したかどうかを示します。1は yes、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="654ad-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-289"><strong>側</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-290">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="654ad-291">通話受信者からの指標が受信されたかどうかを示します。1は yes、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="654ad-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-293">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-294">レポートがセッションの一部を対象としているか、セッション全体を対象としているかを示します。</span><span class="sxs-lookup"><span data-stu-id="654ad-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="654ad-295">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-297">若干</span><span class="sxs-lookup"><span data-stu-id="654ad-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-298">通話が低品質通話 (1) として分類されたか、良好な通話 (0) として分類されたかを示します。</span><span class="sxs-lookup"><span data-stu-id="654ad-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="654ad-299">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="654ad-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-302">発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="654ad-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="654ad-303">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="654ad-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="654ad-306">発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="654ad-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="654ad-307">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-309">int</span><span class="sxs-lookup"><span data-stu-id="654ad-309">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-310">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-311">通話を発信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="654ad-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="654ad-312">NAT (ネットワークアドレス変換) を使用する組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="654ad-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="654ad-313">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-315">int</span><span class="sxs-lookup"><span data-stu-id="654ad-315">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-316">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-317">通話を発信したユーザーによって使用されている WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="654ad-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="654ad-318">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-320">int</span><span class="sxs-lookup"><span data-stu-id="654ad-320">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-321">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-322">通話を発信したユーザーによって使用されている WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="654ad-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="654ad-323">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-325">int</span><span class="sxs-lookup"><span data-stu-id="654ad-325">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-326">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-327">呼び出しを受信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="654ad-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="654ad-328">NAT (ネットワークアドレス変換) を使用する組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="654ad-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="654ad-329">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654ad-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-331">int</span><span class="sxs-lookup"><span data-stu-id="654ad-331">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-332">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-333">通話を受信したユーザーによって使用されている WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="654ad-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="654ad-334">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654ad-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="654ad-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="654ad-336">int</span><span class="sxs-lookup"><span data-stu-id="654ad-336">int</span></span></p></td>
<td><p><span data-ttu-id="654ad-337">外部</span><span class="sxs-lookup"><span data-stu-id="654ad-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="654ad-338">通話を受信したユーザーによって使用されている WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="654ad-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="654ad-339">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="654ad-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

