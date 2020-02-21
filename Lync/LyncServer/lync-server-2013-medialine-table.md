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
ms.openlocfilehash: 84aa652a51934a8b513392869a0875f60689f759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="7043a-102">Lync Server 2013 の MediaLine テーブル</span><span class="sxs-lookup"><span data-stu-id="7043a-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7043a-103">_**トピックの最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="7043a-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="7043a-104">各レコードは1つのメディアラインを表します。</span><span class="sxs-lookup"><span data-stu-id="7043a-104">Each record represents one media line.</span></span> <span data-ttu-id="7043a-105">(1 つのオーディオセッションには、通常1つのオーディオメディア回線が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7043a-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="7043a-106">通常、1つの音声ビデオ (A/V) セッションには1つのオーディオメディア行と1つのビデオメディア回線が含まれますが、会議デバイスが使用されている場合や、ギャラリービューが使用されている場合は、セッションに2つのビデオメディア回線が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="7043a-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7043a-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7043a-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7043a-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7043a-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7043a-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-112">日付型</span><span class="sxs-lookup"><span data-stu-id="7043a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7043a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7043a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7043a-114"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-116">int</span><span class="sxs-lookup"><span data-stu-id="7043a-116">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="7043a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="7043a-118"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="7043a-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7043a-121">Primary</span><span class="sxs-lookup"><span data-stu-id="7043a-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="7043a-122">0はメインオーディオ、1はメインビデオ、2はパノラマビデオ、3はアプリケーション/デスクトップ共有です。</span><span class="sxs-lookup"><span data-stu-id="7043a-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="7043a-123">このラベルは、1つのセッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7043a-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="7043a-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-126">この列は存在しますが、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="7043a-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="7043a-127">メディアラインに使用される接続に関する情報は、CallerConnectivityICE および CalleeConnectivityICE の各列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-129">int</span><span class="sxs-lookup"><span data-stu-id="7043a-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-130">「Bits フラグ」で説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="7043a-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="7043a-131">詳細については、「 <em>Qexperience Monitoring Server Protocol Specification</em>」を参照してください。ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7043a-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-133">int</span><span class="sxs-lookup"><span data-stu-id="7043a-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-134">CallerIceWarningFlags と同じですが、呼び出し先側で行います。</span><span class="sxs-lookup"><span data-stu-id="7043a-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="7043a-135">詳細については、「 <em>Qexperience Monitoring Server Protocol Specification</em>」を参照してください。ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7043a-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-136"><strong>セキュリティ</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="7043a-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-138">使用されているセキュリティプロファイル。</span><span class="sxs-lookup"><span data-stu-id="7043a-138">The security profile in use.</span></span> <span data-ttu-id="7043a-139">0 は NONE、1 は SRTP、2 は V1 です。</span><span class="sxs-lookup"><span data-stu-id="7043a-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="7043a-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-142">0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="7043a-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-144">int</span><span class="sxs-lookup"><span data-stu-id="7043a-144">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-145">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-146">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7043a-146">IP Address of the caller.</span></span> <span data-ttu-id="7043a-147">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7043a-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-149">int</span><span class="sxs-lookup"><span data-stu-id="7043a-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-150">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="7043a-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-152">int</span><span class="sxs-lookup"><span data-stu-id="7043a-152">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-153"> 外部</span><span class="sxs-lookup"><span data-stu-id="7043a-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-154">発信者のサブネット。</span><span class="sxs-lookup"><span data-stu-id="7043a-154">The subnet of the caller.</span></span> <span data-ttu-id="7043a-155">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7043a-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-157">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-158">1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="7043a-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-160">int</span><span class="sxs-lookup"><span data-stu-id="7043a-160">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-161">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-162">発信者の mac アドレス。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-164">int</span><span class="sxs-lookup"><span data-stu-id="7043a-164">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-165">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-166">発信者が使用する Lync Server の音声ビデオエッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7043a-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="7043a-167">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7043a-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-169">int</span><span class="sxs-lookup"><span data-stu-id="7043a-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-170">発信者が音声ビデオエッジサービスで使用するポートです。</span><span class="sxs-lookup"><span data-stu-id="7043a-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-172">int</span><span class="sxs-lookup"><span data-stu-id="7043a-172">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-173">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-174">発信者によって使用されるキャプチャデバイス。</span><span class="sxs-lookup"><span data-stu-id="7043a-174">Capture device used by the caller.</span></span> <span data-ttu-id="7043a-175"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-177">int</span><span class="sxs-lookup"><span data-stu-id="7043a-177">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-178">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-179">発信者によって使用されるレンダーデバイス。</span><span class="sxs-lookup"><span data-stu-id="7043a-179">Render device used by caller.</span></span> <span data-ttu-id="7043a-180"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-182">int</span><span class="sxs-lookup"><span data-stu-id="7043a-182">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-183">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-184">発信者のキャプチャデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-186">int</span><span class="sxs-lookup"><span data-stu-id="7043a-186">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-187">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-188">発信者のレンダーデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="7043a-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7043a-191">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-192">発信者がネットワークに接続した方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7043a-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="7043a-193">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="7043a-194">一般的な値は、有線接続の場合は、1つの WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="7043a-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-196">int</span><span class="sxs-lookup"><span data-stu-id="7043a-196">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-197">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-198">発信者の BSSID (ワイヤレスが使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="7043a-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="7043a-199"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="7043a-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-201">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-202">発信者のリンク。</span><span class="sxs-lookup"><span data-stu-id="7043a-202">The caller's link.</span></span> <span data-ttu-id="7043a-203">1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="7043a-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-205">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="7043a-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-206">発信者のエンドポイントのネットワークリンクの速度 (単位は bps)。</span><span class="sxs-lookup"><span data-stu-id="7043a-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-208">int</span><span class="sxs-lookup"><span data-stu-id="7043a-208">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-209">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-210">通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7043a-210">IP Address of the call receiver.</span></span> <span data-ttu-id="7043a-211">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7043a-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-213">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-214">通話受信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="7043a-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-216">int</span><span class="sxs-lookup"><span data-stu-id="7043a-216">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-217">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-218">呼び出し先のサブネット。</span><span class="sxs-lookup"><span data-stu-id="7043a-218">Subnet of callee.</span></span> <span data-ttu-id="7043a-219">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7043a-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-221">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-222">1は、通話受信者がエンタープライズネットワーク内にあることを意味します。0は、通話受信者がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7043a-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-224">int</span><span class="sxs-lookup"><span data-stu-id="7043a-224">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-225">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-226">呼び出し先 Mac アドレス。</span><span class="sxs-lookup"><span data-stu-id="7043a-226">Callee Mac address.</span></span> <span data-ttu-id="7043a-227"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-229">int</span><span class="sxs-lookup"><span data-stu-id="7043a-229">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-230">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-231">通話受信者が使用する音声ビデオエッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7043a-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="7043a-232">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7043a-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-234">int</span><span class="sxs-lookup"><span data-stu-id="7043a-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-235">通話受信者が使用する音声ビデオエッジサービスのポート。</span><span class="sxs-lookup"><span data-stu-id="7043a-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-236"><strong>Calleecapのアーキテクチャ開発</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-237">int</span><span class="sxs-lookup"><span data-stu-id="7043a-237">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-238">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-239">通話レシーバーによって使用されるキャプチャデバイス。</span><span class="sxs-lookup"><span data-stu-id="7043a-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="7043a-240"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-242">int</span><span class="sxs-lookup"><span data-stu-id="7043a-242">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-243">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-244">呼び出しレシーバーによって使用されるレンダリングデバイス。</span><span class="sxs-lookup"><span data-stu-id="7043a-244">Render device used by the call receiver.</span></span> <span data-ttu-id="7043a-245"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-246"><strong>Calleecapアーキテクチャ Devdriver</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-247">int</span><span class="sxs-lookup"><span data-stu-id="7043a-247">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-248">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-249">通話受信者のキャプチャデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="7043a-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="7043a-250"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="7043a-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7043a-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7043a-253">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-254">呼び出しレシーバーのレンダーデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="7043a-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="7043a-255"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="7043a-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="7043a-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7043a-258">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-259">呼び出し先がネットワークに接続された方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7043a-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="7043a-260">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="7043a-261">一般的な値は、有線接続の場合は、1つの WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="7043a-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-263">int</span><span class="sxs-lookup"><span data-stu-id="7043a-263">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-264">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-265">ワイヤレスが使用されている場合は、呼び出し先の BSSID。</span><span class="sxs-lookup"><span data-stu-id="7043a-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="7043a-266"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="7043a-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-268">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-269">通話受信者のリンク。1は仮想プライベートネットワーク (VPN)、0は非 VPN。</span><span class="sxs-lookup"><span data-stu-id="7043a-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-271">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="7043a-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-272">通話受信者のエンドポイントのネットワークリンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="7043a-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-274">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="7043a-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-275">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="7043a-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-277">int</span><span class="sxs-lookup"><span data-stu-id="7043a-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-278">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された、特定の送信側ストリームに適用される実際の帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="7043a-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="7043a-279">帯域幅の推定値に基づいて、有効な帯域幅を低くすることができるため、これを効果的な帯域幅と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7043a-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="7043a-280">これは基本的に、送信ストリームが帯域幅の見積もりによって課される制限を受けることができる最大帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="7043a-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-282">smallint</span><span class="sxs-lookup"><span data-stu-id="7043a-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-283">適用されている帯域幅キャップのソースです。</span><span class="sxs-lookup"><span data-stu-id="7043a-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="7043a-284">帯域幅制限の対象となる場所 ("Policy Server"、"TURN Server"、"モダリティ" など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="7043a-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="7043a-285"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7043a-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-287">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-288">発信者からの指標を受信したかどうかを示します。1は yes、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="7043a-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-289"><strong>側</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-290">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7043a-291">通話受信者からの指標が受信されたかどうかを示します。1は yes、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="7043a-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-293">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-294">レポートがセッションの一部を対象としているか、セッション全体を対象としているかを示します。</span><span class="sxs-lookup"><span data-stu-id="7043a-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="7043a-295">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-297">若干</span><span class="sxs-lookup"><span data-stu-id="7043a-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-298">通話が低品質通話 (1) として分類されたか、良好な通話 (0) として分類されたかを示します。</span><span class="sxs-lookup"><span data-stu-id="7043a-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="7043a-299">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="7043a-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-302">発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7043a-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="7043a-303">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="7043a-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7043a-306">発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7043a-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="7043a-307">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-309">int</span><span class="sxs-lookup"><span data-stu-id="7043a-309">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-310">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-311">通話を発信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7043a-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="7043a-312">NAT (ネットワークアドレス変換) を使用する組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="7043a-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="7043a-313">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-315">int</span><span class="sxs-lookup"><span data-stu-id="7043a-315">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-316">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-317">通話を発信したユーザーによって使用されている WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="7043a-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="7043a-318">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-320">int</span><span class="sxs-lookup"><span data-stu-id="7043a-320">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-321">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-322">通話を発信したユーザーによって使用されている WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="7043a-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="7043a-323">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-325">int</span><span class="sxs-lookup"><span data-stu-id="7043a-325">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-326">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-327">呼び出しを受信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7043a-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="7043a-328">NAT (ネットワークアドレス変換) を使用する組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="7043a-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="7043a-329">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7043a-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-331">int</span><span class="sxs-lookup"><span data-stu-id="7043a-331">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-332">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-333">通話を受信したユーザーによって使用されている WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="7043a-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="7043a-334">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7043a-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7043a-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7043a-336">int</span><span class="sxs-lookup"><span data-stu-id="7043a-336">int</span></span></p></td>
<td><p><span data-ttu-id="7043a-337">外部</span><span class="sxs-lookup"><span data-stu-id="7043a-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7043a-338">通話を受信したユーザーによって使用されている WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="7043a-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="7043a-339">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7043a-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

