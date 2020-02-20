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
ms.openlocfilehash: a217ddc3ef362c99e5cb7686594e5f9068ce4970
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="07a05-102">Lync Server 2013 の McuJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="07a05-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07a05-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="07a05-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="07a05-104">McuJoinsAndLeaves ビューには、1 つの会議サーバーのユーザーの参加および退出情報についての情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="07a05-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="07a05-105">このビューの各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="07a05-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="07a05-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="07a05-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07a05-107">列</span><span class="sxs-lookup"><span data-stu-id="07a05-107">Column</span></span></th>
<th><span data-ttu-id="07a05-108">データ型</span><span class="sxs-lookup"><span data-stu-id="07a05-108">Data Type</span></span></th>
<th><span data-ttu-id="07a05-109">詳細</span><span class="sxs-lookup"><span data-stu-id="07a05-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07a05-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-111">日付型</span><span class="sxs-lookup"><span data-stu-id="07a05-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="07a05-112">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="07a05-112">Time of conference instance.</span></span> <span data-ttu-id="07a05-113">SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="07a05-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="07a05-114">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a05-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a05-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-116">int</span><span class="sxs-lookup"><span data-stu-id="07a05-116">int</span></span></p></td>
<td><p><span data-ttu-id="07a05-117">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="07a05-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="07a05-118">SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="07a05-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="07a05-119">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a05-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a05-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="07a05-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="07a05-122">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="07a05-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a05-123"><strong>Mcuuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="07a05-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="07a05-125">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="07a05-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="07a05-126">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a05-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a05-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="07a05-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="07a05-129">会議サーバーの参加/退出情報がキャプチャされたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="07a05-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a05-130"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="07a05-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="07a05-132">会議サーバーの参加/退出情報がキャプチャされたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="07a05-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="07a05-133">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a05-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a05-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="07a05-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="07a05-136">会議サーバーの参加/退出情報がキャプチャされたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="07a05-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="07a05-137">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a05-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a05-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="07a05-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="07a05-140">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="07a05-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a05-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-142">int</span><span class="sxs-lookup"><span data-stu-id="07a05-142">int</span></span></p></td>
<td><p><span data-ttu-id="07a05-143">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="07a05-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="07a05-144">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a05-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a05-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="07a05-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="07a05-147">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="07a05-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a05-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-149">int</span><span class="sxs-lookup"><span data-stu-id="07a05-149">int</span></span></p></td>
<td><p><span data-ttu-id="07a05-150">複数のデバイスに同時にログオンしているユーザー用に、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="07a05-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a05-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-152">若干</span><span class="sxs-lookup"><span data-stu-id="07a05-152">bit</span></span></p></td>
<td><p><span data-ttu-id="07a05-153">ユーザーが内部ユーザーかどうかを示すビット。</span><span class="sxs-lookup"><span data-stu-id="07a05-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a05-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-155">日付型</span><span class="sxs-lookup"><span data-stu-id="07a05-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="07a05-156">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="07a05-156">Time of session request.</span></span> <span data-ttu-id="07a05-157">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="07a05-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="07a05-158">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a05-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a05-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-160">int</span><span class="sxs-lookup"><span data-stu-id="07a05-160">int</span></span></p></td>
<td><p><span data-ttu-id="07a05-161">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="07a05-161">ID number to identify the session.</span></span> <span data-ttu-id="07a05-162">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="07a05-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="07a05-163">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a05-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a05-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="07a05-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="07a05-p110">セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。</span><span class="sxs-lookup"><span data-stu-id="07a05-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a05-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-169">日付型</span><span class="sxs-lookup"><span data-stu-id="07a05-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="07a05-170">ユーザーが会議サーバーに参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="07a05-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a05-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="07a05-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="07a05-172">日付型</span><span class="sxs-lookup"><span data-stu-id="07a05-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="07a05-173">ユーザーが会議サーバーから退出した時刻。</span><span class="sxs-lookup"><span data-stu-id="07a05-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

