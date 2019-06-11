---
title: 'Lync Server 2013: ポスター: 主要な正常性インジケーター'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013 の主要な正常性インジケーター

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-10_

この記事では、主要な正常性インジケーターの管理について説明します。これは、ダウンロードセンターからダウンロードできる[正常な Lync server ポスターを保守するための基盤](http://go.microsoft.com/fwlink/?linkid=391838)です。

![KHI データを使ったトラブルシューティングについて説明しているポスター](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI データを使ったトラブルシューティングについて説明しているポスター")

このポスターを使って、重要な正常性インジケーター (KHIs) について説明します。パフォーマンスカウンターは、ユーザーエクスペリエンスの問題を明らかにすることを目的としたしきい値を備えています。 KHI データの収集は、通常、通話品質の方法 (CQM) を実装するための最初の手順であり、Lync ユーザーの品質オーディオエクスペリエンスを実現することに重点を置いています。

CQM の使い方について質問がある場合は、cqmfeedback@microsoft.com に質問を送信できます。

このポスターでは、次の領域について説明します。

  - 主要な正常性インジケーターとは

  - KHI データを収集するには

  - すべてのサーバーの役割の改善フロー

  - 解説

  - フロントエンドサーバー

  - バックエンドの SQL Server

  - 仲介サーバー

  - エッジ サーバー

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>主要な正常性インジケーターとは

主要な正常性インジケーターは、ユーザーエクスペリエンスの問題を明らかにするしきい値を持つパフォーマンスカウンターです。 KHI データの収集は、通常、通話品質の方法 (CQM) を実装するための最初の手順であり、Lync ユーザーの品質オーディオエクスペリエンスを実現することに重点を置いています。

KHIs は、これらのソリューションではなく、標準の Lync 監視ソリューション (System Center Operations Manager、代理トランザクション、監視サーバーなど) に加えて使用されます。

KHI パフォーマンスカウンターを収集し、[ネットワークガイド] に [ネットワークガイド] と表示された、Lync 展開のサーバーの正常性を判断するのに役立つスコアカードを作成します。 設定が完了したら、環境の修復について説明し、他の関係者に関する詳しい情報を提供します。 KHIs を月単位で評価し、展開の進行中の運用プロセスに組み込みます。

[Lync Server ネットワークガイド](http://go.microsoft.com/fwlink/p/?linkid=390677)をダウンロードして、khis の一覧を参照し、関連するスプレッドシートを取得してください。

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>KHI データを収集するには

1.  Lync Server ネットワークガイドに含まれている KHI スクリプトを各 Lync サーバーに実行します。 これにより、パフォーマンスモニターの内部にデータコレクターが作成され、その名前に "こんにちは" という名前が付いています。 既定では、データは15秒ごとにポーリングされます。

2.  会社の就業日の開始前に、各 Lync サーバーに移動し、KHI データコレクターを開始します。

3.  その日の最後に、KHI データコレクターを停止し、データを1か所にコピーします。

4.  パフォーマンスモニターを使用して、Lync Server ネットワークガイドのダウンロードに含まれている KHI スプレッドシートに入力したら、結果と推奨されるターゲットを比較します。

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>すべてのサーバーの役割の改善フロー

Lync の実装の各サーバーについて、サーバーのコンポーネントの正常性とシステムのパフォーマンスが目的のレベル以上であることを確認することから始めます。 その後にのみ、Lync の実装でのサーバーの役割に関連するインジケーターを確認する必要があります。

まず、すべてのサーバーについて KHI のパフォーマンスデータを収集します。 システムの各役割 (このドキュメントの後半で説明します) で、基本的なシステムコンポーネントが推奨されるターゲットを満たしているかどうかを確認します。 そうしない場合は、システムのパフォーマンスを改善し、KHI データを再収集して、Lync の実装でサーバーの役割に固有の基準を確認する前に、システムの正常性を確保します。 すべての役割のコンポーネントの正常性は、次のように定義されます。

  - CPU 使用\<率 80%

  - 平均ディスク書き込み\< 10 ms

  - 平均ディスク読み取り\< 10 ms

  - 使用可能\>なメモリ 20% システム合計 MB

  - ネットワークキューの\<長さ2

  - 破棄されたパケット (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>解説

このポスターでは、次の用語と頭字語が使用されています。

MCU = アプリケーション共有マルチポイントコントロールユニット

AV MCU = オーディオ/ビデオ MCU

IM MCU = インスタントメッセージング MCU

UCWA = ユニファイドコミュニケーションの Web API

AV Edge = edge 経由の音声/ビデオのトラバーサル

AV Auth = 音声/ビデオ認証

SIP スタック = Lync のコア SIP の実装が含まれています。

データプロキシ = edge 会議に使用

I Ss = Lync ストレージサービス

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>フロントエンドサーバー

以下の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、フロントエンドサーバーに固有のものです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能領域</th>
<th>目標指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/AV/IM MCU</p></td>
<td><p>MCU 正常性&lt;状態2</p></td>
</tr>
<tr class="even">
<td><p>Web コンポーネント</p></td>
<td><p>配布リスト展開広告タイムアウト&lt;0</p>
<p>ABWQ エラー = 0</p>
<p>LIS のエラー = 0</p>
<p>認証エラー &lt; 1/秒</p>
<p>ASP.NET v4 要求が拒否されました = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP スタック</p></td>
<td><p>平均受信メッセージ ( &lt; 1 秒)</p>
<p>着信応答の&lt;ドロップ 1/秒の受信&lt;要求 1/秒</p>
<p>キュー待機&lt;時間100ミリ秒</p>
<p>ストアドプロシージャ&lt;待機時間100ミリ秒</p>
<p>調整要求 = 0</p>
<p>認証エラー &lt; 1/秒</p>
<p>受信メッセージがタイムアウト&lt;しました2</p>
<p>平均受信メッセージ1秒&lt;を保持</p>
<p>フロー制御接続&lt; 2</p>
<p>Avg キューの遅延&lt; 2 秒</p></td>
</tr>
<tr class="even">
<td><p>一 Ss</p></td>
<td><p>Storage Service DB &lt; 80 で使用されている領域の割合</p>
<p>#レプリカレプリケーションエラーの数 = 0</p>
<p>#データ損失イベントの数 = 0</p></td>
</tr>
<tr class="odd">
<td><p>『</p></td>
<td><p>ページ寿命の&gt;予測300秒</p>
<p>バッチ要求/秒&lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>バックエンドの SQL Server

以下の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、SQL server に固有のものです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能領域</th>
<th>目標指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>『</p></td>
<td><p>ページ寿命の&gt;予測300秒</p>
<p>バッチ要求/秒&lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>仲介サーバー

以下の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、仲介サーバーに固有のものです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能領域</th>
<th>目標指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>仲介サーバーサービス</p></td>
<td><p>通話の読み込みエラーのインデックス = 0</p>
<p>プロキシ&lt;10 のために失敗した通話</p>
<p>ゲートウェイ&lt;10 のために失敗した通話</p>
<p>通話 (in または out) 拒否 = 0</p>
<p>メディア候補が見つかりません = 0</p>
<p>メディア接続の確認エラー = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>エッジ サーバー

以下の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、エッジサーバーに固有のものです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能領域</th>
<th>目標指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AV Auth</p></td>
<td><p>不正な&lt;リクエスト 20/秒</p></td>
</tr>
<tr class="even">
<td><p>AV Edge</p></td>
<td><p>Auth. 失敗&lt;率 20/秒</p>
<p>割り当てエラー &lt;20/秒</p>
<p>パケットドロップ&lt;300/秒</p></td>
</tr>
<tr class="odd">
<td><p>データプロキシ</p></td>
<td><p>サーバー接続&lt;の調整3</p>
<p>システムの調整&lt;は1</p></td>
</tr>
<tr class="even">
<td><p>SIP スタック</p></td>
<td><p>制限を超えた&lt;接続は切断されました1</p>
<p>送信タイムアウト&lt;10</p>
<p>フロー制御接続&lt;100</p>
<p>着信要求が&lt; 1/秒をドロップしました</p>
<p>平均メッセージ処理&lt; 3 秒</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server ネットワークガイド](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[主要な正常性インジケーター: 正常な Lync サーバーを管理するための基盤](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 通話品質の方法](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

