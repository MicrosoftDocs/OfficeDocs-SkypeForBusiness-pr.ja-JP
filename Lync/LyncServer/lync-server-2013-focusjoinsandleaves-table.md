---
title: 'Lync Server 2013: FocusJoinsAndLeaves テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ead6fc2ce79f7ab1206476ee420bd2ba5a7711f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="d52b6-102">Lync Server 2013 の FocusJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="d52b6-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d52b6-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d52b6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d52b6-104">このテーブルの各レコードには、1人のユーザーの参加に関する CDR 情報と、1人の会議に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d52b6-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="d52b6-105">各会議は、ユーザーが会議に参加して退席するたびに、1つのレコードでこのテーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d52b6-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d52b6-106">列</span><span class="sxs-lookup"><span data-stu-id="d52b6-106">Column</span></span></th>
<th><span data-ttu-id="d52b6-107">データ型</span><span class="sxs-lookup"><span data-stu-id="d52b6-107">Data Type</span></span></th>
<th><span data-ttu-id="d52b6-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="d52b6-108">Key/Index</span></span></th>
<th><span data-ttu-id="d52b6-109">詳細</span><span class="sxs-lookup"><span data-stu-id="d52b6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d52b6-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d52b6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d52b6-112">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d52b6-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d52b6-113">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="d52b6-113">Time of conference instance.</span></span> <span data-ttu-id="d52b6-114">電話会議インスタンスを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="d52b6-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="d52b6-115">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d52b6-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d52b6-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-117">int</span><span class="sxs-lookup"><span data-stu-id="d52b6-117">int</span></span></p></td>
<td><p><span data-ttu-id="d52b6-118">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d52b6-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d52b6-119">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="d52b6-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="d52b6-120">電話会議インスタンスを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="d52b6-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="d52b6-121">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d52b6-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d52b6-122"><strong>/セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-123">datetime</span><span class="sxs-lookup"><span data-stu-id="d52b6-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="d52b6-124">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d52b6-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d52b6-125">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="d52b6-125">Time of session request.</span></span> <span data-ttu-id="d52b6-126">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="d52b6-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d52b6-127">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d52b6-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d52b6-128"><strong>"/セッション Id"</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-129">int</span><span class="sxs-lookup"><span data-stu-id="d52b6-129">int</span></span></p></td>
<td><p><span data-ttu-id="d52b6-130">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d52b6-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d52b6-131">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="d52b6-131">ID number to identify the session.</span></span> <span data-ttu-id="d52b6-132">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="d52b6-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d52b6-133">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d52b6-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d52b6-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-135">int</span><span class="sxs-lookup"><span data-stu-id="d52b6-135">int</span></span></p></td>
<td><p><span data-ttu-id="d52b6-136">外部</span><span class="sxs-lookup"><span data-stu-id="d52b6-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d52b6-137">このユーザーを識別する一意の番号です。 <a href="lync-server-2013-users-table.md">Lync Server 2013 の [ユーザー] テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="d52b6-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d52b6-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-139">int</span><span class="sxs-lookup"><span data-stu-id="d52b6-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d52b6-140">ユーザーが複数のコンピューターまたはデバイスに同時にログオンしている場合は、 <strong>UserInstance</strong>を使って、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="d52b6-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d52b6-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-142">bit</span><span class="sxs-lookup"><span data-stu-id="d52b6-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d52b6-143">ユーザーが内部からログオンしているかどうか。</span><span class="sxs-lookup"><span data-stu-id="d52b6-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d52b6-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-145">int</span><span class="sxs-lookup"><span data-stu-id="d52b6-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d52b6-146">会議でのこのユーザーの役割 (発表者や出席者など)</span><span class="sxs-lookup"><span data-stu-id="d52b6-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d52b6-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-148">datetime</span><span class="sxs-lookup"><span data-stu-id="d52b6-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d52b6-149">このユーザーが会議に参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="d52b6-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d52b6-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-151">datetime</span><span class="sxs-lookup"><span data-stu-id="d52b6-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d52b6-152">このユーザーが会議から退席した時刻。</span><span class="sxs-lookup"><span data-stu-id="d52b6-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d52b6-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-154">int</span><span class="sxs-lookup"><span data-stu-id="d52b6-154">int</span></span></p></td>
<td><p><span data-ttu-id="d52b6-155">外部</span><span class="sxs-lookup"><span data-stu-id="d52b6-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d52b6-156">ユーザーのクライアントソフトウェアのバージョン。 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions テーブル</a>に参照されます。</span><span class="sxs-lookup"><span data-stu-id="d52b6-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d52b6-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d52b6-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d52b6-158">長さ</span><span class="sxs-lookup"><span data-stu-id="d52b6-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d52b6-159">電話会議で使用されるエンドポイントのグローバル一意識別子 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="d52b6-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="d52b6-160">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d52b6-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

