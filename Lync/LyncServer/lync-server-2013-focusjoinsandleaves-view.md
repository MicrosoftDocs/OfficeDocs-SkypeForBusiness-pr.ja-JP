---
title: 'Lync Server 2013: FocusJoinsAndLeaves ビュー'
description: 'Lync Server 2013: FocusJoinsAndLeaves ビュー。'
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
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577453"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="044a9-103">Lync Server 2013 の FocusJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="044a9-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="044a9-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="044a9-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="044a9-105">FocusJoinsAndLeaves ビューには、1 つの会議における参加と退出についての情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="044a9-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="044a9-106">各会議は、ユーザーが会議に参加して会議を退出するたびに書き込まれるレコードによってこのビューで表されます。</span><span class="sxs-lookup"><span data-stu-id="044a9-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="044a9-107">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="044a9-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="044a9-108">Column</span><span class="sxs-lookup"><span data-stu-id="044a9-108">Column</span></span></th>
<th><span data-ttu-id="044a9-109">データ型</span><span class="sxs-lookup"><span data-stu-id="044a9-109">Data Type</span></span></th>
<th><span data-ttu-id="044a9-110">詳細</span><span class="sxs-lookup"><span data-stu-id="044a9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="044a9-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-112">日付型</span><span class="sxs-lookup"><span data-stu-id="044a9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="044a9-113">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="044a9-113">Time of conference instance.</span></span> <span data-ttu-id="044a9-114">SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="044a9-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="044a9-115">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="044a9-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044a9-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-117">int</span><span class="sxs-lookup"><span data-stu-id="044a9-117">int</span></span></p></td>
<td><p><span data-ttu-id="044a9-118">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="044a9-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="044a9-119">SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="044a9-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="044a9-120">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="044a9-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044a9-121"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-122">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="044a9-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="044a9-123">会議の参加/退出情報が取得されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="044a9-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044a9-124"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="044a9-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="044a9-126">会議の参加/退出情報が取得されたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="044a9-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="044a9-127">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="044a9-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044a9-128"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="044a9-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="044a9-130">会議の参加/退出情報が取得されたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="044a9-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="044a9-131">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="044a9-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044a9-132"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-133">識別子</span><span class="sxs-lookup"><span data-stu-id="044a9-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="044a9-134">会議の参加/退出情報が取得されたユーザーの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="044a9-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044a9-135"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="044a9-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="044a9-137">会議の参加/退出情報が取得されたユーザーが使用したクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="044a9-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044a9-138"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-139">int</span><span class="sxs-lookup"><span data-stu-id="044a9-139">int</span></span></p></td>
<td><p><span data-ttu-id="044a9-140">会議の参加/退出情報が取得されたユーザーが使用したクライアント。</span><span class="sxs-lookup"><span data-stu-id="044a9-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="044a9-141">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="044a9-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044a9-142"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-143">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="044a9-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="044a9-144">会議の参加/退出情報が取得されたユーザーが使用したクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="044a9-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044a9-145"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-146">int</span><span class="sxs-lookup"><span data-stu-id="044a9-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044a9-147"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-148">若干</span><span class="sxs-lookup"><span data-stu-id="044a9-148">bit</span></span></p></td>
<td><p><span data-ttu-id="044a9-149">ユーザーが内部ユーザーかどうかを示すビット。</span><span class="sxs-lookup"><span data-stu-id="044a9-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044a9-150"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-151">日付型</span><span class="sxs-lookup"><span data-stu-id="044a9-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="044a9-152">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="044a9-152">Time of session request.</span></span> <span data-ttu-id="044a9-153">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="044a9-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="044a9-154">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="044a9-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044a9-155"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-156">int</span><span class="sxs-lookup"><span data-stu-id="044a9-156">int</span></span></p></td>
<td><p><span data-ttu-id="044a9-157">ユーザーが複数のコンピューターまたはデバイスから同時にログオンしている場合は、UserInstance を使用してユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="044a9-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044a9-158"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-159">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="044a9-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="044a9-p108">セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。</span><span class="sxs-lookup"><span data-stu-id="044a9-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044a9-162"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-163">日付型</span><span class="sxs-lookup"><span data-stu-id="044a9-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="044a9-164">ユーザーが会議に参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="044a9-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044a9-165"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-166">日付型</span><span class="sxs-lookup"><span data-stu-id="044a9-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="044a9-167">ユーザーが会議を退出した時刻。</span><span class="sxs-lookup"><span data-stu-id="044a9-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044a9-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="044a9-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="044a9-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="044a9-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="044a9-170">会議でのユーザーの役割 (発表者、参加者など)。</span><span class="sxs-lookup"><span data-stu-id="044a9-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

