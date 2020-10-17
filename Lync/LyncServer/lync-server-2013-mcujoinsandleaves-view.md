---
title: 'Lync Server 2013: McuJoinsAndLeaves ビュー'
description: 'Lync Server 2013: McuJoinsAndLeaves ビュー。'
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
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556493"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="99c03-103">Lync Server 2013 の McuJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="99c03-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c03-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="99c03-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="99c03-105">McuJoinsAndLeaves ビューには、1 つの会議サーバーのユーザーの参加および退出情報についての情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="99c03-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="99c03-106">このビューの各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99c03-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="99c03-107">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="99c03-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99c03-108">Column</span><span class="sxs-lookup"><span data-stu-id="99c03-108">Column</span></span></th>
<th><span data-ttu-id="99c03-109">データ型</span><span class="sxs-lookup"><span data-stu-id="99c03-109">Data Type</span></span></th>
<th><span data-ttu-id="99c03-110">詳細</span><span class="sxs-lookup"><span data-stu-id="99c03-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99c03-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-112">日付型</span><span class="sxs-lookup"><span data-stu-id="99c03-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="99c03-113">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="99c03-113">Time of conference instance.</span></span> <span data-ttu-id="99c03-114">SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="99c03-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="99c03-115">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c03-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c03-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-117">int</span><span class="sxs-lookup"><span data-stu-id="99c03-117">int</span></span></p></td>
<td><p><span data-ttu-id="99c03-118">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="99c03-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="99c03-119">SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="99c03-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="99c03-120">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c03-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c03-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="99c03-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="99c03-123">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="99c03-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c03-124"><strong>Mcuuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="99c03-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="99c03-126">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="99c03-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="99c03-127">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c03-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c03-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-129">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="99c03-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="99c03-130">会議サーバーの参加/退出情報がキャプチャされたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="99c03-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c03-131"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="99c03-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="99c03-133">会議サーバーの参加/退出情報がキャプチャされたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="99c03-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="99c03-134">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c03-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c03-135"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="99c03-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="99c03-137">会議サーバーの参加/退出情報がキャプチャされたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="99c03-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="99c03-138">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c03-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c03-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="99c03-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="99c03-141">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="99c03-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c03-142"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-143">int</span><span class="sxs-lookup"><span data-stu-id="99c03-143">int</span></span></p></td>
<td><p><span data-ttu-id="99c03-144">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="99c03-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="99c03-145">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c03-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c03-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-147">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="99c03-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="99c03-148">会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="99c03-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c03-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-150">int</span><span class="sxs-lookup"><span data-stu-id="99c03-150">int</span></span></p></td>
<td><p><span data-ttu-id="99c03-151">複数のデバイスに同時にログオンしているユーザー用に、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="99c03-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c03-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-153">若干</span><span class="sxs-lookup"><span data-stu-id="99c03-153">bit</span></span></p></td>
<td><p><span data-ttu-id="99c03-154">ユーザーが内部ユーザーかどうかを示すビット。</span><span class="sxs-lookup"><span data-stu-id="99c03-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c03-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-156">日付型</span><span class="sxs-lookup"><span data-stu-id="99c03-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="99c03-157">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="99c03-157">Time of session request.</span></span> <span data-ttu-id="99c03-158">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="99c03-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="99c03-159">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c03-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c03-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-161">int</span><span class="sxs-lookup"><span data-stu-id="99c03-161">int</span></span></p></td>
<td><p><span data-ttu-id="99c03-162">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="99c03-162">ID number to identify the session.</span></span> <span data-ttu-id="99c03-163">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="99c03-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="99c03-164">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c03-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c03-165"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-166">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="99c03-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="99c03-p110">セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。</span><span class="sxs-lookup"><span data-stu-id="99c03-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c03-169"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-170">日付型</span><span class="sxs-lookup"><span data-stu-id="99c03-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="99c03-171">ユーザーが会議サーバーに参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="99c03-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c03-172"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="99c03-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="99c03-173">日付型</span><span class="sxs-lookup"><span data-stu-id="99c03-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="99c03-174">ユーザーが会議サーバーから退出した時刻。</span><span class="sxs-lookup"><span data-stu-id="99c03-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

