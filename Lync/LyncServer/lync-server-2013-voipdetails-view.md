---
title: 'Lync Server 2013: VoIPDetails ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="778b9-102">Lync Server 2013 の VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="778b9-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="778b9-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="778b9-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="778b9-104">VoIPDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは、少なくとも1人のユーザーが VoIP ユーザーである場合です。</span><span class="sxs-lookup"><span data-stu-id="778b9-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="778b9-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="778b9-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="778b9-106">VoIPDetails ビューには、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A>のすべての列に加えて、以下の列も含まれています。</span><span class="sxs-lookup"><span data-stu-id="778b9-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="778b9-107">列</span><span class="sxs-lookup"><span data-stu-id="778b9-107">Column</span></span></th>
<th><span data-ttu-id="778b9-108">データ型</span><span class="sxs-lookup"><span data-stu-id="778b9-108">Data Type</span></span></th>
<th><span data-ttu-id="778b9-109">詳細</span><span class="sxs-lookup"><span data-stu-id="778b9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="778b9-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="778b9-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="778b9-112">セッションを開始したユーザーの電話の URI。</span><span class="sxs-lookup"><span data-stu-id="778b9-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778b9-113"><strong>電話番号</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="778b9-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="778b9-115">セッションに参加したユーザーの電話の URI。</span><span class="sxs-lookup"><span data-stu-id="778b9-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="778b9-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="778b9-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="778b9-118">セッションを切断したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="778b9-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778b9-119"><strong>Uritん</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="778b9-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="778b9-121">セッションを切断したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="778b9-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="778b9-122">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="778b9-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="778b9-123"><strong>テナント</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="778b9-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="778b9-125">セッションを切断したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="778b9-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778b9-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="778b9-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="778b9-128">セッションを切断したユーザーの電話の URI。</span><span class="sxs-lookup"><span data-stu-id="778b9-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="778b9-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="778b9-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="778b9-131">セッションを開始したユーザーによって使用された仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="778b9-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778b9-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="778b9-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="778b9-134">セッションに参加したユーザーが使用した仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="778b9-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="778b9-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="778b9-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="778b9-137">セッションを開始したユーザーによって使用されたゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="778b9-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778b9-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="778b9-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="778b9-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="778b9-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="778b9-140">セッションに参加したユーザーが使用したゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="778b9-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

