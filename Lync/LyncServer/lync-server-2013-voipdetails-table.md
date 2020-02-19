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
ms.openlocfilehash: 4aac4ae26de4c80f7ed1396e647701a0b49a1c4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42119240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="a6ae6-102">Lync Server 2013 の VoipDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="a6ae6-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6ae6-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a6ae6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a6ae6-104">それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6ae6-105">列</span><span class="sxs-lookup"><span data-stu-id="a6ae6-105">Column</span></span></th>
<th><span data-ttu-id="a6ae6-106">データ型</span><span class="sxs-lookup"><span data-stu-id="a6ae6-106">Data Type</span></span></th>
<th><span data-ttu-id="a6ae6-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a6ae6-107">Key/Index</span></span></th>
<th><span data-ttu-id="a6ae6-108">詳細</span><span class="sxs-lookup"><span data-stu-id="a6ae6-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6ae6-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-110">日付型</span><span class="sxs-lookup"><span data-stu-id="a6ae6-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a6ae6-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-112">Time of session request.</span></span> <span data-ttu-id="a6ae6-113">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a6ae6-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ae6-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-116">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-116">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a6ae6-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-118">ID number to identify the session.</span></span> <span data-ttu-id="a6ae6-119">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a6ae6-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ae6-121"><strong>Fromnumber Id</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-122">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-122">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-123">外部</span><span class="sxs-lookup"><span data-stu-id="a6ae6-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-124">発信者の <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="a6ae6-125">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="a6ae6-126">この値と <strong>FromGatewayId</strong> がどちらも NULL でない場合、発信者は PSTN ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ae6-127"><strong>Connectednumber Id</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-128">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-128">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-129">外部</span><span class="sxs-lookup"><span data-stu-id="a6ae6-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-130">通話の受信者の <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="a6ae6-131">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="a6ae6-132">この値と <strong>ToGatewayId</strong> がどちらも NULL でない場合、通話の受信者は PSTN ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ae6-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-134">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-134">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-135">外部</span><span class="sxs-lookup"><span data-stu-id="a6ae6-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-136">通話の発信元の仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="a6ae6-137">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ae6-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-139">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-139">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-140">外部</span><span class="sxs-lookup"><span data-stu-id="a6ae6-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-141">通話の発信先の仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="a6ae6-142">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ae6-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-144">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-144">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-145">外部</span><span class="sxs-lookup"><span data-stu-id="a6ae6-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-146">通話の発信元のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-146">Gateway the call is coming from.</span></span> <span data-ttu-id="a6ae6-147">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ae6-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-149">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-149">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-150">外部</span><span class="sxs-lookup"><span data-stu-id="a6ae6-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-151">通話の発信先のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-151">Gateway the call is going to.</span></span> <span data-ttu-id="a6ae6-152">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ae6-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-154">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-154">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-155">外部</span><span class="sxs-lookup"><span data-stu-id="a6ae6-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-156">通話を切断したユーザーの URI (ユーザーが URI を持つ場合)。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="a6ae6-157">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ae6-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="a6ae6-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ae6-159">int</span><span class="sxs-lookup"><span data-stu-id="a6ae6-159">int</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-160">外部</span><span class="sxs-lookup"><span data-stu-id="a6ae6-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6ae6-161">別の電話から切断された通話を切断した電話の ID。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="a6ae6-162">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ae6-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

