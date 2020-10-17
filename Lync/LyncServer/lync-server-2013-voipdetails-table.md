---
title: 'Lync Server 2013: VoipDetails テーブル'
description: 'Lync Server 2013: VoipDetails テーブル。'
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566283"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="b4ac7-103">Lync Server 2013 の VoipDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="b4ac7-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4ac7-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b4ac7-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b4ac7-105">それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4ac7-106">Column</span><span class="sxs-lookup"><span data-stu-id="b4ac7-106">Column</span></span></th>
<th><span data-ttu-id="b4ac7-107">データ型</span><span class="sxs-lookup"><span data-stu-id="b4ac7-107">Data Type</span></span></th>
<th><span data-ttu-id="b4ac7-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="b4ac7-108">Key/Index</span></span></th>
<th><span data-ttu-id="b4ac7-109">詳細</span><span class="sxs-lookup"><span data-stu-id="b4ac7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4ac7-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-111">日付型</span><span class="sxs-lookup"><span data-stu-id="b4ac7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b4ac7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-113">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-113">Time of session request.</span></span> <span data-ttu-id="b4ac7-114">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b4ac7-115">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4ac7-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-117">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-117">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-118">Primary</span><span class="sxs-lookup"><span data-stu-id="b4ac7-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-119">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-119">ID number to identify the session.</span></span> <span data-ttu-id="b4ac7-120">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b4ac7-121">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4ac7-122"><strong>Fromnumber Id</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-123">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-123">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-124">外部</span><span class="sxs-lookup"><span data-stu-id="b4ac7-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-125">発信者の <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="b4ac7-126">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b4ac7-127">この値と <strong>FromGatewayId</strong> がどちらも NULL でない場合、発信者は PSTN ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4ac7-128"><strong>Connectednumber Id</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-129">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-129">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-130">外部</span><span class="sxs-lookup"><span data-stu-id="b4ac7-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-131">通話の受信者の <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="b4ac7-132">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b4ac7-133">この値と <strong>ToGatewayId</strong> がどちらも NULL でない場合、通話の受信者は PSTN ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4ac7-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-135">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-135">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-136">外部</span><span class="sxs-lookup"><span data-stu-id="b4ac7-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-137">通話の発信元の仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="b4ac7-138">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4ac7-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-140">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-140">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-141">外部</span><span class="sxs-lookup"><span data-stu-id="b4ac7-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-142">通話の発信先の仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="b4ac7-143">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4ac7-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-145">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-145">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-146">外部</span><span class="sxs-lookup"><span data-stu-id="b4ac7-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-147">通話の発信元のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-147">Gateway the call is coming from.</span></span> <span data-ttu-id="b4ac7-148">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4ac7-149"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-150">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-150">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-151">外部</span><span class="sxs-lookup"><span data-stu-id="b4ac7-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-152">通話の発信先のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-152">Gateway the call is going to.</span></span> <span data-ttu-id="b4ac7-153">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4ac7-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-155">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-155">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-156">外部</span><span class="sxs-lookup"><span data-stu-id="b4ac7-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-157">通話を切断したユーザーの URI (ユーザーが URI を持つ場合)。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="b4ac7-158">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4ac7-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="b4ac7-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4ac7-160">int</span><span class="sxs-lookup"><span data-stu-id="b4ac7-160">int</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-161">外部</span><span class="sxs-lookup"><span data-stu-id="b4ac7-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4ac7-162">別の電話から切断された通話を切断した電話の ID。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="b4ac7-163">詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ac7-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

