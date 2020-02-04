---
title: 'Lync Server 2013: 会議ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="94a7b-102">Lync Server 2013 での会議ビュー</span><span class="sxs-lookup"><span data-stu-id="94a7b-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94a7b-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="94a7b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="94a7b-104">会議ビューには、会議に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="94a7b-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="94a7b-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="94a7b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94a7b-106">列</span><span class="sxs-lookup"><span data-stu-id="94a7b-106">Column</span></span></th>
<th><span data-ttu-id="94a7b-107">データ型</span><span class="sxs-lookup"><span data-stu-id="94a7b-107">Data Type</span></span></th>
<th><span data-ttu-id="94a7b-108">詳細</span><span class="sxs-lookup"><span data-stu-id="94a7b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94a7b-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="94a7b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="94a7b-111">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="94a7b-111">Time of session request.</span></span> <span data-ttu-id="94a7b-112">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="94a7b-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="94a7b-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a7b-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94a7b-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-115">int</span><span class="sxs-lookup"><span data-stu-id="94a7b-115">int</span></span></p></td>
<td><p><span data-ttu-id="94a7b-116">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="94a7b-116">ID number to identify the session.</span></span> <span data-ttu-id="94a7b-117">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="94a7b-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="94a7b-118">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a7b-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94a7b-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="94a7b-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="94a7b-121">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="94a7b-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94a7b-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="94a7b-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="94a7b-124">会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="94a7b-124">Type of the conference URI.</span></span> <span data-ttu-id="94a7b-125">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a7b-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94a7b-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-127">長さ</span><span class="sxs-lookup"><span data-stu-id="94a7b-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="94a7b-128">定期的な会議に使用されます。</span><span class="sxs-lookup"><span data-stu-id="94a7b-128">Used for recurring conferences.</span></span> <span data-ttu-id="94a7b-129">定期的な会議の各インスタンスには、同じ ConferenceUri がありますが、ConfInstance は異なります。</span><span class="sxs-lookup"><span data-stu-id="94a7b-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94a7b-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-131">datetime</span><span class="sxs-lookup"><span data-stu-id="94a7b-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="94a7b-132">会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="94a7b-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94a7b-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-134">datetime</span><span class="sxs-lookup"><span data-stu-id="94a7b-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="94a7b-135">会議の終了時刻。</span><span class="sxs-lookup"><span data-stu-id="94a7b-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94a7b-136"><strong>オーガナイザーの Uri</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="94a7b-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="94a7b-138">会議を開催したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="94a7b-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94a7b-139"><strong>オーガナイザーの種類</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="94a7b-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="94a7b-141">会議を開催したユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="94a7b-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="94a7b-142">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a7b-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94a7b-143"><strong>組織のテナント</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="94a7b-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="94a7b-145">会議を開催したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="94a7b-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="94a7b-146">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a7b-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94a7b-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="94a7b-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="94a7b-149">会議をホストしているプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="94a7b-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94a7b-150"><strong>フラッグ</strong></span><span class="sxs-lookup"><span data-stu-id="94a7b-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="94a7b-151">smallint</span><span class="sxs-lookup"><span data-stu-id="94a7b-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="94a7b-152">会議の属性が含まれているビットマスク。</span><span class="sxs-lookup"><span data-stu-id="94a7b-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="94a7b-153">値の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94a7b-153">Possible values are:</span></span></p>
<p><span data-ttu-id="94a7b-154">0X01 –代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="94a7b-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

