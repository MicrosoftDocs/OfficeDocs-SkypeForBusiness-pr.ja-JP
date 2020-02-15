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
ms.openlocfilehash: db7291674485dec30211d88e2739b0da89fb334f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="7325b-102">Lync Server 2013 の IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="7325b-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7325b-103">_**トピックの最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="7325b-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="7325b-p101">企業ネットワーク上でインターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301 ～ 4309 を参照) を導入している場合、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートに対して IPsec を無効にする必要があります。これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="7325b-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="7325b-106">次の表に、推奨される IPsec 例外設定を示します。</span><span class="sxs-lookup"><span data-stu-id="7325b-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="7325b-107">推奨される IPSec 例外設定</span><span class="sxs-lookup"><span data-stu-id="7325b-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="7325b-108">ルール名</span><span class="sxs-lookup"><span data-stu-id="7325b-108">Rule name</span></span></th>
<th><span data-ttu-id="7325b-109">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="7325b-109">Source IP</span></span></th>
<th><span data-ttu-id="7325b-110">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="7325b-110">Destination IP</span></span></th>
<th><span data-ttu-id="7325b-111">プロトコル</span><span class="sxs-lookup"><span data-stu-id="7325b-111">Protocol</span></span></th>
<th><span data-ttu-id="7325b-112">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="7325b-112">Source port</span></span></th>
<th><span data-ttu-id="7325b-113">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="7325b-113">Destination port</span></span></th>
<th><span data-ttu-id="7325b-114">認証要件</span><span class="sxs-lookup"><span data-stu-id="7325b-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7325b-115">内部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7325b-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-116">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-116">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-117">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="7325b-118">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-119">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-119">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-120">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-120">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-121">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7325b-122">外部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7325b-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-123">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-123">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-124">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="7325b-125">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-126">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-127">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-127">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-128">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7325b-129">内部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="7325b-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-130">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="7325b-131">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-131">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-133">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-133">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-134">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-135">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7325b-136">外部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="7325b-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-137">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="7325b-138">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-139">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-140">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-140">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-141">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-142">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7325b-143">仲介サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7325b-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-144">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-144">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-145">仲介</span><span class="sxs-lookup"><span data-stu-id="7325b-145">Mediation</span></span></p>
<p><span data-ttu-id="7325b-146">サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="7325b-147">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-148">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-148">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-149">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-149">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-150">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7325b-151">仲介サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="7325b-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-152">仲介</span><span class="sxs-lookup"><span data-stu-id="7325b-152">Mediation</span></span></p>
<p><span data-ttu-id="7325b-153">サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="7325b-154">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-155">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-156">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-156">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-157">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-157">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-158">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7325b-159">会議アテンダント/受信</span><span class="sxs-lookup"><span data-stu-id="7325b-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-160">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-160">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-161">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="7325b-162">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-163">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-163">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-164">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-164">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-165">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7325b-166">会議アテンダント/送信</span><span class="sxs-lookup"><span data-stu-id="7325b-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-167">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="7325b-168">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-168">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-169">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-170">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-170">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-171">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-171">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-172">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7325b-173">音声ビデオ会議サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7325b-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-174">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-175">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="7325b-176">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-177">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-177">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-178">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-179">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7325b-180">音声ビデオ会議/送信</span><span class="sxs-lookup"><span data-stu-id="7325b-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-181">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="7325b-182">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-182">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-183">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-184">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-184">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-185">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-185">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-186">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7325b-187">Exchange/受信</span><span class="sxs-lookup"><span data-stu-id="7325b-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-188">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-188">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-189">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="7325b-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="7325b-190">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-191">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-191">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-192">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-192">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-193">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7325b-194">アプリケーション共有サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7325b-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-195">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-195">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-196">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="7325b-197">TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-198">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-198">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-199">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-199">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-200">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7325b-201">アプリケーション共有サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="7325b-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-202">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="7325b-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="7325b-203">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-203">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-204">TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-205">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-205">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-206">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-206">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-207">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7325b-208">Exchange/送信</span><span class="sxs-lookup"><span data-stu-id="7325b-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="7325b-209">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="7325b-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="7325b-210">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-210">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-211">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7325b-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7325b-212">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-212">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-213">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-213">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-214">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7325b-215">クライアント</span><span class="sxs-lookup"><span data-stu-id="7325b-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="7325b-216">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-216">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-217">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-217">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-218">受信</span><span class="sxs-lookup"><span data-stu-id="7325b-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="7325b-219">指定メディア ポート範囲</span><span class="sxs-lookup"><span data-stu-id="7325b-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="7325b-220">任意</span><span class="sxs-lookup"><span data-stu-id="7325b-220">Any</span></span></p></td>
<td><p><span data-ttu-id="7325b-221">認証しない</span><span class="sxs-lookup"><span data-stu-id="7325b-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

