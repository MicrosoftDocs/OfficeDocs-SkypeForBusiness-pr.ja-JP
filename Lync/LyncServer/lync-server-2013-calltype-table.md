---
title: 'Lync Server 2013: CallType テーブル'
TOCTitle: CallType テーブル
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48273133
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の CallType テーブル

 

_**トピックの最終更新日:** 2015-03-09_

CallType テーブルは、可能な通話の種類を一覧にした静的なテーブルです。


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar</p></td>
<td><p></p></td>
<td><p>有効な値は次のとおりです。</p>
<ul>
<li><p>0 – 不明</p></li>
<li><p>1 – インスタント メッセージング</p></li>
<li><p>2 – アプリケーション共有</p></li>
<li><p>3 – 音声</p></li>
<li><p>4 – 音声およびビデオ</p></li>
<li><p>5 – ファイル送信</p></li>
</ul></td>
</tr>
</tbody>
</table>

