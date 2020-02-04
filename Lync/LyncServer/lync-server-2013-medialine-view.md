---
title: 'Lync Server 2013: MediaLine view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="d7810-102">Lync Server 2013 での MediaLine の表示</span><span class="sxs-lookup"><span data-stu-id="d7810-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7810-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d7810-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d7810-104">MediaLine ビューには、データベース内の各メディアラインに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d7810-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="d7810-105">1つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d7810-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="d7810-106">通常、1つのオーディオとビデオ (A/V) セッションには、1つのオーディオメディアラインと1つのビデオメディアラインが含まれます。ただし、会議デバイスが使用されている場合、または [ギャラリー] ビューを使用している場合は、2つのビデオメディアがセッションに含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d7810-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="d7810-107">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d7810-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7810-108">列</span><span class="sxs-lookup"><span data-stu-id="d7810-108">Column</span></span></th>
<th><span data-ttu-id="d7810-109">データ型</span><span class="sxs-lookup"><span data-stu-id="d7810-109">Data Type</span></span></th>
<th><span data-ttu-id="d7810-110">説明</span><span class="sxs-lookup"><span data-stu-id="d7810-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7810-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="d7810-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="d7810-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d7810-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d7810-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="d7810-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="d7810-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="d7810-115">int</span><span class="sxs-lookup"><span data-stu-id="d7810-115">int</span></span></p></td>
<td><p><span data-ttu-id="d7810-116"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="d7810-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="d7810-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="d7810-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7810-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7810-119"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="d7810-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d7810-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d7810-121">int</span><span class="sxs-lookup"><span data-stu-id="d7810-121">int</span></span></p></td>
<td><p><span data-ttu-id="d7810-122">発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="d7810-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="d7810-123">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7810-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d7810-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d7810-125">int</span><span class="sxs-lookup"><span data-stu-id="d7810-125">int</span></span></p></td>
<td><p><span data-ttu-id="d7810-126">対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。</span><span class="sxs-lookup"><span data-stu-id="d7810-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="d7810-127">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7810-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-128">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d7810-128">Security</span></span></p></td>
<td><p><span data-ttu-id="d7810-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7810-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7810-130">セキュリティプロファイルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="d7810-130">Security profile in use.</span></span> <span data-ttu-id="d7810-131">0は NONE、1は SRTP、2は V1 です。</span><span class="sxs-lookup"><span data-stu-id="d7810-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-132">Transport</span><span class="sxs-lookup"><span data-stu-id="d7810-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="d7810-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7810-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7810-134">トランスポートの種類。</span><span class="sxs-lookup"><span data-stu-id="d7810-134">Transport type.</span></span> <span data-ttu-id="d7810-135">0は UDP、1は TCP です。</span><span class="sxs-lookup"><span data-stu-id="d7810-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7810-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7810-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7810-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7810-138">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="d7810-138">IP address of the caller.</span></span> <span data-ttu-id="d7810-139">これは IPv4 または IPv6 のアドレスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7810-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="d7810-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="d7810-141">int</span><span class="sxs-lookup"><span data-stu-id="d7810-141">int</span></span></p></td>
<td><p><span data-ttu-id="d7810-142">発信者によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="d7810-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="d7810-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="d7810-144">bit</span><span class="sxs-lookup"><span data-stu-id="d7810-144">bit</span></span></p></td>
<td><p><span data-ttu-id="d7810-145">発信者が組織のネットワーク内にあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7810-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="d7810-146">1発信者がエンタープライズネットワーク内にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d7810-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="d7810-147">0は、発信者がネットワーク外であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d7810-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="d7810-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="d7810-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-150">発信者によって使用されるネットワークインターフェイスの MAC アドレスです。</span><span class="sxs-lookup"><span data-stu-id="d7810-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7810-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7810-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7810-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7810-153">発信者によって使用される A/V Edge サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="d7810-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="d7810-154">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7810-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d7810-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d7810-156">int</span><span class="sxs-lookup"><span data-stu-id="d7810-156">int</span></span></p></td>
<td><p><span data-ttu-id="d7810-157">発信者が使用する A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="d7810-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7810-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7810-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7810-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7810-160">A/V Edge サービスによって報告された発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="d7810-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="d7810-161">このアドレスは、クライアントが NAT の背後にある場合など、CallerIPAddr と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7810-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d7810-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d7810-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-164">発信者のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="d7810-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="d7810-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d7810-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-167">発信者のレンダーデバイス名。</span><span class="sxs-lookup"><span data-stu-id="d7810-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7810-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7810-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-170">発信者のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="d7810-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7810-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7810-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-173">発信者のレンダーデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="d7810-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="d7810-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="d7810-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="d7810-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="d7810-176">発信者の Wifi ドライバーの説明。</span><span class="sxs-lookup"><span data-stu-id="d7810-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="d7810-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="d7810-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-179">発信者の Wifi ドライババージョン。</span><span class="sxs-lookup"><span data-stu-id="d7810-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d7810-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="d7810-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-182">発信者のネットワーク接続の詳細。</span><span class="sxs-lookup"><span data-stu-id="d7810-182">Details of caller’s network connection.</span></span> <span data-ttu-id="d7810-183">詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での Networkconnectiondetail の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7810-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="d7810-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="d7810-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-186">発信者の WiFi 接続で使用される基本サービスセット識別子。</span><span class="sxs-lookup"><span data-stu-id="d7810-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="d7810-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="d7810-188">bit</span><span class="sxs-lookup"><span data-stu-id="d7810-188">bit</span></span></p></td>
<td><p><span data-ttu-id="d7810-189">発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7810-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="d7810-190">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="d7810-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7810-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7810-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7810-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7810-193">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="d7810-193">IP address of the callee.</span></span> <span data-ttu-id="d7810-194">これは IPv4 または IPv6 のアドレスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7810-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="d7810-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="d7810-196">int</span><span class="sxs-lookup"><span data-stu-id="d7810-196">int</span></span></p></td>
<td><p><span data-ttu-id="d7810-197">呼び出し先によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="d7810-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="d7810-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="d7810-199">bit</span><span class="sxs-lookup"><span data-stu-id="d7810-199">bit</span></span></p></td>
<td><p><span data-ttu-id="d7810-200">呼び出し先がエンタープライズネットワーク内にあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7810-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="d7810-201">1は、呼び出し先がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d7810-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="d7810-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="d7810-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-204">呼び出し先によって使用されるネットワークインターフェイスの MAC アドレスです。</span><span class="sxs-lookup"><span data-stu-id="d7810-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7810-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7810-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7810-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7810-207">呼び出し先によって使用される A/V エッジサービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="d7810-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="d7810-208">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7810-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d7810-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d7810-210">int</span><span class="sxs-lookup"><span data-stu-id="d7810-210">int</span></span></p></td>
<td><p><span data-ttu-id="d7810-211">呼び出し先によって使用される A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="d7810-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7810-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7810-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7810-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7810-214">A/V Edge サービスによって報告された呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="d7810-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="d7810-215">このアドレスは、クライアントが NAT の背後にある場合など、CalleeIPAddr と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7810-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-216">Calleecapdev</span><span class="sxs-lookup"><span data-stu-id="d7810-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d7810-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7810-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7810-218">呼び出し先のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="d7810-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-219">Calle・ Enderdev</span><span class="sxs-lookup"><span data-stu-id="d7810-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d7810-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-221">呼び出し先のレンダリングデバイス名。</span><span class="sxs-lookup"><span data-stu-id="d7810-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-222">Calleecapdevdriver</span><span class="sxs-lookup"><span data-stu-id="d7810-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7810-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-224">呼び出し先のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="d7810-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7810-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7810-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-227">呼び出し先のレンダリングデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="d7810-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="d7810-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="d7810-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-230">呼び出し先の Wifi ドライバーの説明。</span><span class="sxs-lookup"><span data-stu-id="d7810-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="d7810-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="d7810-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="d7810-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="d7810-233">呼び出し先の Wifi ドライバーバージョン。</span><span class="sxs-lookup"><span data-stu-id="d7810-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d7810-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="d7810-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-236">呼び出し先のネットワーク接続の詳細。</span><span class="sxs-lookup"><span data-stu-id="d7810-236">Details of callee’s network connection.</span></span> <span data-ttu-id="d7810-237">詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での Networkconnectiondetail の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7810-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="d7810-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="d7810-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-240">呼び出し先の WiFi 接続で使用される基本サービスセット識別子。</span><span class="sxs-lookup"><span data-stu-id="d7810-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="d7810-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="d7810-242">bit</span><span class="sxs-lookup"><span data-stu-id="d7810-242">bit</span></span></p></td>
<td><p><span data-ttu-id="d7810-243">呼び出し先が仮想プライベートネットワーク経由で接続されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7810-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="d7810-244">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="d7810-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="d7810-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="d7810-246">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d7810-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d7810-247">オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="d7810-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="d7810-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="d7810-249">int</span><span class="sxs-lookup"><span data-stu-id="d7810-249">int</span></span></p></td>
<td><p><span data-ttu-id="d7810-250">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) によって指定された send side stream に適用される実際の帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="d7810-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="d7810-251">これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d7810-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="d7810-252">これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</span><span class="sxs-lookup"><span data-stu-id="d7810-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="d7810-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="d7810-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7810-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7810-255">適用される帯域幅キャップのソース。</span><span class="sxs-lookup"><span data-stu-id="d7810-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="d7810-256">帯域幅の制限の対象となる場所 (たとえば、"Policy Server"、"TURN Server"、"モダリティ" など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7810-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-257">[発信者]</span><span class="sxs-lookup"><span data-stu-id="d7810-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="d7810-258">bit</span><span class="sxs-lookup"><span data-stu-id="d7810-258">bit</span></span></p></td>
<td><p><span data-ttu-id="d7810-259">呼び出し元からのメトリックが受信されたかどうかを示します。1は yes、0はいいえ。</span><span class="sxs-lookup"><span data-stu-id="d7810-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-260">[呼び出し先]</span><span class="sxs-lookup"><span data-stu-id="d7810-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="d7810-261">bit</span><span class="sxs-lookup"><span data-stu-id="d7810-261">bit</span></span></p></td>
<td><p><span data-ttu-id="d7810-262">通話レシーバーからのメトリックが受信されたかどうかを示します。1は yes、0はいいえ。</span><span class="sxs-lookup"><span data-stu-id="d7810-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="d7810-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="d7810-264">bit</span><span class="sxs-lookup"><span data-stu-id="d7810-264">bit</span></span></p></td>
<td><p><span data-ttu-id="d7810-265">レポートが通話の一部であるか、または完了しているかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7810-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="d7810-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="d7810-267">bit</span><span class="sxs-lookup"><span data-stu-id="d7810-267">bit</span></span></p></td>
<td><p><span data-ttu-id="d7810-268">通話が低品質通話 (1) として分類されたか、または良好な通話 (0) であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7810-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7810-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="d7810-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="d7810-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7810-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7810-271">発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7810-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7810-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="d7810-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="d7810-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7810-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7810-274">ユーザーが ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7810-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

