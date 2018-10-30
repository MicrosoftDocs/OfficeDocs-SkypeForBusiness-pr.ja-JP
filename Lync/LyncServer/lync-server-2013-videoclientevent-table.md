---
title: 'Lync Server 2013: VideoClientEvent テーブル'
TOCTitle: VideoClientEvent テーブル
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48274019
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の VideoClientEvent テーブル

 

_**トピックの最終更新日:** 2015-03-09_

各レコードには、ビデオ通話の 1 つのエンドポイントのクライアント イベントが格納されます。通常、1 件の通話に対して、発信者と呼び出し先の 2 つのレコードが存在します。


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
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>主/プライマリ</p></td>
<td><p>0: 呼び出し先のデータ</p>
<p>1: 呼び出し元のデータ</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して LowBandwidth イベントが発生したセッションの割合。帯域幅が不足しているために、満足のいく状態で音声を利用できません。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して ReceiveSendQuality イベントが発生したセッションの割合。</p>
<p>ジッターまたはパケット損失の面でネットワーク品質が厳しく、受信する音声の品質に影響します。</p></td>
</tr>
</tbody>
</table>

