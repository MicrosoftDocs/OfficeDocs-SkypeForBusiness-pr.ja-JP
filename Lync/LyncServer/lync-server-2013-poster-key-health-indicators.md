---
title: 主要状態インジケーター
TOCTitle: 'ポスター: 主要状態インジケーター'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084846
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 主要状態インジケーター

 

_**トピックの最終更新日:** 2016-12-08_

この記事は、ダウンロード センターから提供されている「[主要状態インジケーター: Lync Serverの正常性を維持する基盤 (Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers)](http://go.microsoft.com/fwlink/?linkid=391838)」のポスターと併せてご覧ください。

![KHI データを使用したトラブルシューティングのポスター](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI データを使用したトラブルシューティングのポスター")

このポスターは、主要状態インジケーター (KHI) について説明しています。これはユーザー エクスペリエンスの問題を解明するためのしきい値が設定されたパフォーマンス カウンターです。KHI データの収集は、通常は通話の品質保証の方法論 (CQM) を実装するための最初のステップで、Lync ユーザーの音声エクスペリエンスの品質を保証するものです。

CQM の使用方法について疑問がある場合は、cqmfeedback@microsoft.com までご連絡ください。

このポスターは、次の領域について説明しています。

  - 主要状態インジケーターとは

  - KHI のデータを収集するには

  - すべてのサーバー ロールの修復フロー

  - 用語集

  - フロントエンド サーバー

  - バックエンド SQL サーバー

  - 仲介サーバー

  - エッジ サーバー

## 主要状態インジケーターとは

主要状態インジケーター (KHI) とは、ユーザー エクスペリエンスの問題を解明するためのしきい値が設定されたパフォーマンス カウンターです。KHI データの収集は、通常は通話の品質保証の方法論 (CQM) を実装するための最初のステップで、Lync ユーザーの音声エクスペリエンスの品質を保証するものです。

KHI は、標準の Lync 監視ソリューション (System Center Operations Manager、代理トランザクション、監視サーバーなど) とともに使用されるもので、標準の監視ソリューションに代わるものではありません。

KHI パフォーマンス カウンターのデータを収集して Networking Guide に付属の KHI スプレッドシートに取り込み、スコアカードを生成すると、Lync 展開のサーバーの状態を確認できます。一度データを取り込むと、環境を修復する指針になり、他の要因についてさらに洞察するのに役立ちます。KHI を毎月評価して、それをすべての展開の継続的な運用プロセスに組み込んでください。

KHI の完全なリストを確認して関連するスプレッドシートを入手するには、「[Lync Server ネットワーク ガイド (Lync Server Networking Guide)](http://go.microsoft.com/fwlink/p/?linkid=390677)」をダウンロードしてください。

## KHI のデータを収集するには

1.  各 Lync Server で、Lync Server ネットワーク ガイド (Lync Server Networking Guide) に含まれている KHI スクリプトを実行します。これにより、Performance Monitor 内部に Data Collector が作成されて KHI という名前が与えられます。既定では、15 秒ごとにデータがポーリングされます。

2.  会社がその日の営業を開始する前に、各 Lync Server で KHI Data Collector を起動します。

3.  営業終了時に KHI Data Collector を停止して、データを中央の場所にコピーします。

4.  Performance Monitor を使って KHI スプレッドシート (Lync Server ネットワーク ガイド (Lync Server Networking Guide) ダウンロードに含まれている) にデータを設定したら、結果を推奨される目標と比較します。

## すべてのサーバー ロールの修復フロー

Lync 実装のすべてのサーバーに対して、最初に、そのサーバーのコンポーネントの状態とシステム パフォーマンスが必要なレベル以上であるかどうかを確認します。その後、Lync 実装全体に対するそのサーバーのロールに関連したインジケーターを確認します。

最初に、すべてのサーバーの KHI パフォーマンス データを収集します。それぞれのシステム ロール (後半で説明されています) に対して、基本的なシステム コンポーネントが推奨される目標を達成しているかどうか確認します。目標を達成していない場合は、システムのパフォーマンスを修復してから再度 KHI データを収集し、システムの状態を確認してから、Lync 実装内でのそのサーバーのロールに特化した指標を確認します。コンポーネントの状態は、すべてのロールに対して次のように定義されています。

  - CPU 使用率 \< 80%

  - 平均ディスク書き込み時間 \< 10 ミリ秒

  - 平均ディスク読み取り時間 \< 10 ミリ秒

  - 使用可能メモリ \> 20% システムの合計メモリ容量

  - ネットワーク キューの長さ \< 2

  - 廃棄されたパケット数 (着信/発信) = 0

## 用語集

このポスターでは次の用語と省略語が使用されています。

AS MCU = アプリケーション共有 Multipoint Control Unit

AV MCU = 音声ビデオ MCU

IM MCU = インスタント メッセージング MCU

UCWA = 統合コミュニケーション Web API

AV Edge = エッジ経由の音声ビデオのトラバース

AV Auth = 音声ビデオ認証

SIP スタック = Lync の中核的な SIP 実装が含まれる

データ プロキシ = エッジ会議に使用される

LySS = Lync Storage Service

## フロントエンド サーバー

次の、KHI の推奨される目標値は、基本のコンポーネント状態に加えてフロントエンド サーバーに特化した値です。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能の領域</th>
<th>目標の指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>MCU Health State &lt; 2</p></td>
</tr>
<tr class="even">
<td><p>Web コンポーネント</p></td>
<td><p>Distribution List expansion AD timeouts &lt; 0</p>
<p>ABWQ failures = 0</p>
<p>LIS failures = 0</p>
<p>Authentication Errors &lt; 1/秒</p>
<p>ASP.NET v4 Requests Rejected = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP スタック</p></td>
<td><p>Avg. Incoming Message Processing &lt; 1 秒</p>
<p>Incoming Responses Dropped &lt; 1/秒 Incoming Requests Dropped &lt; 1/秒</p>
<p>Queue Latency &lt; 100 ミリ秒</p>
<p>Sproc Latency &lt; 100 ミリ秒</p>
<p>Throttled Requests = 0</p>
<p>Authentication Errors &lt; 1/秒</p>
<p>Incoming Messages Timed Out &lt; 2</p>
<p>Avg. Incoming Message Hold &lt; 1 秒</p>
<p>Flow Controlled Connections &lt; 2</p>
<p>Avg. Out Queue Delay &lt; 2 秒</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% of space used by Storage Service DB &lt; 80</p>
<p># of replica replication failures = 0</p>
<p># of data loss events = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Page life expectancy &gt; 300 秒</p>
<p>Batch requests/秒 &lt; 2500</p></td>
</tr>
</tbody>
</table>


## バックエンド SQL サーバー

次の、KHI の推奨される目標値は、基本のコンポーネント状態に加えて SQL サーバーに特化した値です。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能の領域</th>
<th>目標の指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Page life expectancy &gt; 300 秒</p>
<p>Batch requests/秒 &lt; 2500</p></td>
</tr>
</tbody>
</table>


## 仲介サーバー

次の、KHI の推奨される目標値は、基本のコンポーネント状態に加えて仲介サーバーに特化した値です。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能の領域</th>
<th>目標の指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>仲介サーバー サービス</p></td>
<td><p>Load Call Failure Index = 0</p>
<p>Failed Calls due to Proxy &lt; 10</p>
<p>Failed Calls due to Gateway &lt; 10</p>
<p>Calls (in or out) rejected = 0</p>
<p>Media Candidates missing = 0</p>
<p>Media Connectivity Check Failures = 0</p></td>
</tr>
</tbody>
</table>


## エッジ サーバー

次の、KHI の推奨される目標値は、基本のコンポーネント状態に加えてエッジ サーバーに特化した値です。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能の領域</th>
<th>目標の指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AV Auth</p></td>
<td><p>Bad Requests &lt; 20/秒</p></td>
</tr>
<tr class="even">
<td><p>AV Edge</p></td>
<td><p>Auth. Failures &lt; 20/秒</p>
<p>Allocation Failures &lt; 20/秒</p>
<p>Packets Dropped &lt; 300/秒</p></td>
</tr>
<tr class="odd">
<td><p>データ プロキシ</p></td>
<td><p>Throttled Server connections &lt; 3</p>
<p>System is Throttling &lt; 1</p></td>
</tr>
<tr class="even">
<td><p>SIP スタック</p></td>
<td><p>Connections over limit dropped &lt; 1</p>
<p>Sends timed out &lt; 10</p>
<p>Flow Controlled Connections &lt; 100</p>
<p>Incoming requests dropped &lt; 1/秒</p>
<p>Avg. Message Processing &lt; 3 秒</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### その他のリソース

[Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[主要状態インジケーター: Lync Serverの正常性を維持する基盤 (Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers)](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync Call Quality Methodology (通話の品質保証の方法論)](http://go.microsoft.com/fwlink/?linkid=391841)

