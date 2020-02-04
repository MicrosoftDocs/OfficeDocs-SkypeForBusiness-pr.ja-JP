---
title: 'Lync Server 2013: McuJoinsAndLeaves view'
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
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="54e24-102">Lync Server 2013 での McuJoinsAndLeaves の表示</span><span class="sxs-lookup"><span data-stu-id="54e24-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54e24-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="54e24-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="54e24-104">McuJoinsAndLeaves ビューには、1台の会議サーバーの情報の参加と脱退に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="54e24-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="54e24-105">このビューの各レコードには、ユーザーの参加または退出と会議サーバーの1つの組み合わせについての通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="54e24-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="54e24-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="54e24-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54e24-107">列</span><span class="sxs-lookup"><span data-stu-id="54e24-107">Column</span></span></th>
<th><span data-ttu-id="54e24-108">データ型</span><span class="sxs-lookup"><span data-stu-id="54e24-108">Data Type</span></span></th>
<th><span data-ttu-id="54e24-109">詳細</span><span class="sxs-lookup"><span data-stu-id="54e24-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54e24-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-111">datetime</span><span class="sxs-lookup"><span data-stu-id="54e24-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="54e24-112">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="54e24-112">Time of conference instance.</span></span> <span data-ttu-id="54e24-113">電話会議インスタンスを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="54e24-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="54e24-114">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e24-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e24-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-116">int</span><span class="sxs-lookup"><span data-stu-id="54e24-116">int</span></span></p></td>
<td><p><span data-ttu-id="54e24-117">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="54e24-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="54e24-118">電話会議インスタンスを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="54e24-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="54e24-119">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e24-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e24-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="54e24-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54e24-122">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="54e24-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e24-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="54e24-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54e24-125">ユーザーが接続した会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="54e24-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="54e24-126">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e24-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e24-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="54e24-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="54e24-129">会議サーバーの参加/脱退情報がキャプチャされたユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="54e24-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e24-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="54e24-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54e24-132">会議サーバーの参加/脱退情報がキャプチャされたユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="54e24-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="54e24-133">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e24-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e24-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="54e24-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54e24-136">会議サーバーの参加/脱退情報がキャプチャされたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="54e24-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="54e24-137">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e24-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e24-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="54e24-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54e24-140">会議サーバーの参加/退席中の情報がキャプチャされたユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="54e24-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e24-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-142">int</span><span class="sxs-lookup"><span data-stu-id="54e24-142">int</span></span></p></td>
<td><p><span data-ttu-id="54e24-143">会議サーバーの参加/脱退情報がキャプチャされたユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="54e24-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="54e24-144">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e24-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e24-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="54e24-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="54e24-147">会議サーバーの参加/脱退情報がキャプチャされたユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="54e24-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e24-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-149">int</span><span class="sxs-lookup"><span data-stu-id="54e24-149">int</span></span></p></td>
<td><p><span data-ttu-id="54e24-150">複数のデバイスに同時にログオンしているユーザーのために、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="54e24-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e24-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-152">bit</span><span class="sxs-lookup"><span data-stu-id="54e24-152">bit</span></span></p></td>
<td><p><span data-ttu-id="54e24-153">ユーザーが内部ユーザーかどうかを表すビット。</span><span class="sxs-lookup"><span data-stu-id="54e24-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e24-154"><strong>/セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-155">datetime</span><span class="sxs-lookup"><span data-stu-id="54e24-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="54e24-156">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="54e24-156">Time of session request.</span></span> <span data-ttu-id="54e24-157">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="54e24-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="54e24-158">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e24-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e24-159"><strong>"/セッション Id"</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-160">int</span><span class="sxs-lookup"><span data-stu-id="54e24-160">int</span></span></p></td>
<td><p><span data-ttu-id="54e24-161">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="54e24-161">ID number to identify the session.</span></span> <span data-ttu-id="54e24-162">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="54e24-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="54e24-163">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e24-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e24-164"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="54e24-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="54e24-166">セッションの SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="54e24-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="54e24-167">形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="54e24-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e24-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-169">datetime</span><span class="sxs-lookup"><span data-stu-id="54e24-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="54e24-170">ユーザーが会議サーバーに参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="54e24-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e24-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="54e24-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="54e24-172">datetime</span><span class="sxs-lookup"><span data-stu-id="54e24-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="54e24-173">ユーザーが会議サーバーを脱退した時刻。</span><span class="sxs-lookup"><span data-stu-id="54e24-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

