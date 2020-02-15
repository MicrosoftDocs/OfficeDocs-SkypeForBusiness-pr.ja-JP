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
ms.openlocfilehash: fee9a2f2b59fc523224a778004b5c0beb041a12d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="12a69-102">Lync Server 2013 の SessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="12a69-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12a69-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="12a69-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="12a69-104">各レコードは、1つのピアツーピアセッションを表します。これは、VoIP 電話、2者間の IM セッション、またはその他の種類のセッションである場合があります。</span><span class="sxs-lookup"><span data-stu-id="12a69-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="12a69-105">[Lync Server 2013 のメディアテーブル](lync-server-2013-media-table.md)を使用してテーブル結合を実行すると、このセッションに含まれる各メディアの詳細を検索できます。</span><span class="sxs-lookup"><span data-stu-id="12a69-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="12a69-106">IsUser1IntegratedWithDeskPhone および IsUser2IntegratedWithDeskPhone フィールドは、Microsoft Lync Server 2013 で使用される SessionDetails テーブルから削除されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12a69-107">列</span><span class="sxs-lookup"><span data-stu-id="12a69-107">Column</span></span></th>
<th><span data-ttu-id="12a69-108">データ型</span><span class="sxs-lookup"><span data-stu-id="12a69-108">Data Type</span></span></th>
<th><span data-ttu-id="12a69-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="12a69-109">Key/Index</span></span></th>
<th><span data-ttu-id="12a69-110">詳細</span><span class="sxs-lookup"><span data-stu-id="12a69-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a69-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-112">日付型</span><span class="sxs-lookup"><span data-stu-id="12a69-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="12a69-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="12a69-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-114">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="12a69-114">Time of session request.</span></span> <span data-ttu-id="12a69-115">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="12a69-116">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-117"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-118">int</span><span class="sxs-lookup"><span data-stu-id="12a69-118">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-119">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="12a69-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-120">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="12a69-120">ID number to identify the session.</span></span> <span data-ttu-id="12a69-121">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用します。 \* 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-123">識別子</span><span class="sxs-lookup"><span data-stu-id="12a69-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-124">複数のセッションを相互に関連付けるための GUID。</span><span class="sxs-lookup"><span data-stu-id="12a69-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-125"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-126">日付型</span><span class="sxs-lookup"><span data-stu-id="12a69-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="12a69-127">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-128">現在のセッションで置き換えられたダイアログを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="12a69-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="12a69-129">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-130"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-131">int</span><span class="sxs-lookup"><span data-stu-id="12a69-131">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-132">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-133">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="12a69-133">ID number to identify the session.</span></span> <span data-ttu-id="12a69-134">このセッションで置き換えられたセッションを一意に識別するために <strong>ReplacesDialogIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="12a69-135">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-137">int</span><span class="sxs-lookup"><span data-stu-id="12a69-137">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-138">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-139">セッションにいる一方のユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="12a69-139">ID of one user in the session.</span></span> <span data-ttu-id="12a69-140">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-142">int</span><span class="sxs-lookup"><span data-stu-id="12a69-142">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-143">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-144">セッションにいる他方のユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="12a69-144">ID of the other user in the session.</span></span> <span data-ttu-id="12a69-145">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-147">識別子</span><span class="sxs-lookup"><span data-stu-id="12a69-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-148">セッションの第 1 のユーザーによって使用されているエンドポイントを示す GUID。</span><span class="sxs-lookup"><span data-stu-id="12a69-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="12a69-149">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="12a69-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-151">識別子</span><span class="sxs-lookup"><span data-stu-id="12a69-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-152">セッションの第 2 のユーザーによって使用されているエンドポイントを示す GUID。</span><span class="sxs-lookup"><span data-stu-id="12a69-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="12a69-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="12a69-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-155">int</span><span class="sxs-lookup"><span data-stu-id="12a69-155">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-156">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-157">SIP 要求における元の送信先ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="12a69-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="12a69-158">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-160">int</span><span class="sxs-lookup"><span data-stu-id="12a69-160">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-161">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-162">セッションを開始したユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="12a69-162">ID of the user who started the session.</span></span> <span data-ttu-id="12a69-163">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-165">int</span><span class="sxs-lookup"><span data-stu-id="12a69-165">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-166">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-167">発信者が代理を務めているユーザーの ID を示します。</span><span class="sxs-lookup"><span data-stu-id="12a69-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="12a69-168">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-170">int</span><span class="sxs-lookup"><span data-stu-id="12a69-170">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-171">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-172">通話の参照元であるユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="12a69-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="12a69-173">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-175">int</span><span class="sxs-lookup"><span data-stu-id="12a69-175">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-176">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-177">このセッションで使用されるフロントエンド サーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="12a69-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="12a69-178">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-180">int</span><span class="sxs-lookup"><span data-stu-id="12a69-180">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-181">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-182">セッションが取得されたプールの ID。</span><span class="sxs-lookup"><span data-stu-id="12a69-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="12a69-183">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a>」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-185">int</span><span class="sxs-lookup"><span data-stu-id="12a69-185">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-186">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-187">セッションで使用されるコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="12a69-187">Content type used in the session.</span></span> <span data-ttu-id="12a69-188">詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-190">int</span><span class="sxs-lookup"><span data-stu-id="12a69-190">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-191">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-192">User1 によって使用されるクライアント バージョン。</span><span class="sxs-lookup"><span data-stu-id="12a69-192">Client version used by User1.</span></span> <span data-ttu-id="12a69-193">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-195">int</span><span class="sxs-lookup"><span data-stu-id="12a69-195">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-196">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-197">User2 によって使用されるクライアント バージョン。</span><span class="sxs-lookup"><span data-stu-id="12a69-197">Client version used by User2.</span></span> <span data-ttu-id="12a69-198">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-200">int</span><span class="sxs-lookup"><span data-stu-id="12a69-200">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-201">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-202">User1 によって使用されるエッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="12a69-202">Edge Server used by User1.</span></span> <span data-ttu-id="12a69-203">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-205">int</span><span class="sxs-lookup"><span data-stu-id="12a69-205">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-206">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-207">User2 によって使用されるエッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="12a69-207">Edge Server used by User2.</span></span> <span data-ttu-id="12a69-208">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-210">若干</span><span class="sxs-lookup"><span data-stu-id="12a69-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-211">User1 が内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="12a69-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-213">若干</span><span class="sxs-lookup"><span data-stu-id="12a69-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-214">User2 が内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="12a69-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-216">日付型</span><span class="sxs-lookup"><span data-stu-id="12a69-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-217">最初の INVITE 要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="12a69-217">The time of the first INVITE request.</span></span> <span data-ttu-id="12a69-218">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="12a69-219">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="12a69-220">このフィールドには通常、セッションの最初の INVITE メッセージから生成されたデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="12a69-221">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-223">日付型</span><span class="sxs-lookup"><span data-stu-id="12a69-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-224">最初の INVITE メッセージへの応答の時刻。</span><span class="sxs-lookup"><span data-stu-id="12a69-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="12a69-225">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="12a69-226">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-228">int</span><span class="sxs-lookup"><span data-stu-id="12a69-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-p121">セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="12a69-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-233">int</span><span class="sxs-lookup"><span data-stu-id="12a69-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-234">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="12a69-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-236">int</span><span class="sxs-lookup"><span data-stu-id="12a69-236">int</span></span></p></td>
<td><p><span data-ttu-id="12a69-237">外部</span><span class="sxs-lookup"><span data-stu-id="12a69-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12a69-238">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="12a69-238">Call priority.</span></span> <span data-ttu-id="12a69-239">詳細については、「 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の呼び出し優先度</a>」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a69-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-241">int</span><span class="sxs-lookup"><span data-stu-id="12a69-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-242">User1 がセッション中に送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="12a69-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-244">int</span><span class="sxs-lookup"><span data-stu-id="12a69-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-245">User2 がセッション中に送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="12a69-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-247">日付型</span><span class="sxs-lookup"><span data-stu-id="12a69-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-248">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="12a69-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-250">int</span><span class="sxs-lookup"><span data-stu-id="12a69-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-p123">このセッションのメディアの種類を示すビット セット。その種類の定義を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="12a69-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a69-253">IM</span><span class="sxs-lookup"><span data-stu-id="12a69-253">IM</span></span></p></td>
<td><p><span data-ttu-id="12a69-254">1 </span><span class="sxs-lookup"><span data-stu-id="12a69-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="12a69-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="12a69-256">2 </span><span class="sxs-lookup"><span data-stu-id="12a69-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="12a69-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="12a69-258">4 </span><span class="sxs-lookup"><span data-stu-id="12a69-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="12a69-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="12a69-260">8 </span><span class="sxs-lookup"><span data-stu-id="12a69-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-261">再生</span><span class="sxs-lookup"><span data-stu-id="12a69-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="12a69-262">16 </span><span class="sxs-lookup"><span data-stu-id="12a69-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-263">画面</span><span class="sxs-lookup"><span data-stu-id="12a69-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="12a69-264">32</span><span class="sxs-lookup"><span data-stu-id="12a69-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="12a69-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="12a69-266">64</span><span class="sxs-lookup"><span data-stu-id="12a69-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-268">smallint</span><span class="sxs-lookup"><span data-stu-id="12a69-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-p124">User1 の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="12a69-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="12a69-271">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="12a69-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-273">smallint</span><span class="sxs-lookup"><span data-stu-id="12a69-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-p125">User2 の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="12a69-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="12a69-276">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="12a69-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a69-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-278">smallint</span><span class="sxs-lookup"><span data-stu-id="12a69-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-p126">通話の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="12a69-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="12a69-281">0x01 - 再試行されたセッション</span><span class="sxs-lookup"><span data-stu-id="12a69-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="12a69-282">0x02 - 応答グループの代理を務めるエージェントによって行われた通話</span><span class="sxs-lookup"><span data-stu-id="12a69-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a69-283"><strong>実行</strong></span><span class="sxs-lookup"><span data-stu-id="12a69-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="12a69-284">若干</span><span class="sxs-lookup"><span data-stu-id="12a69-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12a69-285">監視サービスの内部用テーブル。</span><span class="sxs-lookup"><span data-stu-id="12a69-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="12a69-286">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="12a69-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="12a69-287">\*ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="12a69-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="12a69-288">まったく同時に複数のセッションが開始した場合、あるセッションの SessionIdSeq は 1、別のセッションは 2、などとなります。</span><span class="sxs-lookup"><span data-stu-id="12a69-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

