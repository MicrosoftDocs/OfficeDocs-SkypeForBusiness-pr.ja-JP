---
title: 'Lync Server 2013: SessionCorrelation テーブル'
TOCTitle: SessionCorrelation テーブル
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48271114
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の SessionCorrelation テーブル

 

_**トピックの最終更新日:** 2015-03-09_

SessionCorrelation テーブルはサポート テーブルです。各レコードは、複数のセッションの関連付けに使用される 1 つの CorrelationID を表します。


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
<td><p><strong>Checksum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>この音声ビデオ会議サーバーを示す一意の番号です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationID</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>一意</p></td>
<td><p>相互に関連付けられるセッションは、同じ関連付け ID を持ちます。</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>

