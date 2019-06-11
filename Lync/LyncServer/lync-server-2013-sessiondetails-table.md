---
title: 'Lync Server 2013: SessionDetails テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="b0cc1-102">Lync Server 2013 の SessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="b0cc1-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0cc1-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b0cc1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b0cc1-104">各レコードは、1つのピアツーピアセッションを表します。これは、VoIP の電話通話、2パーティの IM セッション、または他の種類のセッションである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="b0cc1-105">[Lync Server 2013 でメディアテーブル](lync-server-2013-media-table.md)を使用してテーブルを結合して、このセッションに関連する各メディアの詳細を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="b0cc1-106">IsUser1IntegratedWithDeskPhone と IsUser2IntegratedWithDeskPhone フィールドが、Microsoft Lync Server 2013 で使用されている SessionDetails テーブルから削除されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0cc1-107">列</span><span class="sxs-lookup"><span data-stu-id="b0cc1-107">Column</span></span></th>
<th><span data-ttu-id="b0cc1-108">データ型</span><span class="sxs-lookup"><span data-stu-id="b0cc1-108">Data Type</span></span></th>
<th><span data-ttu-id="b0cc1-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="b0cc1-109">Key/Index</span></span></th>
<th><span data-ttu-id="b0cc1-110">詳細</span><span class="sxs-lookup"><span data-stu-id="b0cc1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-111"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b0cc1-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-114">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-114">Time of session request.</span></span> <span data-ttu-id="b0cc1-115">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b0cc1-116">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-118">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-118">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-119">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-120">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-120">ID number to identify the session.</span></span> <span data-ttu-id="b0cc1-121">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。 \* 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-123">長さ</span><span class="sxs-lookup"><span data-stu-id="b0cc1-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-124">複数のセッションを関連付けるための GUID。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-125"><strong>Edialogidtime の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-126">datetime</span><span class="sxs-lookup"><span data-stu-id="b0cc1-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-127">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-128">現在のセッションによって置き換えられたダイアログを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="b0cc1-129">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-130"><strong>Edialogidseq の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-131">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-131">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-132">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-133">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-133">ID number to identify the session.</span></span> <span data-ttu-id="b0cc1-134">このセッションによっ<strong></strong>て置き換えられるセッションを一意に識別するために、代替の操作と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="b0cc1-135">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-137">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-137">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-138">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-139">セッションの1人のユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-139">ID of one user in the session.</span></span> <span data-ttu-id="b0cc1-140">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-142">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-142">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-143">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-144">セッション内の他のユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-144">ID of the other user in the session.</span></span> <span data-ttu-id="b0cc1-145">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-147">長さ</span><span class="sxs-lookup"><span data-stu-id="b0cc1-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-148">セッションの最初のユーザーによって使用されるエンドポイントを示す GUID。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="b0cc1-149">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-151">長さ</span><span class="sxs-lookup"><span data-stu-id="b0cc1-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-152">セッション内の2番目のユーザーによって使用されるエンドポイントを識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="b0cc1-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-155">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-155">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-156">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-157">SIP 要求の元の To ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="b0cc1-158">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-160">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-160">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-161">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-162">セッションを開始したユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-162">ID of the user who started the session.</span></span> <span data-ttu-id="b0cc1-163">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-165">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-165">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-166">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-167">発信者が代理としているユーザーの ID を示します。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="b0cc1-168">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-170">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-170">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-171">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-172">通話を参照するユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="b0cc1-173">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-175">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-175">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-176">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-177">このセッションで使用するフロントエンドサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="b0cc1-178">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-180">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-180">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-181">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-182">セッションがキャプチャされたプールの ID です。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="b0cc1-183">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-185">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-185">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-186">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-187">セッションで使用されるコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-187">Content type used in the session.</span></span> <span data-ttu-id="b0cc1-188">詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-190">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-190">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-191">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-192">User1 が使用するクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-192">Client version used by User1.</span></span> <span data-ttu-id="b0cc1-193">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-195">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-195">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-196">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-197">User2 が使用するクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-197">Client version used by User2.</span></span> <span data-ttu-id="b0cc1-198">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-200">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-200">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-201">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-202">User1 で使用されるエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-202">Edge Server used by User1.</span></span> <span data-ttu-id="b0cc1-203">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-205">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-205">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-206">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-207">User2 によって使用されるエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-207">Edge Server used by User2.</span></span> <span data-ttu-id="b0cc1-208">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-210">bit</span><span class="sxs-lookup"><span data-stu-id="b0cc1-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-211">User1 が内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-213">bit</span><span class="sxs-lookup"><span data-stu-id="b0cc1-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-214">User2 が内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-216">datetime</span><span class="sxs-lookup"><span data-stu-id="b0cc1-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-217">最初の招待要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-217">The time of the first INVITE request.</span></span> <span data-ttu-id="b0cc1-218">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b0cc1-219">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="b0cc1-220">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b0cc1-221">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-223">datetime</span><span class="sxs-lookup"><span data-stu-id="b0cc1-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-224">最初の招待メッセージに対する応答の時刻。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="b0cc1-225">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b0cc1-226">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-227"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-228">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-229">セッション招待状への SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="b0cc1-230">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b0cc1-231">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-233">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-234">SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-236">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-236">int</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-237">外部</span><span class="sxs-lookup"><span data-stu-id="b0cc1-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-238">通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-238">Call priority.</span></span> <span data-ttu-id="b0cc1-239">詳細については、「 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の Callpriorities テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-241">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-242">セッション中に User1 から送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-244">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-245">セッション中に User2 から送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-246"><strong>セッション終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-247">datetime</span><span class="sxs-lookup"><span data-stu-id="b0cc1-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-248">セッションの終了時。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-250">int</span><span class="sxs-lookup"><span data-stu-id="b0cc1-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-251">このセッションのメディアの種類を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="b0cc1-252">表示される型の定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-253">インスタント メッセージ</span><span class="sxs-lookup"><span data-stu-id="b0cc1-253">IM</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-254">1</span><span class="sxs-lookup"><span data-stu-id="b0cc1-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="b0cc1-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-256">2</span><span class="sxs-lookup"><span data-stu-id="b0cc1-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="b0cc1-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-258">4</span><span class="sxs-lookup"><span data-stu-id="b0cc1-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="b0cc1-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-260">個</span><span class="sxs-lookup"><span data-stu-id="b0cc1-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-261">オーディオトランジション</span><span class="sxs-lookup"><span data-stu-id="b0cc1-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-262">16</span><span class="sxs-lookup"><span data-stu-id="b0cc1-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-263">ビデオ</span><span class="sxs-lookup"><span data-stu-id="b0cc1-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-264">32</span><span class="sxs-lookup"><span data-stu-id="b0cc1-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="b0cc1-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="b0cc1-266">64</span><span class="sxs-lookup"><span data-stu-id="b0cc1-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-268">smallint</span><span class="sxs-lookup"><span data-stu-id="b0cc1-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-269">User1 属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="b0cc1-270">次の属性定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="b0cc1-271">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="b0cc1-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-273">smallint</span><span class="sxs-lookup"><span data-stu-id="b0cc1-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-274">User2 の属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="b0cc1-275">次の属性定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="b0cc1-276">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="b0cc1-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0cc1-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-278">smallint</span><span class="sxs-lookup"><span data-stu-id="b0cc1-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-279">呼び出し属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="b0cc1-280">次の属性定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="b0cc1-281">0x01-再試行セッション</span><span class="sxs-lookup"><span data-stu-id="b0cc1-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="b0cc1-282">0x02-応答グループの代理としてエージェントによって発信された通話</span><span class="sxs-lookup"><span data-stu-id="b0cc1-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0cc1-283"><strong>処理</strong></span><span class="sxs-lookup"><span data-stu-id="b0cc1-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="b0cc1-284">bit</span><span class="sxs-lookup"><span data-stu-id="b0cc1-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0cc1-285">監視サービスで内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="b0cc1-286">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0cc1-287">\*ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="b0cc1-288">複数のセッションが同時に開始された場合は、1つのセッションの SessionIdSeq は1、それ以外の場合は2となります。</span><span class="sxs-lookup"><span data-stu-id="b0cc1-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

