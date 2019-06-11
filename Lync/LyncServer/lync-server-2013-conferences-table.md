---
title: 'Lync Server 2013: Conferences テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="ff9f0-102">Lync Server 2013 の Conferences テーブル</span><span class="sxs-lookup"><span data-stu-id="ff9f0-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff9f0-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ff9f0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ff9f0-104">この表の各レコードには、1人の会議に関する通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff9f0-105">列</span><span class="sxs-lookup"><span data-stu-id="ff9f0-105">Column</span></span></th>
<th><span data-ttu-id="ff9f0-106">データ型</span><span class="sxs-lookup"><span data-stu-id="ff9f0-106">Data Type</span></span></th>
<th><span data-ttu-id="ff9f0-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="ff9f0-107">Key/Index</span></span></th>
<th><span data-ttu-id="ff9f0-108">詳細</span><span class="sxs-lookup"><span data-stu-id="ff9f0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff9f0-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ff9f0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ff9f0-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-112">会議出席依頼が CDR エージェントによってキャプチャされた時刻。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="ff9f0-113">会議インスタンスを一意に識別するために、主キーとしてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f0-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-115">int</span><span class="sxs-lookup"><span data-stu-id="ff9f0-115">int</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-116">Primary</span><span class="sxs-lookup"><span data-stu-id="ff9f0-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-117">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-117">ID number to identify the session.</span></span> <span data-ttu-id="ff9f0-118">電話会議インスタンスを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f0-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-120">int</span><span class="sxs-lookup"><span data-stu-id="ff9f0-120">int</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-121">外部</span><span class="sxs-lookup"><span data-stu-id="ff9f0-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-122">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-122">Conference URI.</span></span> <span data-ttu-id="ff9f0-123">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f0-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-125">長さ</span><span class="sxs-lookup"><span data-stu-id="ff9f0-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff9f0-126">定期的な会議に便利。定期的な会議の各インスタンスには、同じ<strong>ConferenceUri</strong>がありますが、別の<strong>confinstance</strong>があります。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f0-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-128">datetime</span><span class="sxs-lookup"><span data-stu-id="ff9f0-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff9f0-129">会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f0-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-131">datetime</span><span class="sxs-lookup"><span data-stu-id="ff9f0-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff9f0-132">会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f0-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-134">int</span><span class="sxs-lookup"><span data-stu-id="ff9f0-134">int</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-135">外部</span><span class="sxs-lookup"><span data-stu-id="ff9f0-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-136">会議がキャプチャされたプールを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="ff9f0-137">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f0-138"><strong>オーガナイザー Erid</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-139">Int</span><span class="sxs-lookup"><span data-stu-id="ff9f0-139">Int</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-140">外部</span><span class="sxs-lookup"><span data-stu-id="ff9f0-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff9f0-141">この会議の開催者の URI を識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="ff9f0-142">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f0-143"><strong>フラッグ</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-144">smallint</span><span class="sxs-lookup"><span data-stu-id="ff9f0-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff9f0-145">会議の属性が含まれているビットマスク。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="ff9f0-146">値の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff9f0-147">0X01</span><span class="sxs-lookup"><span data-stu-id="ff9f0-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="ff9f0-148">Synthetic</span><span class="sxs-lookup"><span data-stu-id="ff9f0-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="ff9f0-149">トランザクション</span><span class="sxs-lookup"><span data-stu-id="ff9f0-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f0-150"><strong>処理</strong></span><span class="sxs-lookup"><span data-stu-id="ff9f0-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="ff9f0-151">bit</span><span class="sxs-lookup"><span data-stu-id="ff9f0-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff9f0-152">監視サービスで使用される内部フィールド。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="ff9f0-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff9f0-154">\*ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="ff9f0-155">2つのセッションがまったく同じ時刻に開始された場合、1つのセッションの SessionIdSeq は1になり、残りのセッションは2になります。</span><span class="sxs-lookup"><span data-stu-id="ff9f0-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

