---
title: 'Lync Server 2013: Phones テーブル'
TOCTitle: Phones テーブル
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48271882
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Phones テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Phones テーブルは、サポート テーブルです。このテーブルの各レコードには、レコードがデータベースに含まれる VoIP 通話に関係する 1 つの電話番号についての情報が格納されます。


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
<td><p><strong>PhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>この電話を示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>PhoneUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p>電話番号です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>dateTime</p></td>
<td><p></p></td>
<td><p>タイム スタンプです (内部でのみ使用)。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

