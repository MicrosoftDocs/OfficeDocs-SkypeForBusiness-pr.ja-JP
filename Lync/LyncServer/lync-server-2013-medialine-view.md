---
title: 'Lync Server 2013: MediaLine ビュー'
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
ms.openlocfilehash: 5c6e5fd3c1afe27bc1baa8790527ee239bdba990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="e99a6-102">Lync Server 2013 の MediaLine ビュー</span><span class="sxs-lookup"><span data-stu-id="e99a6-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e99a6-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e99a6-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e99a6-104">メディア ライン ビューは、各メディア ラインに関する情報をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="e99a6-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="e99a6-105">通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e99a6-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="e99a6-106">また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="e99a6-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="e99a6-107">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e99a6-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e99a6-108">列</span><span class="sxs-lookup"><span data-stu-id="e99a6-108">Column</span></span></th>
<th><span data-ttu-id="e99a6-109">データ型</span><span class="sxs-lookup"><span data-stu-id="e99a6-109">Data Type</span></span></th>
<th><span data-ttu-id="e99a6-110">詳細</span><span class="sxs-lookup"><span data-stu-id="e99a6-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="e99a6-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="e99a6-112">日付型</span><span class="sxs-lookup"><span data-stu-id="e99a6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e99a6-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e99a6-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e99a6-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e99a6-115">int</span><span class="sxs-lookup"><span data-stu-id="e99a6-115">int</span></span></p></td>
<td><p><span data-ttu-id="e99a6-116"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e99a6-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="e99a6-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="e99a6-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="e99a6-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e99a6-119"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e99a6-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e99a6-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e99a6-121">int</span><span class="sxs-lookup"><span data-stu-id="e99a6-121">int</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p102">発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e99a6-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e99a6-125">int</span><span class="sxs-lookup"><span data-stu-id="e99a6-125">int</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p103">受信者についてビット フラグで記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-128">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e99a6-128">Security</span></span></p></td>
<td><p><span data-ttu-id="e99a6-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="e99a6-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p104">使用するセキュリティ プロファイル。0 は NONE、1 は SRTP、2 は V1 です。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-132">Transport</span><span class="sxs-lookup"><span data-stu-id="e99a6-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="e99a6-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="e99a6-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p105">トランスポートの種類。0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e99a6-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e99a6-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="e99a6-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p106">発信者の IP アドレス。IPv4 アドレスまたは IPv6 アドレスです。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e99a6-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e99a6-141">int</span><span class="sxs-lookup"><span data-stu-id="e99a6-141">int</span></span></p></td>
<td><p><span data-ttu-id="e99a6-142">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="e99a6-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e99a6-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e99a6-144">若干</span><span class="sxs-lookup"><span data-stu-id="e99a6-144">bit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p107">発信者が組織のネットワーク内に存在するかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示します。0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="e99a6-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="e99a6-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-150">発信者が使用するネットワーク インターフェイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="e99a6-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e99a6-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e99a6-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="e99a6-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-153">発信者が使用する音声ビデオ エッジ サービスの IPアドレス。</span><span class="sxs-lookup"><span data-stu-id="e99a6-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e99a6-154">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99a6-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e99a6-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e99a6-156">int</span><span class="sxs-lookup"><span data-stu-id="e99a6-156">int</span></span></p></td>
<td><p><span data-ttu-id="e99a6-157">発信者が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="e99a6-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="e99a6-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e99a6-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="e99a6-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-160">音声ビデオ エッジ サービスからレポートされる発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e99a6-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="e99a6-161">クライアントが NAT の背後にある場合など、このアドレスが CallerIPAddr と異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="e99a6-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e99a6-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e99a6-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-164">発信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="e99a6-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e99a6-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e99a6-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-167">発信者のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="e99a6-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e99a6-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e99a6-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-170">発信者のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="e99a6-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e99a6-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e99a6-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-173">発信者のレンダー デバイスのドライバー名。</span><span class="sxs-lookup"><span data-stu-id="e99a6-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="e99a6-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="e99a6-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="e99a6-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="e99a6-176">発信者の WiFi ドライバーの説明。</span><span class="sxs-lookup"><span data-stu-id="e99a6-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="e99a6-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="e99a6-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-179">発信者の WiFi ドライバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="e99a6-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="e99a6-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="e99a6-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-182">発信者のネットワーク接続の詳細。</span><span class="sxs-lookup"><span data-stu-id="e99a6-182">Details of caller’s network connection.</span></span> <span data-ttu-id="e99a6-183">詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99a6-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="e99a6-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="e99a6-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-186">発信者の WiFi 接続で使用する基本サービス セット識別子。</span><span class="sxs-lookup"><span data-stu-id="e99a6-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e99a6-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e99a6-188">若干</span><span class="sxs-lookup"><span data-stu-id="e99a6-188">bit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p111">発信者が仮想プライベート ネットワーク経由で接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e99a6-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e99a6-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="e99a6-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-193">通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e99a6-193">IP address of the callee.</span></span> <span data-ttu-id="e99a6-194">IPv4 アドレスまたは IPv6 アドレスです。</span><span class="sxs-lookup"><span data-stu-id="e99a6-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e99a6-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e99a6-196">int</span><span class="sxs-lookup"><span data-stu-id="e99a6-196">int</span></span></p></td>
<td><p><span data-ttu-id="e99a6-197">呼び出し先が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="e99a6-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e99a6-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e99a6-199">若干</span><span class="sxs-lookup"><span data-stu-id="e99a6-199">bit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p113">通話受信者がエンタープライズ ネットワーク内に存在するかどうかを示します。1 は、通話受信者がエンタープライズ ネットワーク内に存在することを示し、0 は、通話受信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="e99a6-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="e99a6-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-204">通話受信者が使用するネットワーク インターフェイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="e99a6-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e99a6-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e99a6-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="e99a6-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-207">通話受信者が使用する音声ビデオ エッジ サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e99a6-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e99a6-208">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99a6-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e99a6-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e99a6-210">int</span><span class="sxs-lookup"><span data-stu-id="e99a6-210">int</span></span></p></td>
<td><p><span data-ttu-id="e99a6-211">通話受信者が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="e99a6-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="e99a6-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e99a6-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="e99a6-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-214">音声ビデオ エッジ サービスからレポートされる通話受信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e99a6-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="e99a6-215">クライアントが NAT の背後にある場合など、このアドレスが CalleeIPAddr と異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="e99a6-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-216">Calleecapのアーキテクチャ開発</span><span class="sxs-lookup"><span data-stu-id="e99a6-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e99a6-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="e99a6-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-218">通話受信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="e99a6-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e99a6-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e99a6-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-221">呼び出し先のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="e99a6-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-222">Calleecapアーキテクチャ Devdriver</span><span class="sxs-lookup"><span data-stu-id="e99a6-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e99a6-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-224">呼び出し先のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="e99a6-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e99a6-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e99a6-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-227">通話受信者のレンダー デバイスのドライバー名。</span><span class="sxs-lookup"><span data-stu-id="e99a6-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="e99a6-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="e99a6-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-230">通話受信者の WiFi ドライバーの説明。</span><span class="sxs-lookup"><span data-stu-id="e99a6-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="e99a6-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="e99a6-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="e99a6-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="e99a6-233">通話受信者の WiFi ドライバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="e99a6-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="e99a6-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="e99a6-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-236">通話受信者のネットワーク接続の詳細。</span><span class="sxs-lookup"><span data-stu-id="e99a6-236">Details of callee’s network connection.</span></span> <span data-ttu-id="e99a6-237">詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99a6-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="e99a6-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="e99a6-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-240">通話受信者の WiFi 接続で使用する基本サービス セット識別子。</span><span class="sxs-lookup"><span data-stu-id="e99a6-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e99a6-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e99a6-242">若干</span><span class="sxs-lookup"><span data-stu-id="e99a6-242">bit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p117">通話受信者が仮想プライベート ネットワーク経由で接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e99a6-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e99a6-246">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="e99a6-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-247">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="e99a6-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e99a6-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-249">int</span><span class="sxs-lookup"><span data-stu-id="e99a6-249">int</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p118">これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅です。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="e99a6-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="e99a6-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e99a6-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e99a6-p119">適用されている帯域幅制限のソースです。帯域幅制限の適用元を示します ("Policy Server"、"TURN Server"、"Modality" など)。</span><span class="sxs-lookup"><span data-stu-id="e99a6-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-257">Caller</span><span class="sxs-lookup"><span data-stu-id="e99a6-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="e99a6-258">若干</span><span class="sxs-lookup"><span data-stu-id="e99a6-258">bit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-259">発信者からの指標が受信されたかどうかを示します。1 は "はい"、0 は "いいえ" です。</span><span class="sxs-lookup"><span data-stu-id="e99a6-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-260">側</span><span class="sxs-lookup"><span data-stu-id="e99a6-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="e99a6-261">若干</span><span class="sxs-lookup"><span data-stu-id="e99a6-261">bit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-262">通話受信者からの指標が受信されたかどうかを示します。1 は "はい"、0 は "いいえ" です。</span><span class="sxs-lookup"><span data-stu-id="e99a6-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="e99a6-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="e99a6-264">若干</span><span class="sxs-lookup"><span data-stu-id="e99a6-264">bit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-265">レポートの対象が通話の一部か全部かを示します。</span><span class="sxs-lookup"><span data-stu-id="e99a6-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="e99a6-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="e99a6-267">若干</span><span class="sxs-lookup"><span data-stu-id="e99a6-267">bit</span></span></p></td>
<td><p><span data-ttu-id="e99a6-268">通話が低品質通話 (1) と高品質通話 (0) のどちらに分類されたかを示します。</span><span class="sxs-lookup"><span data-stu-id="e99a6-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e99a6-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="e99a6-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="e99a6-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="e99a6-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e99a6-271">発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e99a6-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e99a6-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="e99a6-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="e99a6-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="e99a6-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e99a6-274">通話受信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e99a6-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

