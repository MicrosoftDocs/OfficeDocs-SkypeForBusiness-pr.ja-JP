---
title: 'Lync Server 2013: ポスター: 主要な正常性インジケーター'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aca31ca681c75438bbcbb67b1d2dc5c0b6305cb7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013 の主要な正常性インジケーター

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-10_

この記事では、正常な[Lync Servers ポスターを維持するための基礎となる主要な正常性インジケーターについ](https://go.microsoft.com/fwlink/?linkid=391838)て説明します。これは、ダウンロードセンターからダウンロードできます。

![KHI データを使用したトラブルシューティングについて説明するポスター](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI データを使用したトラブルシューティングについて説明するポスター")

このポスターを使用して、主要な正常性インジケーター (KHIs) について説明し、しきい値を使用して、ユーザーの利便性の問題を明らかにすることを目的としたパフォーマンスカウンターを示します。 通話品質の方法論 (CQM) を実装するための最初の手順は、通常、Lync ユーザー向けの高品質なオーディオ操作を実現することに重点を置いて、KHI データを収集することです。

CQM の使用方法について質問がある場合は、cqmfeedback@microsoft.com に質問を送信できます。

ポスターは、以下の領域について説明します。

  - 重要な正常性インジケーターとは

  - KHI データを収集するには

  - すべてのサーバーの役割の修復フロー

  - 用語集

  - フロントエンドサーバー

  - バックエンドの SQL サーバー

  - 仲介サーバー

  - エッジ サーバー

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>重要な正常性インジケーターとは

キー正常性インジケーターは、パフォーマンスカウンターのしきい値によって、ユーザーの作業環境の問題を明らかにします。 通話品質の方法論 (CQM) を実装するための最初の手順は、通常、Lync ユーザー向けの高品質なオーディオ操作を実現することに重点を置いて、KHI データを収集することです。

KHIs は、標準的な Lync 監視ソリューション (System Center Operations Manager、代理トランザクション、監視サーバーなど) に加えて、これらのソリューションの代わりに使用されます。

KHI パフォーマンスカウンターを収集し、ネットワークガイドに付属する KHI スプレッドシートに、Lync 展開のサーバーの状態を判断するのに役立つスコアカードを作成します。 情報を入力すると、環境を修復して、他の関係者に対してさらに洞察を提供することができます。 KHIs を月単位で評価し、展開の継続的な運用プロセスに組み込みます。

[Lync Server ネットワークガイド](https://go.microsoft.com/fwlink/p/?linkid=390677)をダウンロードして、khis の完全なリストを確認し、関連するスプレッドシートを取得します。

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>KHI データを収集するには

1.  各 Lync Server で Lync Server ネットワークガイドに含まれている KHI スクリプトを実行します。 これにより、パフォーマンスモニターの内部にデータコレクターが作成され、KHI という名前になります。 既定では、データは15秒ごとにポーリングされます。

2.  会社の就業日の開始前に、各 Lync Server に移動し、KHI データコレクターを開始します。

3.  その日の最後に、KHI Data コレクターを停止し、データを1か所にコピーします。

4.  パフォーマンスモニターを使用して Lync Server ネットワークガイドのダウンロードに含まれている KHI スプレッドシートにデータを入力した後、結果を推奨されるターゲットと比較します。

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>すべてのサーバーの役割の修復フロー

Lync 実装の各サーバーについては、まず、サーバーのコンポーネントの正常性とシステムのパフォーマンスが目的のレベル以上であることを確認します。 その後、Lync の実装全体におけるサーバーの役割に関連する指標を確認する必要があります。

まず、すべてのサーバーの KHI パフォーマンスデータを収集します。 各システムの役割 (このドキュメントで後述します) について、基本的なシステムコンポーネントが推奨されるターゲットを満たしているかどうかを判断します。 そうでない場合は、Lync の実装でのサーバーの役割に固有の指標を確認する前に、システムのパフォーマンスを修復し、KHI データを再度収集して、システムの正常性を確保します。 すべての役割のコンポーネントの正常性は次のように定義されます。

  - CPU 使用\<率80%

  - 平均ディスク書き込み\< 10 ミリ秒

  - 平均ディスク読み取り\< 10 ミリ秒

  - 使用可能\>なメモリ20% システムの合計 MB

  - ネットワークキューの\<長さ2

  - 破棄されたパケット (入力/出力) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>用語集

このポスターでは、次の用語と略語を使用しています。

MCU として = アプリケーション共有マルチポイントコントロールユニット

AV MCU = 音声/ビデオ MCU

IM MCU = インスタントメッセージング MCU

UCWA = 統合コミュニケーション Web API

AV Edge = エッジ経由の音声/ビデオのトラバース

AV Auth = 音声/ビデオ認証

SIP スタック = Lync のコア SIP 実装が含まれています。

データプロキシ = エッジ会議に使用

その他の Ss = Lync Storage Service

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>フロントエンドサーバー

次の KHI ターゲットは、基本コンポーネントの正常性に加えて、フロントエンドサーバーに固有のものです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能領域</th>
<th>ターゲット指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>MCU 正常性&lt;状態2</p></td>
</tr>
<tr class="even">
<td><p>Web コンポーネント</p></td>
<td><p>配布リスト展開 AD タイムアウト&lt;0</p>
<p>ABWQ の失敗 = 0</p>
<p>LIS のエラー = 0</p>
<p>認証エラー &lt; 1/秒</p>
<p>ASP.NET v4 要求が拒否されました = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP スタック</p></td>
<td><p>1秒あたりの平均&lt;受信メッセージ処理</p>
<p>着信応答ドロップ&lt;された 1/Sec &lt;受信要求ドロップ 1/秒</p>
<p>キュー待機&lt;時間100ミリ秒</p>
<p>ストアドプロシージャ&lt;待機時間100ミリ秒</p>
<p>調整される要求 = 0</p>
<p>認証エラー &lt; 1/秒</p>
<p>受信メッセージがタイムアウト&lt;になりました2</p>
<p>受信メッセージの平均保持&lt;時間1秒</p>
<p>フロー制御さ&lt;れた接続2</p>
<p>平均アウトキュー遅延&lt; 2 秒</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>Storage Service DB &lt; 80 で使用される領域の割合 (%)</p>
<p>#レプリカレプリケーションエラーの数 = 0</p>
<p>#データ損失イベントの数 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>ページ寿命の&gt;予測300秒。</p>
<p>Batch requests/sec &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>バックエンドの SQL サーバー

次の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、SQL server に固有のものです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能領域</th>
<th>ターゲット指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>ページ寿命の&gt;予測300秒。</p>
<p>Batch requests/sec &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>仲介サーバー

次の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、仲介サーバーに固有です。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能領域</th>
<th>ターゲット指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>仲介サーバーサービス</p></td>
<td><p>読み込み呼び出しエラーのインデックス = 0</p>
<p>プロキシ&lt;10 のために失敗した通話</p>
<p>ゲートウェイ&lt;10 が原因で失敗した通話</p>
<p>拒否された呼び出し (in または out) = 0</p>
<p>メディア候補がありません = 0</p>
<p>メディア接続チェックの失敗 = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>エッジ サーバー

基本的なコンポーネントの正常性に加えて、エッジサーバーに固有の以下の KHI ターゲットが推奨されます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能領域</th>
<th>ターゲット指標</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AV 認証</p></td>
<td><p>無効な&lt;要求数 20/秒</p></td>
</tr>
<tr class="even">
<td><p>AV エッジ</p></td>
<td><p>Auth. 失敗&lt;回数 20/秒</p>
<p>割り当てエラー &lt;数 20/秒</p>
<p>削除&lt;されたパケット数 300/秒</p></td>
</tr>
<tr class="odd">
<td><p>データプロキシ</p></td>
<td><p>サーバー接続&lt;の調整3</p>
<p>システムが調整&lt;1</p></td>
</tr>
<tr class="even">
<td><p>SIP スタック</p></td>
<td><p>制限を超えた&lt;接続の削除1</p>
<p>送信タイムアウト&lt;10</p>
<p>フロー制御さ&lt;れた接続100</p>
<p>1/sec &lt;がドロップした着信要求</p>
<p>平均メッセージ処理&lt;時間3秒</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server ネットワークガイド](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[主要な正常性インジケーター: 正常な Lync Server を維持するための基礎](https://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 通話品質の方法論](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

