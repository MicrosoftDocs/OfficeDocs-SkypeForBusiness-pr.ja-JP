---
title: 'Lync Server 2013: 電話会議テーブル'
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
ms.openlocfilehash: 218879c8e2c64178fc140d46199529f86ec7dc31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="70f2b-102">Lync Server 2013 の会議テーブル</span><span class="sxs-lookup"><span data-stu-id="70f2b-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70f2b-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="70f2b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="70f2b-104">この表の各レコードには、1つの会議に関する通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="70f2b-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70f2b-105">列</span><span class="sxs-lookup"><span data-stu-id="70f2b-105">Column</span></span></th>
<th><span data-ttu-id="70f2b-106">データ型</span><span class="sxs-lookup"><span data-stu-id="70f2b-106">Data Type</span></span></th>
<th><span data-ttu-id="70f2b-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="70f2b-107">Key/Index</span></span></th>
<th><span data-ttu-id="70f2b-108">詳細</span><span class="sxs-lookup"><span data-stu-id="70f2b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70f2b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-110">日付型</span><span class="sxs-lookup"><span data-stu-id="70f2b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="70f2b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="70f2b-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="70f2b-112">会議出席依頼が CDR エージェントによってキャプチャされた時刻。</span><span class="sxs-lookup"><span data-stu-id="70f2b-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="70f2b-113">会議インスタンスを一意に識別する主キーとしてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="70f2b-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f2b-114"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-115">int</span><span class="sxs-lookup"><span data-stu-id="70f2b-115">int</span></span></p></td>
<td><p><span data-ttu-id="70f2b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="70f2b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="70f2b-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="70f2b-117">ID number to identify the session.</span></span> <span data-ttu-id="70f2b-118"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="70f2b-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f2b-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-120">int</span><span class="sxs-lookup"><span data-stu-id="70f2b-120">int</span></span></p></td>
<td><p><span data-ttu-id="70f2b-121">外部</span><span class="sxs-lookup"><span data-stu-id="70f2b-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="70f2b-122">会議 URI。</span><span class="sxs-lookup"><span data-stu-id="70f2b-122">Conference URI.</span></span> <span data-ttu-id="70f2b-123">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70f2b-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f2b-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-125">識別子</span><span class="sxs-lookup"><span data-stu-id="70f2b-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70f2b-126">定期的な電話会議に役立ちます。定期的な会議の各インスタンスには同じ<strong>ConferenceUri</strong>がありますが、別の<strong>confinstance</strong>があります。</span><span class="sxs-lookup"><span data-stu-id="70f2b-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f2b-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-128">日付型</span><span class="sxs-lookup"><span data-stu-id="70f2b-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70f2b-129">電話会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="70f2b-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f2b-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-131">日付型</span><span class="sxs-lookup"><span data-stu-id="70f2b-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70f2b-132">電話会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="70f2b-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f2b-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-134">int</span><span class="sxs-lookup"><span data-stu-id="70f2b-134">int</span></span></p></td>
<td><p><span data-ttu-id="70f2b-135">外部</span><span class="sxs-lookup"><span data-stu-id="70f2b-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="70f2b-136">電話会議がキャプチャされたプールを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="70f2b-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="70f2b-137">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a>」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70f2b-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f2b-138"><strong>組織の Erid</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-139">Int</span><span class="sxs-lookup"><span data-stu-id="70f2b-139">Int</span></span></p></td>
<td><p><span data-ttu-id="70f2b-140">外部</span><span class="sxs-lookup"><span data-stu-id="70f2b-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="70f2b-141">この電話会議の開催者 URI を識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="70f2b-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="70f2b-142">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70f2b-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f2b-143"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-144">smallint</span><span class="sxs-lookup"><span data-stu-id="70f2b-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="70f2b-145">会議の属性を含むビットマスク。</span><span class="sxs-lookup"><span data-stu-id="70f2b-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="70f2b-146">使用可能な値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="70f2b-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="70f2b-147">0X01</span><span class="sxs-lookup"><span data-stu-id="70f2b-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="70f2b-148">代理</span><span class="sxs-lookup"><span data-stu-id="70f2b-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="70f2b-149">トランザクション</span><span class="sxs-lookup"><span data-stu-id="70f2b-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f2b-150"><strong>実行</strong></span><span class="sxs-lookup"><span data-stu-id="70f2b-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="70f2b-151">若干</span><span class="sxs-lookup"><span data-stu-id="70f2b-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="70f2b-152">監視サービスによって使用される内部フィールド。</span><span class="sxs-lookup"><span data-stu-id="70f2b-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="70f2b-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="70f2b-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="70f2b-154">\*ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="70f2b-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="70f2b-155">2つのセッションがまったく同じ時刻に開始された場合は、1つの SessionIdSeq が1になります。その他の場合は2になります。</span><span class="sxs-lookup"><span data-stu-id="70f2b-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

