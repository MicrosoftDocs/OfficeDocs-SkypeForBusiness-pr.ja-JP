---
title: 'Lync Server 2013: デバイスレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc453ca1e83d8077e67ef130ef7a83e03c138be2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a>Lync Server 2013 のデバイスレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-12_

デバイス レポートは、通話に関連した指標 (低品質通話のパーセンテージ、エコー、音声切り替え時間など) を通話で使用されたマイクとスピーカーによってグループ化して取得するため、マイクとスピーカーのレポートと呼んだほうが良いかもしれません。 IP 電話 (通常は "デバイス" とも呼ばれます) に関心がある場合は、代わりに[Lync Server 2013 の Ip 電話インベントリレポート](lync-server-2013-ip-phone-inventory-report.md)を使用します。

デバイス レポートは、特定のタイプのデバイスで低品質通話が他のデバイスより多く発生しているかどうかを管理者が確認するのに非常に役立ちます。これは、新規デバイスの購入や既存デバイスの置き換えの場合の決定に影響する可能性があります。

既定では、デバイス レポートに表示される情報は、通話で使用されたマイク (キャプチャ デバイス) とスピーカー/ヘッドセット (レンダー デバイス) にも基づいています。たとえば、以下のキャプチャ デバイスとレンダー デバイスを使用する複数のユーザーがいるとします。

  - キャプチャ デバイス -- マイク (SoundMAX Integrated Digital HD Audio)

  - レンダー デバイス -- ヘッドセット イヤホン (Microsoft LifeChat LX-3000)

これらのユーザーが合計 254 回の通話を行ったとすると、レポートには以下のようなエントリが表示されます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>キャプチャ デバイス</th>
<th>レンダー デバイス</th>
<th>通話ボリューム</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>マイク (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>ヘッドセット イヤホン (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


次に、同じキャプチャ デバイスを使用するがレンダー デバイスは異なる複数のユーザーがいるとします。その場合、レポートにはキャプチャ デバイスとレンダー デバイスのその独自の組み合わせに関する 2 行目のエントリが表示されます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>[キャプチャ デバイス]</th>
<th>レンダー デバイス</th>
<th>通話ボリューム</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>マイク (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>ヘッドセット イヤホン (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>マイク (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>スピーカー (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


特定のデバイスに関する合計 (たとえば、使用されたレンダー デバイスにかかわらず SoundMAX キャプチャ デバイスに関する合計) を表示するには、[デバイスの種類] ドロップダウン リストから適切なオプション ([キャプチャ デバイス] か [レンダー デバイス]) を選択します。この例で [キャプチャ デバイス] を選択すると、出力は以下のようになります。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>キャプチャ デバイス</th>
<th>通話ボリューム</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>マイク (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>デバイス レポートへのアクセス

デバイス レポートは通常、監視レポート ホーム ページからアクセスされます。 ただし、 [Lync Server 2013 で [通話の詳細] レポート](lync-server-2013-call-detail-report.md)を表示している場合は、次の指標のいずれかをクリックして、特定のデバイスのデバイスレポートにドリルダウンすることができます。

  - キャプチャ デバイス

  - レンダー デバイス

デバイスレポートでは、次の指標のいずれかをクリックして、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)にドリルダウンすることができます。

  - 通話ボリューム

  - 低品質通話のパーセンテージ

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>デバイス レポートの活用

デバイス名に関して、デバイス レポートは非常に詳細です。たとえば、以下のキャプチャ デバイスがあるとします。

  - Aastra 3002 マイク (2- Aastra 3002)

  - Aastra 3002 マイク (3- Aastra 3002)

  - Aastra 3002 マイク (Aastra 3002)

  - Aastra 6725ip

  - Aastra 6725ip マイク (10- Aastra 6725ip)

  - Aastra 6725ip マイク (10- Aastra 6725ip)-V0

  - Aastra 6725ip マイク (2- Aastra 6725ip)

  - Aastra 6725ip マイク (3- Aastra 6725ip)

  - Aastra 6725ip マイク (4- Aastra 6725ip)

  - Aastra 6725ip マイク (5- Aastra 6725ip)

  - Aastra 6725ip マイク (6- Aastra 6725ip)

  - Aastra 6725ip マイク (7- Aastra 6725ip)

  - Aastra 6725ip マイク (9- Aastra 6725ip)

  - Aastra 6725ip マイク (9-Aastra 6725ip)-V0

  - Aastra 6725ip マイク (Aastra 6725ip)

  - Aastra 6725ip マイク (Aastra 6725ip)-V0

  - Aastra 6725ip マイク (USB オーディオデバイス)

  - Aastra 6725ip マイク (USB オーディオデバイス)-V0

<div>


> [!NOTE]  
> ローカライズされたバージョンの Lync Server 2013 を実行している場合、デバイス名のキャプチャは同じではないことに注意してください。 Aastra 6725ip マイク (Aastra 6725ip) という名前のデバイス (米国英語の V0 はフランス語またはスペイン語で異なる名前を持つ場合があります)。



</div>

多くの場合、詳細レベルが必要になります。ただし、モデル番号に関係なく、複数の通話で Aastra マイクを使用することに関心がある場合もあります。 そのような情報を取得する方法の1つとして、デバイスレポートデータを Microsoft Excel にエクスポートし、そのデータをコンマ区切り値ファイル (たとえば、\\C\\:\_data Devices Report .csv) に保存します。 次のような一連のコマンドを使用して、をインポートできます。CSV ファイルを Windows PowerShell にコピーし、Aastra キャプチャデバイスを使って発信した通話の合計数を報告します。

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

これは、Aastra キャプチャデバイスを使って発信した通話の合計数を表す1つの値を返します。 次に例を示します。

    384

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。 たとえば、デバイスレポートでは、通話の種類 (クライアント呼び出しの呼び出し)、電話会議、公衆交換電話網 (PSTN) 通話など、さまざまな機能についてフィルター処理することができます。 また、データをグループ化する方法を選択することもできます。 この場合、デバイスは時間、日、週、または月でグループ化されます。

次の表に、デバイスレポートで使用できるフィルターを示します。

### <a name="device-report-filters"></a>デバイスレポートフィルター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>開始</strong></p></td>
<td><p>時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="even">
<td><p><strong>終了</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="odd">
<td><p><strong>音声スイッチの原因</strong></p></td>
<td><p>エコーを防ぐために、通話が半二重モードになっていた理由。 半二重モードでは、トランシーバーを使用して通信している場合と同じように、通信は一度に1つの方向にしか伝達されません。 次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>なし</p>
</dd>
<dt><span></span></dt>
<dd><p>不正なタイムスタンプ</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (動的非線形プロセッサ)</p>
</dd>
<dt><span></span></dt>
<dd><p>複雑さが低い</p>
</dd>
<dt><span></span></dt>
<dd><p>デバイスの状態が正しくない</p>
</dd>
<dt><span></span></dt>
<dd><p>AEC 後のエコー (アコースティックエコーキャンセル)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>エコーの原因</strong></p></td>
<td><p>通話で許可されたレベルより上のエコーが検出された理由。 (通信では、エコーはサウンドの反射になります。これと同じ現象が見られた場合は、通話の一番下まで移動しても聞こえます)。次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>なし</p>
</dd>
<dt><span></span></dt>
<dd><p>不正なタイムスタンプ</p>
</dd>
<dt><span></span></dt>
<dd><p>AEC 後のエコー (アコースティックエコーキャンセル)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (アダプティブ非線形プロセッサ)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (動的非線形プロセッサ)</p>
</dd>
<dt><span></span></dt>
<dd><p>マイクのクリップ</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>通話の種類</strong></p></td>
<td><p>行われた通話の種類を示します。 次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>クライアント通話</p>
</dd>
<dt><span></span></dt>
<dd><p>PSTN 通話</p>
</dd>
<dt><span></span></dt>
<dd><p>電話会議</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>[アクセスの種類]</strong></p></td>
<td><p>クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>内部</p>
</dd>
<dt><span></span></dt>
<dd><p>外部</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>[ネットワークの種類]</strong></p></td>
<td><p>通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>有線</p>
</dd>
<dt><span></span></dt>
<dd><p>ワイヤレス</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>非 VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>デバイスの種類</strong></p></td>
<td><p>デバイスの種類を示します。 次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>キャプチャ デバイス</p>
</dd>
<dt><span></span></dt>
<dd><p>レンダー デバイス</p>
</dd>
<dt><span></span></dt>
<dd><p>デバイスペアのキャプチャとレンダリング</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>デバイス名</strong></p></td>
<td><p>キャプチャまたはレンダーデバイスの名前。 完全なデバイス名、またはデバイス名の任意の部分を入力できます。 たとえば、デバイスマイク (Microsoft LifeCam VX-1000) を見つけるには、次のように完全なデバイス名を入力します。</p>
<p>マイク (Microsoft LifeCam VX-1000)</p>
<p>または、名前の一部だけを入力することもできます。 次に例を示します。</p>
<p>LifeCam</p>
<p>上のフィルターでは、名前の任意の場所に&quot;文字列&quot; LifeCam が含まれているすべてのデバイスが返されることに注意してください。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表は、デバイスレポートに表示される情報を示しています。

### <a name="device-report-metrics"></a>デバイスレポートのメトリック

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
<td><p><strong>デバイスをキャプチャする</strong></p></td>
<td><p>はい</p></td>
<td><p>デバイス (マイクや web カメラなど) を使ってオーディオを送信します。</p></td>
</tr>
<tr class="even">
<td><p><strong>レンダリングデバイス</strong></p></td>
<td><p>はい</p></td>
<td><p>オーディオを受信するために使用されるデバイス (ヘッドセットやスピーカーなど)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話ボリューム</strong></p></td>
<td><p>可</p></td>
<td><p>発信された通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p><strong>低品質通話のパーセンテージ</strong></p></td>
<td><p>可</p></td>
<td><p>低品質として&quot;分類された通話の割合。&quot;低品質通話とは、測定されたメトリックの少なくとも1つが許可値 (過大なジッターを経験した呼び出しなど) を超えた呼び出しです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>一意のユーザー</strong></p></td>
<td><p>はい</p></td>
<td><p>デバイスを使用した一意のユーザー。 ユーザーがデバイスを13回使用した場合、1つの一意のユーザーとしてカウントされます。これは、そのデバイスを1回だけ使用したユーザーと同じです。</p></td>
</tr>
<tr class="even">
<td><p><strong>音声切り替え時間の比率</strong></p></td>
<td><p>はい</p></td>
<td><p>エコーを防ぐために、半二重モードで実行する必要があった通話の割合。 半二重モードでは、トランシーバーを使用して通信している場合と同じように、通信は一度に1つの方向にしか伝達されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>マイクの比率が機能しない</strong></p></td>
<td><p>はい</p></td>
<td><p>キャプチャデバイスが許容レベルで機能していなかった通話の割合。 大きい値を指定すると、主に、キャプチャデバイスが予期したとおりに動作しないことが原因で、通話の品質の問題が発生します。</p></td>
</tr>
<tr class="even">
<td><p><strong>スピーカーが機能しない場合の比率</strong></p></td>
<td><p>はい</p></td>
<td><p>レンダーデバイスが許容レベルで機能していなかった通話の割合。 高い値を指定すると、主に、レンダリングデバイスが予期したとおりに動作しないことが原因となって、通話の品質の問題が発生します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>音声スイッチを使った通話 (%)</strong></p></td>
<td><p>はい</p></td>
<td><p>半二重モードに設定された合計通話のパーセンテージ。 半二重モードでは、トランシーバーを使用して通信している場合と同じように、通信は一度に1つの方向にしか伝達されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>エコーマイク (%)</strong></p></td>
<td><p>はい</p></td>
<td><p>マイクのキャプチャストリームでエコーが検出された時間の割合。 一般的に、ヘッドセットまたはハンドセットの値は低く、スピーカーフォンやスタンドアロンスピーカーでは高くなります。 オンボード音響エコーキャンセルをサポートしているデバイスでは、高値を指定するとエコーリークが発生します。 その他のデバイスでは、デバイスの品質を評価するためにこのメトリックを使用しないようにする必要があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>エコー送信 (%)</strong></p></td>
<td><p>はい</p></td>
<td><p>他のユーザーに送信されたエコーのパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>エコー (%) で通話</strong></p></td>
<td><p>はい</p></td>
<td><p>エコーが許容レベルを超えていた合計通話の割合。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

