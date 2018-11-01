---
title: 'Lync Server 2013: 常設チャット サーバーのテーブルのリスト'
TOCTitle: 常設チャット サーバーのテーブルのリスト
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48271518
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の常設チャット サーバーのテーブルのリスト

 

_**トピックの最終更新日:** 2015-03-09_

常設チャットのデータベース スキーマは、次のテーブルで構成されます。

## Active Directory の同期


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
<td><p>現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。各行は、常設チャット サーバーが変更をアクティブに監視する Active Directory ドメイン サービス ドメインに対応します (このテーブルでは、常設チャット サーバーに関係のある Active Directory ドメインだけが表されます)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 の tblPrincipalMemberDifference</a></p></td>
<td><p>後続の Active Directory 同期手順でまだ処理されていないグループ メンバーシップの変更 (メンバーの追加と削除の両方) が格納され、Active Directory の同期の最初の手順で (tblADUpdates テーブルと共に) 使用される一時テーブルの 1 つです。</p>
<p>メンバーシップの変更が格納および処理されるのは、tblPrincipal テーブルにリストされているグループ、またはメンバーが既にここにリストされているグループについてだけです。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 の tblADUpdates</a></p></td>
<td><p>後続の Active Directory 同期手順でまだ処理されていない Active Directory ドメイン サービス に対する変更が格納され、Active Directory の同期の最初の手順で (tblPrincipalMemberDifference テーブルと共に) 使用される一時テーブルの 1 つです。</p>
<p>Active Directory の変更が格納および処理されるのは、tblPrincipal テーブルに既にリストされているプリンシパルについてだけです。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 の tblPrincipalMembers</a></p></td>
<td><p>プリンシパルのメンバーシップが格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 の tblPrincipalMeta</a></p></td>
<td><p>Active Directory から更新する必要のあるプリンシパルが格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 の tblSkippedAffiliations</a></p></td>
<td><p>何らかの理由で (通常は、Active Directory のアクセス エラーのため) 更新できなかった所属が格納されます。</p>
<p>このテーブルは情報提供のみを目的としています。内容は使用されません。</p>
<p>適切に更新できなかった所属のあるプリンシパルは、tblPrincipalMeta テーブルに保持され、再度更新が試みられます。</p></td>
</tr>
</tbody>
</table>


## プリンシパル、所属、ノード、スコープ、役割


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
<td><p>tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が格納されます。このテーブルは静的です。データベース作成時に設定され、変更されません。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 の tblPrincipal</a></p></td>
<td><p>すべてのプリンシパル (ユーザー、フォルダー、グループなど) が格納されます。常設チャット サーバーは、これをフラットな異種リストとして扱います。さまざまな列は、各プリンシパルの種類に基づきます。</p>
<p>これらのプリンシパルのほとんどは、Active Directory に格納されているオブジェクトのキャッシュされたコピーです。Active Directory オブジェクトのキャッシュされたコピーを Principal テーブルに作成することを、<em>プロビジョニング</em>といいます。</p>
<p>一部のプリンシパルは他よりも積極的に作成され、一部の Active Directory オブジェクトはまったく無視されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 の tblPrincipalAffiliations</a></p></td>
<td><p>Active Directory セキュリティ グループ、Active Directory コンテナーなどでのメンバーシップを記述するプリンシパルの所属が格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013 の tblNode</a></p></td>
<td><p>Lync Server コントロール パネルで管理されるのと同じようなカテゴリ ノードが格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013 の tblRoleType</a></p></td>
<td><p>役割の種類とそれに関連付けられているアクセス許可セットが格納されます。この検索テーブルは静的です。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 の tblScopePrincipal</a></p></td>
<td><p>ノードに割り当てられたスコープが格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 の tblPrincipalRole</a></p></td>
<td><p>ノードに割り当てられた役割が格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 の tblSiopWhiteList</a></p></td>
<td><p>ノードと関連付けることのできる登録されたアドインが格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 の tblEnumAttribute</a></p></td>
<td><p>tblNode テーブルで使用されるハードコードされた &quot;表示&quot; および &quot;動作&quot; 属性だけが格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 の tblEnumValue</a></p></td>
<td><p>tblNode テーブルで使用されるハードコードされた &quot;表示&quot; および &quot;動作&quot; 属性の値が格納されます。</p></td>
</tr>
</tbody>
</table>


## 招待、チャット、および他のクライアントのサポート


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
<td><p>ファイル送信を目的とする一時的なトークンが格納されます。ファイルがアップロードまたはダウンロードされるたびに、常設チャット サービスはクライアントが Web サービスのファイル ストアにアクセスするために使用するトークンを生成します。</p></td>
</tr>
</tbody>
</table>


## サーバーのサポート


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
<td><p>常設チャット サーバー プール内のアクティブなサーバーが格納されます。</p></td>
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
<td><p>常設チャット サービス間の現在のピアツーピア接続が格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013 の tblConfig</a></p></td>
<td><p>常設チャット サーバーのサポートされていない構成が格納されます。</p></td>
</tr>
</tbody>
</table>

