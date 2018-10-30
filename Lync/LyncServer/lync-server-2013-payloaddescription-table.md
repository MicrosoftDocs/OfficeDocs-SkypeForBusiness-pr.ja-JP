---
title: 'Lync Server 2013: PayloadDescription テーブル'
TOCTitle: PayloadDescription テーブル
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48273507
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の PayloadDescription テーブル

 

_**トピックの最終更新日:** 2015-03-09_

PayloadDescription テーブルは、サポート テーブルです。各レコードが、音声セッションまたはビデオ セッションで使用される 1 つのコーデックを表します。


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
<td><p><strong>PayloadDescriptionKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>コーデックを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>PayloadDescription</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>一意</p></td>
<td><p>コーデック名。</p></td>
</tr>
</tbody>
</table>

