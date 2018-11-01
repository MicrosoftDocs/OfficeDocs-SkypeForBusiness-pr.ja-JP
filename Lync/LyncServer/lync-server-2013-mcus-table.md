---
title: 'Lync Server 2013: Mcus テーブル'
TOCTitle: Mcus テーブル
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48271603
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Mcus テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Mcus テーブルはサポート テーブルです。各レコードには、1 つの会議サービスに関する情報が格納されます。これには、IM 会議サービスとテレフォニー会議サービス (フロントエンド サーバーでのプロセスとして実行)、および Web 会議サービスと音声ビデオ会議サービスが含まれます。


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
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>この会議サーバーを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><strong>McuTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外部</p></td>
<td><p>conf:chat (IM の場合) や conf:audio-video など、会議サーバーの種類です。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

