---
title: 'Lync Server 2013: VoipDetails テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="d1621-102">Lync Server 2013 の VoipDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="d1621-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1621-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d1621-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d1621-104">各レコードは、少なくとも1人のユーザーが VoIP ユーザーである 1 2 パーティーの通話を表します。</span><span class="sxs-lookup"><span data-stu-id="d1621-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1621-105">列</span><span class="sxs-lookup"><span data-stu-id="d1621-105">Column</span></span></th>
<th><span data-ttu-id="d1621-106">データ型</span><span class="sxs-lookup"><span data-stu-id="d1621-106">Data Type</span></span></th>
<th><span data-ttu-id="d1621-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="d1621-107">Key/Index</span></span></th>
<th><span data-ttu-id="d1621-108">詳細</span><span class="sxs-lookup"><span data-stu-id="d1621-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1621-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d1621-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1621-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d1621-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="d1621-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="d1621-112">Time of session request.</span></span> <span data-ttu-id="d1621-113">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1621-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d1621-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1621-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-116">int</span><span class="sxs-lookup"><span data-stu-id="d1621-116">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d1621-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="d1621-118">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="d1621-118">ID number to identify the session.</span></span> <span data-ttu-id="d1621-119">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1621-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d1621-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1621-121"><strong>Fromnumber Id</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-122">int</span><span class="sxs-lookup"><span data-stu-id="d1621-122">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-123">外部</span><span class="sxs-lookup"><span data-stu-id="d1621-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1621-124">発信者の<strong>PhoneId</strong> 。</span><span class="sxs-lookup"><span data-stu-id="d1621-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="d1621-125">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 で電話の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="d1621-126">Not NULL と<strong>Fromgatewayid</strong>が null でない場合は、発信者は PSTN ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d1621-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1621-127"><strong>Connected番号 Id</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-128">int</span><span class="sxs-lookup"><span data-stu-id="d1621-128">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-129">外部</span><span class="sxs-lookup"><span data-stu-id="d1621-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1621-130">通話受信者の<strong>PhoneId</strong> 。</span><span class="sxs-lookup"><span data-stu-id="d1621-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="d1621-131">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 で電話の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="d1621-132">Not NULL と<strong>Togatewayid</strong>が null でない場合は、通話レシーバーは PSTN ユーザーでした。</span><span class="sxs-lookup"><span data-stu-id="d1621-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1621-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-134">int</span><span class="sxs-lookup"><span data-stu-id="d1621-134">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-135">外部</span><span class="sxs-lookup"><span data-stu-id="d1621-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1621-136">通話が発信される仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="d1621-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="d1621-137">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1621-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-139">int</span><span class="sxs-lookup"><span data-stu-id="d1621-139">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-140">外部</span><span class="sxs-lookup"><span data-stu-id="d1621-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1621-141">仲介サーバーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d1621-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="d1621-142">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1621-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-144">int</span><span class="sxs-lookup"><span data-stu-id="d1621-144">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-145">外部</span><span class="sxs-lookup"><span data-stu-id="d1621-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1621-146">ゲートウェイ通話の発信元です。</span><span class="sxs-lookup"><span data-stu-id="d1621-146">Gateway the call is coming from.</span></span> <span data-ttu-id="d1621-147">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1621-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-149">int</span><span class="sxs-lookup"><span data-stu-id="d1621-149">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-150">外部</span><span class="sxs-lookup"><span data-stu-id="d1621-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1621-151">通話の発信先のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="d1621-151">Gateway the call is going to.</span></span> <span data-ttu-id="d1621-152">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1621-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-154">int</span><span class="sxs-lookup"><span data-stu-id="d1621-154">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-155">外部</span><span class="sxs-lookup"><span data-stu-id="d1621-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1621-156">ユーザーが URI を持っている場合に、通話を切断したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="d1621-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="d1621-157">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1621-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="d1621-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1621-159">int</span><span class="sxs-lookup"><span data-stu-id="d1621-159">int</span></span></p></td>
<td><p><span data-ttu-id="d1621-160">外部</span><span class="sxs-lookup"><span data-stu-id="d1621-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1621-161">通話を切断した電話の ID が電話から切断されました。</span><span class="sxs-lookup"><span data-stu-id="d1621-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="d1621-162">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 で電話の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1621-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

