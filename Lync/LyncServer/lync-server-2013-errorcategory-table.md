---
title: ErrorCategory テーブル
TOCTitle: ErrorCategory テーブル
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48271287
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ErrorCategory テーブル

 

_**トピックの最終更新日:** 2015-03-09_

ErrorCategory テーブルには、Microsoft Lync Server 2013 での診断の分類を表すフレンドリ名が含まれます。Lync Server 2013 では、既定で次の分類を使用します。

  - 0 -- 成功

  - 1 -- 予期されたエラー

  - 2 – 予期しないエラー

この表は Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>CategoryId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p>分類の一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>分類に割り当てられる値とフレンドリ名。有効な値は次のとおりです。</p>
<ul>
<li><p>0 -- 成功</p></li>
<li><p>1 -- 予期されたエラー</p></li>
<li><p>2 – 予期しないエラー</p></li>
</ul></td>
</tr>
</tbody>
</table>

