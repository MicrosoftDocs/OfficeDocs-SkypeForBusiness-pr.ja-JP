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
ms.openlocfilehash: bd649cea823ce13460de924ffc49741b3ca5c6d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="7ed91-102">Lync Server 2013 の IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="7ed91-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ed91-103">_**トピックの最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="7ed91-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="7ed91-p101">企業ネットワーク上でインターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301 ～ 4309 を参照) を導入している場合、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートに対して IPsec を無効にする必要があります。これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="7ed91-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="7ed91-106">次の表に、推奨される IPsec 例外設定を示します。</span><span class="sxs-lookup"><span data-stu-id="7ed91-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="7ed91-107">推奨される IPSec 例外設定</span><span class="sxs-lookup"><span data-stu-id="7ed91-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="7ed91-108">ルール名</span><span class="sxs-lookup"><span data-stu-id="7ed91-108">Rule name</span></span></th>
<th><span data-ttu-id="7ed91-109">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="7ed91-109">Source IP</span></span></th>
<th><span data-ttu-id="7ed91-110">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="7ed91-110">Destination IP</span></span></th>
<th><span data-ttu-id="7ed91-111">プロトコル</span><span class="sxs-lookup"><span data-stu-id="7ed91-111">Protocol</span></span></th>
<th><span data-ttu-id="7ed91-112">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="7ed91-112">Source port</span></span></th>
<th><span data-ttu-id="7ed91-113">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="7ed91-113">Destination port</span></span></th>
<th><span data-ttu-id="7ed91-114">認証要件</span><span class="sxs-lookup"><span data-stu-id="7ed91-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ed91-115">内部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7ed91-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-116">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-116">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-117">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="7ed91-118">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-119">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-119">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-120">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-120">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-121">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed91-122">外部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7ed91-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-123">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-123">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-124">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="7ed91-125">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-126">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-126">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-127">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-127">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-128">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed91-129">内部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="7ed91-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-130">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="7ed91-131">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-131">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-133">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-133">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-134">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-134">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-135">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed91-136">外部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="7ed91-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-137">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="7ed91-138">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-138">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-139">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-140">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-140">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-141">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-141">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-142">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed91-143">仲介サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7ed91-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-144">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-144">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-145">仲介</span><span class="sxs-lookup"><span data-stu-id="7ed91-145">Mediation</span></span></p>
<p><span data-ttu-id="7ed91-146">サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="7ed91-147">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-148">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-148">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-149">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-149">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-150">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed91-151">仲介サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="7ed91-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-152">仲介</span><span class="sxs-lookup"><span data-stu-id="7ed91-152">Mediation</span></span></p>
<p><span data-ttu-id="7ed91-153">サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="7ed91-154">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-154">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-155">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-156">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-156">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-157">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-157">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-158">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed91-159">会議アテンダント/受信</span><span class="sxs-lookup"><span data-stu-id="7ed91-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-160">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-160">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-161">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="7ed91-162">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-163">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-163">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-164">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-164">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-165">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed91-166">会議アテンダント/送信</span><span class="sxs-lookup"><span data-stu-id="7ed91-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-167">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="7ed91-168">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-168">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-169">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-170">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-170">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-171">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-171">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-172">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed91-173">音声ビデオ会議サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7ed91-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-174">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-174">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-175">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="7ed91-176">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-177">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-177">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-178">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-178">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-179">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed91-180">音声ビデオ会議/送信</span><span class="sxs-lookup"><span data-stu-id="7ed91-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-181">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="7ed91-182">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-182">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-183">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-184">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-184">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-185">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-185">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-186">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed91-187">Exchange/受信</span><span class="sxs-lookup"><span data-stu-id="7ed91-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-188">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-188">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-189">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="7ed91-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="7ed91-190">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-191">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-191">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-192">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-192">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-193">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed91-194">アプリケーション共有サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="7ed91-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-195">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-195">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-196">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="7ed91-197">TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-198">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-198">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-199">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-199">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-200">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed91-201">アプリケーション共有サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="7ed91-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-202">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="7ed91-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="7ed91-203">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-203">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-204">TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-205">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-205">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-206">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-206">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-207">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ed91-208">Exchange/送信</span><span class="sxs-lookup"><span data-stu-id="7ed91-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="7ed91-209">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="7ed91-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="7ed91-210">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-210">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-211">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="7ed91-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-212">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-212">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-213">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-213">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-214">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ed91-215">クライアント</span><span class="sxs-lookup"><span data-stu-id="7ed91-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="7ed91-216">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-216">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-217">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-217">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-218">受信</span><span class="sxs-lookup"><span data-stu-id="7ed91-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="7ed91-219">指定メディア ポート範囲</span><span class="sxs-lookup"><span data-stu-id="7ed91-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="7ed91-220">任意</span><span class="sxs-lookup"><span data-stu-id="7ed91-220">Any</span></span></p></td>
<td><p><span data-ttu-id="7ed91-221">認証しない</span><span class="sxs-lookup"><span data-stu-id="7ed91-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

