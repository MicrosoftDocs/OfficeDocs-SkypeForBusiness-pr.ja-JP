---
title: UserAgent ビュー
TOCTitle: UserAgent ビュー
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49887115
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UserAgent ビュー

 

_**トピックの最終更新日:** 2015-03-09_

UserAgent ビューには、データベースに記録があるセッションに参加したユーザー エージェントについての情報が格納されています。このビューは、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>このユーザー エージェントを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>ユーザー エージェントの文字列。</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>ユーザー エージェントの種類。詳細については、「<a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>ユーザー エージェントが属するカテゴリ。たとえば、ユーザー エージェント Conferencing_Attendant_1.0 は UACategory CAA に属します。</p></td>
</tr>
</tbody>
</table>

