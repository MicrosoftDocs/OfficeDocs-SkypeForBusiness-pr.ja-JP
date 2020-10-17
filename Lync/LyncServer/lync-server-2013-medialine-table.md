---
title: 'Lync Server 2013: MediaLine テーブル'
description: 'Lync Server 2013: MediaLine テーブル。'
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572113"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="f079d-103">Lync Server 2013 の MediaLine テーブル</span><span class="sxs-lookup"><span data-stu-id="f079d-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f079d-104">_**トピックの最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="f079d-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="f079d-105">各レコードは1つのメディアラインを表します。</span><span class="sxs-lookup"><span data-stu-id="f079d-105">Each record represents one media line.</span></span> <span data-ttu-id="f079d-106">(1 つのオーディオセッションには、通常1つのオーディオメディア回線が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f079d-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="f079d-107">通常、1つの音声ビデオ (A/V) セッションには1つのオーディオメディア行と1つのビデオメディア回線が含まれますが、会議デバイスが使用されている場合や、ギャラリービューが使用されている場合は、セッションに2つのビデオメディア回線が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="f079d-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f079d-108"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f079d-109"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f079d-110"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f079d-111"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f079d-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-113">日付型</span><span class="sxs-lookup"><span data-stu-id="f079d-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="f079d-114">Primary</span><span class="sxs-lookup"><span data-stu-id="f079d-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="f079d-115"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-117">int</span><span class="sxs-lookup"><span data-stu-id="f079d-117">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-118">Primary</span><span class="sxs-lookup"><span data-stu-id="f079d-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="f079d-119"><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-121">tinyint</span><span class="sxs-lookup"><span data-stu-id="f079d-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f079d-122">Primary</span><span class="sxs-lookup"><span data-stu-id="f079d-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="f079d-123">0はメインオーディオ、1はメインビデオ、2はパノラマビデオ、3はアプリケーション/デスクトップ共有です。</span><span class="sxs-lookup"><span data-stu-id="f079d-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="f079d-124">このラベルは、1つのセッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f079d-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-126">tinyint</span><span class="sxs-lookup"><span data-stu-id="f079d-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-127">この列は存在しますが、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="f079d-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f079d-128">メディアラインに使用される接続に関する情報は、CallerConnectivityICE および CalleeConnectivityICE の各列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-130">int</span><span class="sxs-lookup"><span data-stu-id="f079d-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-131">「Bits フラグ」で説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="f079d-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="f079d-132">詳細については、「 <em>Qexperience Monitoring Server Protocol Specification</em>」を参照してください。ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f079d-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-134">int</span><span class="sxs-lookup"><span data-stu-id="f079d-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-135">CallerIceWarningFlags と同じですが、呼び出し先側で行います。</span><span class="sxs-lookup"><span data-stu-id="f079d-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="f079d-136">詳細については、「 <em>Qexperience Monitoring Server Protocol Specification</em>」を参照してください。ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f079d-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-137"><strong>セキュリティ</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-138">tinyint</span><span class="sxs-lookup"><span data-stu-id="f079d-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-139">使用されているセキュリティプロファイル。</span><span class="sxs-lookup"><span data-stu-id="f079d-139">The security profile in use.</span></span> <span data-ttu-id="f079d-140">0 は NONE、1 は SRTP、2 は V1 です。</span><span class="sxs-lookup"><span data-stu-id="f079d-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-141"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-142">tinyint</span><span class="sxs-lookup"><span data-stu-id="f079d-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-143">0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="f079d-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-145">int</span><span class="sxs-lookup"><span data-stu-id="f079d-145">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-146">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-147">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f079d-147">IP Address of the caller.</span></span> <span data-ttu-id="f079d-148">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f079d-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-150">int</span><span class="sxs-lookup"><span data-stu-id="f079d-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-151">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="f079d-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-153">int</span><span class="sxs-lookup"><span data-stu-id="f079d-153">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-154"> 外部</span><span class="sxs-lookup"><span data-stu-id="f079d-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-155">発信者のサブネット。</span><span class="sxs-lookup"><span data-stu-id="f079d-155">The subnet of the caller.</span></span> <span data-ttu-id="f079d-156">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f079d-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-158">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-159">1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="f079d-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-160"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-161">int</span><span class="sxs-lookup"><span data-stu-id="f079d-161">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-162">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-163">発信者の mac アドレス。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-165">int</span><span class="sxs-lookup"><span data-stu-id="f079d-165">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-166">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-167">発信者が使用する Lync Server の音声ビデオエッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f079d-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="f079d-168">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f079d-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-170">int</span><span class="sxs-lookup"><span data-stu-id="f079d-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-171">発信者が音声ビデオエッジサービスで使用するポートです。</span><span class="sxs-lookup"><span data-stu-id="f079d-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-173">int</span><span class="sxs-lookup"><span data-stu-id="f079d-173">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-174">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-175">発信者によって使用されるキャプチャデバイス。</span><span class="sxs-lookup"><span data-stu-id="f079d-175">Capture device used by the caller.</span></span> <span data-ttu-id="f079d-176"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-178">int</span><span class="sxs-lookup"><span data-stu-id="f079d-178">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-179">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-180">発信者によって使用されるレンダーデバイス。</span><span class="sxs-lookup"><span data-stu-id="f079d-180">Render device used by caller.</span></span> <span data-ttu-id="f079d-181"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-183">int</span><span class="sxs-lookup"><span data-stu-id="f079d-183">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-184">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-185">発信者のキャプチャデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-187">int</span><span class="sxs-lookup"><span data-stu-id="f079d-187">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-188">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-189">発信者のレンダーデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="f079d-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f079d-192">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-193">発信者がネットワークに接続した方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f079d-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="f079d-194">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="f079d-195">一般的な値は、有線接続の場合は、1つの WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="f079d-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-197">int</span><span class="sxs-lookup"><span data-stu-id="f079d-197">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-198">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-199">発信者の BSSID (ワイヤレスが使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="f079d-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="f079d-200"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="f079d-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-202">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-203">発信者のリンク。</span><span class="sxs-lookup"><span data-stu-id="f079d-203">The caller's link.</span></span> <span data-ttu-id="f079d-204">1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="f079d-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-206">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="f079d-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-207">発信者のエンドポイントのネットワークリンクの速度 (単位は bps)。</span><span class="sxs-lookup"><span data-stu-id="f079d-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-209">int</span><span class="sxs-lookup"><span data-stu-id="f079d-209">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-210">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-211">通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f079d-211">IP Address of the call receiver.</span></span> <span data-ttu-id="f079d-212">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f079d-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-214">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-215">通話受信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="f079d-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-217">int</span><span class="sxs-lookup"><span data-stu-id="f079d-217">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-218">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-219">呼び出し先のサブネット。</span><span class="sxs-lookup"><span data-stu-id="f079d-219">Subnet of callee.</span></span> <span data-ttu-id="f079d-220">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f079d-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-222">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-223">1は、通話受信者がエンタープライズネットワーク内にあることを意味します。0は、通話受信者がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f079d-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-225">int</span><span class="sxs-lookup"><span data-stu-id="f079d-225">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-226">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-227">呼び出し先 Mac アドレス。</span><span class="sxs-lookup"><span data-stu-id="f079d-227">Callee Mac address.</span></span> <span data-ttu-id="f079d-228"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-230">int</span><span class="sxs-lookup"><span data-stu-id="f079d-230">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-231">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-232">通話受信者が使用する音声ビデオエッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f079d-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="f079d-233">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f079d-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-235">int</span><span class="sxs-lookup"><span data-stu-id="f079d-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-236">通話受信者が使用する音声ビデオエッジサービスのポート。</span><span class="sxs-lookup"><span data-stu-id="f079d-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-237"><strong>Calleecapのアーキテクチャ開発</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-238">int</span><span class="sxs-lookup"><span data-stu-id="f079d-238">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-239">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-240">通話レシーバーによって使用されるキャプチャデバイス。</span><span class="sxs-lookup"><span data-stu-id="f079d-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="f079d-241"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-243">int</span><span class="sxs-lookup"><span data-stu-id="f079d-243">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-244">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-245">呼び出しレシーバーによって使用されるレンダリングデバイス。</span><span class="sxs-lookup"><span data-stu-id="f079d-245">Render device used by the call receiver.</span></span> <span data-ttu-id="f079d-246"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-247"><strong>Calleecapアーキテクチャ Devdriver</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-248">int</span><span class="sxs-lookup"><span data-stu-id="f079d-248">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-249">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-250">通話受信者のキャプチャデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="f079d-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="f079d-251"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="f079d-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-253">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f079d-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f079d-254">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-255">呼び出しレシーバーのレンダーデバイスのドライバー。</span><span class="sxs-lookup"><span data-stu-id="f079d-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="f079d-256"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="f079d-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-258">tinyint</span><span class="sxs-lookup"><span data-stu-id="f079d-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f079d-259">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-260">呼び出し先がネットワークに接続された方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f079d-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="f079d-261">値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="f079d-262">一般的な値は、有線接続の場合は、1つの WiFi 接続の場合は0です。イーサネット接続の場合は3。</span><span class="sxs-lookup"><span data-stu-id="f079d-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-264">int</span><span class="sxs-lookup"><span data-stu-id="f079d-264">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-265">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-266">ワイヤレスが使用されている場合は、呼び出し先の BSSID。</span><span class="sxs-lookup"><span data-stu-id="f079d-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="f079d-267"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="f079d-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-269">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-270">通話受信者のリンク。1は仮想プライベートネットワーク (VPN)、0は非 VPN。</span><span class="sxs-lookup"><span data-stu-id="f079d-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-272">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="f079d-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-273">通話受信者のエンドポイントのネットワークリンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="f079d-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-275">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="f079d-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-276">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="f079d-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-278">int</span><span class="sxs-lookup"><span data-stu-id="f079d-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-279">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された、特定の送信側ストリームに適用される実際の帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="f079d-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="f079d-280">帯域幅の推定値に基づいて、有効な帯域幅を低くすることができるため、これを効果的な帯域幅と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f079d-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="f079d-281">これは基本的に、送信ストリームが帯域幅の見積もりによって課される制限を受けることができる最大帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="f079d-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-283">smallint</span><span class="sxs-lookup"><span data-stu-id="f079d-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-284">適用されている帯域幅キャップのソースです。</span><span class="sxs-lookup"><span data-stu-id="f079d-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="f079d-285">帯域幅制限の対象となる場所 ("Policy Server"、"TURN Server"、"モダリティ" など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="f079d-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="f079d-286"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f079d-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-287"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-288">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-289">発信者からの指標を受信したかどうかを示します。1は yes、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="f079d-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-290"><strong>側</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-291">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f079d-292">通話受信者からの指標が受信されたかどうかを示します。1は yes、null 値は no です。</span><span class="sxs-lookup"><span data-stu-id="f079d-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-294">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-295">レポートがセッションの一部を対象としているか、セッション全体を対象としているかを示します。</span><span class="sxs-lookup"><span data-stu-id="f079d-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="f079d-296">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-298">若干</span><span class="sxs-lookup"><span data-stu-id="f079d-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-299">通話が低品質通話 (1) として分類されたか、良好な通話 (0) として分類されたかを示します。</span><span class="sxs-lookup"><span data-stu-id="f079d-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="f079d-300">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="f079d-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-303">発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f079d-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="f079d-304">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-306">tinyint</span><span class="sxs-lookup"><span data-stu-id="f079d-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f079d-307">発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f079d-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="f079d-308">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-310">int</span><span class="sxs-lookup"><span data-stu-id="f079d-310">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-311">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-312">通話を発信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f079d-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="f079d-313">NAT (ネットワークアドレス変換) を使用する組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="f079d-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="f079d-314">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-316">int</span><span class="sxs-lookup"><span data-stu-id="f079d-316">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-317">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-318">通話を発信したユーザーによって使用されている WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="f079d-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="f079d-319">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-321">int</span><span class="sxs-lookup"><span data-stu-id="f079d-321">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-322">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-323">通話を発信したユーザーによって使用されている WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="f079d-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="f079d-324">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-326">int</span><span class="sxs-lookup"><span data-stu-id="f079d-326">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-327">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-328">呼び出しを受信したユーザーの再帰 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f079d-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="f079d-329">NAT (ネットワークアドレス変換) を使用する組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="f079d-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="f079d-330">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f079d-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-332">int</span><span class="sxs-lookup"><span data-stu-id="f079d-332">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-333">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-334">通話を受信したユーザーによって使用されている WiFi ドライバーのデバイスの説明。</span><span class="sxs-lookup"><span data-stu-id="f079d-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="f079d-335">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f079d-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f079d-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f079d-337">int</span><span class="sxs-lookup"><span data-stu-id="f079d-337">int</span></span></p></td>
<td><p><span data-ttu-id="f079d-338">外部</span><span class="sxs-lookup"><span data-stu-id="f079d-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f079d-339">通話を受信したユーザーによって使用されている WiFi ドライバーのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="f079d-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="f079d-340">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f079d-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

