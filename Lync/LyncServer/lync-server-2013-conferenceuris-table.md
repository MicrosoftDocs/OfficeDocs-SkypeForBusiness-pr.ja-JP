---
title: 'Lync Server 2013: ConferenceUris テーブル'
TOCTitle: ConferenceUris テーブル
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48273301
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の ConferenceUris テーブル

 

_**トピックの最終更新日:** 2015-03-09_

ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ</p></td>
<td><p>タイム スタンプ (社内使用向け)。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>この会議 URI を識別する一意の番号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p></p></td>
<td><p>会議 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>Checksum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>ConferenceUri のチェックサム。データベース検索の速度を速めるために使用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>URI の種類。たとえば、conf:chat (IM 会議の場合)、conf:audio-video (音声ビデオ会議の場合)。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

