---
title: 'Lync Server 2013: Conferences テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="6173d-102">Lync Server 2013 の Conferences テーブル</span><span class="sxs-lookup"><span data-stu-id="6173d-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6173d-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6173d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6173d-104">この表の各レコードには、1人の会議に関する通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6173d-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6173d-105">列</span><span class="sxs-lookup"><span data-stu-id="6173d-105">Column</span></span></th>
<th><span data-ttu-id="6173d-106">データ型</span><span class="sxs-lookup"><span data-stu-id="6173d-106">Data Type</span></span></th>
<th><span data-ttu-id="6173d-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="6173d-107">Key/Index</span></span></th>
<th><span data-ttu-id="6173d-108">詳細</span><span class="sxs-lookup"><span data-stu-id="6173d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6173d-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="6173d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="6173d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="6173d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="6173d-112">会議出席依頼が CDR エージェントによってキャプチャされた時刻。</span><span class="sxs-lookup"><span data-stu-id="6173d-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="6173d-113">会議インスタンスを一意に識別するために、主キーとしてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="6173d-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6173d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-115">int</span><span class="sxs-lookup"><span data-stu-id="6173d-115">int</span></span></p></td>
<td><p><span data-ttu-id="6173d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="6173d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="6173d-117">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="6173d-117">ID number to identify the session.</span></span> <span data-ttu-id="6173d-118">電話会議インスタンスを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="6173d-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6173d-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-120">int</span><span class="sxs-lookup"><span data-stu-id="6173d-120">int</span></span></p></td>
<td><p><span data-ttu-id="6173d-121">外部</span><span class="sxs-lookup"><span data-stu-id="6173d-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6173d-122">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="6173d-122">Conference URI.</span></span> <span data-ttu-id="6173d-123">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6173d-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6173d-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-125">長さ</span><span class="sxs-lookup"><span data-stu-id="6173d-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6173d-126">定期的な会議に便利。定期的な会議の各インスタンスには、同じ<strong>ConferenceUri</strong>がありますが、別の<strong>confinstance</strong>があります。</span><span class="sxs-lookup"><span data-stu-id="6173d-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6173d-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-128">datetime</span><span class="sxs-lookup"><span data-stu-id="6173d-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6173d-129">会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="6173d-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6173d-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-131">datetime</span><span class="sxs-lookup"><span data-stu-id="6173d-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6173d-132">会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="6173d-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6173d-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-134">int</span><span class="sxs-lookup"><span data-stu-id="6173d-134">int</span></span></p></td>
<td><p><span data-ttu-id="6173d-135">外部</span><span class="sxs-lookup"><span data-stu-id="6173d-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6173d-136">会議がキャプチャされたプールを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="6173d-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="6173d-137">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6173d-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6173d-138"><strong>オーガナイザー Erid</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-139">Int</span><span class="sxs-lookup"><span data-stu-id="6173d-139">Int</span></span></p></td>
<td><p><span data-ttu-id="6173d-140">外部</span><span class="sxs-lookup"><span data-stu-id="6173d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6173d-141">この会議の開催者の URI を識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="6173d-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="6173d-142">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6173d-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6173d-143"><strong>フラッグ</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-144">smallint</span><span class="sxs-lookup"><span data-stu-id="6173d-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6173d-145">会議の属性が含まれているビットマスク。</span><span class="sxs-lookup"><span data-stu-id="6173d-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="6173d-146">値の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6173d-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6173d-147">0X01</span><span class="sxs-lookup"><span data-stu-id="6173d-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="6173d-148">Synthetic</span><span class="sxs-lookup"><span data-stu-id="6173d-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="6173d-149">トランザクション</span><span class="sxs-lookup"><span data-stu-id="6173d-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6173d-150"><strong>処理</strong></span><span class="sxs-lookup"><span data-stu-id="6173d-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="6173d-151">bit</span><span class="sxs-lookup"><span data-stu-id="6173d-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6173d-152">監視サービスで使用される内部フィールド。</span><span class="sxs-lookup"><span data-stu-id="6173d-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="6173d-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6173d-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6173d-154">\*ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="6173d-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="6173d-155">2つのセッションがまったく同じ時刻に開始された場合、1つのセッションの SessionIdSeq は1になり、残りのセッションは2になります。</span><span class="sxs-lookup"><span data-stu-id="6173d-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

