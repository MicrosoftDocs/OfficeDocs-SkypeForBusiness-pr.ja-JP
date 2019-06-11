---
title: 'Lync Server 2013: FocusJoinsAndLeaves view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="2811e-102">Lync Server 2013 での FocusJoinsAndLeaves の表示</span><span class="sxs-lookup"><span data-stu-id="2811e-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2811e-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2811e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2811e-104">FocusJoinsAndLeaves ビューには、1人の会議に参加するための情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="2811e-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="2811e-105">各会議は、ユーザーが会議に参加して退席するたびに書き込まれるレコードによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="2811e-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="2811e-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2811e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2811e-107">列</span><span class="sxs-lookup"><span data-stu-id="2811e-107">Column</span></span></th>
<th><span data-ttu-id="2811e-108">データ型</span><span class="sxs-lookup"><span data-stu-id="2811e-108">Data Type</span></span></th>
<th><span data-ttu-id="2811e-109">詳細</span><span class="sxs-lookup"><span data-stu-id="2811e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2811e-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="2811e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2811e-112">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="2811e-112">Time of conference instance.</span></span> <span data-ttu-id="2811e-113">電話会議インスタンスを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="2811e-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="2811e-114">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2811e-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2811e-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-116">int</span><span class="sxs-lookup"><span data-stu-id="2811e-116">int</span></span></p></td>
<td><p><span data-ttu-id="2811e-117">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="2811e-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="2811e-118">電話会議インスタンスを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="2811e-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="2811e-119">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2811e-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2811e-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2811e-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2811e-122">会議の参加/退出情報がキャプチャされたユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="2811e-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2811e-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2811e-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2811e-125">会議の参加/退出情報がキャプチャされたユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="2811e-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="2811e-126">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2811e-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2811e-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2811e-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2811e-129">会議の参加/退出情報がキャプチャされたユーザーのテナントです。</span><span class="sxs-lookup"><span data-stu-id="2811e-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="2811e-130">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2811e-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2811e-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-132">長さ</span><span class="sxs-lookup"><span data-stu-id="2811e-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2811e-133">会議の参加/退出情報がキャプチャされたユーザーを表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="2811e-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2811e-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2811e-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2811e-136">会議の参加/退出情報がキャプチャされたユーザーが使用したクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="2811e-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2811e-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-138">int</span><span class="sxs-lookup"><span data-stu-id="2811e-138">int</span></span></p></td>
<td><p><span data-ttu-id="2811e-139">電話会議の参加/退出情報がキャプチャされたユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="2811e-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="2811e-140">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2811e-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2811e-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2811e-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2811e-143">会議の参加/退出情報がキャプチャされたユーザーが使用したクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="2811e-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2811e-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-145">int</span><span class="sxs-lookup"><span data-stu-id="2811e-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2811e-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-147">bit</span><span class="sxs-lookup"><span data-stu-id="2811e-147">bit</span></span></p></td>
<td><p><span data-ttu-id="2811e-148">ユーザーが内部ユーザーかどうかを表すビット。</span><span class="sxs-lookup"><span data-stu-id="2811e-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2811e-149"><strong>/セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-150">datetime</span><span class="sxs-lookup"><span data-stu-id="2811e-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="2811e-151">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="2811e-151">Time of session request.</span></span> <span data-ttu-id="2811e-152">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="2811e-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="2811e-153">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2811e-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2811e-154"><strong>"/セッション Id"</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-155">int</span><span class="sxs-lookup"><span data-stu-id="2811e-155">int</span></span></p></td>
<td><p><span data-ttu-id="2811e-156">ユーザーが複数のコンピューターまたはデバイスに同時にログオンしている場合は、UserInstance を使って、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="2811e-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2811e-157"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="2811e-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="2811e-159">セッションの SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="2811e-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="2811e-160">形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2811e-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2811e-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-162">datetime</span><span class="sxs-lookup"><span data-stu-id="2811e-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="2811e-163">ユーザーが会議に参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="2811e-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2811e-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-165">datetime</span><span class="sxs-lookup"><span data-stu-id="2811e-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="2811e-166">ユーザーが会議から退出した時刻。</span><span class="sxs-lookup"><span data-stu-id="2811e-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2811e-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="2811e-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="2811e-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2811e-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2811e-169">会議でのユーザーの役割 (発表者や出席者など)</span><span class="sxs-lookup"><span data-stu-id="2811e-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

