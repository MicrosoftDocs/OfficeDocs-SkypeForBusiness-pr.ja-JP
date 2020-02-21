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
ms.openlocfilehash: 6f01d7fb0a2cb0526d4d6954b303a7cf78bb9333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="c1cab-102">Lync Server 2013 の会議ビュー</span><span class="sxs-lookup"><span data-stu-id="c1cab-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1cab-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c1cab-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c1cab-104">[電話会議] ビューには、電話会議に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c1cab-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="c1cab-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c1cab-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1cab-106">列</span><span class="sxs-lookup"><span data-stu-id="c1cab-106">Column</span></span></th>
<th><span data-ttu-id="c1cab-107">データ型</span><span class="sxs-lookup"><span data-stu-id="c1cab-107">Data Type</span></span></th>
<th><span data-ttu-id="c1cab-108">詳細</span><span class="sxs-lookup"><span data-stu-id="c1cab-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1cab-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-110">日付型</span><span class="sxs-lookup"><span data-stu-id="c1cab-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c1cab-111">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="c1cab-111">Time of session request.</span></span> <span data-ttu-id="c1cab-112">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="c1cab-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c1cab-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1cab-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1cab-114"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-115">int</span><span class="sxs-lookup"><span data-stu-id="c1cab-115">int</span></span></p></td>
<td><p><span data-ttu-id="c1cab-116">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c1cab-116">ID number to identify the session.</span></span> <span data-ttu-id="c1cab-117">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="c1cab-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c1cab-118">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1cab-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1cab-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c1cab-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c1cab-121">電話会議の URI。</span><span class="sxs-lookup"><span data-stu-id="c1cab-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1cab-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c1cab-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1cab-124">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c1cab-124">Type of the conference URI.</span></span> <span data-ttu-id="c1cab-125">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1cab-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1cab-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-127">識別子</span><span class="sxs-lookup"><span data-stu-id="c1cab-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c1cab-p105">定期的な電話会議に使用されます。定期的な電話会議の各インスタンスは、ConferenceUri は同じですが、ConfInstance はそれぞれ異なります。</span><span class="sxs-lookup"><span data-stu-id="c1cab-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1cab-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-131">日付型</span><span class="sxs-lookup"><span data-stu-id="c1cab-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="c1cab-132">電話会議の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="c1cab-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1cab-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-134">日付型</span><span class="sxs-lookup"><span data-stu-id="c1cab-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="c1cab-135">電話会議の終了時刻。</span><span class="sxs-lookup"><span data-stu-id="c1cab-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1cab-136"><strong>オーガナイザー Eruri</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c1cab-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c1cab-138">電話会議を開催したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="c1cab-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1cab-139"><strong>オーガナイザー Ertype</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c1cab-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1cab-141">電話会議を開催したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c1cab-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="c1cab-142">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1cab-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1cab-143"><strong>組織のテナント</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c1cab-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1cab-145">電話会議を開催したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="c1cab-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="c1cab-146">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1cab-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1cab-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c1cab-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1cab-149">電話会議をホストしたプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="c1cab-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1cab-150"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c1cab-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c1cab-151">smallint</span><span class="sxs-lookup"><span data-stu-id="c1cab-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="c1cab-p108">電話会議の属性が格納されているビット マスク。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c1cab-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="c1cab-154">0X01 – 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="c1cab-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

