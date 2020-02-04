---
title: 'Lync Server 2013: IP アドレス タイプの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="27899-102">Lync Server 2013 の IP アドレス タイプの概要</span><span class="sxs-lookup"><span data-stu-id="27899-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27899-103">_**最終更新日:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="27899-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="27899-104">Lync Server 2013 で IP アドレスを構成する際には、次の3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="27899-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="27899-105">Lync Server 2013 は、IP バージョン 4 (IPv4)、IP バージョン 6 (IPv6)、またはその両方の組み合わせ (*デュアルスタック*とも呼ばれます) をサポートするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="27899-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="27899-106">各種の構成には、いくつか考慮すべき問題があります。</span><span class="sxs-lookup"><span data-stu-id="27899-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="27899-107">**Ipv4 のみ**   ipv4 アドレスが不足しているため、IPv6 のみが作成されました。</span><span class="sxs-lookup"><span data-stu-id="27899-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="27899-108">最終的には、IPv6 は世界中で完全にサポートされますが、現時点では、企業が通信する必要がある多くの会社やデバイスは IPv6 をサポートしていませんが、しばらくの間、そうでない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27899-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="27899-109">IPv4 のみの構成は、Lync Server の実装が、既存のほとんどのデバイスと通信できるようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="27899-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="27899-110">**Ipv6 のみ**   逆に、現時点では ipv6 の完全な実装であるため、多くの既存のデバイスとの通信は除外されます。</span><span class="sxs-lookup"><span data-stu-id="27899-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="27899-111">**デュアルスタック**   デュアルスタックは、IPv4 アドレスと IPv6 アドレスの両方が有効になっているネットワークです。</span><span class="sxs-lookup"><span data-stu-id="27899-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="27899-112">この構成は Lync Server 2013 でサポートされているため、ほとんどの場合、フル IPv4 からフル-IPv6 への移行は数年で完了します。</span><span class="sxs-lookup"><span data-stu-id="27899-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="27899-113">以下のセクションでは、Lync Server のさまざまな機能について、これらの3つの構成の互換性についての概要を示します。</span><span class="sxs-lookup"><span data-stu-id="27899-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27899-p104">クライアントまたはサーバーを IPv6 のみの構成にすることは、試験や検証の目的でのみサポートされています。IPv6 のみの構成は運用展開ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27899-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="27899-116">クライアントの登録</span><span class="sxs-lookup"><span data-stu-id="27899-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27899-117">クライアント エンドポイント ネットワーク</span><span class="sxs-lookup"><span data-stu-id="27899-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="27899-118">サーバー ネットワーク</span><span class="sxs-lookup"><span data-stu-id="27899-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27899-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="27899-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="27899-122">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-123">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-125">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-126">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-127">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="27899-130">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="27899-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="27899-133">ピアツーピア クライアント</span><span class="sxs-lookup"><span data-stu-id="27899-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="27899-p105">ピアツーピア通信には、オーディオ、音声ビデオ、アプリケーション共有、ファイル転送などがあります。両方のクライアントが正常に登録された後、次の組み合わせがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="27899-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27899-136">クライアント エンドポイント 1</span><span class="sxs-lookup"><span data-stu-id="27899-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="27899-137">クライアント エンドポイント 2</span><span class="sxs-lookup"><span data-stu-id="27899-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27899-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="27899-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="27899-141">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-142">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-143">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="27899-145">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="27899-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="27899-148">会議</span><span class="sxs-lookup"><span data-stu-id="27899-148">Conferencing</span></span>

<span data-ttu-id="27899-149">会議には、音声/ビデオ、アプリケーション共有、データコラボレーション (whiteboarding とファイル共有) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27899-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27899-150">クライアント エンドポイント ネットワーク</span><span class="sxs-lookup"><span data-stu-id="27899-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="27899-151">サーバー ネットワーク</span><span class="sxs-lookup"><span data-stu-id="27899-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27899-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="27899-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="27899-155">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-156">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-158">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-159">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-160">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="27899-163">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="27899-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="27899-166">仲介サーバー/PSTN</span><span class="sxs-lookup"><span data-stu-id="27899-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="27899-167">トラフィックが IPv6 インターフェイスを通過している場合、Lync Server 2013 は、公衆交換電話網 (PSTN) 通話のメディアバイパスをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="27899-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="27899-168">メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27899-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27899-169">プライマリ インターフェイス\*</span><span class="sxs-lookup"><span data-stu-id="27899-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="27899-170">PSTN インターフェイス (仲介サーバー上)</span><span class="sxs-lookup"><span data-stu-id="27899-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="27899-171">PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="27899-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27899-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="27899-173">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-175">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-176">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-178">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-179">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27899-181">\*プライマリインターフェイスは、Lync Server コンポーネントと通信するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="27899-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="27899-182">リモート ユーザーのピアツーピア通信</span><span class="sxs-lookup"><span data-stu-id="27899-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="27899-183">リモート ユーザーとのピアツーピア通信には、インスタント メッセージング、音声ビデオ、アプリケーション共有、およびファイル転送が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27899-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27899-184">リモート ユーザー ネットワーク</span><span class="sxs-lookup"><span data-stu-id="27899-184">Remote user network</span></span></th>
<th><span data-ttu-id="27899-185">エッジ サーバー (外部エッジ)</span><span class="sxs-lookup"><span data-stu-id="27899-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27899-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="27899-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-188">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="27899-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-190">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="27899-191">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="27899-193">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="27899-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="27899-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="27899-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="27899-196">フロントエンド プールとエッジ プールの構成</span><span class="sxs-lookup"><span data-stu-id="27899-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="27899-197">次の表は、フロントエンドサーバープールと内部エッジサーバープールの間のサポートマトリックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="27899-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="27899-198">フロントエンド プールとエッジ プール (内部エッジ) のマトリックス</span><span class="sxs-lookup"><span data-stu-id="27899-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="27899-199"><strong>エッジ プール: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="27899-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-200"><strong>エッジ プール: デュアル スタック</strong></span><span class="sxs-lookup"><span data-stu-id="27899-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-201"><strong>エッジ プール: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="27899-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-202"><strong>フロントエンド プール: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="27899-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-203">はい</span><span class="sxs-lookup"><span data-stu-id="27899-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="27899-204">あり</span><span class="sxs-lookup"><span data-stu-id="27899-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="27899-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="27899-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-206"><strong>フロントエンド プール: デュアル スタック</strong></span><span class="sxs-lookup"><span data-stu-id="27899-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-207">はい</span><span class="sxs-lookup"><span data-stu-id="27899-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="27899-208">はい</span><span class="sxs-lookup"><span data-stu-id="27899-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="27899-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="27899-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-210"><strong>フロントエンド プール: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="27899-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-211">なし</span><span class="sxs-lookup"><span data-stu-id="27899-211">No</span></span></p></td>
<td><p><span data-ttu-id="27899-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="27899-212">No</span></span></p></td>
<td><p><span data-ttu-id="27899-213">はい\*</span><span class="sxs-lookup"><span data-stu-id="27899-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27899-214">\*この組み合わせは、ラボ環境でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="27899-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="27899-215">次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。</span><span class="sxs-lookup"><span data-stu-id="27899-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="27899-216">エッジ プール (内部エッジ) とエッジ プール (外部エッジ) のマトリックス</span><span class="sxs-lookup"><span data-stu-id="27899-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="27899-217"><strong>エッジ プール (外部エッジ): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="27899-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-218"><strong>エッジ プール (外部エッジ): デュアル スタック</strong></span><span class="sxs-lookup"><span data-stu-id="27899-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-219"><strong>エッジ プール (外部エッジ): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="27899-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-220"><strong>エッジ プール (内部エッジ): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="27899-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-221">はい</span><span class="sxs-lookup"><span data-stu-id="27899-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="27899-222">はい</span><span class="sxs-lookup"><span data-stu-id="27899-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="27899-223">いいえ</span><span class="sxs-lookup"><span data-stu-id="27899-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27899-224"><strong>エッジ プール (内部エッジ): デュアル スタック</strong></span><span class="sxs-lookup"><span data-stu-id="27899-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="27899-225">No</span></span></p></td>
<td><p><span data-ttu-id="27899-226">あり</span><span class="sxs-lookup"><span data-stu-id="27899-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="27899-227">いいえ</span><span class="sxs-lookup"><span data-stu-id="27899-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27899-228"><strong>エッジ プール (内部エッジ): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="27899-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="27899-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="27899-229">No</span></span></p></td>
<td><p><span data-ttu-id="27899-230">いいえ</span><span class="sxs-lookup"><span data-stu-id="27899-230">No</span></span></p></td>
<td><p><span data-ttu-id="27899-231">はい\*</span><span class="sxs-lookup"><span data-stu-id="27899-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27899-232">\*この組み合わせは、ラボ環境でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="27899-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="27899-233">IPv6 の高度なエンタープライズ VoIP のサポート</span><span class="sxs-lookup"><span data-stu-id="27899-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="27899-234">通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27899-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27899-235">デュアルスタック展開では、Lync クライアントが IPv6 を使って Lync サーバーに接続している場合でも、Lync では、E9-1 をサポートする適切な IPv4 アドレスをマッピングすることが最善に行われます。</span><span class="sxs-lookup"><span data-stu-id="27899-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="27899-236">IPv6 アドレスを使用した位置情報サービスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27899-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="27899-p107">Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27899-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="27899-240">IPv6 向けのその他の Lync Server 2013 機能のサポート</span><span class="sxs-lookup"><span data-stu-id="27899-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="27899-241">前に説明した機能とコンポーネントに加えて、Lync Server 2013 では、次の機能の IPv6 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="27899-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="27899-242">**常設チャット**</span><span class="sxs-lookup"><span data-stu-id="27899-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="27899-243">"トポロジビルダー" を使用して、常設チャットの IPv6 を構成します。</span><span class="sxs-lookup"><span data-stu-id="27899-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="27899-244">常設チャットの設定の詳細については、「常設チャットサーバーのマニュアルの展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27899-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="27899-245">**Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**</span><span class="sxs-lookup"><span data-stu-id="27899-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="27899-246">IPv4 と IPv6 のいずれの場合でも、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。</span><span class="sxs-lookup"><span data-stu-id="27899-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

