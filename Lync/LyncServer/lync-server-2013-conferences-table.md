---
title: 'Lync Server 2013: 電話会議テーブル'
description: 'Lync Server 2013: 電話会議テーブル'
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
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561603"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="9db13-103">Lync Server 2013 の会議テーブル</span><span class="sxs-lookup"><span data-stu-id="9db13-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9db13-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9db13-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9db13-105">この表の各レコードには、1つの会議に関する通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9db13-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9db13-106">Column</span><span class="sxs-lookup"><span data-stu-id="9db13-106">Column</span></span></th>
<th><span data-ttu-id="9db13-107">データ型</span><span class="sxs-lookup"><span data-stu-id="9db13-107">Data Type</span></span></th>
<th><span data-ttu-id="9db13-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="9db13-108">Key/Index</span></span></th>
<th><span data-ttu-id="9db13-109">詳細</span><span class="sxs-lookup"><span data-stu-id="9db13-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9db13-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-111">日付型</span><span class="sxs-lookup"><span data-stu-id="9db13-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9db13-112">Primary</span><span class="sxs-lookup"><span data-stu-id="9db13-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9db13-113">会議出席依頼が CDR エージェントによってキャプチャされた時刻。</span><span class="sxs-lookup"><span data-stu-id="9db13-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="9db13-114">会議インスタンスを一意に識別する主キーとしてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="9db13-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db13-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-116">int</span><span class="sxs-lookup"><span data-stu-id="9db13-116">int</span></span></p></td>
<td><p><span data-ttu-id="9db13-117">Primary</span><span class="sxs-lookup"><span data-stu-id="9db13-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="9db13-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="9db13-118">ID number to identify the session.</span></span> <span data-ttu-id="9db13-119"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9db13-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db13-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-121">int</span><span class="sxs-lookup"><span data-stu-id="9db13-121">int</span></span></p></td>
<td><p><span data-ttu-id="9db13-122">外部</span><span class="sxs-lookup"><span data-stu-id="9db13-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db13-123">会議 URI。</span><span class="sxs-lookup"><span data-stu-id="9db13-123">Conference URI.</span></span> <span data-ttu-id="9db13-124">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9db13-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db13-125"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-126">識別子</span><span class="sxs-lookup"><span data-stu-id="9db13-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9db13-127">定期的な電話会議に役立ちます。定期的な会議の各インスタンスには同じ <strong>ConferenceUri</strong>がありますが、別の <strong>confinstance</strong>があります。</span><span class="sxs-lookup"><span data-stu-id="9db13-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db13-128"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-129">日付型</span><span class="sxs-lookup"><span data-stu-id="9db13-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9db13-130">電話会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="9db13-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db13-131"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-132">日付型</span><span class="sxs-lookup"><span data-stu-id="9db13-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9db13-133">電話会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="9db13-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db13-134"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-135">int</span><span class="sxs-lookup"><span data-stu-id="9db13-135">int</span></span></p></td>
<td><p><span data-ttu-id="9db13-136">外部</span><span class="sxs-lookup"><span data-stu-id="9db13-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db13-137">電話会議がキャプチャされたプールを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="9db13-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="9db13-138">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9db13-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db13-139"><strong>組織の Erid</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-140">Int</span><span class="sxs-lookup"><span data-stu-id="9db13-140">Int</span></span></p></td>
<td><p><span data-ttu-id="9db13-141">外部</span><span class="sxs-lookup"><span data-stu-id="9db13-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db13-142">この電話会議の開催者 URI を識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="9db13-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="9db13-143">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9db13-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db13-144"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-145">smallint</span><span class="sxs-lookup"><span data-stu-id="9db13-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9db13-146">会議の属性を含むビットマスク。</span><span class="sxs-lookup"><span data-stu-id="9db13-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="9db13-147">使用可能な値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="9db13-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9db13-148">0X01</span><span class="sxs-lookup"><span data-stu-id="9db13-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="9db13-149">代理</span><span class="sxs-lookup"><span data-stu-id="9db13-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="9db13-150">トランザクション</span><span class="sxs-lookup"><span data-stu-id="9db13-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db13-151"><strong>実行</strong></span><span class="sxs-lookup"><span data-stu-id="9db13-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="9db13-152">若干</span><span class="sxs-lookup"><span data-stu-id="9db13-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9db13-153">監視サービスによって使用される内部フィールド。</span><span class="sxs-lookup"><span data-stu-id="9db13-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="9db13-154">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9db13-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9db13-155">\* ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="9db13-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="9db13-156">2つのセッションがまったく同じ時刻に開始された場合は、1つの SessionIdSeq が1になります。その他の場合は2になります。</span><span class="sxs-lookup"><span data-stu-id="9db13-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

