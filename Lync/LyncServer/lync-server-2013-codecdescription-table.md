---
title: CodecDescription テーブル
TOCTitle: CodecDescription テーブル
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48271729
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CodecDescription テーブル

 

_**トピックの最終更新日:** 2015-03-09_

CodecDescription テーブルは、対応するコーデックに一意コーデック識別子をマップします。コーデックは、送受信とブロードキャスト用にデジタル信号をコード化し、再生時にそれらの信号を読み取る目的で使用されます。このテーブルは Microsoft Lync Server 2013 で導入されました


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
<td><p><strong>CodecDescriptionKey</strong></p></td>
<td><p>smallint</p></td>
<td><p>主/プライマリ</p></td>
<td><p>新しいコーデックに割り当てる一意識別子です。</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>一意</p></td>
<td><p>CodecDescriptionKey に対応しているコーデックの一意詳細。</p></td>
</tr>
</tbody>
</table>

