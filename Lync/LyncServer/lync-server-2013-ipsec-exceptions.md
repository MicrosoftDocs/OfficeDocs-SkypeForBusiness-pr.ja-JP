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
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="f6c28-102">Lync Server 2013 の IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="f6c28-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6c28-103">_**トピックの最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="f6c28-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="f6c28-p101">企業ネットワーク上でインターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301 ～ 4309 を参照) を導入している場合、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートに対して IPsec を無効にする必要があります。これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="f6c28-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="f6c28-106">次の表に、推奨される IPsec 例外設定を示します。</span><span class="sxs-lookup"><span data-stu-id="f6c28-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="f6c28-107">推奨される IPSec 例外設定</span><span class="sxs-lookup"><span data-stu-id="f6c28-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="f6c28-108">ルール名</span><span class="sxs-lookup"><span data-stu-id="f6c28-108">Rule name</span></span></th>
<th><span data-ttu-id="f6c28-109">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f6c28-109">Source IP</span></span></th>
<th><span data-ttu-id="f6c28-110">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f6c28-110">Destination IP</span></span></th>
<th><span data-ttu-id="f6c28-111">プロトコル</span><span class="sxs-lookup"><span data-stu-id="f6c28-111">Protocol</span></span></th>
<th><span data-ttu-id="f6c28-112">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="f6c28-112">Source port</span></span></th>
<th><span data-ttu-id="f6c28-113">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="f6c28-113">Destination port</span></span></th>
<th><span data-ttu-id="f6c28-114">認証要件</span><span class="sxs-lookup"><span data-stu-id="f6c28-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6c28-115">内部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="f6c28-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-116">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-116">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-117">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="f6c28-118">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-119">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-119">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-120">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-120">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-121">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6c28-122">外部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="f6c28-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-123">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-123">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-124">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="f6c28-125">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-126">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-126">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-127">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-127">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-128">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6c28-129">内部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="f6c28-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-130">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="f6c28-131">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-131">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-133">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-133">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-134">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-134">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-135">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6c28-136">外部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="f6c28-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-137">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="f6c28-138">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-138">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-139">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-140">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-140">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-141">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-141">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-142">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6c28-143">仲介サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="f6c28-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-144">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-144">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-145">仲介</span><span class="sxs-lookup"><span data-stu-id="f6c28-145">Mediation</span></span></p>
<p><span data-ttu-id="f6c28-146">サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="f6c28-147">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-148">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-148">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-149">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-149">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-150">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6c28-151">仲介サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="f6c28-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-152">仲介</span><span class="sxs-lookup"><span data-stu-id="f6c28-152">Mediation</span></span></p>
<p><span data-ttu-id="f6c28-153">サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="f6c28-154">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-154">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-155">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-156">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-156">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-157">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-157">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-158">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6c28-159">会議アテンダント/受信</span><span class="sxs-lookup"><span data-stu-id="f6c28-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-160">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-160">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-161">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="f6c28-162">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-163">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-163">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-164">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-164">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-165">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6c28-166">会議アテンダント/送信</span><span class="sxs-lookup"><span data-stu-id="f6c28-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-167">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="f6c28-168">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-168">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-169">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-170">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-170">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-171">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-171">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-172">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6c28-173">音声ビデオ会議サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="f6c28-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-174">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-174">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-175">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f6c28-176">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-177">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-177">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-178">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-178">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-179">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6c28-180">音声ビデオ会議/送信</span><span class="sxs-lookup"><span data-stu-id="f6c28-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-181">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f6c28-182">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-182">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-183">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-184">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-184">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-185">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-185">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-186">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6c28-187">Exchange/受信</span><span class="sxs-lookup"><span data-stu-id="f6c28-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-188">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-188">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-189">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="f6c28-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="f6c28-190">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-191">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-191">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-192">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-192">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-193">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6c28-194">アプリケーション共有サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="f6c28-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-195">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-195">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-196">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="f6c28-197">TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-198">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-198">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-199">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-199">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-200">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6c28-201">アプリケーション共有サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="f6c28-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-202">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="f6c28-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="f6c28-203">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-203">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-204">TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-205">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-205">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-206">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-206">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-207">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6c28-208">Exchange/送信</span><span class="sxs-lookup"><span data-stu-id="f6c28-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="f6c28-209">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="f6c28-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="f6c28-210">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-210">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-211">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="f6c28-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-212">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-212">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-213">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-213">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-214">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6c28-215">クライアント</span><span class="sxs-lookup"><span data-stu-id="f6c28-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="f6c28-216">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-216">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-217">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-217">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-218">受信</span><span class="sxs-lookup"><span data-stu-id="f6c28-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="f6c28-219">指定メディア ポート範囲</span><span class="sxs-lookup"><span data-stu-id="f6c28-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="f6c28-220">任意</span><span class="sxs-lookup"><span data-stu-id="f6c28-220">Any</span></span></p></td>
<td><p><span data-ttu-id="f6c28-221">認証しない</span><span class="sxs-lookup"><span data-stu-id="f6c28-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

