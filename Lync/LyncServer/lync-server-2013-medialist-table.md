---
title: 'Lync Server 2013: MediaList テーブル'
TOCTitle: MediaList テーブル
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48271534
ms.date: 07/13/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の MediaList テーブル

 

_**トピックの最終更新日:** 2016-07-12_

MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>有効な値は次のとおりです。</p>
<ul>
<li><p>1 – IM</p></li>
<li><p>2 – ファイル送信</p></li>
<li><p>3 – リモート アシスタンス</p></li>
<li><p>4 – アプリケーション共有</p></li>
<li><p>5 – 音声</p></li>
<li><p>6 – ビデオ</p></li>
<li><p>7 – アプリケーション招待</p></li>
</ul></td>
</tr>
</tbody>
</table>

