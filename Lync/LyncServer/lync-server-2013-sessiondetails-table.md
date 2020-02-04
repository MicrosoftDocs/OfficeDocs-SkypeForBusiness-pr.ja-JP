---
title: 'Lync Server 2013: SessionDetails テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b68c50fc17199c68a69c5a7c6dd6abc8a5bd1dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="c8c24-102">Lync Server 2013 の SessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="c8c24-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8c24-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c8c24-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c8c24-104">各レコードは、1つのピアツーピアセッションを表します。これは、VoIP の電話通話、2パーティの IM セッション、または他の種類のセッションである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8c24-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="c8c24-105">[Lync Server 2013 でメディアテーブル](lync-server-2013-media-table.md)を使用してテーブルを結合して、このセッションに関連する各メディアの詳細を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="c8c24-106">IsUser1IntegratedWithDeskPhone と IsUser2IntegratedWithDeskPhone フィールドが、Microsoft Lync Server 2013 で使用されている SessionDetails テーブルから削除されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8c24-107">列</span><span class="sxs-lookup"><span data-stu-id="c8c24-107">Column</span></span></th>
<th><span data-ttu-id="c8c24-108">データ型</span><span class="sxs-lookup"><span data-stu-id="c8c24-108">Data Type</span></span></th>
<th><span data-ttu-id="c8c24-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="c8c24-109">Key/Index</span></span></th>
<th><span data-ttu-id="c8c24-110">詳細</span><span class="sxs-lookup"><span data-stu-id="c8c24-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-111"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c8c24-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c8c24-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-114">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="c8c24-114">Time of session request.</span></span> <span data-ttu-id="c8c24-115">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c8c24-116">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-118">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-118">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-119">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-120">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c8c24-120">ID number to identify the session.</span></span> <span data-ttu-id="c8c24-121">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。 \* 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-123">長さ</span><span class="sxs-lookup"><span data-stu-id="c8c24-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-124">複数のセッションを関連付けるための GUID。</span><span class="sxs-lookup"><span data-stu-id="c8c24-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-125"><strong>Edialogidtime の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-126">datetime</span><span class="sxs-lookup"><span data-stu-id="c8c24-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="c8c24-127">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-128">現在のセッションによって置き換えられたダイアログを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c8c24-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="c8c24-129">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-130"><strong>Edialogidseq の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-131">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-131">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-132">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-133">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c8c24-133">ID number to identify the session.</span></span> <span data-ttu-id="c8c24-134">このセッションによって置き換えられるセッションを一意に識別するために、<strong>代替の操作と組み合わせ</strong>て使います。</span><span class="sxs-lookup"><span data-stu-id="c8c24-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="c8c24-135">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-137">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-137">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-138">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-139">セッションの1人のユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="c8c24-139">ID of one user in the session.</span></span> <span data-ttu-id="c8c24-140">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-142">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-142">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-143">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-144">セッション内の他のユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="c8c24-144">ID of the other user in the session.</span></span> <span data-ttu-id="c8c24-145">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-147">長さ</span><span class="sxs-lookup"><span data-stu-id="c8c24-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-148">セッションの最初のユーザーによって使用されるエンドポイントを示す GUID。</span><span class="sxs-lookup"><span data-stu-id="c8c24-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="c8c24-149">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c8c24-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-151">長さ</span><span class="sxs-lookup"><span data-stu-id="c8c24-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-152">セッション内の2番目のユーザーによって使用されるエンドポイントを識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="c8c24-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="c8c24-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c8c24-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-155">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-155">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-156">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-157">SIP 要求の元の To ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="c8c24-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="c8c24-158">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-160">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-160">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-161">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-162">セッションを開始したユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="c8c24-162">ID of the user who started the session.</span></span> <span data-ttu-id="c8c24-163">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-165">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-165">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-166">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-167">発信者が代理としているユーザーの ID を示します。</span><span class="sxs-lookup"><span data-stu-id="c8c24-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="c8c24-168">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-170">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-170">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-171">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-172">通話を参照するユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="c8c24-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="c8c24-173">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-175">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-175">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-176">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-177">このセッションで使用するフロントエンドサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="c8c24-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="c8c24-178">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-180">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-180">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-181">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-182">セッションがキャプチャされたプールの ID です。</span><span class="sxs-lookup"><span data-stu-id="c8c24-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="c8c24-183">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-185">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-185">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-186">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-187">セッションで使用されるコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="c8c24-187">Content type used in the session.</span></span> <span data-ttu-id="c8c24-188">詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-190">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-190">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-191">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-192">User1 が使用するクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="c8c24-192">Client version used by User1.</span></span> <span data-ttu-id="c8c24-193">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-195">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-195">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-196">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-197">User2 が使用するクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="c8c24-197">Client version used by User2.</span></span> <span data-ttu-id="c8c24-198">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-200">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-200">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-201">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-202">User1 で使用されるエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="c8c24-202">Edge Server used by User1.</span></span> <span data-ttu-id="c8c24-203">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-205">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-205">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-206">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-207">User2 によって使用されるエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="c8c24-207">Edge Server used by User2.</span></span> <span data-ttu-id="c8c24-208">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-210">bit</span><span class="sxs-lookup"><span data-stu-id="c8c24-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-211">User1 が内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c8c24-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-213">bit</span><span class="sxs-lookup"><span data-stu-id="c8c24-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-214">User2 が内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c8c24-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-216">datetime</span><span class="sxs-lookup"><span data-stu-id="c8c24-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-217">最初の招待要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="c8c24-217">The time of the first INVITE request.</span></span> <span data-ttu-id="c8c24-218">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c8c24-219">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="c8c24-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="c8c24-220">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c8c24-221">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="c8c24-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-223">datetime</span><span class="sxs-lookup"><span data-stu-id="c8c24-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-224">最初の招待メッセージに対する応答の時刻。</span><span class="sxs-lookup"><span data-stu-id="c8c24-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="c8c24-225">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c8c24-226">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="c8c24-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-227"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-228">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-229">セッション招待状への SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="c8c24-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="c8c24-230">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c8c24-231">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="c8c24-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-233">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-234">SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="c8c24-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-236">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-236">int</span></span></p></td>
<td><p><span data-ttu-id="c8c24-237">外部</span><span class="sxs-lookup"><span data-stu-id="c8c24-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8c24-238">通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="c8c24-238">Call priority.</span></span> <span data-ttu-id="c8c24-239">詳細については、「 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の Callpriorities テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c24-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-241">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-242">セッション中に User1 から送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="c8c24-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-244">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-245">セッション中に User2 から送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="c8c24-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-246"><strong>セッション終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-247">datetime</span><span class="sxs-lookup"><span data-stu-id="c8c24-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-248">セッションの終了時。</span><span class="sxs-lookup"><span data-stu-id="c8c24-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-250">int</span><span class="sxs-lookup"><span data-stu-id="c8c24-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-251">このセッションのメディアの種類を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="c8c24-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="c8c24-252">表示される型の定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c8c24-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-253">インスタント メッセージ</span><span class="sxs-lookup"><span data-stu-id="c8c24-253">IM</span></span></p></td>
<td><p><span data-ttu-id="c8c24-254">1</span><span class="sxs-lookup"><span data-stu-id="c8c24-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="c8c24-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="c8c24-256">両面</span><span class="sxs-lookup"><span data-stu-id="c8c24-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="c8c24-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="c8c24-258">4</span><span class="sxs-lookup"><span data-stu-id="c8c24-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="c8c24-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="c8c24-260">個</span><span class="sxs-lookup"><span data-stu-id="c8c24-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-261">オーディオトランジション</span><span class="sxs-lookup"><span data-stu-id="c8c24-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="c8c24-262">16</span><span class="sxs-lookup"><span data-stu-id="c8c24-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-263">ビデオ</span><span class="sxs-lookup"><span data-stu-id="c8c24-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="c8c24-264">32</span><span class="sxs-lookup"><span data-stu-id="c8c24-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="c8c24-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="c8c24-266">64</span><span class="sxs-lookup"><span data-stu-id="c8c24-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-268">smallint</span><span class="sxs-lookup"><span data-stu-id="c8c24-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-269">User1 属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="c8c24-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="c8c24-270">次の属性定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8c24-271">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="c8c24-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-273">smallint</span><span class="sxs-lookup"><span data-stu-id="c8c24-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-274">User2 の属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="c8c24-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="c8c24-275">次の属性定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8c24-276">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="c8c24-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c24-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-278">smallint</span><span class="sxs-lookup"><span data-stu-id="c8c24-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-279">呼び出し属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="c8c24-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="c8c24-280">次の属性定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8c24-281">0x01-再試行セッション</span><span class="sxs-lookup"><span data-stu-id="c8c24-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="c8c24-282">0x02-応答グループの代理としてエージェントによって発信された通話</span><span class="sxs-lookup"><span data-stu-id="c8c24-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c24-283"><strong>処理</strong></span><span class="sxs-lookup"><span data-stu-id="c8c24-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="c8c24-284">bit</span><span class="sxs-lookup"><span data-stu-id="c8c24-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8c24-285">監視サービスで内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c24-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="c8c24-286">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c8c24-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c8c24-287">\*ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="c8c24-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="c8c24-288">複数のセッションが同時に開始された場合は、1つのセッションの SessionIdSeq は1、それ以外の場合は2となります。</span><span class="sxs-lookup"><span data-stu-id="c8c24-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

