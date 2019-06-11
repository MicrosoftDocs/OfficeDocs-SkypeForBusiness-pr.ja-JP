---
title: 'Lync Server 2013: McuJoinsAndLeaves view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="06749-102">Lync Server 2013 での McuJoinsAndLeaves の表示</span><span class="sxs-lookup"><span data-stu-id="06749-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06749-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="06749-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="06749-104">McuJoinsAndLeaves ビューには、1台の会議サーバーの情報の参加と脱退に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="06749-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="06749-105">このビューの各レコードには、ユーザーの参加または退出と会議サーバーの1つの組み合わせについての通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06749-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="06749-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="06749-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06749-107">列</span><span class="sxs-lookup"><span data-stu-id="06749-107">Column</span></span></th>
<th><span data-ttu-id="06749-108">データ型</span><span class="sxs-lookup"><span data-stu-id="06749-108">Data Type</span></span></th>
<th><span data-ttu-id="06749-109">詳細</span><span class="sxs-lookup"><span data-stu-id="06749-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06749-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="06749-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-111">datetime</span><span class="sxs-lookup"><span data-stu-id="06749-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="06749-112">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="06749-112">Time of conference instance.</span></span> <span data-ttu-id="06749-113">電話会議インスタンスを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="06749-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="06749-114">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06749-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06749-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="06749-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-116">int</span><span class="sxs-lookup"><span data-stu-id="06749-116">int</span></span></p></td>
<td><p><span data-ttu-id="06749-117">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="06749-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="06749-118">電話会議インスタンスを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="06749-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="06749-119">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06749-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06749-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="06749-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06749-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="06749-122">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="06749-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06749-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="06749-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06749-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="06749-125">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="06749-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="06749-126">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06749-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06749-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="06749-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="06749-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="06749-129">会議サーバーの参加/脱退情報がキャプチャされたユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="06749-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06749-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="06749-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06749-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="06749-132">会議サーバーの参加/脱退情報がキャプチャされたユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="06749-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="06749-133">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06749-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06749-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="06749-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06749-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="06749-136">会議サーバーの参加/脱退情報がキャプチャされたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="06749-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="06749-137">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06749-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06749-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="06749-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06749-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="06749-140">会議サーバーの参加/退席中の情報がキャプチャされたユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="06749-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06749-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="06749-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-142">int</span><span class="sxs-lookup"><span data-stu-id="06749-142">int</span></span></p></td>
<td><p><span data-ttu-id="06749-143">会議サーバーの参加/脱退情報がキャプチャされたユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="06749-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="06749-144">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06749-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06749-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="06749-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="06749-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="06749-147">会議サーバーの参加/脱退情報がキャプチャされたユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="06749-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06749-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="06749-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-149">int</span><span class="sxs-lookup"><span data-stu-id="06749-149">int</span></span></p></td>
<td><p><span data-ttu-id="06749-150">複数のデバイスに同時にログオンしているユーザーのために、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="06749-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06749-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="06749-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-152">bit</span><span class="sxs-lookup"><span data-stu-id="06749-152">bit</span></span></p></td>
<td><p><span data-ttu-id="06749-153">ユーザーが内部ユーザーかどうかを表すビット。</span><span class="sxs-lookup"><span data-stu-id="06749-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06749-154"><strong>/セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="06749-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-155">datetime</span><span class="sxs-lookup"><span data-stu-id="06749-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="06749-156">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="06749-156">Time of session request.</span></span> <span data-ttu-id="06749-157">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="06749-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="06749-158">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06749-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06749-159"><strong>"/セッション Id"</strong></span><span class="sxs-lookup"><span data-stu-id="06749-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-160">int</span><span class="sxs-lookup"><span data-stu-id="06749-160">int</span></span></p></td>
<td><p><span data-ttu-id="06749-161">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="06749-161">ID number to identify the session.</span></span> <span data-ttu-id="06749-162">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="06749-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="06749-163">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06749-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06749-164"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="06749-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="06749-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="06749-166">セッションの SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="06749-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="06749-167">形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="06749-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06749-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="06749-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-169">datetime</span><span class="sxs-lookup"><span data-stu-id="06749-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="06749-170">ユーザーが会議サーバーに参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="06749-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06749-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="06749-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="06749-172">datetime</span><span class="sxs-lookup"><span data-stu-id="06749-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="06749-173">ユーザーが会議サーバーを脱退した時刻。</span><span class="sxs-lookup"><span data-stu-id="06749-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

