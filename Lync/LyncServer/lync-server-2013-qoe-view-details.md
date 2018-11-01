---
title: Lync Server 2013 での QoE ビューの詳細
TOCTitle: Lync Server 2013 での QoE ビューの詳細
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49886990
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での QoE ビューの詳細

 

_**トピックの最終更新日:** 2015-03-09_

ビューは、QoE SQL データベースからデータを取得するための一般的なシナリオのほとんどをカバーします。カスタム レポートを構築する場合は、データベース テーブルに直接アクセスするのではなくビューを使用することをお勧めします。ビューの方が、今後のリリースで下位互換性が維持される可能性が高いためです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ビュー名</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail ビュー</a></p></td>
<td><p>データベース内の各オーディオ ストリームについての情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">MediaLine ビュー</a></p></td>
<td><p>データベース内の各メディア ラインについての情報を格納します。通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings ビュー</a></p></td>
<td><p>ネットワーク構成についての情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Session ビュー</a></p></td>
<td><p>データベース内のレコードを持つセッションについての情報を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">UserAgent ビュー</a></p></td>
<td><p>データベース内のレコードを持つセッションに関与しているユーザー エージェントについての情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail ビュー</a></p></td>
<td><p>データベース内の各ビデオ ストリームについての情報を格納します。</p></td>
</tr>
</tbody>
</table>

