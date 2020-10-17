---
title: 'Lync Server 2013: 会議ビュー'
description: 'Lync Server 2013: 会議ビュー。'
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
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561583"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="56c1c-103">Lync Server 2013 の会議ビュー</span><span class="sxs-lookup"><span data-stu-id="56c1c-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56c1c-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="56c1c-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="56c1c-105">[電話会議] ビューには、電話会議に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="56c1c-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="56c1c-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="56c1c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56c1c-107">Column</span><span class="sxs-lookup"><span data-stu-id="56c1c-107">Column</span></span></th>
<th><span data-ttu-id="56c1c-108">データ型</span><span class="sxs-lookup"><span data-stu-id="56c1c-108">Data Type</span></span></th>
<th><span data-ttu-id="56c1c-109">詳細</span><span class="sxs-lookup"><span data-stu-id="56c1c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56c1c-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-111">日付型</span><span class="sxs-lookup"><span data-stu-id="56c1c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="56c1c-112">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="56c1c-112">Time of session request.</span></span> <span data-ttu-id="56c1c-113">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="56c1c-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="56c1c-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c1c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56c1c-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-116">int</span><span class="sxs-lookup"><span data-stu-id="56c1c-116">int</span></span></p></td>
<td><p><span data-ttu-id="56c1c-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="56c1c-117">ID number to identify the session.</span></span> <span data-ttu-id="56c1c-118">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="56c1c-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="56c1c-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c1c-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56c1c-120"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="56c1c-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="56c1c-122">電話会議の URI。</span><span class="sxs-lookup"><span data-stu-id="56c1c-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56c1c-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="56c1c-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="56c1c-125">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="56c1c-125">Type of the conference URI.</span></span> <span data-ttu-id="56c1c-126">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c1c-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56c1c-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-128">識別子</span><span class="sxs-lookup"><span data-stu-id="56c1c-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="56c1c-p105">定期的な電話会議に使用されます。定期的な電話会議の各インスタンスは、ConferenceUri は同じですが、ConfInstance はそれぞれ異なります。</span><span class="sxs-lookup"><span data-stu-id="56c1c-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56c1c-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-132">日付型</span><span class="sxs-lookup"><span data-stu-id="56c1c-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="56c1c-133">電話会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="56c1c-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56c1c-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-135">日付型</span><span class="sxs-lookup"><span data-stu-id="56c1c-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="56c1c-136">電話会議の終了時刻。</span><span class="sxs-lookup"><span data-stu-id="56c1c-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56c1c-137"><strong>オーガナイザー Eruri</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="56c1c-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="56c1c-139">電話会議を開催したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="56c1c-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56c1c-140"><strong>オーガナイザー Ertype</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="56c1c-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="56c1c-142">電話会議を開催したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="56c1c-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="56c1c-143">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c1c-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56c1c-144"><strong>組織のテナント</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="56c1c-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="56c1c-146">電話会議を開催したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="56c1c-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="56c1c-147">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c1c-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56c1c-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="56c1c-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="56c1c-150">電話会議をホストしたプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="56c1c-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56c1c-151"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="56c1c-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="56c1c-152">smallint</span><span class="sxs-lookup"><span data-stu-id="56c1c-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="56c1c-p108">電話会議の属性が格納されているビット マスク。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56c1c-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="56c1c-155">0X01 – 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="56c1c-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

