---
title: 'Lync Server 2013: MediaLine view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="c25d0-102">Lync Server 2013 での MediaLine の表示</span><span class="sxs-lookup"><span data-stu-id="c25d0-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c25d0-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c25d0-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c25d0-104">MediaLine ビューには、データベース内の各メディアラインに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c25d0-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="c25d0-105">1つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c25d0-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="c25d0-106">通常、1つのオーディオとビデオ (A/V) セッションには、1つのオーディオメディアラインと1つのビデオメディアラインが含まれます。ただし、会議デバイスが使用されている場合、または [ギャラリー] ビューを使用している場合は、2つのビデオメディアがセッションに含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c25d0-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="c25d0-107">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c25d0-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c25d0-108">列</span><span class="sxs-lookup"><span data-stu-id="c25d0-108">Column</span></span></th>
<th><span data-ttu-id="c25d0-109">データ型</span><span class="sxs-lookup"><span data-stu-id="c25d0-109">Data Type</span></span></th>
<th><span data-ttu-id="c25d0-110">説明</span><span class="sxs-lookup"><span data-stu-id="c25d0-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="c25d0-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="c25d0-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c25d0-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c25d0-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c25d0-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="c25d0-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="c25d0-115">int</span><span class="sxs-lookup"><span data-stu-id="c25d0-115">int</span></span></p></td>
<td><p><span data-ttu-id="c25d0-116"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c25d0-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="c25d0-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="c25d0-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="c25d0-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c25d0-119"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="c25d0-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c25d0-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c25d0-121">int</span><span class="sxs-lookup"><span data-stu-id="c25d0-121">int</span></span></p></td>
<td><p><span data-ttu-id="c25d0-122">発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="c25d0-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="c25d0-123">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25d0-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c25d0-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c25d0-125">int</span><span class="sxs-lookup"><span data-stu-id="c25d0-125">int</span></span></p></td>
<td><p><span data-ttu-id="c25d0-126">対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="c25d0-127">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25d0-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-128">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c25d0-128">Security</span></span></p></td>
<td><p><span data-ttu-id="c25d0-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="c25d0-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c25d0-130">セキュリティプロファイルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="c25d0-130">Security profile in use.</span></span> <span data-ttu-id="c25d0-131">0は NONE、1は SRTP、2は V1 です。</span><span class="sxs-lookup"><span data-stu-id="c25d0-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-132">Transport</span><span class="sxs-lookup"><span data-stu-id="c25d0-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="c25d0-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="c25d0-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c25d0-134">トランスポートの種類。</span><span class="sxs-lookup"><span data-stu-id="c25d0-134">Transport type.</span></span> <span data-ttu-id="c25d0-135">0は UDP、1は TCP です。</span><span class="sxs-lookup"><span data-stu-id="c25d0-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="c25d0-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c25d0-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="c25d0-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-138">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c25d0-138">IP address of the caller.</span></span> <span data-ttu-id="c25d0-139">これは IPv4 または IPv6 のアドレスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c25d0-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="c25d0-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="c25d0-141">int</span><span class="sxs-lookup"><span data-stu-id="c25d0-141">int</span></span></p></td>
<td><p><span data-ttu-id="c25d0-142">発信者によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="c25d0-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="c25d0-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="c25d0-144">bit</span><span class="sxs-lookup"><span data-stu-id="c25d0-144">bit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-145">発信者が組織のネットワーク内にあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="c25d0-146">1発信者がエンタープライズネットワーク内にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="c25d0-147">0は、発信者がネットワーク外であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="c25d0-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="c25d0-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-150">発信者によって使用されるネットワークインターフェイスの MAC アドレスです。</span><span class="sxs-lookup"><span data-stu-id="c25d0-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c25d0-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c25d0-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="c25d0-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-153">発信者によって使用される A/V Edge サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c25d0-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="c25d0-154">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25d0-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="c25d0-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c25d0-156">int</span><span class="sxs-lookup"><span data-stu-id="c25d0-156">int</span></span></p></td>
<td><p><span data-ttu-id="c25d0-157">発信者が使用する A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="c25d0-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="c25d0-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c25d0-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="c25d0-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-160">A/V Edge サービスによって報告された発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c25d0-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="c25d0-161">このアドレスは、クライアントが NAT の背後にある場合など、CallerIPAddr と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25d0-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c25d0-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c25d0-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-164">発信者のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="c25d0-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="c25d0-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c25d0-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-167">発信者のレンダーデバイス名。</span><span class="sxs-lookup"><span data-stu-id="c25d0-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c25d0-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c25d0-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-170">発信者のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="c25d0-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="c25d0-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c25d0-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-173">発信者のレンダーデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="c25d0-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="c25d0-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="c25d0-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="c25d0-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="c25d0-176">発信者の Wifi ドライバーの説明。</span><span class="sxs-lookup"><span data-stu-id="c25d0-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="c25d0-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="c25d0-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-179">発信者の Wifi ドライババージョン。</span><span class="sxs-lookup"><span data-stu-id="c25d0-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="c25d0-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="c25d0-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-182">発信者のネットワーク接続の詳細。</span><span class="sxs-lookup"><span data-stu-id="c25d0-182">Details of caller’s network connection.</span></span> <span data-ttu-id="c25d0-183">詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での Networkconnectiondetail の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25d0-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="c25d0-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="c25d0-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-186">発信者の WiFi 接続で使用される基本サービスセット識別子。</span><span class="sxs-lookup"><span data-stu-id="c25d0-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="c25d0-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="c25d0-188">bit</span><span class="sxs-lookup"><span data-stu-id="c25d0-188">bit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-189">発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="c25d0-190">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="c25d0-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="c25d0-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c25d0-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="c25d0-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-193">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c25d0-193">IP address of the callee.</span></span> <span data-ttu-id="c25d0-194">これは IPv4 または IPv6 のアドレスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c25d0-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="c25d0-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="c25d0-196">int</span><span class="sxs-lookup"><span data-stu-id="c25d0-196">int</span></span></p></td>
<td><p><span data-ttu-id="c25d0-197">呼び出し先によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="c25d0-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="c25d0-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="c25d0-199">bit</span><span class="sxs-lookup"><span data-stu-id="c25d0-199">bit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-200">呼び出し先がエンタープライズネットワーク内にあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="c25d0-201">1は、呼び出し先がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="c25d0-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="c25d0-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-204">呼び出し先によって使用されるネットワークインターフェイスの MAC アドレスです。</span><span class="sxs-lookup"><span data-stu-id="c25d0-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c25d0-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c25d0-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="c25d0-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-207">呼び出し先によって使用される A/V エッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c25d0-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="c25d0-208">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25d0-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="c25d0-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c25d0-210">int</span><span class="sxs-lookup"><span data-stu-id="c25d0-210">int</span></span></p></td>
<td><p><span data-ttu-id="c25d0-211">呼び出し先によって使用される A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="c25d0-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="c25d0-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c25d0-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="c25d0-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-214">A/V Edge サービスによって報告された呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c25d0-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="c25d0-215">このアドレスは、クライアントが NAT の背後にある場合など、CalleeIPAddr と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c25d0-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-216">Calleecapdev</span><span class="sxs-lookup"><span data-stu-id="c25d0-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c25d0-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="c25d0-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-218">呼び出し先のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="c25d0-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-219">Calle・ Enderdev</span><span class="sxs-lookup"><span data-stu-id="c25d0-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c25d0-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-221">呼び出し先のレンダリングデバイス名。</span><span class="sxs-lookup"><span data-stu-id="c25d0-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-222">Calleecapdevdriver</span><span class="sxs-lookup"><span data-stu-id="c25d0-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c25d0-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-224">呼び出し先のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="c25d0-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="c25d0-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c25d0-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-227">呼び出し先のレンダリングデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="c25d0-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="c25d0-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="c25d0-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-230">呼び出し先の Wifi ドライバーの説明。</span><span class="sxs-lookup"><span data-stu-id="c25d0-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="c25d0-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="c25d0-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="c25d0-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="c25d0-233">呼び出し先の Wifi ドライバーバージョン。</span><span class="sxs-lookup"><span data-stu-id="c25d0-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="c25d0-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="c25d0-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-236">呼び出し先のネットワーク接続の詳細。</span><span class="sxs-lookup"><span data-stu-id="c25d0-236">Details of callee’s network connection.</span></span> <span data-ttu-id="c25d0-237">詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での Networkconnectiondetail の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c25d0-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="c25d0-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="c25d0-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-240">呼び出し先の WiFi 接続で使用される基本サービスセット識別子。</span><span class="sxs-lookup"><span data-stu-id="c25d0-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="c25d0-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="c25d0-242">bit</span><span class="sxs-lookup"><span data-stu-id="c25d0-242">bit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-243">呼び出し先が仮想プライベートネットワーク経由で接続されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="c25d0-244">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="c25d0-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="c25d0-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="c25d0-246">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c25d0-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-247">オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="c25d0-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="c25d0-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-249">int</span><span class="sxs-lookup"><span data-stu-id="c25d0-249">int</span></span></p></td>
<td><p><span data-ttu-id="c25d0-250">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) によって指定された send side stream に適用される実際の帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="c25d0-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="c25d0-251">これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c25d0-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="c25d0-252">これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</span><span class="sxs-lookup"><span data-stu-id="c25d0-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="c25d0-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="c25d0-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c25d0-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c25d0-255">適用される帯域幅キャップのソース。</span><span class="sxs-lookup"><span data-stu-id="c25d0-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="c25d0-256">帯域幅の制限の対象となる場所 (たとえば、"Policy Server"、"TURN Server"、"モダリティ" など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-257">[発信者]</span><span class="sxs-lookup"><span data-stu-id="c25d0-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="c25d0-258">bit</span><span class="sxs-lookup"><span data-stu-id="c25d0-258">bit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-259">呼び出し元からのメトリックが受信されたかどうかを示します。1は yes、0はいいえ。</span><span class="sxs-lookup"><span data-stu-id="c25d0-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-260">[呼び出し先]</span><span class="sxs-lookup"><span data-stu-id="c25d0-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="c25d0-261">bit</span><span class="sxs-lookup"><span data-stu-id="c25d0-261">bit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-262">通話レシーバーからのメトリックが受信されたかどうかを示します。1は yes、0はいいえ。</span><span class="sxs-lookup"><span data-stu-id="c25d0-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="c25d0-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="c25d0-264">bit</span><span class="sxs-lookup"><span data-stu-id="c25d0-264">bit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-265">レポートが通話の一部であるか、または完了しているかを示します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="c25d0-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="c25d0-267">bit</span><span class="sxs-lookup"><span data-stu-id="c25d0-267">bit</span></span></p></td>
<td><p><span data-ttu-id="c25d0-268">通話が低品質通話 (1) として分類されたか、または良好な通話 (0) であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c25d0-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="c25d0-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="c25d0-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="c25d0-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c25d0-271">発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c25d0-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="c25d0-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="c25d0-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="c25d0-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c25d0-274">ユーザーが ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c25d0-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

