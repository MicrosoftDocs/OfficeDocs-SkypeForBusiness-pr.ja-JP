---
title: Lync Server 2013 IPsec の例外
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="39c67-102">Lync Server 2013 での IPsec の例外</span><span class="sxs-lookup"><span data-stu-id="39c67-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39c67-103">_**最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="39c67-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="39c67-104">インターネットプロトコルセキュリティ (IPsec 4301-4309) が展開されているエンタープライズネットワークの場合、オーディオ、ビデオ、およびパノラマビデオの配信に使用するポートの範囲で IPsec を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39c67-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="39c67-105">この操作を行うと、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="39c67-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="39c67-106">次の表に、推奨される IPsec 例外設定を示します。</span><span class="sxs-lookup"><span data-stu-id="39c67-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="39c67-107">推奨される IPSec 例外設定</span><span class="sxs-lookup"><span data-stu-id="39c67-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="39c67-108">ルール名</span><span class="sxs-lookup"><span data-stu-id="39c67-108">Rule name</span></span></th>
<th><span data-ttu-id="39c67-109">発信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="39c67-109">Source IP</span></span></th>
<th><span data-ttu-id="39c67-110">送信先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="39c67-110">Destination IP</span></span></th>
<th><span data-ttu-id="39c67-111">プロトコル</span><span class="sxs-lookup"><span data-stu-id="39c67-111">Protocol</span></span></th>
<th><span data-ttu-id="39c67-112">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="39c67-112">Source port</span></span></th>
<th><span data-ttu-id="39c67-113">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="39c67-113">Destination port</span></span></th>
<th><span data-ttu-id="39c67-114">認証要件</span><span class="sxs-lookup"><span data-stu-id="39c67-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39c67-115">内部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="39c67-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-116">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-116">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-117">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="39c67-118">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-119">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-119">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-120">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-120">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-121">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39c67-122">外部音声ビデオ エッジ サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="39c67-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-123">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-123">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-124">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="39c67-125">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-126">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-126">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-127">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-127">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-128">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39c67-129">内部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="39c67-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-130">内部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="39c67-131">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-131">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-133">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-133">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-134">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-134">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-135">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39c67-136">外部音声ビデオ エッジ サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="39c67-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-137">外部音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="39c67-138">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-138">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-139">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-140">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-140">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-141">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-141">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-142">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39c67-143">仲介サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="39c67-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-144">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-144">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-145">仲介</span><span class="sxs-lookup"><span data-stu-id="39c67-145">Mediation</span></span></p>
<p><span data-ttu-id="39c67-146">サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="39c67-147">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-148">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-148">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-149">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-149">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-150">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39c67-151">仲介サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="39c67-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-152">仲介</span><span class="sxs-lookup"><span data-stu-id="39c67-152">Mediation</span></span></p>
<p><span data-ttu-id="39c67-153">サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="39c67-154">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-154">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-155">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-156">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-156">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-157">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-157">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-158">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39c67-159">会議アテンダント/受信</span><span class="sxs-lookup"><span data-stu-id="39c67-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-160">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-160">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-161">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="39c67-162">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-163">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-163">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-164">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-164">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-165">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39c67-166">会議アテンダント/送信</span><span class="sxs-lookup"><span data-stu-id="39c67-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-167">会議アテンダントを実行するフロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="39c67-168">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-168">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-169">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-170">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-170">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-171">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-171">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-172">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39c67-173">音声ビデオ会議サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="39c67-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-174">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-174">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-175">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="39c67-176">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-177">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-177">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-178">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-178">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-179">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39c67-180">音声ビデオ会議/送信</span><span class="sxs-lookup"><span data-stu-id="39c67-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-181">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="39c67-182">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-182">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-183">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-184">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-184">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-185">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-185">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-186">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39c67-187">Exchange/受信</span><span class="sxs-lookup"><span data-stu-id="39c67-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-188">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-188">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-189">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="39c67-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="39c67-190">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-191">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-191">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-192">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-192">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-193">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39c67-194">アプリケーション共有サーバー/受信</span><span class="sxs-lookup"><span data-stu-id="39c67-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-195">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-195">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-196">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="39c67-197">TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-198">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-198">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-199">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-199">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-200">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39c67-201">アプリケーション共有サーバー/送信</span><span class="sxs-lookup"><span data-stu-id="39c67-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-202">アプリケーション共有サーバー</span><span class="sxs-lookup"><span data-stu-id="39c67-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="39c67-203">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-203">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-204">TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-205">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-205">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-206">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-206">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-207">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39c67-208">Exchange/送信</span><span class="sxs-lookup"><span data-stu-id="39c67-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="39c67-209">Exchange ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="39c67-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="39c67-210">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-210">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-211">UDP および TCP</span><span class="sxs-lookup"><span data-stu-id="39c67-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39c67-212">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-212">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-213">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-213">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-214">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39c67-215">クライアント</span><span class="sxs-lookup"><span data-stu-id="39c67-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="39c67-216">任意 </span><span class="sxs-lookup"><span data-stu-id="39c67-216">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-217">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-217">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-218">UDP</span><span class="sxs-lookup"><span data-stu-id="39c67-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="39c67-219">指定メディア ポート範囲</span><span class="sxs-lookup"><span data-stu-id="39c67-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="39c67-220">任意</span><span class="sxs-lookup"><span data-stu-id="39c67-220">Any</span></span></p></td>
<td><p><span data-ttu-id="39c67-221">認証しない</span><span class="sxs-lookup"><span data-stu-id="39c67-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

