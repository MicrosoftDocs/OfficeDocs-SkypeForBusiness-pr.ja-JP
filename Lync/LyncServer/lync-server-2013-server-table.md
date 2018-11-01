---
title: 'Lync Server 2013: サーバー テーブル'
TOCTitle: サーバー テーブル
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48272954
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のサーバー テーブル

 

_**トピックの最終更新日:** 2015-03-09_

サーバー テーブルは補助的なテーブルです。個々のレコードが 1 つのサーバーを表します。


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
<td><p><strong>ServerKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>サーバーを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>インデックス</p></td>
<td><p>MAC アドレス文字列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>1: 仲介サーバー</p>
<p>2: 音声ビデオ会議サーバー16394: 音声ビデオ エッジ サービス 32769: ゲートウェイ</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar (512)</p></td>
<td><p></p></td>
<td><p>サーバーが所属するプール。音声ビデオ会議サーバーにのみ適用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>

