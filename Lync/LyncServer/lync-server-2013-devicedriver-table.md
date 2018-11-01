---
title: 'Lync Server 2013: DeviceDriver テーブル'
TOCTitle: DeviceDriver テーブル
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48273598
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の DeviceDriver テーブル

 

_**トピックの最終更新日:** 2015-03-09_

DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。


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
<td><p><strong>DeviceDriverKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このデバイス ドライバー レコードを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>一意</p></td>
<td><p>デバイス ドライバー名。</p></td>
</tr>
</tbody>
</table>

