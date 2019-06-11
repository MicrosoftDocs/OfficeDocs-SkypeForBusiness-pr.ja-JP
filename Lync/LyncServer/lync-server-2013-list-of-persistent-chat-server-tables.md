---
title: 'Lync Server 2013: 常設チャット サーバーのテーブルのリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d5c16160d51373fe1eef5b7cbaefe728b904545
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="ce574-102">Lync Server 2013 の常設チャット サーバーのテーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="ce574-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce574-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ce574-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ce574-104">常設チャットデータベーススキーマは、次の表で構成されています。</span><span class="sxs-lookup"><span data-stu-id="ce574-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="ce574-105">Active Directory の同期</span><span class="sxs-lookup"><span data-stu-id="ce574-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce574-106">テーブル</span><span class="sxs-lookup"><span data-stu-id="ce574-106">Table</span></span></th>
<th><span data-ttu-id="ce574-107">説明</span><span class="sxs-lookup"><span data-stu-id="ce574-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce574-108"><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 の tblADCookie</a></span><span class="sxs-lookup"><span data-stu-id="ce574-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-109">現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="ce574-110">各行は、常設チャットサーバーが変更を積極的に監視している Active Directory ドメインサービスドメインに対応しています。</span><span class="sxs-lookup"><span data-stu-id="ce574-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="ce574-111">(この表では、常設チャットサーバーに関連する Active Directory ドメインのみが示されています。)</span><span class="sxs-lookup"><span data-stu-id="ce574-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 の tblPrincipalMemberDifference</a></span><span class="sxs-lookup"><span data-stu-id="ce574-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-113">Active directory 同期の以降の手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除の両方) が含まれています。また、Active Directory 同期の最初の手順で使用されている一時的なテーブル (tblADUpdates table と共に表示されます) の1つです。</span><span class="sxs-lookup"><span data-stu-id="ce574-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="ce574-114">メンバーシップの変更は、tblPrincipal テーブルに一覧表示されている、または既に表示されているメンバーが含まれているグループに対してのみ、保存、処理、またはその両方になります。</span><span class="sxs-lookup"><span data-stu-id="ce574-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-115"><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 の tblADUpdates</a></span><span class="sxs-lookup"><span data-stu-id="ce574-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-116">Active directory の以降の同期手順でまだ処理されていない Active Directory ドメインサービスへの変更が含まれています。また、Active directory の最初の手順で使用される一時的なテーブル (tblPrincipalMemberDifference テーブルと共に表示されます) の1つです。せる.</span><span class="sxs-lookup"><span data-stu-id="ce574-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="ce574-117">Active Directory への変更は、tblPrincipal テーブルに既に一覧表示されているプリンシパルに対してのみ保存、処理、またはその両方が行われます。</span><span class="sxs-lookup"><span data-stu-id="ce574-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-118"><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 の tblPrincipalMembers</a></span><span class="sxs-lookup"><span data-stu-id="ce574-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-119">プリンシパルメンバーシップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-120"><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 の tblPrincipalMeta</a></span><span class="sxs-lookup"><span data-stu-id="ce574-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-121">Active Directory から更新する必要があるプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-122"><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 の tblSkippedAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="ce574-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-123">何らかの理由で更新できない所属先が含まれています。通常、Active Directory アクセスエラーが原因です。</span><span class="sxs-lookup"><span data-stu-id="ce574-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="ce574-124">この表は、情報提供のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ce574-124">This table is for informational purposes only.</span></span> <span data-ttu-id="ce574-125">コンテンツは使用されません。</span><span class="sxs-lookup"><span data-stu-id="ce574-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="ce574-126">適切に更新できなかった所属のプリンシパルは、tblPrincipalMeta テーブルに保存され、もう一度更新される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce574-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="ce574-127">プリンシパル、所属、ノード、スコープ、およびロール</span><span class="sxs-lookup"><span data-stu-id="ce574-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce574-128">テーブル</span><span class="sxs-lookup"><span data-stu-id="ce574-128">Table</span></span></th>
<th><span data-ttu-id="ce574-129">説明</span><span class="sxs-lookup"><span data-stu-id="ce574-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce574-130"><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 の tblPrincipalType</a></span><span class="sxs-lookup"><span data-stu-id="ce574-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-131">TblPrincipal テーブルの内容を分類するプリンシパルの型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="ce574-132">この表は静的です。</span><span class="sxs-lookup"><span data-stu-id="ce574-132">This table is static.</span></span> <span data-ttu-id="ce574-133">データベースの作成中に設定され、変更されません。</span><span class="sxs-lookup"><span data-stu-id="ce574-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-134"><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 の tblPrincipal</a></span><span class="sxs-lookup"><span data-stu-id="ce574-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-135">すべてのプリンシパル (ユーザー、フォルダー、グループなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="ce574-136">常設チャットサーバーは、フラットな異種混在リストとして処理します。</span><span class="sxs-lookup"><span data-stu-id="ce574-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="ce574-137">さまざまな列は、各プリンシパルの種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ce574-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="ce574-138">これらのプリンシパルのほとんどは、Active Directory に保存されているオブジェクトのキャッシュコピーです。</span><span class="sxs-lookup"><span data-stu-id="ce574-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="ce574-139">これらの Active Directory オブジェクトのプリンシパルテーブルに、キャッシュされたコピーを作成することは、<em>プロビジョニング</em>と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="ce574-140">一部のプリンシパルは、他のプリンシパルよりも積極的に作成され、一部の Active Directory オブジェクトは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ce574-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-141"><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 の tblPrincipalAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="ce574-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-142">Active Directory セキュリティグループ、Active Directory コンテナーなどのメンバーシップについて説明するプリンシパルメンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-143"><a href="lync-server-2013-tblnode.md">Lync Server 2013 の tblNode</a></span><span class="sxs-lookup"><span data-stu-id="ce574-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-144">Lync Server コントロールパネルで管理される [カテゴリ] ノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-145"><a href="lync-server-2013-tblroletype.md">Lync Server 2013 の tblRoleType</a></span><span class="sxs-lookup"><span data-stu-id="ce574-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-146">ロールの種類とそれに関連付けられているアクセス許可セットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="ce574-147">この参照テーブルは静的です。</span><span class="sxs-lookup"><span data-stu-id="ce574-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-148"><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 の tblScopePrincipal</a></span><span class="sxs-lookup"><span data-stu-id="ce574-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-149">ノードに割り当てられたスコープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-150"><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 の tblPrincipalRole</a></span><span class="sxs-lookup"><span data-stu-id="ce574-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-151">ノードに割り当てられている役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-152"><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 の tblSiopWhiteList</a></span><span class="sxs-lookup"><span data-stu-id="ce574-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-153">ノードに関連付けることができる登録済みのアドインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-154"><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 の tblEnumAttribute</a></span><span class="sxs-lookup"><span data-stu-id="ce574-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-155">TblNode テーブルで使用&quot;さ&quot;れる&quot;、&quot;ハードコーディングされた表示属性と動作属性のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-156"><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 の tblEnumValue</a></span><span class="sxs-lookup"><span data-stu-id="ce574-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-157">TblNode テーブルで使用される&quot;、ハードコーディングされ&quot;た可視性 "と" 動作属性の値が格納されています。</span><span class="sxs-lookup"><span data-stu-id="ce574-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="ce574-158">招待、チャット、その他のクライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="ce574-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce574-159">テーブル</span><span class="sxs-lookup"><span data-stu-id="ce574-159">Table</span></span></th>
<th><span data-ttu-id="ce574-160">説明</span><span class="sxs-lookup"><span data-stu-id="ce574-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce574-161"><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 の tblPrincipalInvites</a></span><span class="sxs-lookup"><span data-stu-id="ce574-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-162">自動招待が有効になっているすべてのノードについて、システム内のプロビジョニングされたすべてのユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-163"><a href="lync-server-2013-tblchat.md">Lync Server 2013 の tblChat</a></span><span class="sxs-lookup"><span data-stu-id="ce574-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-164">すべてのチャットメッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-165"><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 の tblLastInviteId</a></span><span class="sxs-lookup"><span data-stu-id="ce574-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-166">各ユーザーに対して生成された (tblPrincipalInvites テーブルで使用される) 最後の招待 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-167"><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 の tblLastChatId</a></span><span class="sxs-lookup"><span data-stu-id="ce574-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-168">各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-169"><a href="lync-server-2013-tblpreference.md">Lync Server 2013 の tblPreference</a></span><span class="sxs-lookup"><span data-stu-id="ce574-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-170">ユーザークライアントの設定が含まれます (レガシクライアントでのみ使用されます)。</span><span class="sxs-lookup"><span data-stu-id="ce574-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-171"><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 の tblFileToken</a></span><span class="sxs-lookup"><span data-stu-id="ce574-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-172">ファイル転送のための一時トークンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="ce574-173">ファイルがアップロードまたはダウンロードされるたびに、常設チャットサービスは、クライアントが Web サービスファイルストアへのアクセスに使用するトークンを生成します。</span><span class="sxs-lookup"><span data-stu-id="ce574-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="ce574-174">サーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="ce574-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce574-175">テーブル</span><span class="sxs-lookup"><span data-stu-id="ce574-175">Table</span></span></th>
<th><span data-ttu-id="ce574-176">説明</span><span class="sxs-lookup"><span data-stu-id="ce574-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce574-177"><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 の tblServerIdentity</a></span><span class="sxs-lookup"><span data-stu-id="ce574-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-178">常設チャットサーバープール内のアクティブなサーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-179"><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 の tblAdminLock</a></span><span class="sxs-lookup"><span data-stu-id="ce574-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-180">一部の管理者コマンドを実行するための管理者ロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="ce574-181">TblSystemRevision テーブルのシステムリビジョンエントリは、ロックの各リリースの後でインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="ce574-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-182"><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 の tblSystemRevision</a></span><span class="sxs-lookup"><span data-stu-id="ce574-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-183">複数のサーバー間で一貫性を確保するために使用されるリビジョン番号エントリ (tblAdminLock テーブルと共に) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce574-184"><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 の tblActivePeers</a></span><span class="sxs-lookup"><span data-stu-id="ce574-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-185">常設チャットサービス間の現在のピアツーピア接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce574-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce574-186"><a href="lync-server-2013-tblconfig.md">Lync Server 2013 の tblConfig</a></span><span class="sxs-lookup"><span data-stu-id="ce574-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce574-187">常設チャットサーバーでサポートされていない構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce574-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

