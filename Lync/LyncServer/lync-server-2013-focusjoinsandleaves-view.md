---
title: 'Lync Server 2013: FocusJoinsAndLeaves view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7cc1da4f5923a7c42e74c9069054863f1d99a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="324ed-102">Lync Server 2013 での FocusJoinsAndLeaves の表示</span><span class="sxs-lookup"><span data-stu-id="324ed-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="324ed-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="324ed-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="324ed-104">FocusJoinsAndLeaves ビューには、1人の会議に参加するための情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="324ed-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="324ed-105">各会議は、ユーザーが会議に参加して退席するたびに書き込まれるレコードによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="324ed-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="324ed-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="324ed-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="324ed-107">列</span><span class="sxs-lookup"><span data-stu-id="324ed-107">Column</span></span></th>
<th><span data-ttu-id="324ed-108">データ型</span><span class="sxs-lookup"><span data-stu-id="324ed-108">Data Type</span></span></th>
<th><span data-ttu-id="324ed-109">詳細</span><span class="sxs-lookup"><span data-stu-id="324ed-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="324ed-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-111">datetime</span><span class="sxs-lookup"><span data-stu-id="324ed-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="324ed-112">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="324ed-112">Time of conference instance.</span></span> <span data-ttu-id="324ed-113">電話会議インスタンスを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="324ed-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="324ed-114">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="324ed-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="324ed-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-116">int</span><span class="sxs-lookup"><span data-stu-id="324ed-116">int</span></span></p></td>
<td><p><span data-ttu-id="324ed-117">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="324ed-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="324ed-118">電話会議インスタンスを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="324ed-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="324ed-119">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="324ed-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="324ed-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="324ed-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="324ed-122">会議の参加/退出情報がキャプチャされたユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="324ed-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="324ed-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="324ed-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="324ed-125">会議の参加/退出情報がキャプチャされたユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="324ed-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="324ed-126">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="324ed-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="324ed-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="324ed-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="324ed-129">会議の参加/退出情報がキャプチャされたユーザーのテナントです。</span><span class="sxs-lookup"><span data-stu-id="324ed-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="324ed-130">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="324ed-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="324ed-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-132">長さ</span><span class="sxs-lookup"><span data-stu-id="324ed-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="324ed-133">会議の参加/退出情報がキャプチャされたユーザーを表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="324ed-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="324ed-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="324ed-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="324ed-136">会議の参加/退出情報がキャプチャされたユーザーが使用したクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="324ed-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="324ed-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-138">int</span><span class="sxs-lookup"><span data-stu-id="324ed-138">int</span></span></p></td>
<td><p><span data-ttu-id="324ed-139">電話会議の参加/退出情報がキャプチャされたユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="324ed-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="324ed-140">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="324ed-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="324ed-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="324ed-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="324ed-143">会議の参加/退出情報がキャプチャされたユーザーが使用したクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="324ed-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="324ed-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-145">int</span><span class="sxs-lookup"><span data-stu-id="324ed-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="324ed-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-147">bit</span><span class="sxs-lookup"><span data-stu-id="324ed-147">bit</span></span></p></td>
<td><p><span data-ttu-id="324ed-148">ユーザーが内部ユーザーかどうかを表すビット。</span><span class="sxs-lookup"><span data-stu-id="324ed-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="324ed-149"><strong>/セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-150">datetime</span><span class="sxs-lookup"><span data-stu-id="324ed-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="324ed-151">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="324ed-151">Time of session request.</span></span> <span data-ttu-id="324ed-152">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="324ed-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="324ed-153">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="324ed-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="324ed-154"><strong>"/セッション Id"</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-155">int</span><span class="sxs-lookup"><span data-stu-id="324ed-155">int</span></span></p></td>
<td><p><span data-ttu-id="324ed-156">ユーザーが複数のコンピューターまたはデバイスに同時にログオンしている場合は、UserInstance を使って、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="324ed-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="324ed-157"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="324ed-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="324ed-159">セッションの SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="324ed-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="324ed-160">形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="324ed-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="324ed-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-162">datetime</span><span class="sxs-lookup"><span data-stu-id="324ed-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="324ed-163">ユーザーが会議に参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="324ed-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="324ed-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-165">datetime</span><span class="sxs-lookup"><span data-stu-id="324ed-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="324ed-166">ユーザーが会議から退出した時刻。</span><span class="sxs-lookup"><span data-stu-id="324ed-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="324ed-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="324ed-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="324ed-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="324ed-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="324ed-169">会議でのユーザーの役割 (発表者や出席者など)</span><span class="sxs-lookup"><span data-stu-id="324ed-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

