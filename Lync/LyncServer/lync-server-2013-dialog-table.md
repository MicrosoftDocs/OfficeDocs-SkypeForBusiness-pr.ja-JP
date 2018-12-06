---
title: 'Lync Server 2013: Dialog テーブル'
TOCTitle: Dialog テーブル
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48272040
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Dialog テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Dialog テーブルは、サポート テーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ</p></td>
<td><p>QoE (Quality of Excellence) エージェントが発信者または呼び出し先から最初のレポートを受信する時刻です。セッションを一意に識別するために SessionSeq と併用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>複数のセッションの ConferenceDateTime が同じであるときに、セッションどうしを区別するためのシーケンス番号です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogID</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p></p></td>
<td><p>グローバルに一意のダイアログ ID です。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogIDChecksum</strong></p></td>
<td><p>int</p></td>
<td><p>インデックス</p></td>
<td><p>ダイアログ ID のチェックサムです。</p></td>
</tr>
</tbody>
</table>

