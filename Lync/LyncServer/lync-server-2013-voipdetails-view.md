---
title: 'Lync Server 2013: VoIPDetails ビュー'
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
ms.openlocfilehash: 0dc01632579c6455c47113f34e181f6598b7c781
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535384"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="2e410-102">Lync Server 2013 の VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="2e410-102">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e410-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2e410-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2e410-104">VoIPDetails ビューには、少なくとも 1 人のユーザーが VoIP ユーザーであるピアツーピア セッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e410-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="2e410-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2e410-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e410-106">VoIPDetails ビューには、以下の列に加えて、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A> のすべての列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e410-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e410-107">Column</span><span class="sxs-lookup"><span data-stu-id="2e410-107">Column</span></span></th>
<th><span data-ttu-id="2e410-108">データ型</span><span class="sxs-lookup"><span data-stu-id="2e410-108">Data Type</span></span></th>
<th><span data-ttu-id="2e410-109">詳細</span><span class="sxs-lookup"><span data-stu-id="2e410-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e410-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2e410-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2e410-112">セッションを開始したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="2e410-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e410-113"><strong>ToPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2e410-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2e410-115">セッションに参加したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="2e410-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e410-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2e410-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2e410-118">セッションを切断したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="2e410-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e410-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2e410-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2e410-121">セッションを切断したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="2e410-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="2e410-122">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e410-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e410-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2e410-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2e410-125">セッションを切断したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="2e410-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e410-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2e410-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2e410-128">セッションを切断したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="2e410-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e410-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2e410-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2e410-131">セッションを開始したユーザーの仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="2e410-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e410-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2e410-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2e410-134">セッションに参加したユーザーの仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="2e410-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e410-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2e410-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2e410-137">セッションを開始したユーザーが使用するゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="2e410-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e410-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="2e410-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2e410-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2e410-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2e410-140">セッションに参加したユーザーが使用するゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="2e410-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

