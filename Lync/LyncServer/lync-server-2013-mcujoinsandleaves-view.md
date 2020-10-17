---
title: 'Lync Server 2013: McuJoinsAndLeaves ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 329396549a02a354939b166c8785b875faee2f78
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524724"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="7bf95-102">Lync Server 2013 の McuJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="7bf95-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bf95-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7bf95-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7bf95-104">McuJoinsAndLeaves ビューには、1 つの会議サーバーのユーザーの参加および退出情報についての情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7bf95-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="7bf95-105">このビューの各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7bf95-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="7bf95-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7bf95-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bf95-107">Column</span><span class="sxs-lookup"><span data-stu-id="7bf95-107">Column</span></span></th>
<th><span data-ttu-id="7bf95-108">データ型</span><span class="sxs-lookup"><span data-stu-id="7bf95-108">Data Type</span></span></th>
<th><span data-ttu-id="7bf95-109">詳細</span><span class="sxs-lookup"><span data-stu-id="7bf95-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-111">日付型</span><span class="sxs-lookup"><span data-stu-id="7bf95-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7bf95-112">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="7bf95-112">Time of conference instance.</span></span> <span data-ttu-id="7bf95-113">SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="7bf95-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="7bf95-114">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf95-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf95-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-116">int</span><span class="sxs-lookup"><span data-stu-id="7bf95-116">int</span></span></p></td>
<td><p><span data-ttu-id="7bf95-117">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="7bf95-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="7bf95-118">SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="7bf95-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="7bf95-119">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf95-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7bf95-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7bf95-122">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="7bf95-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf95-123"><strong>Mcuuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7bf95-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7bf95-125">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="7bf95-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="7bf95-126">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf95-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7bf95-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7bf95-129">会議サーバーの参加/退出情報がキャプチャされたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="7bf95-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf95-130"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7bf95-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7bf95-132">会議サーバーの参加/退出情報がキャプチャされたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="7bf95-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="7bf95-133">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf95-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7bf95-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7bf95-136">会議サーバーの参加/退出情報がキャプチャされたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="7bf95-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="7bf95-137">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf95-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf95-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7bf95-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7bf95-140">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="7bf95-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-142">int</span><span class="sxs-lookup"><span data-stu-id="7bf95-142">int</span></span></p></td>
<td><p><span data-ttu-id="7bf95-143">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="7bf95-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="7bf95-144">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf95-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf95-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7bf95-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7bf95-147">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="7bf95-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-149">int</span><span class="sxs-lookup"><span data-stu-id="7bf95-149">int</span></span></p></td>
<td><p><span data-ttu-id="7bf95-150">複数のデバイスに同時にログオンしているユーザー用に、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="7bf95-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf95-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-152">若干</span><span class="sxs-lookup"><span data-stu-id="7bf95-152">bit</span></span></p></td>
<td><p><span data-ttu-id="7bf95-153">ユーザーが内部ユーザーかどうかを示すビット。</span><span class="sxs-lookup"><span data-stu-id="7bf95-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-155">日付型</span><span class="sxs-lookup"><span data-stu-id="7bf95-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="7bf95-156">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="7bf95-156">Time of session request.</span></span> <span data-ttu-id="7bf95-157">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="7bf95-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="7bf95-158">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf95-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf95-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-160">int</span><span class="sxs-lookup"><span data-stu-id="7bf95-160">int</span></span></p></td>
<td><p><span data-ttu-id="7bf95-161">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="7bf95-161">ID number to identify the session.</span></span> <span data-ttu-id="7bf95-162">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="7bf95-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="7bf95-163">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf95-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="7bf95-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="7bf95-p110">セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。</span><span class="sxs-lookup"><span data-stu-id="7bf95-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf95-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-169">日付型</span><span class="sxs-lookup"><span data-stu-id="7bf95-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="7bf95-170">ユーザーが会議サーバーに参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="7bf95-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf95-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="7bf95-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7bf95-172">日付型</span><span class="sxs-lookup"><span data-stu-id="7bf95-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="7bf95-173">ユーザーが会議サーバーから退出した時刻。</span><span class="sxs-lookup"><span data-stu-id="7bf95-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

