---
title: 'Lync Server 2013: Conference テーブル'
TOCTitle: Conference テーブル
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48271528
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Conference テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Conference テーブルは、サポート テーブルです。各レコードは、1 つの会議またはピアツーピア セッションを表します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>この会議レコードを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>一意</p></td>
<td><p>これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Checksum</strong></p></td>
<td><p>int</p></td>
<td><p>インデックス</p></td>
<td><p>会議 URI のチェックサム。これは内部で使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>

