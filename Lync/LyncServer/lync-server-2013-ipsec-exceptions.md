---
title: Lync Server 2013 IPsec の例外
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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="af0d4-102">Lync Server 2013 での IPsec の例外</span><span class="sxs-lookup"><span data-stu-id="af0d4-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af0d4-103">_**最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="af0d4-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="af0d4-104">インターネットプロトコルセキュリティ (IPsec 4301-4309) が展開されているエンタープライズネットワークの場合、オーディオ、ビデオ、およびパノラマビデオの配信に使用するポートの範囲で IPsec を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af0d4-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="af0d4-105">この操作を行うと、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="af0d4-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="af0d4-106">次の表に、推奨される IPsec 例外設定を示します。</span><span class="sxs-lookup"><span data-stu-id="af0d4-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="af0d4-107">推奨される IPSec 例外設定</span><span class="sxs-lookup"><span data-stu-id="af0d4-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="af0d4-108">ルール名</span><span class="sxs-lookup"><span data-stu-id="af0d4-108">Rule name</span></span></th>
<th><span data-ttu-id="af0d4-109">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="af0d4-109">Source IP</span></span></th>
<th><span data-ttu-id="af0d4-110">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="af0d4-110">Destination IP</span></span></th>
<th><span data-ttu-id="af0d4-111">プロトコル</span><span class="sxs-lookup"><span data-stu-id="af0d4-111">Protocol</span></span></th>
<th><span data-ttu-id="af0d4-112">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="af0d4-112">Source port</span></span></th>
<th><span data-ttu-id="af0d4-113">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="af0d4-113">Destination port</span></span></th>
<th><span data-ttu-id="af0d4-114">認証要件</span><span class="sxs-lookup"><span data-stu-id="af0d4-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af0d4-115">内部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="af0d4-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-116">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-116">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-117">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="af0d4-118">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-119">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-119">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-120">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-120">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-121">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af0d4-122">外部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="af0d4-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-123">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-123">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-124">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="af0d4-125">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-126">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-126">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-127">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-127">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-128">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af0d4-129">内部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="af0d4-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-130">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="af0d4-131">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-131">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-133">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-133">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-134">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-134">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-135">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af0d4-136">外部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="af0d4-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-137">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="af0d4-138">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-138">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-139">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-140">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-140">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-141">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-141">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-142">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af0d4-143">仲介サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="af0d4-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-144">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-144">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-145">仲介</span><span class="sxs-lookup"><span data-stu-id="af0d4-145">Mediation</span></span></p>
<p><span data-ttu-id="af0d4-146">サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="af0d4-147">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-148">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-148">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-149">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-149">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-150">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af0d4-151">仲介サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="af0d4-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-152">仲介</span><span class="sxs-lookup"><span data-stu-id="af0d4-152">Mediation</span></span></p>
<p><span data-ttu-id="af0d4-153">サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="af0d4-154">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-154">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-155">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-156">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-156">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-157">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-157">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-158">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af0d4-159">会議アテンダント/受信</span><span class="sxs-lookup"><span data-stu-id="af0d4-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-160">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-160">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-161">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="af0d4-162">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-163">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-163">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-164">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-164">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-165">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af0d4-166">会議アテンダント/送信</span><span class="sxs-lookup"><span data-stu-id="af0d4-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-167">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="af0d4-168">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-168">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-169">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-170">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-170">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-171">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-171">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-172">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af0d4-173">音声ビデオ会議サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="af0d4-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-174">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-174">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-175">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af0d4-176">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-177">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-177">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-178">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-178">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-179">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af0d4-180">音声ビデオ会議/送信</span><span class="sxs-lookup"><span data-stu-id="af0d4-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-181">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af0d4-182">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-182">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-183">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-184">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-184">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-185">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-185">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-186">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af0d4-187">Exchange/受信</span><span class="sxs-lookup"><span data-stu-id="af0d4-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-188">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-188">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-189">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="af0d4-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="af0d4-190">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-191">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-191">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-192">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-192">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-193">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af0d4-194">アプリケーション共有サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="af0d4-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-195">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-195">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-196">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="af0d4-197">TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-198">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-198">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-199">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-199">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-200">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af0d4-201">アプリケーション共有サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="af0d4-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-202">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="af0d4-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="af0d4-203">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-203">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-204">TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-205">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-205">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-206">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-206">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-207">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af0d4-208">Exchange/送信</span><span class="sxs-lookup"><span data-stu-id="af0d4-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="af0d4-209">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="af0d4-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="af0d4-210">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-210">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-211">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="af0d4-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-212">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-212">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-213">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-213">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-214">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af0d4-215">クライアント</span><span class="sxs-lookup"><span data-stu-id="af0d4-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="af0d4-216">任意 </span><span class="sxs-lookup"><span data-stu-id="af0d4-216">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-217">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-217">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-218">UDP</span><span class="sxs-lookup"><span data-stu-id="af0d4-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="af0d4-219">指定メディア ポート範囲</span><span class="sxs-lookup"><span data-stu-id="af0d4-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="af0d4-220">任意</span><span class="sxs-lookup"><span data-stu-id="af0d4-220">Any</span></span></p></td>
<td><p><span data-ttu-id="af0d4-221">認証しない</span><span class="sxs-lookup"><span data-stu-id="af0d4-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

