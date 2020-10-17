---
title: 'Lync Server 2013: VoIPDetails ビュー'
description: 'Lync Server 2013: VoIPDetails ビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566203"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="c74fe-103">Lync Server 2013 の VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="c74fe-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c74fe-104">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c74fe-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c74fe-105">VoIPDetails ビューには、少なくとも 1 人のユーザーが VoIP ユーザーであるピアツーピア セッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c74fe-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="c74fe-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c74fe-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c74fe-107">VoIPDetails ビューには、以下の列に加えて、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A> のすべての列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c74fe-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c74fe-108">Column</span><span class="sxs-lookup"><span data-stu-id="c74fe-108">Column</span></span></th>
<th><span data-ttu-id="c74fe-109">データ型</span><span class="sxs-lookup"><span data-stu-id="c74fe-109">Data Type</span></span></th>
<th><span data-ttu-id="c74fe-110">詳細</span><span class="sxs-lookup"><span data-stu-id="c74fe-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c74fe-111"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c74fe-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-113">セッションを開始したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="c74fe-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c74fe-114"><strong>ToPhone</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c74fe-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-116">セッションに参加したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="c74fe-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c74fe-117"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c74fe-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-119">セッションを切断したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="c74fe-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c74fe-120"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c74fe-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-122">セッションを切断したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c74fe-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="c74fe-123">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c74fe-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c74fe-124"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c74fe-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-126">セッションを切断したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="c74fe-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c74fe-127"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c74fe-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-129">セッションを切断したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="c74fe-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c74fe-130"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c74fe-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-132">セッションを開始したユーザーの仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="c74fe-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c74fe-133"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c74fe-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-135">セッションに参加したユーザーの仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="c74fe-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c74fe-136"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c74fe-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-138">セッションを開始したユーザーが使用するゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="c74fe-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c74fe-139"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="c74fe-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="c74fe-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c74fe-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c74fe-141">セッションに参加したユーザーが使用するゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="c74fe-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

