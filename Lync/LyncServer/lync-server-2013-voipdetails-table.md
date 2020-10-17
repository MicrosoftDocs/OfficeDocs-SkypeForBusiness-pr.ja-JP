---
title: 'Lync Server 2013: VoipDetails テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26feac5b9995aa1a8444029442adcb9c935083d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535414"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="ffe14-102">Lync Server 2013 の VoipDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="ffe14-102">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffe14-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ffe14-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ffe14-104">それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。</span><span class="sxs-lookup"><span data-stu-id="ffe14-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffe14-105">Column</span><span class="sxs-lookup"><span data-stu-id="ffe14-105">Column</span></span></th>
<th><span data-ttu-id="ffe14-106">データ型</span><span class="sxs-lookup"><span data-stu-id="ffe14-106">Data Type</span></span></th>
<th><span data-ttu-id="ffe14-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="ffe14-107">Key/Index</span></span></th>
<th><span data-ttu-id="ffe14-108">詳細</span><span class="sxs-lookup"><span data-stu-id="ffe14-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffe14-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-110">日付型</span><span class="sxs-lookup"><span data-stu-id="ffe14-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ffe14-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ffe14-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="ffe14-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="ffe14-112">Time of session request.</span></span> <span data-ttu-id="ffe14-113">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="ffe14-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ffe14-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe14-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-116">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-116">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-117">Primary</span><span class="sxs-lookup"><span data-stu-id="ffe14-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ffe14-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ffe14-118">ID number to identify the session.</span></span> <span data-ttu-id="ffe14-119">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="ffe14-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ffe14-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe14-121"><strong>Fromnumber Id</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-122">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-122">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-123">外部</span><span class="sxs-lookup"><span data-stu-id="ffe14-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ffe14-124">発信者の <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="ffe14-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="ffe14-125">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ffe14-126">この値と <strong>FromGatewayId</strong> がどちらも NULL でない場合、発信者は PSTN ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ffe14-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe14-127"><strong>Connectednumber Id</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-128">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-128">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-129">外部</span><span class="sxs-lookup"><span data-stu-id="ffe14-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ffe14-130">通話の受信者の <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="ffe14-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="ffe14-131">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ffe14-132">この値と <strong>ToGatewayId</strong> がどちらも NULL でない場合、通話の受信者は PSTN ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ffe14-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe14-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-134">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-134">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-135">外部</span><span class="sxs-lookup"><span data-stu-id="ffe14-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ffe14-136">通話の発信元の仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="ffe14-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="ffe14-137">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe14-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-139">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-139">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-140">外部</span><span class="sxs-lookup"><span data-stu-id="ffe14-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ffe14-141">通話の発信先の仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="ffe14-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="ffe14-142">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe14-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-144">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-144">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-145">外部</span><span class="sxs-lookup"><span data-stu-id="ffe14-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ffe14-146">通話の発信元のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="ffe14-146">Gateway the call is coming from.</span></span> <span data-ttu-id="ffe14-147">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe14-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-149">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-149">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-150">外部</span><span class="sxs-lookup"><span data-stu-id="ffe14-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ffe14-151">通話の発信先のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="ffe14-151">Gateway the call is going to.</span></span> <span data-ttu-id="ffe14-152">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe14-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-154">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-154">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-155">外部</span><span class="sxs-lookup"><span data-stu-id="ffe14-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ffe14-156">通話を切断したユーザーの URI (ユーザーが URI を持つ場合)。</span><span class="sxs-lookup"><span data-stu-id="ffe14-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="ffe14-157">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe14-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="ffe14-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="ffe14-159">int</span><span class="sxs-lookup"><span data-stu-id="ffe14-159">int</span></span></p></td>
<td><p><span data-ttu-id="ffe14-160">外部</span><span class="sxs-lookup"><span data-stu-id="ffe14-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ffe14-161">別の電話から切断された通話を切断した電話の ID。</span><span class="sxs-lookup"><span data-stu-id="ffe14-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="ffe14-162">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe14-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

