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
ms.openlocfilehash: ef5e8811ad4b0adaccd8964e2f0bca718ca531e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529264"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="511b1-102">Lync Server 2013 の会議テーブル</span><span class="sxs-lookup"><span data-stu-id="511b1-102">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="511b1-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="511b1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="511b1-104">この表の各レコードには、1つの会議に関する通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="511b1-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="511b1-105">Column</span><span class="sxs-lookup"><span data-stu-id="511b1-105">Column</span></span></th>
<th><span data-ttu-id="511b1-106">データ型</span><span class="sxs-lookup"><span data-stu-id="511b1-106">Data Type</span></span></th>
<th><span data-ttu-id="511b1-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="511b1-107">Key/Index</span></span></th>
<th><span data-ttu-id="511b1-108">詳細</span><span class="sxs-lookup"><span data-stu-id="511b1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="511b1-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-110">日付型</span><span class="sxs-lookup"><span data-stu-id="511b1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="511b1-111">Primary</span><span class="sxs-lookup"><span data-stu-id="511b1-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="511b1-112">会議出席依頼が CDR エージェントによってキャプチャされた時刻。</span><span class="sxs-lookup"><span data-stu-id="511b1-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="511b1-113">会議インスタンスを一意に識別する主キーとしてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="511b1-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="511b1-114"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-115">int</span><span class="sxs-lookup"><span data-stu-id="511b1-115">int</span></span></p></td>
<td><p><span data-ttu-id="511b1-116">Primary</span><span class="sxs-lookup"><span data-stu-id="511b1-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="511b1-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="511b1-117">ID number to identify the session.</span></span> <span data-ttu-id="511b1-118"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="511b1-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="511b1-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-120">int</span><span class="sxs-lookup"><span data-stu-id="511b1-120">int</span></span></p></td>
<td><p><span data-ttu-id="511b1-121">外部</span><span class="sxs-lookup"><span data-stu-id="511b1-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="511b1-122">会議 URI。</span><span class="sxs-lookup"><span data-stu-id="511b1-122">Conference URI.</span></span> <span data-ttu-id="511b1-123">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="511b1-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="511b1-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-125">識別子</span><span class="sxs-lookup"><span data-stu-id="511b1-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="511b1-126">定期的な電話会議に役立ちます。定期的な会議の各インスタンスには同じ <strong>ConferenceUri</strong>がありますが、別の <strong>confinstance</strong>があります。</span><span class="sxs-lookup"><span data-stu-id="511b1-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="511b1-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-128">日付型</span><span class="sxs-lookup"><span data-stu-id="511b1-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="511b1-129">電話会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="511b1-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="511b1-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-131">日付型</span><span class="sxs-lookup"><span data-stu-id="511b1-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="511b1-132">電話会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="511b1-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="511b1-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-134">int</span><span class="sxs-lookup"><span data-stu-id="511b1-134">int</span></span></p></td>
<td><p><span data-ttu-id="511b1-135">外部</span><span class="sxs-lookup"><span data-stu-id="511b1-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="511b1-136">電話会議がキャプチャされたプールを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="511b1-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="511b1-137">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="511b1-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="511b1-138"><strong>組織の Erid</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-139">Int</span><span class="sxs-lookup"><span data-stu-id="511b1-139">Int</span></span></p></td>
<td><p><span data-ttu-id="511b1-140">外部</span><span class="sxs-lookup"><span data-stu-id="511b1-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="511b1-141">この電話会議の開催者 URI を識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="511b1-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="511b1-142">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="511b1-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="511b1-143"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-144">smallint</span><span class="sxs-lookup"><span data-stu-id="511b1-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="511b1-145">会議の属性を含むビットマスク。</span><span class="sxs-lookup"><span data-stu-id="511b1-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="511b1-146">使用可能な値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="511b1-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="511b1-147">0X01</span><span class="sxs-lookup"><span data-stu-id="511b1-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="511b1-148">代理</span><span class="sxs-lookup"><span data-stu-id="511b1-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="511b1-149">トランザクション</span><span class="sxs-lookup"><span data-stu-id="511b1-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="511b1-150"><strong>実行</strong></span><span class="sxs-lookup"><span data-stu-id="511b1-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="511b1-151">若干</span><span class="sxs-lookup"><span data-stu-id="511b1-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="511b1-152">監視サービスによって使用される内部フィールド。</span><span class="sxs-lookup"><span data-stu-id="511b1-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="511b1-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="511b1-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="511b1-154">\* ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="511b1-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="511b1-155">2つのセッションがまったく同じ時刻に開始された場合は、1つの SessionIdSeq が1になります。その他の場合は2になります。</span><span class="sxs-lookup"><span data-stu-id="511b1-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

