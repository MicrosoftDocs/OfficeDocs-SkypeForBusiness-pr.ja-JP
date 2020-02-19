---
title: 'Lync Server 2013: FocusJoinsAndLeaves テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49021f6b03481ccb5661c85cec87e5786a8d83dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="0621a-102">Lync Server 2013 の FocusJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="0621a-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0621a-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0621a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0621a-104">この表の各レコードには、1つの会議に関する1人のユーザーの参加および退出情報に関する CDR 情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0621a-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="0621a-105">各会議は、ユーザーが会議に参加および退室するたびに1つずつ、このテーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0621a-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0621a-106">列</span><span class="sxs-lookup"><span data-stu-id="0621a-106">Column</span></span></th>
<th><span data-ttu-id="0621a-107">データ型</span><span class="sxs-lookup"><span data-stu-id="0621a-107">Data Type</span></span></th>
<th><span data-ttu-id="0621a-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="0621a-108">Key/Index</span></span></th>
<th><span data-ttu-id="0621a-109">詳細</span><span class="sxs-lookup"><span data-stu-id="0621a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0621a-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-111">日付型</span><span class="sxs-lookup"><span data-stu-id="0621a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0621a-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="0621a-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0621a-113">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="0621a-113">Time of conference instance.</span></span> <span data-ttu-id="0621a-114"><strong>Sessionidseq</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0621a-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="0621a-115">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0621a-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0621a-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-117">int</span><span class="sxs-lookup"><span data-stu-id="0621a-117">int</span></span></p></td>
<td><p><span data-ttu-id="0621a-118">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="0621a-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0621a-119">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="0621a-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="0621a-120"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0621a-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="0621a-121">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0621a-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0621a-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-123">日付型</span><span class="sxs-lookup"><span data-stu-id="0621a-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="0621a-124">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="0621a-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0621a-125">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="0621a-125">Time of session request.</span></span> <span data-ttu-id="0621a-126">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="0621a-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0621a-127">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0621a-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0621a-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-129">int</span><span class="sxs-lookup"><span data-stu-id="0621a-129">int</span></span></p></td>
<td><p><span data-ttu-id="0621a-130">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="0621a-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0621a-131">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="0621a-131">ID number to identify the session.</span></span> <span data-ttu-id="0621a-132">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="0621a-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0621a-133">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0621a-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0621a-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-135">int</span><span class="sxs-lookup"><span data-stu-id="0621a-135">int</span></span></p></td>
<td><p><span data-ttu-id="0621a-136">外部</span><span class="sxs-lookup"><span data-stu-id="0621a-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0621a-137">このユーザーを示す一意の番号。 <a href="lync-server-2013-users-table.md">Lync Server 2013 の [ユーザー] テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="0621a-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0621a-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-139">int</span><span class="sxs-lookup"><span data-stu-id="0621a-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0621a-140">ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、 <strong>UserInstance</strong>を使用して、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="0621a-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0621a-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-142">若干</span><span class="sxs-lookup"><span data-stu-id="0621a-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0621a-143">ユーザーが内部からログオンしたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0621a-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0621a-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-145">int</span><span class="sxs-lookup"><span data-stu-id="0621a-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0621a-146">会議でのこのユーザーの役割 (発表者や参加者など)。</span><span class="sxs-lookup"><span data-stu-id="0621a-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0621a-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-148">日付型</span><span class="sxs-lookup"><span data-stu-id="0621a-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0621a-149">このユーザーが会議に参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="0621a-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0621a-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-151">日付型</span><span class="sxs-lookup"><span data-stu-id="0621a-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0621a-152">このユーザーが会議から退席した時刻。</span><span class="sxs-lookup"><span data-stu-id="0621a-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0621a-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-154">int</span><span class="sxs-lookup"><span data-stu-id="0621a-154">int</span></span></p></td>
<td><p><span data-ttu-id="0621a-155">外部</span><span class="sxs-lookup"><span data-stu-id="0621a-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0621a-156">ユーザーのクライアントソフトウェアのバージョン。 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions テーブル</a>に参照されます。</span><span class="sxs-lookup"><span data-stu-id="0621a-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0621a-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="0621a-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="0621a-158">識別子</span><span class="sxs-lookup"><span data-stu-id="0621a-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0621a-159">電話会議で使用されるエンドポイントのグローバル一意識別子 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="0621a-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="0621a-160">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0621a-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

