---
title: 'Lync Server 2013: tblPrincipal'
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48272605
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblPrincipal

 

_**トピックの最終更新日:** 2015-03-09_

tblPrincipal テーブルには、ユーザー、フォルダー、グループなど、すべてのプリンシパルが格納されます。

### 列

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>型</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>NULL でない int</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>プリンシパル GUID。その重要性は本来の枠を超えて Active Directory ドメイン サービス の領域にも及ぶため、代替の主キーとして幅広く使用されます (キャッシュされたプリンシパルの GUID は対応する Active Directory オブジェクトの GUID と同じです)。</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>プリンシパル URI。SIP スキームはユーザーで使用され、ma-grp はユーザーを除くほぼすべてで使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>共通名。ユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>表示名。ユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会社名。ユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>電子メール。ユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>プリンシパルがキャッシュされたバージョンである Active Directory オブジェクトのドメイン名。Active Directory オブジェクトでない種類 (システム ユーザーなど) では NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>ユーザーのユーザー プリンシパル名 (UPN)。通常のユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>NULL でない smallint</p></td>
<td><ul>
<li><p>0: プリンシパルはアクティブです。</p></li>
<li><p>1: ユーザーの SIP 機能が無効であるため、プリンシパルは無効です。</p></li>
<li><p>2: 関連付けられている AD オブジェクトが削除されたため、プリンシパルは削除されます。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>プリンシパルの種類 (tblPrincipalType テーブルに基づいています)。</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>プリンシパルに対する Lync プールの割り当て。</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>タグ タイプのポリシーが存在する場合、ユーザーの 常設チャット サーバー ポリシーの値。</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>作成者のプリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>作成時刻のタイム スタンプ。</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>このテーブルを最後に更新したプリンシパルの ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>最後の更新のタイム スタンプ。</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>NULL でない datetime</p></td>
<td><p>プリンシパルに対する Active Directory の同期による最終更新の日付と時刻。</p></td>
</tr>
</tbody>
</table>


### キー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>tblPrincipalType.ptypeID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

