---
title: 'Lync Server 2013: SessionDetails テーブル'
description: 'Lync Server 2013: SessionDetails テーブル。'
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
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569933"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="c4661-103">Lync Server 2013 の SessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="c4661-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4661-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c4661-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c4661-105">各レコードは1つのピアツーピアセッションを表します。これは VoIP-VoIP 電話、2者間の IM セッション、またはその他の種類のセッションである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4661-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="c4661-106">[Lync Server 2013 のメディアテーブル](lync-server-2013-media-table.md)を使用してテーブル結合を実行すると、このセッションに含まれる各メディアの詳細を検索できます。</span><span class="sxs-lookup"><span data-stu-id="c4661-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="c4661-107">IsUser1IntegratedWithDeskPhone および IsUser2IntegratedWithDeskPhone フィールドは、Microsoft Lync Server 2013 で使用される SessionDetails テーブルから削除されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4661-108">Column</span><span class="sxs-lookup"><span data-stu-id="c4661-108">Column</span></span></th>
<th><span data-ttu-id="c4661-109">データ型</span><span class="sxs-lookup"><span data-stu-id="c4661-109">Data Type</span></span></th>
<th><span data-ttu-id="c4661-110">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="c4661-110">Key/Index</span></span></th>
<th><span data-ttu-id="c4661-111">詳細</span><span class="sxs-lookup"><span data-stu-id="c4661-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4661-112"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-113">日付型</span><span class="sxs-lookup"><span data-stu-id="c4661-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4661-114">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="c4661-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-115">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="c4661-115">Time of session request.</span></span> <span data-ttu-id="c4661-116">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c4661-117">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-118"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-119">int</span><span class="sxs-lookup"><span data-stu-id="c4661-119">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-120">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="c4661-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-121">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c4661-121">ID number to identify the session.</span></span> <span data-ttu-id="c4661-122">セッションを一意に識別するために <strong>Sessionidtime</strong> と組み合わせて使用します。 \* 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-123"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-124">識別子</span><span class="sxs-lookup"><span data-stu-id="c4661-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-125">複数のセッションを相互に関連付けるための GUID。</span><span class="sxs-lookup"><span data-stu-id="c4661-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-126"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-127">日付型</span><span class="sxs-lookup"><span data-stu-id="c4661-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4661-128">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-129">現在のセッションで置き換えられたダイアログを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c4661-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="c4661-130">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-131"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-132">int</span><span class="sxs-lookup"><span data-stu-id="c4661-132">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-133">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-134">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c4661-134">ID number to identify the session.</span></span> <span data-ttu-id="c4661-135">このセッションで置き換えられたセッションを一意に識別するために <strong>ReplacesDialogIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="c4661-136">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-137"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-138">int</span><span class="sxs-lookup"><span data-stu-id="c4661-138">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-139">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-140">セッションにいる一方のユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="c4661-140">ID of one user in the session.</span></span> <span data-ttu-id="c4661-141">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-143">int</span><span class="sxs-lookup"><span data-stu-id="c4661-143">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-144">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-145">セッションにいる他方のユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="c4661-145">ID of the other user in the session.</span></span> <span data-ttu-id="c4661-146">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-148">識別子</span><span class="sxs-lookup"><span data-stu-id="c4661-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-149">セッションの第 1 のユーザーによって使用されているエンドポイントを示す GUID。</span><span class="sxs-lookup"><span data-stu-id="c4661-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="c4661-150">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c4661-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-152">識別子</span><span class="sxs-lookup"><span data-stu-id="c4661-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-153">セッションの第 2 のユーザーによって使用されているエンドポイントを示す GUID。</span><span class="sxs-lookup"><span data-stu-id="c4661-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="c4661-154">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c4661-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-156">int</span><span class="sxs-lookup"><span data-stu-id="c4661-156">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-157">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-158">SIP 要求における元の送信先ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="c4661-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="c4661-159">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-161">int</span><span class="sxs-lookup"><span data-stu-id="c4661-161">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-162">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-163">セッションを開始したユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="c4661-163">ID of the user who started the session.</span></span> <span data-ttu-id="c4661-164">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-166">int</span><span class="sxs-lookup"><span data-stu-id="c4661-166">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-167">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-168">発信者が代理を務めているユーザーの ID を示します。</span><span class="sxs-lookup"><span data-stu-id="c4661-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="c4661-169">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-171">int</span><span class="sxs-lookup"><span data-stu-id="c4661-171">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-172">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-173">通話の参照元であるユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="c4661-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="c4661-174">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-176">int</span><span class="sxs-lookup"><span data-stu-id="c4661-176">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-177">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-178">このセッションで使用されるフロントエンド サーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="c4661-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="c4661-179">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-180"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-181">int</span><span class="sxs-lookup"><span data-stu-id="c4661-181">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-182">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-183">セッションが取得されたプールの ID。</span><span class="sxs-lookup"><span data-stu-id="c4661-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="c4661-184">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-186">int</span><span class="sxs-lookup"><span data-stu-id="c4661-186">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-187">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-188">セッションで使用されるコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="c4661-188">Content type used in the session.</span></span> <span data-ttu-id="c4661-189">詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-191">int</span><span class="sxs-lookup"><span data-stu-id="c4661-191">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-192">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-193">User1 によって使用されるクライアント バージョン。</span><span class="sxs-lookup"><span data-stu-id="c4661-193">Client version used by User1.</span></span> <span data-ttu-id="c4661-194">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-196">int</span><span class="sxs-lookup"><span data-stu-id="c4661-196">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-197">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-198">User2 によって使用されるクライアント バージョン。</span><span class="sxs-lookup"><span data-stu-id="c4661-198">Client version used by User2.</span></span> <span data-ttu-id="c4661-199">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-201">int</span><span class="sxs-lookup"><span data-stu-id="c4661-201">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-202">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-203">User1 によって使用されるエッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="c4661-203">Edge Server used by User1.</span></span> <span data-ttu-id="c4661-204">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-206">int</span><span class="sxs-lookup"><span data-stu-id="c4661-206">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-207">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-208">User2 によって使用されるエッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="c4661-208">Edge Server used by User2.</span></span> <span data-ttu-id="c4661-209">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-211">若干</span><span class="sxs-lookup"><span data-stu-id="c4661-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-212">User1 が内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c4661-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-214">若干</span><span class="sxs-lookup"><span data-stu-id="c4661-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-215">User2 が内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c4661-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-216"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-217">日付型</span><span class="sxs-lookup"><span data-stu-id="c4661-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-218">最初の INVITE 要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="c4661-218">The time of the first INVITE request.</span></span> <span data-ttu-id="c4661-219">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c4661-220">INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="c4661-221">このフィールドには通常、セッションの最初の INVITE メッセージから生成されたデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c4661-222">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-223"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-224">日付型</span><span class="sxs-lookup"><span data-stu-id="c4661-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-225">最初の INVITE メッセージへの応答の時刻。</span><span class="sxs-lookup"><span data-stu-id="c4661-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="c4661-226">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c4661-227">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-229">int</span><span class="sxs-lookup"><span data-stu-id="c4661-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-p121">セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4661-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-233"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-234">int</span><span class="sxs-lookup"><span data-stu-id="c4661-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-235">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="c4661-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-237">int</span><span class="sxs-lookup"><span data-stu-id="c4661-237">int</span></span></p></td>
<td><p><span data-ttu-id="c4661-238">外部</span><span class="sxs-lookup"><span data-stu-id="c4661-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c4661-239">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="c4661-239">Call priority.</span></span> <span data-ttu-id="c4661-240">詳細については、「 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の呼び出し優先度</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4661-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-242">int</span><span class="sxs-lookup"><span data-stu-id="c4661-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-243">User1 がセッション中に送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="c4661-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-245">int</span><span class="sxs-lookup"><span data-stu-id="c4661-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-246">User2 がセッション中に送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="c4661-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-248">日付型</span><span class="sxs-lookup"><span data-stu-id="c4661-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-249">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="c4661-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-251">int</span><span class="sxs-lookup"><span data-stu-id="c4661-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-p123">このセッションのメディアの種類を示すビット セット。その種類の定義を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c4661-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4661-254">IM</span><span class="sxs-lookup"><span data-stu-id="c4661-254">IM</span></span></p></td>
<td><p><span data-ttu-id="c4661-255">1-d</span><span class="sxs-lookup"><span data-stu-id="c4661-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="c4661-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="c4661-257">pbm-2</span><span class="sxs-lookup"><span data-stu-id="c4661-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="c4661-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="c4661-259">4 </span><span class="sxs-lookup"><span data-stu-id="c4661-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="c4661-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="c4661-261">8 </span><span class="sxs-lookup"><span data-stu-id="c4661-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-262">再生</span><span class="sxs-lookup"><span data-stu-id="c4661-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="c4661-263">16 </span><span class="sxs-lookup"><span data-stu-id="c4661-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-264">画面</span><span class="sxs-lookup"><span data-stu-id="c4661-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="c4661-265">32</span><span class="sxs-lookup"><span data-stu-id="c4661-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="c4661-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="c4661-267">64</span><span class="sxs-lookup"><span data-stu-id="c4661-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-269">smallint</span><span class="sxs-lookup"><span data-stu-id="c4661-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-p124">User1 の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="c4661-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c4661-272">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="c4661-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-274">smallint</span><span class="sxs-lookup"><span data-stu-id="c4661-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-p125">User2 の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="c4661-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c4661-277">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="c4661-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4661-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-279">smallint</span><span class="sxs-lookup"><span data-stu-id="c4661-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-p126">通話の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="c4661-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c4661-282">0x01 - 再試行されたセッション</span><span class="sxs-lookup"><span data-stu-id="c4661-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="c4661-283">0x02 - 応答グループの代理を務めるエージェントによって行われた通話</span><span class="sxs-lookup"><span data-stu-id="c4661-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4661-284"><strong>実行</strong></span><span class="sxs-lookup"><span data-stu-id="c4661-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="c4661-285">若干</span><span class="sxs-lookup"><span data-stu-id="c4661-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c4661-286">監視サービスの内部用テーブル。</span><span class="sxs-lookup"><span data-stu-id="c4661-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="c4661-287">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c4661-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4661-288">\* ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="c4661-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="c4661-289">まったく同時に複数のセッションが開始した場合、あるセッションの SessionIdSeq は 1、別のセッションは 2、などとなります。</span><span class="sxs-lookup"><span data-stu-id="c4661-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

