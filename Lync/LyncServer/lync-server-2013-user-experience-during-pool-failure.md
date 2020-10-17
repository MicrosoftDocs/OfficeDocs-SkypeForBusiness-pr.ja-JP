---
title: Lync Server 2013 プール障害時のユーザー環境
description: プール障害時の Lync Server 2013 ユーザーの作業。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0483a01b643d8195e7f8f6259c11ab6fc3561f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569793"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="0806b-103">Lync Server 2013 でのプール障害時のユーザー環境</span><span class="sxs-lookup"><span data-stu-id="0806b-103">User experience during pool failure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0806b-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0806b-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0806b-105">プールがフェールオーバーされた場合、影響を受けるプールのすべてのユーザーが強制的にサインアウトされ、バックアップ プールにサインインされます。</span><span class="sxs-lookup"><span data-stu-id="0806b-105">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="0806b-106">バックアップ プールにサインインしたユーザーは、短い時間、復元モードになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0806b-106">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="0806b-107">復元モードでは、ユーザーは、連絡先の追加など、Lync Server で永続的な変更を発生させるタスクを実行できません。</span><span class="sxs-lookup"><span data-stu-id="0806b-107">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="0806b-108">フェールオーバー完了後、すべてのユーザーはバックアップ プールからすべてのサービスを受けることができます。</span><span class="sxs-lookup"><span data-stu-id="0806b-108">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="0806b-109">プール障害発生時にユーザーが保持していたセッションはすべて中断されるため、ユーザーはフェイルオーバー後にそれらのセッションを再確立して続行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0806b-109">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="0806b-p102">フェールオーバーまたはフェールバック時にユーザーの所属先は変更されません。障害が発生したプールに所属するユーザーは、一時的にバックアップ プールによってサービスを受けます。ホーム プールが復元されると、管理者はこれらのユーザーをフェールバックして、元のホーム プールによってサービスを受けるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0806b-p102">Users are not rehomed during failover or failback. Users who are homed on a pool that fails will be temporarily serviced by the backup pool. When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="0806b-113">メモ Lync 2013 では、場所情報サーバーデータベースはバックアッププールにレプリケートされません。</span><span class="sxs-lookup"><span data-stu-id="0806b-113">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="0806b-114">ベスト プラクティスとして、管理者が LIS データベースを定期的にバックアップし、フェールオーバー後に最新のバックアップ コピーを使用してバックアップ プールに LIS データベースを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0806b-114">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="0806b-115">フェールオーバー中のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="0806b-115">User Experience During Failover</span></span>

<span data-ttu-id="0806b-p104">障害が発生したプールにいる場合、そのユーザーはログアウトされます。そのユーザーが参加していたピアツーピア セッションと、そのユーザーによって開催された会議は終了します。レジストラーの復元タイマーが時間切れになるか、管理者がフェールオーバー手順を開始するまで (いずれか早い方)、ユーザーは再びログインできません。再びログインしたとき、ユーザーはバックアップ プールにログインします。フェールオーバー完了前にログインした場合は、フェールオーバーが完了するまで復元モードになります。フェールオーバーが完了して初めて、ユーザーは新しいセッションを確立したり、以前のセッションを再確立したりできます。</span><span class="sxs-lookup"><span data-stu-id="0806b-p104">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user. The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first. When the user logs back in, they will log in to the backup pool. If they log in before the failover has completed, they will be in Resiliency mode until failover is complete. Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="0806b-121">フェールバック中のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="0806b-121">User Experience During Failback</span></span>

<span data-ttu-id="0806b-p105">影響を受けるユーザーがバックアップ プールにログオンしている間に、プールのフェールバックが発生する可能性があります。ユーザーは、フェールバック中もログオンしたままで、作業を続けられます。フェールバック プロセスの完了には数分かかります。参考として、ユーザー数 20,000 のプールの場合、最大 60 分かかることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="0806b-p105">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback. Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="0806b-125">次の表に、Lync 2013 クライアントまたは Microsoft Lync 2010 クライアントを使用しているユーザーがフェールバックの間に影響を受ける方法、および他のプール内のユーザーが、フェールバックされているプール内のユーザーを表示して操作する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0806b-125">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="0806b-126">Microsoft Office Communicator 2007 R2 クライアントを使用しているユーザーは、フロントエンドプールが完全にフェールバックされるまでサインインできません。)</span><span class="sxs-lookup"><span data-stu-id="0806b-126">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="0806b-p107">「影響を受けるユーザー\*\*」という用語は、ホーム プールからフェールオーバーされ、バックアップ プールによってサービスを受けているユーザーを指します。当然、もともとバックアップ プールに所属するユーザーは影響を受けるユーザーではありません。</span><span class="sxs-lookup"><span data-stu-id="0806b-p107">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool. By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="0806b-129">フェールバックしているプールの影響を受けるユーザーのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="0806b-129">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0806b-130">ユーザー状態またはタスク</span><span class="sxs-lookup"><span data-stu-id="0806b-130">User state or task</span></span></th>
<th><span data-ttu-id="0806b-131">フェールバック中</span><span class="sxs-lookup"><span data-stu-id="0806b-131">During failback</span></span></th>
<th><span data-ttu-id="0806b-132">フェールバックの完了後</span><span class="sxs-lookup"><span data-stu-id="0806b-132">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0806b-133">既にログインしているユーザーのユーザー状態</span><span class="sxs-lookup"><span data-stu-id="0806b-133">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="0806b-p108">ユーザーはサインインしたままで、バックアップ プールに接続されます。ある時点で、ユーザーはサインアウトされ、元のホーム プールに復元モードで再びサインインされます。</span><span class="sxs-lookup"><span data-stu-id="0806b-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="0806b-136">ユーザーはサインインしたままで、通常モードになります。</span><span class="sxs-lookup"><span data-stu-id="0806b-136">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0806b-137">新しくログインするユーザー</span><span class="sxs-lookup"><span data-stu-id="0806b-137">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="0806b-138">ユーザーは復元モードでホーム プールにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="0806b-138">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="0806b-139">ユーザーは通常モードで元のホーム プールにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="0806b-139">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0806b-140">影響を受けるユーザーによって開催中の会議</span><span class="sxs-lookup"><span data-stu-id="0806b-140">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="0806b-p109">会議のすべてのモダリティが終了されます。[再度参加] ボタンが表示されますが、影響を受けるユーザーが復元モードでいる間は、ユーザーは再度参加できません。</span><span class="sxs-lookup"><span data-stu-id="0806b-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="0806b-p110">すべてのモダリティが機能するようになります。すべての参加者は、クリックによって会議に再度参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0806b-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0806b-145">影響を受けないユーザーによって開催された進行中の会議</span><span class="sxs-lookup"><span data-stu-id="0806b-145">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="0806b-p111">会議は続行され、影響を受けるユーザーは会議にとどまることができます。影響を受けるユーザーが実行できるのは、復元モードで実行可能な機能に制限されます。</span><span class="sxs-lookup"><span data-stu-id="0806b-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="0806b-148">会議は続行され、影響を受けるユーザーは会議にとどまることができます。すべてのモダリティは、ユーザーが復元モードでなくなった後に動作します。</span><span class="sxs-lookup"><span data-stu-id="0806b-148">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0806b-149">会議の予定のスケジュールまたは変更、臨時会議の作成</span><span class="sxs-lookup"><span data-stu-id="0806b-149">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="0806b-150">ユーザーが復元モードの間は実行できません。</span><span class="sxs-lookup"><span data-stu-id="0806b-150">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="0806b-151">すべてのモダリティで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="0806b-151">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0806b-152">同じプールの他のユーザーによって確認されるプレゼンス</span><span class="sxs-lookup"><span data-stu-id="0806b-152">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="0806b-153">ユーザーが復元モードでバックアップ プールにサインインしている間、プレゼンスは不明です。</span><span class="sxs-lookup"><span data-stu-id="0806b-153">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="0806b-154">ユーザーが最後に設定したプレゼンス状態が表示されます。プレゼンスの変更が反映されるようになります。</span><span class="sxs-lookup"><span data-stu-id="0806b-154">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0806b-155">連絡先リストとアドレス帳サービスの可用性</span><span class="sxs-lookup"><span data-stu-id="0806b-155">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="0806b-156">該当なし</span><span class="sxs-lookup"><span data-stu-id="0806b-156">Not available</span></span></p></td>
<td><p><span data-ttu-id="0806b-157">Available</span><span class="sxs-lookup"><span data-stu-id="0806b-157">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0806b-158">すべてのピアツーピア セッションおよびモダリティ</span><span class="sxs-lookup"><span data-stu-id="0806b-158">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="0806b-159">Available</span><span class="sxs-lookup"><span data-stu-id="0806b-159">Available</span></span></p></td>
<td><p><span data-ttu-id="0806b-160">Available</span><span class="sxs-lookup"><span data-stu-id="0806b-160">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="0806b-161">別のプールのフェールバック中に影響を受けないプールに所属するユーザーのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="0806b-161">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0806b-162">ユーザー タスク</span><span class="sxs-lookup"><span data-stu-id="0806b-162">User task</span></span></th>
<th><span data-ttu-id="0806b-163">フェールバック中</span><span class="sxs-lookup"><span data-stu-id="0806b-163">During failback</span></span></th>
<th><span data-ttu-id="0806b-164">フェールバックの完了後</span><span class="sxs-lookup"><span data-stu-id="0806b-164">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0806b-165">影響を受けるユーザーのプレゼンスの表示</span><span class="sxs-lookup"><span data-stu-id="0806b-165">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="0806b-166">影響を受けるユーザーが最後に設定したプレゼンス状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0806b-166">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="0806b-p112">動作しています。影響を受けないユーザーには、影響を受けるユーザーによる更新が見えます。</span><span class="sxs-lookup"><span data-stu-id="0806b-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0806b-169">影響を受けるユーザーによって開催中の会議</span><span class="sxs-lookup"><span data-stu-id="0806b-169">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="0806b-170">会議のすべてのモダリティが終了されます。</span><span class="sxs-lookup"><span data-stu-id="0806b-170">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="0806b-p113">すべてのモダリティが機能するようになります。すべての参加者は、クリックによって会議に再度参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0806b-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0806b-173">影響を受けないユーザーによって開催された進行中の会議</span><span class="sxs-lookup"><span data-stu-id="0806b-173">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="0806b-174">会議は続行されます。影響を受けないユーザーは会議に留まることができ、すべてのモダリティが機能します。</span><span class="sxs-lookup"><span data-stu-id="0806b-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="0806b-175">会議は続行されます。影響を受けないユーザーは会議に留まることができ、すべてのモダリティが機能します。</span><span class="sxs-lookup"><span data-stu-id="0806b-175">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0806b-176">すべてのピアツーピア セッションおよびモダリティ</span><span class="sxs-lookup"><span data-stu-id="0806b-176">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="0806b-177">Available</span><span class="sxs-lookup"><span data-stu-id="0806b-177">Available</span></span></p></td>
<td><p><span data-ttu-id="0806b-178">Available</span><span class="sxs-lookup"><span data-stu-id="0806b-178">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

