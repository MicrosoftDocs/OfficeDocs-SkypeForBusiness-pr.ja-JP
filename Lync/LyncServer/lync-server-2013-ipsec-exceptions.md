---
title: Lync Server 2013 の IPsec 例外
description: Lync Server 2013 の IPsec 例外。
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
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575003"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="0922b-103">Lync Server 2013 の IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="0922b-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0922b-104">_**トピックの最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="0922b-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="0922b-p101">企業ネットワーク上でインターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301 ～ 4309 を参照) を導入している場合、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートに対して IPsec を無効にする必要があります。これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="0922b-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="0922b-107">次の表に、推奨される IPsec 例外設定を示します。</span><span class="sxs-lookup"><span data-stu-id="0922b-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="0922b-108">推奨される IPSec 例外設定</span><span class="sxs-lookup"><span data-stu-id="0922b-108">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="0922b-109">ルール名</span><span class="sxs-lookup"><span data-stu-id="0922b-109">Rule name</span></span></th>
<th><span data-ttu-id="0922b-110">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="0922b-110">Source IP</span></span></th>
<th><span data-ttu-id="0922b-111">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="0922b-111">Destination IP</span></span></th>
<th><span data-ttu-id="0922b-112">プロトコル</span><span class="sxs-lookup"><span data-stu-id="0922b-112">Protocol</span></span></th>
<th><span data-ttu-id="0922b-113">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="0922b-113">Source port</span></span></th>
<th><span data-ttu-id="0922b-114">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="0922b-114">Destination port</span></span></th>
<th><span data-ttu-id="0922b-115">認証要件</span><span class="sxs-lookup"><span data-stu-id="0922b-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0922b-116">内部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="0922b-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-117">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-117">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-118">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0922b-119">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-120">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-120">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-121">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-121">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-122">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0922b-123">外部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="0922b-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-124">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-124">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-125">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0922b-126">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-127">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-127">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-128">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-128">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-129">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0922b-130">内部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="0922b-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-131">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0922b-132">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-132">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-133">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-134">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-135">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-135">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-136">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0922b-137">外部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="0922b-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-138">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0922b-139">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-139">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-140">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-141">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-142">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-142">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-143">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0922b-144">仲介サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="0922b-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-145">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-145">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-146">仲介</span><span class="sxs-lookup"><span data-stu-id="0922b-146">Mediation</span></span></p>
<p><span data-ttu-id="0922b-147">サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0922b-148">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-149">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-149">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-150">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-150">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-151">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0922b-152">仲介サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="0922b-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-153">仲介</span><span class="sxs-lookup"><span data-stu-id="0922b-153">Mediation</span></span></p>
<p><span data-ttu-id="0922b-154">サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0922b-155">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-155">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-156">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-157">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-157">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-158">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-158">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-159">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0922b-160">会議アテンダント/受信</span><span class="sxs-lookup"><span data-stu-id="0922b-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-161">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-161">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-162">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0922b-163">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-164">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-164">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-165">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-165">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-166">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0922b-167">会議アテンダント/送信</span><span class="sxs-lookup"><span data-stu-id="0922b-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-168">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0922b-169">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-169">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-170">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-171">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-171">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-172">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-172">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-173">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0922b-174">音声ビデオ会議サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="0922b-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-175">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-175">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-176">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0922b-177">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-178">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-179">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-179">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-180">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0922b-181">音声ビデオ会議/送信</span><span class="sxs-lookup"><span data-stu-id="0922b-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-182">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0922b-183">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-183">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-184">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-185">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-185">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-186">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-186">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-187">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0922b-188">Exchange/受信</span><span class="sxs-lookup"><span data-stu-id="0922b-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-189">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-189">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-190">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="0922b-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0922b-191">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-192">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-192">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-193">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-193">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-194">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0922b-195">アプリケーション共有サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="0922b-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-196">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-196">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-197">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0922b-198">TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-199">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-199">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-200">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-200">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-201">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0922b-202">アプリケーション共有サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="0922b-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-203">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="0922b-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0922b-204">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-204">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-205">TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-206">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-206">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-207">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-207">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-208">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0922b-209">Exchange/送信</span><span class="sxs-lookup"><span data-stu-id="0922b-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="0922b-210">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="0922b-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0922b-211">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-211">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-212">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="0922b-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0922b-213">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-213">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-214">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-214">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-215">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0922b-216">クライアント</span><span class="sxs-lookup"><span data-stu-id="0922b-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="0922b-217">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-217">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-218">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-218">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-219">受信</span><span class="sxs-lookup"><span data-stu-id="0922b-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="0922b-220">指定メディア ポート範囲</span><span class="sxs-lookup"><span data-stu-id="0922b-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="0922b-221">任意</span><span class="sxs-lookup"><span data-stu-id="0922b-221">Any</span></span></p></td>
<td><p><span data-ttu-id="0922b-222">認証しない</span><span class="sxs-lookup"><span data-stu-id="0922b-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

