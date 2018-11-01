---
title: UserStatistics テーブル
TOCTitle: UserStatistics テーブル
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49887155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UserStatistics テーブル

 

_**トピックの最終更新日:** 2015-03-09_

UserStatistics テーブルはサポート テーブルです。このテーブル内の各レコードは、システムの個々のユーザーの使用状況についての情報を格納しています。このテーブルは、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このユーザーを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>LastLogInTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>ユーザーが最後にログインした時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizedTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>ユーザーが最後に会議を開催した時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>LastCallOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>ユーザーが最後に通話に失敗した時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>ユーザーが会議開催者として最後に通話に失敗した時刻。</p></td>
</tr>
</tbody>
</table>

