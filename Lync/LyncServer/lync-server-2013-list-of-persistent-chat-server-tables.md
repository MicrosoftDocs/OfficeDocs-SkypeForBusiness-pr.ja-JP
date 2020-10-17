---
title: 'Lync Server 2013: 常設チャットサーバーテーブルのリスト'
description: 'Lync Server 2013: 常設チャットサーバーテーブルのリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 838e6d8f83b137923075851b29df4c602a487391
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550053"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="2e46b-103">Lync Server 2013 の常設チャットサーバーのテーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="2e46b-103">List of Persistent Chat Server tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e46b-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="2e46b-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="2e46b-105">常設チャットデータベーススキーマは、次の表で構成されています。</span><span class="sxs-lookup"><span data-stu-id="2e46b-105">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="2e46b-106">Active Directory 同期</span><span class="sxs-lookup"><span data-stu-id="2e46b-106">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e46b-107">Table</span><span class="sxs-lookup"><span data-stu-id="2e46b-107">Table</span></span></th>
<th><span data-ttu-id="2e46b-108">説明</span><span class="sxs-lookup"><span data-stu-id="2e46b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-109"><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 の tblADCookie</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-110">現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が保存されています。</span><span class="sxs-lookup"><span data-stu-id="2e46b-110">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="2e46b-111">各行は、Active Directory ドメインサービスドメインに対応しており、常設チャットサーバーは、変更を積極的に監視しています。</span><span class="sxs-lookup"><span data-stu-id="2e46b-111">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="2e46b-112">(この表では、常設チャットサーバーに関連する Active Directory ドメインのみが示されています)。</span><span class="sxs-lookup"><span data-stu-id="2e46b-112">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 の tblPrincipalMemberDifference</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-114">Active directory 同期の最初のステップで使用される、グループメンバーシップの変更 (メンバーの追加および削除) がまだ処理されていない場合に、この後の Active Directory 同期手順では処理されず、一時テーブル (tblADUpdates テーブルと共に) のいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-114">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="2e46b-115">メンバーシップの変更が格納および処理されるのは、tblPrincipal テーブルにリストされているグループ、またはメンバーが既にここにリストされているグループについてだけです。</span><span class="sxs-lookup"><span data-stu-id="2e46b-115">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-116"><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 の tblADUpdates</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-117">Active directory の同期手順でまだ処理されていない Active Directory ドメインサービスへの変更が含まれており、Active Directory 同期の最初の手順で使用される一時テーブル (tblPrincipalMemberDifference テーブルと共に) の1つです。</span><span class="sxs-lookup"><span data-stu-id="2e46b-117">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="2e46b-118">Active Directory への変更は、tblPrincipal テーブルに既に一覧表示されているプリンシパルに対してのみ保存、処理、またはその両方になります。</span><span class="sxs-lookup"><span data-stu-id="2e46b-118">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-119"><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 の tblPrincipalMembers</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-120">プリンシパルのメンバーシップが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-120">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-121"><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 の tblPrincipalMeta</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-122">Active Directory から更新する必要があるプリンシパルが保存されています。</span><span class="sxs-lookup"><span data-stu-id="2e46b-122">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-123"><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 の tblSkippedAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-124">何らかの理由で更新できなかった所属が含まれています。通常は、Active Directory アクセスエラーが原因です。</span><span class="sxs-lookup"><span data-stu-id="2e46b-124">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="2e46b-p102">このテーブルは情報提供のみを目的としています。内容は使用されません。</span><span class="sxs-lookup"><span data-stu-id="2e46b-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="2e46b-127">適切に更新できなかった所属のあるプリンシパルは、tblPrincipalMeta テーブルに保持され、再度更新が試みられます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-127">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="2e46b-128">プリンシパル、所属、ノード、スコープ、役割</span><span class="sxs-lookup"><span data-stu-id="2e46b-128">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e46b-129">Table</span><span class="sxs-lookup"><span data-stu-id="2e46b-129">Table</span></span></th>
<th><span data-ttu-id="2e46b-130">説明</span><span class="sxs-lookup"><span data-stu-id="2e46b-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-131"><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 の tblPrincipalType</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-p103">tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が格納されます。このテーブルは静的です。データベース作成時に設定され、変更されません。</span><span class="sxs-lookup"><span data-stu-id="2e46b-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-135"><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 の tblPrincipal</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-136">すべてのプリンシパル (ユーザー、フォルダー、グループなど) が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-136">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="2e46b-137">常設チャットサーバーは、これをフラットな異種リストとして処理します。</span><span class="sxs-lookup"><span data-stu-id="2e46b-137">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="2e46b-138">さまざまな列は、各プリンシパルの種類に基づきます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-138">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="2e46b-139">これらのプリンシパルのほとんどは、Active Directory に格納されているオブジェクトのキャッシュコピーです。</span><span class="sxs-lookup"><span data-stu-id="2e46b-139">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="2e46b-140">これらの Active Directory オブジェクトのプリンシパルテーブルにキャッシュコピーを作成することを、 <em>プロビジョニング</em>と呼びます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-140">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="2e46b-141">一部のプリンシパルは他のプリンシパルよりも積極的に作成され、一部の Active Directory オブジェクトは完全に無視されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-141">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-142"><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 の tblPrincipalAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-143">Active Directory セキュリティグループ、Active Directory コンテナーなどのメンバーシップを記述するプリンシパルの所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e46b-143">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-144"><a href="lync-server-2013-tblnode.md">Lync Server 2013 の tblNode</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-145">[Lync Server コントロールパネル] で管理されるカテゴリノードを含みます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-145">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-146"><a href="lync-server-2013-tblroletype.md">Lync Server 2013 の tblRoleType</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-147">役割の種類とそれに関連付けられているアクセス許可セットが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-147">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="2e46b-148">この検索テーブルは静的です。</span><span class="sxs-lookup"><span data-stu-id="2e46b-148">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-149"><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 の tblScopePrincipal</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-150">ノードに割り当てられたスコープが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-150">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-151"><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 のに tblprincipalrole</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-152">ノードに割り当てられた役割が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-152">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-153"><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 の tblSiopWhiteList</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-154">ノードと関連付けることのできる登録されたアドインが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-154">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-155"><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 の tblEnumAttribute</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-156">&quot; &quot; &quot; &quot; TblNode テーブルで使用されるハードコーディングされた可視性属性と動作属性のみを含みます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-156">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-157"><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 の tblEnumValue</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-158">&quot; &quot; TblNode テーブルで使用される、ハードコーディングされた可視性 "および" 動作属性の値を格納します。</span><span class="sxs-lookup"><span data-stu-id="2e46b-158">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="2e46b-159">招待、チャット、および他のクライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="2e46b-159">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e46b-160">Table</span><span class="sxs-lookup"><span data-stu-id="2e46b-160">Table</span></span></th>
<th><span data-ttu-id="2e46b-161">説明</span><span class="sxs-lookup"><span data-stu-id="2e46b-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-162"><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 のそして tblprincipalinvites</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-163">自動招待が有効になっているすべてのノードに対する、システム内のプロビジョニングされたすべてのユーザーの招待が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-163">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-164"><a href="lync-server-2013-tblchat.md">Lync Server 2013 の tblChat</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-165">すべてのチャット メッセージが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-165">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-166"><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 の tblLastInviteId</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-167">各ユーザーに対して生成された (そして tblPrincipalInvites テーブルで使用された) 最後の招待 ID が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-167">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-168"><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 の tblLastChatId</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-169">各ユーザーに対して生成された (そして tblChat テーブルで使用された) 最後のチャット ID が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-169">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-170"><a href="lync-server-2013-tblpreference.md">Lync Server 2013 の tblPreference</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-171">ユーザーのクライアントの基本設定 (レガシ クライアントでのみ使用される) が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-171">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-172"><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 の tblFileToken</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-173">ファイル送信を目的とする一時的なトークンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-173">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="2e46b-174">ファイルがアップロードまたはダウンロードされるたびに、常設チャットサービスは、クライアントが Web サービスファイルストアにアクセスするために使用するトークンを生成します。</span><span class="sxs-lookup"><span data-stu-id="2e46b-174">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="2e46b-175">サーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="2e46b-175">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e46b-176">Table</span><span class="sxs-lookup"><span data-stu-id="2e46b-176">Table</span></span></th>
<th><span data-ttu-id="2e46b-177">説明</span><span class="sxs-lookup"><span data-stu-id="2e46b-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-178"><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 の tblServerIdentity</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-179">常設チャットサーバープール内のアクティブなサーバーが保存されています。</span><span class="sxs-lookup"><span data-stu-id="2e46b-179">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-180"><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 の tblAdminLock</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-p108">管理者コマンドを実行するための管理者ロックが格納されます。ロックが解除されるたびに、tblSystemRevision テーブル内のシステム リビジョン エントリがインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-183"><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 の tblSystemRevision</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-184">複数のサーバー間の整合性を実現するために (tblAdminLock テーブルと共に) 使用されるリビジョン番号エントリが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-184">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e46b-185"><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 の tblActivePeers</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-186">常設チャットサービス間の現在のピアツーピア接続を含みます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-186">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e46b-187"><a href="lync-server-2013-tblconfig.md">Lync Server 2013 の tblConfig</a></span><span class="sxs-lookup"><span data-stu-id="2e46b-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2e46b-188">常設チャットサーバーのサポートされていない構成を含みます。</span><span class="sxs-lookup"><span data-stu-id="2e46b-188">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

