---
title: 'Lync Server 2013: IP アドレス タイプの概要'
TOCTitle: Lync Server の IP アドレス タイプの概要
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48273944
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の IP アドレス タイプの概要

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 では、IP アドレスを構成する際に 3 つのオプションを利用できます。IP version 4 (IPv4) または IP version 6 (IPv6) のみをサポートするよう Lync Server 2013 を構成するか、両方を組み合わせて構成 ( *デュアル スタック* ) することができます。各構成には、いくつか考慮すべき問題があります。

  - **IPv4 のみ**   IPv6 は IPv4 アドレスが枯渇し始めたために開発されました。IPv6 は最終的に世界中で完全にサポートされることになりますが、現時点では企業が通信する可能性のある会社やデバイスの多くがまだ IPv6 に対応していません。また、この状況はしばらく続く可能性があります。IPv4 のみの構成で Lync Server を実装すれば、ほぼすべての既存デバイスと通信できます。

  - **IPv6 のみ**   反対に、現時点で完全な IPv6 実装を行うと、多くの既存デバイスと通信できなくなります。

  - **デュアル スタック**   デュアル スタックは、IPv4 と IPv6 アドレスの両方を使用できるネットワークです。完全な IPv4 から完全な IPv6 への移行にはおそらく数年を要するため、 Lync Server 2013 ではこの構成をサポートしています。

このセクションでは、 Lync Server の各種機能に対するこれら 3 構成の互換性について概要を説明します。

> [!NOTE]
> クライアントまたはサーバーを IPv6 のみの構成にすることは、試験や検証の目的でのみサポートされています。IPv6 のみの構成は運用展開ではサポートされていません。


## クライアントの登録


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント エンドポイント ネットワーク</th>
<th>サーバー ネットワーク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


## ピアツーピア クライアント

ピアツーピア通信には、オーディオ、音声ビデオ、アプリケーション共有、ファイル転送などがあります。両方のクライアントが正常に登録された後、次の組み合わせがサポートされます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント エンドポイント 1</th>
<th>クライアント エンドポイント 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


## 電話会議

会議には、音声ビデオ、アプリケーション共有、およびデータ コラボレーション (ホワイト ボードとファイル共有) が含まれます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント エンドポイント ネットワーク</th>
<th>サーバー ネットワーク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


## 仲介サーバー/PSTN

Lync Server 2013 では、トラフィックが IPv6 インターフェイスを経由する場合の公衆交換電話網 (PSTN) 通話のメディア バイパスをサポートしていません。メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プライマリ インターフェイス*</th>
<th>PSTN インターフェイス (仲介サーバー上)</th>
<th>PSTN ゲートウェイの設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\* プライマリ インターフェイスは、 Lync Server コンポーネントと通信を行うインターフェイスです。

## リモート ユーザーのピアツーピア通信

リモート ユーザーとのピアツーピア通信には、インスタント メッセージング、音声ビデオ、アプリケーション共有、およびファイル転送が含まれます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>リモート ユーザー ネットワーク</th>
<th>エッジ サーバー (外部エッジ)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


## フロントエンド プールとエッジ プールの構成

次の表は、 フロント エンド サーバー プールと内部 エッジ サーバー プールの間のサポート マトリックスを示しています。

### フロントエンド プールとエッジ プール (内部エッジ) のマトリックス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>エッジ プール: IPv4</strong></p></td>
<td><p><strong>エッジ プール: デュアル スタック</strong></p></td>
<td><p><strong>エッジ プール: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>フロントエンド プール: IPv4</strong></p></td>
<td><p>○</p></td>
<td><p>○</p></td>
<td><p>×</p></td>
</tr>
<tr class="odd">
<td><p><strong>フロントエンド プール: デュアル スタック</strong></p></td>
<td><p>○</p></td>
<td><p>○</p></td>
<td><p>×</p></td>
</tr>
<tr class="even">
<td><p><strong>フロントエンド プール: IPv6</strong></p></td>
<td><p>×</p></td>
<td><p>×</p></td>
<td><p>はい*</p></td>
</tr>
</tbody>
</table>


\* ラボ環境のみでこの組み合わせを使用。

次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。

### エッジ プール (内部エッジ) とエッジ プール (外部エッジ) のマトリックス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>エッジ プール (外部エッジ): IPv4</strong></p></td>
<td><p><strong>エッジ プール (外部エッジ): デュアル スタック</strong></p></td>
<td><p><strong>エッジ プール (外部エッジ): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>エッジ プール (内部エッジ): IPv4</strong></p></td>
<td><p>○</p></td>
<td><p>○</p></td>
<td><p>×</p></td>
</tr>
<tr class="odd">
<td><p><strong>エッジ プール (内部エッジ): デュアル スタック</strong></p></td>
<td><p>×</p></td>
<td><p>○</p></td>
<td><p>×</p></td>
</tr>
<tr class="even">
<td><p><strong>エッジ プール (内部エッジ): IPv6</strong></p></td>
<td><p>×</p></td>
<td><p>×</p></td>
<td><p>はい*</p></td>
</tr>
</tbody>
</table>


\* ラボ環境のみでこの組み合わせを使用。

## IPv6 の高度なエンタープライズ VoIP のサポート

通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。

> [!NOTE]
> デュアル スタック展開では、 Lync クライアントが IPv6 を使用して Lync Server に接続した場合も、 Lync は E9-1-1 をサポートするために適切な IPv4 アドレスをマッピングするよう最大限に試みます。


IPv6 アドレスの 場所情報サービス はサポートされていません。

Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。

## IPv6 のその他の Lync Server 2013 機能のサポート

前述の機能およびコンポーネントに加え、 Lync Server 2013 では次の機能についても IPv6 をサポートしています。

  - **常設チャット**
    
    トポロジ ビルダーを使用して、 常設チャット用の IPv6 を構成します。 常設チャットの構成の詳細については、ドキュメント「常設チャット サーバーの展開」を参照してください。

  - **Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**
    
    IPv4 か IPv6 かにかかわらず、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。

