---
title: 'Lync Server 2013: IP アドレスの種類の概要'
description: 'Lync Server 2013: IP アドレスの種類の概要。'
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
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559223"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="ace55-103">Lync Server 2013 の IP アドレスの種類の概要</span><span class="sxs-lookup"><span data-stu-id="ace55-103">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ace55-104">_**トピックの最終更新日:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="ace55-104">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="ace55-105">Lync Server 2013 で IP アドレスを構成する場合、3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ace55-105">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="ace55-106">Lync Server 2013 は、IP バージョン 4 (IPv4)、IP バージョン 6 (IPv6) のみ、または両方の組み合わせ ( *デュアルスタック*とも呼ばれます) をサポートするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="ace55-106">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="ace55-107">各構成には、いくつか考慮すべき問題があります。</span><span class="sxs-lookup"><span data-stu-id="ace55-107">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="ace55-108">**IPv4 のみ**    世界で IPv4 アドレスが不足しているため、IPv6 が作成されました。</span><span class="sxs-lookup"><span data-stu-id="ace55-108">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="ace55-109">最終的には、IPv6 は完全にサポートされていますが、現時点では、企業が通信する必要がある多くの企業やデバイスが IPv6 をサポートしていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ace55-109">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="ace55-110">IPv4 のみの構成は、Lync Server の実装が、ほとんどの既存のデバイスと通信できるようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ace55-110">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="ace55-111">**IPv6 のみ**    反対に、完全な IPv6 実装では、この時点で、多くの既存のデバイスとの通信が除外されます。</span><span class="sxs-lookup"><span data-stu-id="ace55-111">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="ace55-112">**デュアルスタック**    デュアルスタックは、IPv4 と IPv6 の両方のアドレスが有効になっているネットワークです。</span><span class="sxs-lookup"><span data-stu-id="ace55-112">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="ace55-113">この構成は、Lync Server 2013 でサポートされています。ほとんどの場合、フル-IPv4 からフル-IPv6 への移行は数年かかります。</span><span class="sxs-lookup"><span data-stu-id="ace55-113">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="ace55-114">次のセクションでは、Lync Server のさまざまな機能について、これらの3つの構成の互換性について概説します。</span><span class="sxs-lookup"><span data-stu-id="ace55-114">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ace55-p104">クライアントまたはサーバーを IPv6 のみの構成にすることは、試験や検証の目的でのみサポートされています。IPv6 のみの構成は運用展開ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ace55-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="ace55-117">クライアントの登録</span><span class="sxs-lookup"><span data-stu-id="ace55-117">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ace55-118">クライアント エンドポイント ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ace55-118">Client endpoint network</span></span></th>
<th><span data-ttu-id="ace55-119">サーバー ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ace55-119">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ace55-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-120">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ace55-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-121">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-122">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-122">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ace55-123">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-123">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-124">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-124">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-125">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-125">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-126">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-126">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-127">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-127">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-128">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-128">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-129">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-130">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-130">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ace55-131">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-131">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-132">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ace55-133">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-133">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="ace55-134">ピアツーピア クライアント</span><span class="sxs-lookup"><span data-stu-id="ace55-134">Peer-to-Peer Client</span></span>

<span data-ttu-id="ace55-p105">ピアツーピア通信には、オーディオ、音声ビデオ、アプリケーション共有、ファイル転送などがあります。両方のクライアントが正常に登録された後、次の組み合わせがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ace55-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ace55-137">クライアント エンドポイント 1</span><span class="sxs-lookup"><span data-stu-id="ace55-137">Client endpoint 1</span></span></th>
<th><span data-ttu-id="ace55-138">クライアント エンドポイント 2</span><span class="sxs-lookup"><span data-stu-id="ace55-138">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ace55-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-139">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ace55-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-140">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-141">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-141">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ace55-142">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-142">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-143">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-143">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-144">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-144">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-145">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ace55-146">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-146">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-147">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ace55-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-148">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="ace55-149">会議</span><span class="sxs-lookup"><span data-stu-id="ace55-149">Conferencing</span></span>

<span data-ttu-id="ace55-150">会議には、音声ビデオ、アプリケーション共有、およびデータ コラボレーション (ホワイト ボードとファイル共有) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ace55-150">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ace55-151">クライアント エンドポイント ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ace55-151">Client endpoint network</span></span></th>
<th><span data-ttu-id="ace55-152">サーバー ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ace55-152">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ace55-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-153">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ace55-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-154">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-155">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ace55-156">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-156">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-157">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-157">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-158">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-158">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-159">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-159">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-160">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-160">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-161">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-161">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-162">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-163">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ace55-164">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-164">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-165">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ace55-166">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-166">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="ace55-167">仲介サーバー/PSTN</span><span class="sxs-lookup"><span data-stu-id="ace55-167">Mediation Server/PSTN</span></span>

<span data-ttu-id="ace55-168">Lync Server 2013 は、トラフィックが IPv6 インターフェイスを経由している場合は、公衆交換電話網 (PSTN) 通話のメディアバイパスをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ace55-168">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="ace55-169">メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ace55-169">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ace55-170">プライマリ インターフェイス\*</span><span class="sxs-lookup"><span data-stu-id="ace55-170">Primary interface\*</span></span></th>
<th><span data-ttu-id="ace55-171">PSTN インターフェイス (仲介サーバー上)</span><span class="sxs-lookup"><span data-stu-id="ace55-171">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="ace55-172">PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="ace55-172">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ace55-173">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-173">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ace55-174">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-174">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-175">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-176">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-177">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-177">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-178">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-178">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-179">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-180">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-180">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-181">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-181">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ace55-182">\* プライマリインターフェイスは、Lync Server コンポーネントと通信するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="ace55-182">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="ace55-183">リモート ユーザーのピアツーピア通信</span><span class="sxs-lookup"><span data-stu-id="ace55-183">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="ace55-184">リモート ユーザーとのピアツーピア通信には、インスタント メッセージング、音声ビデオ、アプリケーション共有、およびファイル転送が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ace55-184">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ace55-185">リモート ユーザー ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ace55-185">Remote user network</span></span></th>
<th><span data-ttu-id="ace55-186">エッジ サーバー (外部エッジ)</span><span class="sxs-lookup"><span data-stu-id="ace55-186">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ace55-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-187">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ace55-188">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-188">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-189">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-189">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-190">IPv4</span><span class="sxs-lookup"><span data-stu-id="ace55-190">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-191">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-191">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ace55-192">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-192">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-193">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-193">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ace55-194">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="ace55-194">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-195">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ace55-196">IPv6</span><span class="sxs-lookup"><span data-stu-id="ace55-196">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="ace55-197">フロントエンド プールとエッジ プールの構成</span><span class="sxs-lookup"><span data-stu-id="ace55-197">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="ace55-198">次の表は、フロントエンドサーバープールと内部エッジサーバープールの間のサポートマトリックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="ace55-198">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="ace55-199">フロントエンド プールとエッジ プール (内部エッジ) のマトリックス</span><span class="sxs-lookup"><span data-stu-id="ace55-199">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="ace55-200"><strong>エッジ プール: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-200"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-201"><strong>エッジ プール: デュアル スタック</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-201"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-202"><strong>エッジ プール: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-202"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-203"><strong>フロントエンド プール: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-203"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-204">はい</span><span class="sxs-lookup"><span data-stu-id="ace55-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="ace55-205">必要</span><span class="sxs-lookup"><span data-stu-id="ace55-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="ace55-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-206">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-207"><strong>フロントエンド プール: デュアル スタック</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-207"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-208">はい</span><span class="sxs-lookup"><span data-stu-id="ace55-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="ace55-209">必要</span><span class="sxs-lookup"><span data-stu-id="ace55-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="ace55-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-210">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-211"><strong>フロントエンド プール: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-211"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-212">No</span></span></p></td>
<td><p><span data-ttu-id="ace55-213">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-213">No</span></span></p></td>
<td><p><span data-ttu-id="ace55-214">はい\*</span><span class="sxs-lookup"><span data-stu-id="ace55-214">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ace55-215">\* この組み合わせは、ラボ環境でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="ace55-215">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="ace55-216">次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。</span><span class="sxs-lookup"><span data-stu-id="ace55-216">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="ace55-217">エッジ プール (内部エッジ) とエッジ プール (外部エッジ) のマトリックス</span><span class="sxs-lookup"><span data-stu-id="ace55-217">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="ace55-218"><strong>エッジ プール (外部エッジ): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-218"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-219"><strong>エッジ プール (外部エッジ): デュアル スタック</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-219"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-220"><strong>エッジ プール (外部エッジ): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-220"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-221"><strong>エッジ プール (内部エッジ): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-221"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-222">はい</span><span class="sxs-lookup"><span data-stu-id="ace55-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="ace55-223">必要</span><span class="sxs-lookup"><span data-stu-id="ace55-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="ace55-224">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-224">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace55-225"><strong>エッジ プール (内部エッジ): デュアル スタック</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-225"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-226">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-226">No</span></span></p></td>
<td><p><span data-ttu-id="ace55-227">はい</span><span class="sxs-lookup"><span data-stu-id="ace55-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="ace55-228">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-228">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace55-229"><strong>エッジ プール (内部エッジ): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="ace55-229"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="ace55-230">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-230">No</span></span></p></td>
<td><p><span data-ttu-id="ace55-231">いいえ</span><span class="sxs-lookup"><span data-stu-id="ace55-231">No</span></span></p></td>
<td><p><span data-ttu-id="ace55-232">はい\*</span><span class="sxs-lookup"><span data-stu-id="ace55-232">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ace55-233">\* この組み合わせは、ラボ環境でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="ace55-233">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="ace55-234">IPv6 の高度なエンタープライズ VoIP のサポート</span><span class="sxs-lookup"><span data-stu-id="ace55-234">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="ace55-235">通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace55-235">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ace55-236">デュアルスタック展開では、lync クライアントが IPv6 を使用して Lync サーバーに接続している場合でも、Lync は E9-1-1 をサポートするために適切な IPv4 アドレスをマップするための最善の努力を行います。</span><span class="sxs-lookup"><span data-stu-id="ace55-236">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="ace55-237">IPv6 アドレスを使用した場所情報サービスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ace55-237">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="ace55-p107">Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ace55-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="ace55-241">その他の Lync Server 2013 機能の IPv6 のサポート</span><span class="sxs-lookup"><span data-stu-id="ace55-241">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="ace55-242">以前に説明した機能とコンポーネントに加えて、Lync Server 2013 は次の機能に対して IPv6 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ace55-242">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="ace55-243">**常設チャット**</span><span class="sxs-lookup"><span data-stu-id="ace55-243">**Persistent Chat**</span></span>
    
    <span data-ttu-id="ace55-244">常設チャットには、トポロジビルダーを使用して IPv6 を構成します。</span><span class="sxs-lookup"><span data-stu-id="ace55-244">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="ace55-245">常設チャットの構成の詳細については、「常設チャットサーバーのドキュメントを展開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ace55-245">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="ace55-246">**Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**</span><span class="sxs-lookup"><span data-stu-id="ace55-246">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="ace55-247">IPv4 か IPv6 かにかかわらず、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。</span><span class="sxs-lookup"><span data-stu-id="ace55-247">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

