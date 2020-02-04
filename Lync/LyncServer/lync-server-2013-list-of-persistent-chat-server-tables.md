---
title: 'Lync Server 2013: 常設チャット サーバーのテーブルのリスト'
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
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lync Server 2013 の常設チャット サーバーのテーブルのリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

常設チャットデータベーススキーマは、次の表で構成されています。

<div>

## <a name="active-directory-sync"></a>Active Directory の同期


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 の tblADCookie</a></p></td>
<td><p>現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれます。 各行は、常設チャットサーバーが変更を積極的に監視している Active Directory ドメインサービスドメインに対応しています。 (この表では、常設チャットサーバーに関連する Active Directory ドメインのみが示されています。)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 の tblPrincipalMemberDifference</a></p></td>
<td><p>Active directory 同期の以降の手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除の両方) が含まれています。また、Active Directory 同期の最初の手順で使用されている一時的なテーブル (tblADUpdates table と共に表示されます) の1つです。</p>
<p>メンバーシップの変更は、tblPrincipal テーブルに一覧表示されている、または既に表示されているメンバーが含まれているグループに対してのみ、保存、処理、またはその両方になります。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 の tblADUpdates</a></p></td>
<td><p>Active directory の以降の同期手順でまだ処理されていない Active Directory ドメインサービスへの変更が含まれています。また、Active directory の最初の手順で使用される一時的なテーブル (tblPrincipalMemberDifference テーブルと共に表示されます) の1つです。せる.</p>
<p>Active Directory への変更は、tblPrincipal テーブルに既に一覧表示されているプリンシパルに対してのみ保存、処理、またはその両方が行われます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 の tblPrincipalMembers</a></p></td>
<td><p>プリンシパルメンバーシップが含まれます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 の tblPrincipalMeta</a></p></td>
<td><p>Active Directory から更新する必要があるプリンシパルが含まれています。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 の tblSkippedAffiliations</a></p></td>
<td><p>何らかの理由で更新できない所属先が含まれています。通常、Active Directory アクセスエラーが原因です。</p>
<p>この表は、情報提供のみを目的としています。 コンテンツは使用されません。</p>
<p>適切に更新できなかった所属のプリンシパルは、tblPrincipalMeta テーブルに保存され、もう一度更新される可能性があります。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>プリンシパル、所属、ノード、スコープ、およびロール


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 の tblPrincipalType</a></p></td>
<td><p>TblPrincipal テーブルの内容を分類するプリンシパルの型が含まれています。 この表は静的です。 データベースの作成中に設定され、変更されません。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 の tblPrincipal</a></p></td>
<td><p>すべてのプリンシパル (ユーザー、フォルダー、グループなど) が含まれます。 常設チャットサーバーは、フラットな異種混在リストとして処理します。 さまざまな列は、各プリンシパルの種類に基づいています。</p>
<p>これらのプリンシパルのほとんどは、Active Directory に保存されているオブジェクトのキャッシュコピーです。 これらの Active Directory オブジェクトのプリンシパルテーブルに、キャッシュされたコピーを作成することは、<em>プロビジョニング</em>と呼ばれます。</p>
<p>一部のプリンシパルは、他のプリンシパルよりも積極的に作成され、一部の Active Directory オブジェクトは無視されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 の tblPrincipalAffiliations</a></p></td>
<td><p>Active Directory セキュリティグループ、Active Directory コンテナーなどのメンバーシップについて説明するプリンシパルメンバーが含まれています。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013 の tblNode</a></p></td>
<td><p>Lync Server コントロールパネルで管理される [カテゴリ] ノードが含まれています。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013 の tblRoleType</a></p></td>
<td><p>ロールの種類とそれに関連付けられているアクセス許可セットが含まれます。 この参照テーブルは静的です。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 の tblScopePrincipal</a></p></td>
<td><p>ノードに割り当てられたスコープが含まれます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 の tblPrincipalRole</a></p></td>
<td><p>ノードに割り当てられている役割が含まれます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 の tblSiopWhiteList</a></p></td>
<td><p>ノードに関連付けることができる登録済みのアドインが含まれています。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 の tblEnumAttribute</a></p></td>
<td><p>TblNode テーブルで使用&quot;さ&quot;れる&quot;、&quot;ハードコーディングされた表示属性と動作属性のみが含まれます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 の tblEnumValue</a></p></td>
<td><p>TblNode テーブルで使用される&quot;、ハードコーディングされ&quot;た可視性 "と" 動作属性の値が格納されています。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>招待、チャット、その他のクライアントのサポート


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 の tblPrincipalInvites</a></p></td>
<td><p>自動招待が有効になっているすべてのノードについて、システム内のプロビジョニングされたすべてのユーザーの招待が含まれます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">Lync Server 2013 の tblChat</a></p></td>
<td><p>すべてのチャットメッセージが含まれます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 の tblLastInviteId</a></p></td>
<td><p>各ユーザーに対して生成された (tblPrincipalInvites テーブルで使用される) 最後の招待 ID が含まれています。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 の tblLastChatId</a></p></td>
<td><p>各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれています。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Lync Server 2013 の tblPreference</a></p></td>
<td><p>ユーザークライアントの設定が含まれます (レガシクライアントでのみ使用されます)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 の tblFileToken</a></p></td>
<td><p>ファイル転送のための一時トークンが含まれています。 ファイルがアップロードまたはダウンロードされるたびに、常設チャットサービスは、クライアントが Web サービスファイルストアへのアクセスに使用するトークンを生成します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>サーバーのサポート


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 の tblServerIdentity</a></p></td>
<td><p>常設チャットサーバープール内のアクティブなサーバーが含まれます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 の tblAdminLock</a></p></td>
<td><p>一部の管理者コマンドを実行するための管理者ロックが含まれています。 TblSystemRevision テーブルのシステムリビジョンエントリは、ロックの各リリースの後でインクリメントされます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 の tblSystemRevision</a></p></td>
<td><p>複数のサーバー間で一貫性を確保するために使用されるリビジョン番号エントリ (tblAdminLock テーブルと共に) が含まれます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 の tblActivePeers</a></p></td>
<td><p>常設チャットサービス間の現在のピアツーピア接続が含まれます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013 の tblConfig</a></p></td>
<td><p>常設チャットサーバーでサポートされていない構成が含まれています。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

