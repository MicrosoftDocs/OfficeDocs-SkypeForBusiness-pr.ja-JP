---
title: 'Lync Server 2013: 通話の詳細レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb57cde990e4c4218297c69aeb3c8933f9a3fd92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a>Lync Server 2013 の通話の詳細レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

通話の詳細レポートでは、個々の通話の詳細が表示されます。レポートには、次のようなレポートセクションに分かれた、ほぼすべての qoe 指標と Lync Server によって収集された統計情報が含まれています。

  - 通話情報

  - 発信者デバイスと信号測定値

  - 呼び出し先デバイスと信号測定値

  - 発信者クライアント イベント

  - 呼び出し先クライアント イベント

  - 音声ストリーム (発信者から呼び出し先)

  - ビデオ ストリーム (発信者から呼び出し先)

  - 音声ストリーム (呼び出し先から発信者)

  - ビデオ ストリーム (呼び出し先から発信者)

特定のレポートに表示されるカテゴリと測定値は、セッションの種類と、セッションで使用されたエンドポイントの種類に依存します。たとえば、音声のみの通話では、通話にビデオ ストリームがないことにより、ビデオ ストリームの測定値を報告されません。同様に、呼び出し先統計はないが、発信者統計を示すレポートがあることがあります。これは、一般的には、呼び出し先が SIP 準拠のデバイスを使用していなかったことによります。エンドポイントは通話の終了後に、統計を報告します。しかし、(SIP または SIP 統計を関知しない) 携帯電話は、その種類の情報を報告することはできません。だれかに電話して、その人が携帯電話で応答した場合は、通話が終了したときに、その携帯電話からのレポートは得られません。

通話の詳細レポートは、特定の通話でメディアの品質の問題が発生した理由を正確に確認するときに最も役立ちます。

<div>

## <a name="accessing-the-call-detail-report"></a>通話の詳細レポートを表示する

通話の詳細レポートは、以下の任意のレポートから表示できます。

  - [Lync Server 2013 の場所レポート](lync-server-2013-location-report.md)([通話ボリューム] または [低品質通話のパーセンテージ] のどちらかをクリック)

  - [Lync Server 2013 のメディア品質概要レポート](lync-server-2013-media-quality-summary-report.md)([通話ボリューム] または [低品質通話のパーセンテージ] のどちらかをクリック)

  - [Lync server 2013 のメディア品質比較レポート](lync-server-2013-media-quality-comparison-report.md)( [lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)をクリックしてから、詳細指標をクリック)。

  - [Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)([通話ボリューム] または [低品質通話のパーセンテージ] のどちらかをクリック)

  - [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)(詳細指標をクリック)

通話の詳細レポートから、次のいずれかの指標をクリックすることによって、 [Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md)にアクセスできます。

  - キャプチャ デバイス

  - レンダー デバイス

また、音声ビデオ エッジ サーバー測定値をクリックすることによってサーバーメディア品質傾向レポートを表示できます。

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a>通話の詳細レポートの活用

通話の詳細レポートには、一般的には、マイクのタイムスタンプの誤差、低 SNR 時間、および近端エコー時間の項目のような、250 以上のさまざまな測定値が含まれます。これらの測定値の詳細が思い出せない場合は、測定値のラベル上にマウス ポインターを置きます。多くの場合は、その測定値を説明するツール ヒントが表示されます。

特定の測定値が見つからない場合は、検索ボックスに測定値ラベルの一部を入力して、次に [検索] をクリックします。たとえば、低 SNR 時間測定値が見つからない場合は、検索ボックスに "SNR" と入力して、次に [検索] をクリックします。

レポートでは、通話に関する情報のみが追跡されることに注意してください。 通話自体は記録されません。

</div>

<div>

## <a name="filters"></a>フィルター

なし。通話の詳細レポートにはフィルターを適用できません。

</div>

<div>

## <a name="metrics"></a>指標

次の表に、各通話の通話の詳細レポートで提供される情報を示します。

### <a name="call-detail-report-metrics"></a>通話の詳細レポートの指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[<strong>発信者 PAI</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>発信者 URI</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>発信者エンドポイント</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを実行したデバイス。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>発信者ユーザー エージェント</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを実行したデバイスで使用されるソフトウェア。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>通話の開始</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しが最初に開始された日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>仲介サーバーのバイパス通話</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しが仲介サーバーを経由せずに PSTN 音声ゲートウェイまたは適切な IP-PBX に接続されたかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>発信者 OS</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出し元のコンピューターのオペレーティング システム。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>発信者 CPU</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーのコンピューターに搭載される CPU。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>発信者 CPU コア番号</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーが使用するコンピューターのプロセッサ番号。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>発信者 CPU 速度</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーが使用するコンピューターの CPU のクロック速度。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>発信者 CPU 仮想化</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>呼び出し先 PAI</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>通話に招待されたユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>呼び出し先 URI</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出し先ユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>呼び出し先エンドポイント</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを受信したデバイス。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>呼び出し先ユーザー エージェント</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを受信したデバイスで使用されるソフトウェア。</p></td>
</tr>
<tr class="even">
<td><p><strong>Duration</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話時間。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>メディア バイパス警告フラグ</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>仲介サーバーがバイパスされたときに発行された警告。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>呼び出し先 OS</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出し先ユーザーのコンピューターのオペレーティング システム。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>呼び出し先 CPU</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出し先ユーザーのコンピューターに搭載される CPU。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>呼び出し先コア番号</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出し先ユーザーが使用するコンピューターのプロセッサ番号。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>呼び出し先 CPU 速度</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出し先ユーザーが使用するコンピューターの CPU のクロック速度。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>呼び出し先 CPU 仮想化</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>呼び出し先ユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

