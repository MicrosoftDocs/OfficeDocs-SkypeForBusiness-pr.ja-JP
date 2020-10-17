---
title: 'Lync Server 2013: MediaLine ビュー'
description: 'Lync Server 2013: MediaLine ビュー。'
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
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568683"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="fffca-103">Lync Server 2013 の MediaLine ビュー</span><span class="sxs-lookup"><span data-stu-id="fffca-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fffca-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fffca-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fffca-105">メディア ライン ビューは、各メディア ラインに関する情報をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="fffca-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="fffca-106">通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fffca-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="fffca-107">また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="fffca-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="fffca-108">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fffca-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fffca-109">Column</span><span class="sxs-lookup"><span data-stu-id="fffca-109">Column</span></span></th>
<th><span data-ttu-id="fffca-110">データ型</span><span class="sxs-lookup"><span data-stu-id="fffca-110">Data Type</span></span></th>
<th><span data-ttu-id="fffca-111">詳細</span><span class="sxs-lookup"><span data-stu-id="fffca-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fffca-112">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="fffca-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="fffca-113">日付型</span><span class="sxs-lookup"><span data-stu-id="fffca-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="fffca-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="fffca-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="fffca-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="fffca-116">int</span><span class="sxs-lookup"><span data-stu-id="fffca-116">int</span></span></p></td>
<td><p><span data-ttu-id="fffca-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="fffca-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="fffca-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="fffca-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="fffca-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fffca-120"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="fffca-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="fffca-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="fffca-122">int</span><span class="sxs-lookup"><span data-stu-id="fffca-122">int</span></span></p></td>
<td><p><span data-ttu-id="fffca-p102">発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fffca-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="fffca-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="fffca-126">int</span><span class="sxs-lookup"><span data-stu-id="fffca-126">int</span></span></p></td>
<td><p><span data-ttu-id="fffca-p103">受信者についてビット フラグで記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fffca-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-129">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="fffca-129">Security</span></span></p></td>
<td><p><span data-ttu-id="fffca-130">tinyint</span><span class="sxs-lookup"><span data-stu-id="fffca-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fffca-p104">使用するセキュリティ プロファイル。0 は NONE、1 は SRTP、2 は V1 です。</span><span class="sxs-lookup"><span data-stu-id="fffca-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-133">Transport</span><span class="sxs-lookup"><span data-stu-id="fffca-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="fffca-134">tinyint</span><span class="sxs-lookup"><span data-stu-id="fffca-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fffca-p105">トランスポートの種類。0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="fffca-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="fffca-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fffca-138">var (50)</span><span class="sxs-lookup"><span data-stu-id="fffca-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fffca-p106">発信者の IP アドレス。IPv4 アドレスまたは IPv6 アドレスです。</span><span class="sxs-lookup"><span data-stu-id="fffca-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="fffca-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="fffca-142">int</span><span class="sxs-lookup"><span data-stu-id="fffca-142">int</span></span></p></td>
<td><p><span data-ttu-id="fffca-143">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="fffca-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="fffca-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="fffca-145">若干</span><span class="sxs-lookup"><span data-stu-id="fffca-145">bit</span></span></p></td>
<td><p><span data-ttu-id="fffca-p107">発信者が組織のネットワーク内に存在するかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示します。0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="fffca-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-149">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="fffca-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="fffca-150">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-151">発信者が使用するネットワーク インターフェイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="fffca-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="fffca-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fffca-153">var (50)</span><span class="sxs-lookup"><span data-stu-id="fffca-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fffca-154">発信者が使用する音声ビデオ エッジ サービスの IPアドレス。</span><span class="sxs-lookup"><span data-stu-id="fffca-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="fffca-155">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fffca-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="fffca-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="fffca-157">int</span><span class="sxs-lookup"><span data-stu-id="fffca-157">int</span></span></p></td>
<td><p><span data-ttu-id="fffca-158">発信者が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="fffca-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="fffca-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fffca-160">var (50)</span><span class="sxs-lookup"><span data-stu-id="fffca-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fffca-161">音声ビデオ エッジ サービスからレポートされる発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fffca-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="fffca-162">クライアントが NAT の背後にある場合など、このアドレスが CallerIPAddr と異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="fffca-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="fffca-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="fffca-164">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-165">発信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="fffca-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="fffca-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="fffca-167">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-168">発信者のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="fffca-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="fffca-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="fffca-170">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-171">発信者のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="fffca-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="fffca-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="fffca-173">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-174">発信者のレンダー デバイスのドライバー名。</span><span class="sxs-lookup"><span data-stu-id="fffca-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="fffca-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="fffca-176">varchar (256</span><span class="sxs-lookup"><span data-stu-id="fffca-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="fffca-177">発信者の WiFi ドライバーの説明。</span><span class="sxs-lookup"><span data-stu-id="fffca-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="fffca-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="fffca-179">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-180">発信者の WiFi ドライバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="fffca-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="fffca-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="fffca-182">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-183">発信者のネットワーク接続の詳細。</span><span class="sxs-lookup"><span data-stu-id="fffca-183">Details of caller’s network connection.</span></span> <span data-ttu-id="fffca-184">詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fffca-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="fffca-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="fffca-186">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-187">発信者の WiFi 接続で使用する基本サービス セット識別子。</span><span class="sxs-lookup"><span data-stu-id="fffca-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="fffca-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="fffca-189">若干</span><span class="sxs-lookup"><span data-stu-id="fffca-189">bit</span></span></p></td>
<td><p><span data-ttu-id="fffca-p111">発信者が仮想プライベート ネットワーク経由で接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="fffca-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="fffca-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fffca-193">var (50)</span><span class="sxs-lookup"><span data-stu-id="fffca-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fffca-194">通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fffca-194">IP address of the callee.</span></span> <span data-ttu-id="fffca-195">IPv4 アドレスまたは IPv6 アドレスです。</span><span class="sxs-lookup"><span data-stu-id="fffca-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="fffca-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="fffca-197">int</span><span class="sxs-lookup"><span data-stu-id="fffca-197">int</span></span></p></td>
<td><p><span data-ttu-id="fffca-198">呼び出し先が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="fffca-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="fffca-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="fffca-200">若干</span><span class="sxs-lookup"><span data-stu-id="fffca-200">bit</span></span></p></td>
<td><p><span data-ttu-id="fffca-p113">通話受信者がエンタープライズ ネットワーク内に存在するかどうかを示します。1 は、通話受信者がエンタープライズ ネットワーク内に存在することを示し、0 は、通話受信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="fffca-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="fffca-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="fffca-204">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-205">通話受信者が使用するネットワーク インターフェイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="fffca-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="fffca-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fffca-207">var (50)</span><span class="sxs-lookup"><span data-stu-id="fffca-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fffca-208">通話受信者が使用する音声ビデオ エッジ サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fffca-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="fffca-209">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fffca-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="fffca-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="fffca-211">int</span><span class="sxs-lookup"><span data-stu-id="fffca-211">int</span></span></p></td>
<td><p><span data-ttu-id="fffca-212">通話受信者が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="fffca-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-213">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="fffca-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fffca-214">var (50)</span><span class="sxs-lookup"><span data-stu-id="fffca-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fffca-215">音声ビデオ エッジ サービスからレポートされる通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fffca-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="fffca-216">クライアントが NAT の背後にある場合など、このアドレスが CalleeIPAddr と異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="fffca-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-217">Calleecapのアーキテクチャ開発</span><span class="sxs-lookup"><span data-stu-id="fffca-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="fffca-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="fffca-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fffca-219">通話受信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="fffca-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="fffca-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="fffca-221">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-222">呼び出し先のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="fffca-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-223">Calleecapアーキテクチャ Devdriver</span><span class="sxs-lookup"><span data-stu-id="fffca-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="fffca-224">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-225">呼び出し先のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="fffca-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="fffca-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="fffca-227">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-228">通話受信者のレンダー デバイスのドライバー名。</span><span class="sxs-lookup"><span data-stu-id="fffca-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="fffca-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="fffca-230">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-231">通話受信者の WiFi ドライバーの説明。</span><span class="sxs-lookup"><span data-stu-id="fffca-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="fffca-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="fffca-233">varchar (256</span><span class="sxs-lookup"><span data-stu-id="fffca-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="fffca-234">通話受信者の WiFi ドライバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="fffca-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="fffca-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="fffca-236">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-237">通話受信者のネットワーク接続の詳細。</span><span class="sxs-lookup"><span data-stu-id="fffca-237">Details of callee’s network connection.</span></span> <span data-ttu-id="fffca-238">詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fffca-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="fffca-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="fffca-240">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-241">通話受信者の WiFi 接続で使用する基本サービス セット識別子。</span><span class="sxs-lookup"><span data-stu-id="fffca-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="fffca-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="fffca-243">若干</span><span class="sxs-lookup"><span data-stu-id="fffca-243">bit</span></span></p></td>
<td><p><span data-ttu-id="fffca-p117">通話受信者が仮想プライベート ネットワーク経由で接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="fffca-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="fffca-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="fffca-247">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="fffca-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="fffca-248">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="fffca-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="fffca-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="fffca-250">int</span><span class="sxs-lookup"><span data-stu-id="fffca-250">int</span></span></p></td>
<td><p><span data-ttu-id="fffca-p118">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅です。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</span><span class="sxs-lookup"><span data-stu-id="fffca-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="fffca-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="fffca-255">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fffca-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fffca-p119">適用されている帯域幅制限のソースです。帯域幅制限の適用元を示します ("Policy Server"、"TURN Server"、"Modality" など)。</span><span class="sxs-lookup"><span data-stu-id="fffca-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-258">Caller</span><span class="sxs-lookup"><span data-stu-id="fffca-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="fffca-259">若干</span><span class="sxs-lookup"><span data-stu-id="fffca-259">bit</span></span></p></td>
<td><p><span data-ttu-id="fffca-260">発信者からの指標が受信されたかどうかを示します。1 は "はい"、0 は "いいえ" です。</span><span class="sxs-lookup"><span data-stu-id="fffca-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-261">側</span><span class="sxs-lookup"><span data-stu-id="fffca-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="fffca-262">若干</span><span class="sxs-lookup"><span data-stu-id="fffca-262">bit</span></span></p></td>
<td><p><span data-ttu-id="fffca-263">通話受信者からの指標が受信されたかどうかを示します。1 は "はい"、0 は "いいえ" です。</span><span class="sxs-lookup"><span data-stu-id="fffca-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="fffca-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="fffca-265">若干</span><span class="sxs-lookup"><span data-stu-id="fffca-265">bit</span></span></p></td>
<td><p><span data-ttu-id="fffca-266">レポートの対象が通話の一部か全部かを示します。</span><span class="sxs-lookup"><span data-stu-id="fffca-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="fffca-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="fffca-268">若干</span><span class="sxs-lookup"><span data-stu-id="fffca-268">bit</span></span></p></td>
<td><p><span data-ttu-id="fffca-269">通話が低品質通話 (1) と高品質通話 (0) のどちらに分類されたかを示します。</span><span class="sxs-lookup"><span data-stu-id="fffca-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fffca-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="fffca-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="fffca-271">tinyint</span><span class="sxs-lookup"><span data-stu-id="fffca-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fffca-272">発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fffca-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fffca-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="fffca-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="fffca-274">tinyint</span><span class="sxs-lookup"><span data-stu-id="fffca-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fffca-275">通話受信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fffca-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

