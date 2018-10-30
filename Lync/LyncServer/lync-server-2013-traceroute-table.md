---
title: TraceRoute テーブル
TOCTitle: TraceRoute テーブル
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48273375
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# TraceRoute テーブル

 

_**トピックの最終更新日:** 2015-03-09_

TraceRoute テーブルには、通話からのルーティング情報が含まれています。このテーブルは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>主/プライマリ、外部</p></td>
<td><p>通話が開始された日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>同じ日付の同じ時刻に開始された可能性がある複数の通話を区別するために使用される一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>通話で使用されるビデオ ラインの種類を表します。有効な値は次のとおりです。</p>
<ul>
<li><p>0 - 音声</p></li>
<li><p>1 - ビデオ</p></li>
<li><p>2 – パノラマ ビデオ</p></li>
<li><p>3 - アプリケーション共有/デスクトップ共有</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>主/プライマリ</p></td>
<td><p>通話を発信したエンドポイント。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hop</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>ネットワーク ホップ/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>IP アドレスの一意の識別子。IP アドレス情報は、<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>に格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>ラウンド トリップ時間。ラウンド トリップ時間は、音声パケットが宛先に到達してから受信通知を送り返すまでにかかる時間を測定します。</p></td>
</tr>
</tbody>
</table>

