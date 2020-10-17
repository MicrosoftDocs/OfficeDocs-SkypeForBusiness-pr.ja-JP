---
title: Lync Server 2013 の IPsec 例外
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514154"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="e0790-102">Lync Server 2013 の IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="e0790-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0790-103">_**トピックの最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="e0790-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="e0790-p101">企業ネットワーク上でインターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301 ～ 4309 を参照) を導入している場合、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートに対して IPsec を無効にする必要があります。これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="e0790-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="e0790-106">次の表に、推奨される IPsec 例外設定を示します。</span><span class="sxs-lookup"><span data-stu-id="e0790-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="e0790-107">推奨される IPSec 例外設定</span><span class="sxs-lookup"><span data-stu-id="e0790-107">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0790-108">ルール名</span><span class="sxs-lookup"><span data-stu-id="e0790-108">Rule name</span></span></th>
<th><span data-ttu-id="e0790-109">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e0790-109">Source IP</span></span></th>
<th><span data-ttu-id="e0790-110">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e0790-110">Destination IP</span></span></th>
<th><span data-ttu-id="e0790-111">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e0790-111">Protocol</span></span></th>
<th><span data-ttu-id="e0790-112">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="e0790-112">Source port</span></span></th>
<th><span data-ttu-id="e0790-113">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="e0790-113">Destination port</span></span></th>
<th><span data-ttu-id="e0790-114">認証要件</span><span class="sxs-lookup"><span data-stu-id="e0790-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0790-115">内部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="e0790-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-116">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-116">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-117">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="e0790-118">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-119">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-119">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-120">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-120">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-121">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0790-122">外部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="e0790-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-123">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-123">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-124">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="e0790-125">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-126">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-126">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-127">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-127">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-128">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0790-129">内部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="e0790-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-130">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="e0790-131">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-131">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-133">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-133">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-134">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-134">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-135">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0790-136">外部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="e0790-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-137">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="e0790-138">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-138">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-139">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-140">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-140">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-141">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-141">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-142">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0790-143">仲介サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="e0790-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-144">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-144">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-145">仲介</span><span class="sxs-lookup"><span data-stu-id="e0790-145">Mediation</span></span></p>
<p><span data-ttu-id="e0790-146">サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="e0790-147">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-148">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-148">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-149">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-149">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-150">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0790-151">仲介サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="e0790-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-152">仲介</span><span class="sxs-lookup"><span data-stu-id="e0790-152">Mediation</span></span></p>
<p><span data-ttu-id="e0790-153">サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="e0790-154">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-154">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-155">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-156">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-156">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-157">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-157">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-158">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0790-159">会議アテンダント/受信</span><span class="sxs-lookup"><span data-stu-id="e0790-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-160">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-160">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-161">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="e0790-162">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-163">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-163">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-164">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-164">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-165">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0790-166">会議アテンダント/送信</span><span class="sxs-lookup"><span data-stu-id="e0790-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-167">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="e0790-168">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-168">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-169">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-170">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-170">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-171">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-171">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-172">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0790-173">音声ビデオ会議サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="e0790-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-174">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-174">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-175">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e0790-176">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-177">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-177">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-178">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-178">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-179">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0790-180">音声ビデオ会議/送信</span><span class="sxs-lookup"><span data-stu-id="e0790-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-181">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e0790-182">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-182">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-183">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-184">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-184">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-185">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-185">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-186">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0790-187">Exchange/受信</span><span class="sxs-lookup"><span data-stu-id="e0790-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-188">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-188">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-189">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="e0790-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="e0790-190">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-191">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-191">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-192">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-192">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-193">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0790-194">アプリケーション共有サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="e0790-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-195">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-195">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-196">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="e0790-197">TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-198">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-198">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-199">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-199">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-200">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0790-201">アプリケーション共有サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="e0790-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-202">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="e0790-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="e0790-203">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-203">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-204">TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-205">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-205">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-206">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-206">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-207">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0790-208">Exchange/送信</span><span class="sxs-lookup"><span data-stu-id="e0790-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="e0790-209">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="e0790-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="e0790-210">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-210">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-211">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="e0790-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e0790-212">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-212">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-213">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-213">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-214">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0790-215">クライアント</span><span class="sxs-lookup"><span data-stu-id="e0790-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="e0790-216">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-216">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-217">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-217">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-218">受信</span><span class="sxs-lookup"><span data-stu-id="e0790-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="e0790-219">指定メディア ポート範囲</span><span class="sxs-lookup"><span data-stu-id="e0790-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="e0790-220">任意</span><span class="sxs-lookup"><span data-stu-id="e0790-220">Any</span></span></p></td>
<td><p><span data-ttu-id="e0790-221">認証しない</span><span class="sxs-lookup"><span data-stu-id="e0790-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

