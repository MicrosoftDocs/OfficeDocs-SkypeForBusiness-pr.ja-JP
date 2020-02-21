---
title: 'Lync Server 2013: FocusJoinsAndLeaves ビュー'
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
ms.openlocfilehash: 9e97346929851bec53ab228988d72fb4813316d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="29c32-102">Lync Server 2013 の FocusJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="29c32-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29c32-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="29c32-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="29c32-104">FocusJoinsAndLeaves ビューには、1 つの会議における参加と退出についての情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="29c32-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="29c32-105">各会議は、ユーザーが会議に参加して会議を退出するたびに書き込まれるレコードによってこのビューで表されます。</span><span class="sxs-lookup"><span data-stu-id="29c32-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="29c32-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="29c32-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29c32-107">列</span><span class="sxs-lookup"><span data-stu-id="29c32-107">Column</span></span></th>
<th><span data-ttu-id="29c32-108">データ型</span><span class="sxs-lookup"><span data-stu-id="29c32-108">Data Type</span></span></th>
<th><span data-ttu-id="29c32-109">詳細</span><span class="sxs-lookup"><span data-stu-id="29c32-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29c32-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-111">日付型</span><span class="sxs-lookup"><span data-stu-id="29c32-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="29c32-112">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="29c32-112">Time of conference instance.</span></span> <span data-ttu-id="29c32-113">SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="29c32-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="29c32-114">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c32-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c32-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-116">int</span><span class="sxs-lookup"><span data-stu-id="29c32-116">int</span></span></p></td>
<td><p><span data-ttu-id="29c32-117">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="29c32-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="29c32-118">SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="29c32-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="29c32-119">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c32-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c32-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="29c32-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="29c32-122">会議の参加/退出情報が取得されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="29c32-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c32-123"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29c32-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29c32-125">会議の参加/退出情報が取得されたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="29c32-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29c32-126">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c32-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c32-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29c32-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29c32-129">会議の参加/退出情報が取得されたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="29c32-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29c32-130">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c32-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c32-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-132">識別子</span><span class="sxs-lookup"><span data-stu-id="29c32-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="29c32-133">会議の参加/退出情報が取得されたユーザーの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="29c32-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c32-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29c32-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29c32-136">会議の参加/退出情報が取得されたユーザーが使用したクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="29c32-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c32-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-138">int</span><span class="sxs-lookup"><span data-stu-id="29c32-138">int</span></span></p></td>
<td><p><span data-ttu-id="29c32-139">会議の参加/退出情報が取得されたユーザーが使用したクライアント。</span><span class="sxs-lookup"><span data-stu-id="29c32-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29c32-140">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c32-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c32-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="29c32-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="29c32-143">会議の参加/退出情報が取得されたユーザーが使用したクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="29c32-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c32-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-145">int</span><span class="sxs-lookup"><span data-stu-id="29c32-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c32-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-147">若干</span><span class="sxs-lookup"><span data-stu-id="29c32-147">bit</span></span></p></td>
<td><p><span data-ttu-id="29c32-148">ユーザーが内部ユーザーかどうかを示すビット。</span><span class="sxs-lookup"><span data-stu-id="29c32-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c32-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-150">日付型</span><span class="sxs-lookup"><span data-stu-id="29c32-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="29c32-151">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="29c32-151">Time of session request.</span></span> <span data-ttu-id="29c32-152">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="29c32-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="29c32-153">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c32-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c32-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-155">int</span><span class="sxs-lookup"><span data-stu-id="29c32-155">int</span></span></p></td>
<td><p><span data-ttu-id="29c32-156">ユーザーが複数のコンピューターまたはデバイスから同時にログオンしている場合は、UserInstance を使用してユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="29c32-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c32-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="29c32-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="29c32-p108">セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。</span><span class="sxs-lookup"><span data-stu-id="29c32-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c32-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-162">日付型</span><span class="sxs-lookup"><span data-stu-id="29c32-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="29c32-163">ユーザーが会議に参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="29c32-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c32-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-165">日付型</span><span class="sxs-lookup"><span data-stu-id="29c32-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="29c32-166">ユーザーが会議を退出した時刻。</span><span class="sxs-lookup"><span data-stu-id="29c32-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c32-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="29c32-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="29c32-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29c32-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29c32-169">会議でのユーザーの役割 (発表者、参加者など)。</span><span class="sxs-lookup"><span data-stu-id="29c32-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

