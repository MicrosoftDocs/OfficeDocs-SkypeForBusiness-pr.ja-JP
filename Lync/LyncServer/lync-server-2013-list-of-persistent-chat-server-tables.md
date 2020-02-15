---
title: 'Lync Server 2013: 常設チャットサーバーテーブルのリスト'
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
ms.openlocfilehash: 4327e2a72f91e17fd71cd198940ea01d10423b00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lync Server 2013 の常設チャットサーバーのテーブルの一覧

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

常設チャットデータベーススキーマは、次の表で構成されています。

<div>

## <a name="active-directory-sync"></a>Active Directory 同期


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 の tblADCookie</a></p></td>
<td><p>現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が保存されています。 各行は、Active Directory ドメインサービスドメインに対応しており、常設チャットサーバーは、変更を積極的に監視しています。 (この表では、常設チャットサーバーに関連する Active Directory ドメインのみが示されています)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 の tblPrincipalMemberDifference</a></p></td>
<td><p>Active directory 同期の最初のステップで使用される、グループメンバーシップの変更 (メンバーの追加および削除) がまだ処理されていない場合に、この後の Active Directory 同期手順では処理されず、一時テーブル (tblADUpdates テーブルと共に) のいずれかが含まれます。</p>
<p>メンバーシップの変更が格納および処理されるのは、tblPrincipal テーブルにリストされているグループ、またはメンバーが既にここにリストされているグループについてだけです。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 の tblADUpdates</a></p></td>
<td><p>Active directory の同期手順でまだ処理されていない Active Directory ドメインサービスへの変更が含まれています。これは、Active Directory の最初の手順で使用される一時テーブル (tblPrincipalMemberDifference テーブルと共に) の1つです。頻度.</p>
<p>Active Directory への変更は、tblPrincipal テーブルに既に一覧表示されているプリンシパルに対してのみ保存、処理、またはその両方になります。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 の tblPrincipalMembers</a></p></td>
<td><p>プリンシパルのメンバーシップが格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 の tblPrincipalMeta</a></p></td>
<td><p>Active Directory から更新する必要があるプリンシパルが保存されています。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 の tblSkippedAffiliations</a></p></td>
<td><p>何らかの理由で更新できなかった所属が含まれています。通常は、Active Directory アクセスエラーが原因です。</p>
<p>このテーブルは情報提供のみを目的としています。内容は使用されません。</p>
<p>適切に更新できなかった所属のあるプリンシパルは、tblPrincipalMeta テーブルに保持され、再度更新が試みられます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>プリンシパル、所属、ノード、スコープ、役割


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 の tblPrincipalType</a></p></td>
<td><p>tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が格納されます。このテーブルは静的です。データベース作成時に設定され、変更されません。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 の tblPrincipal</a></p></td>
<td><p>すべてのプリンシパル (ユーザー、フォルダー、グループなど) が格納されます。 常設チャットサーバーは、これをフラットな異種リストとして処理します。 さまざまな列は、各プリンシパルの種類に基づきます。</p>
<p>これらのプリンシパルのほとんどは、Active Directory に格納されているオブジェクトのキャッシュコピーです。 これらの Active Directory オブジェクトのプリンシパルテーブルにキャッシュコピーを作成することを、<em>プロビジョニング</em>と呼びます。</p>
<p>一部のプリンシパルは他のプリンシパルよりも積極的に作成され、一部の Active Directory オブジェクトは完全に無視されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 の tblPrincipalAffiliations</a></p></td>
<td><p>Active Directory セキュリティグループ、Active Directory コンテナーなどのメンバーシップを記述するプリンシパルの所属が含まれています。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013 の tblNode</a></p></td>
<td><p>[Lync Server コントロールパネル] で管理されるカテゴリノードを含みます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013 の tblRoleType</a></p></td>
<td><p>役割の種類とそれに関連付けられているアクセス許可セットが格納されます。 この検索テーブルは静的です。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 の tblScopePrincipal</a></p></td>
<td><p>ノードに割り当てられたスコープが格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 のに tblprincipalrole</a></p></td>
<td><p>ノードに割り当てられた役割が格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 の tblSiopWhiteList</a></p></td>
<td><p>ノードと関連付けることのできる登録されたアドインが格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 の tblEnumAttribute</a></p></td>
<td><p>TblNode テーブルで使用&quot;さ&quot;れる&quot;ハード&quot;コーディングされた可視性属性と動作属性のみを含みます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 の tblEnumValue</a></p></td>
<td><p>TblNode テーブルで使用される&quot;、ハードコーディングされ&quot;た可視性 "および" 動作属性の値を格納します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>招待、チャット、および他のクライアントのサポート


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 のそして tblprincipalinvites</a></p></td>
<td><p>自動招待が有効になっているすべてのノードに対する、システム内のプロビジョニングされたすべてのユーザーの招待が格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">Lync Server 2013 の tblChat</a></p></td>
<td><p>すべてのチャット メッセージが格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 の tblLastInviteId</a></p></td>
<td><p>各ユーザーに対して生成された (そして tblPrincipalInvites テーブルで使用された) 最後の招待 ID が格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 の tblLastChatId</a></p></td>
<td><p>各ユーザーに対して生成された (そして tblChat テーブルで使用された) 最後のチャット ID が格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Lync Server 2013 の tblPreference</a></p></td>
<td><p>ユーザーのクライアントの基本設定 (レガシ クライアントでのみ使用される) が格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 の tblFileToken</a></p></td>
<td><p>ファイル送信を目的とする一時的なトークンが格納されます。 ファイルがアップロードまたはダウンロードされるたびに、常設チャットサービスは、クライアントが Web サービスファイルストアにアクセスするために使用するトークンを生成します。</p></td>
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
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 の tblServerIdentity</a></p></td>
<td><p>常設チャットサーバープール内のアクティブなサーバーが保存されています。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 の tblAdminLock</a></p></td>
<td><p>管理者コマンドを実行するための管理者ロックが格納されます。ロックが解除されるたびに、tblSystemRevision テーブル内のシステム リビジョン エントリがインクリメントされます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 の tblSystemRevision</a></p></td>
<td><p>複数のサーバー間の整合性を実現するために (tblAdminLock テーブルと共に) 使用されるリビジョン番号エントリが格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 の tblActivePeers</a></p></td>
<td><p>常設チャットサービス間の現在のピアツーピア接続を含みます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013 の tblConfig</a></p></td>
<td><p>常設チャットサーバーのサポートされていない構成を含みます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

