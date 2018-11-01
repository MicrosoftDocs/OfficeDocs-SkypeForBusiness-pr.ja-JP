---
title: 'Lync Server 2013: デバイス レポート'
TOCTitle: デバイス レポート
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48273986
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 デバイス レポート

 

_**トピックの最終更新日:** 2015-03-09_

デバイス レポートは、通話に関連した指標 (低品質通話のパーセンテージ、エコー、音声切り替え時間など) を通話で使用されたマイクとスピーカーによってグループ化して取得するため、マイクとスピーカーのレポートと呼んだほうが良いかもしれません。IP 電話 (これも一般に "デバイス" と呼ばれます) について知りたい場合、 [Lync Server 2013 の IP 電話インベントリ レポート](lync-server-2013-ip-phone-inventory-report.md)を代わりに使用します。

デバイス レポートは、特定のタイプのデバイスで低品質通話が他のデバイスより多く発生しているかどうかを管理者が確認するのに非常に役立ちます。これは、新規デバイスを購入したり既存デバイスの置き換えたりする際に行わなければならない決定に影響する可能性があります。

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
<th>[通話ボリューム]</th>
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
<th>キャプチャ デバイス</th>
<th>レンダー デバイス</th>
<th>[通話ボリューム]</th>
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


特定のデバイスに関する合計 (たとえば、使用されたレンダー デバイスにかかわらず SoundMAX キャプチャ デバイスに関する合計) を表示するには、\[デバイスの種類\] ドロップダウン リストから適切なオプション (\[キャプチャ デバイス\] か \[レンダー デバイス\]) を選択します。この例で \[キャプチャ デバイス\] を選択すると、出力は以下のようになります。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>キャプチャ デバイス</th>
<th>[通話ボリューム]</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>マイク (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


## デバイス レポートへのアクセス

デバイス レポートは通常、監視レポート ホーム ページからアクセスされます。ただし、 [Lync Server 2013 の通話の詳細レポート](lync-server-2013-call-detail-report.md)を表示している場合は、以下の指標のいずれかをクリックして特定のデバイスに関するデバイス レポートまでドリルダウンできます。

  - キャプチャ デバイス

  - レンダー デバイス

デバイス レポートからは、以下の指標のいずれかをクリックして [Lync Server 2013 の通話リスト レポート](lync-server-2013-call-list-report.md)までドリルダウンできます。

  - \[通話ボリューム\]

  - \[低品質通話のパーセンテージ\]

## デバイス レポートの活用

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

  - Aastra 6725ip マイク (9- Aastra 6725ip)-V0

  - Aastra 6725ip マイク (Aastra 6725ip)

  - Aastra 6725ip マイク (Aastra 6725ip)-V0

  - Aastra 6725ip マイク (USB オーディオ デバイス)

  - Aastra 6725ip マイク (USB オーディオ デバイス)-V0

> [!NOTE]
> ローカライズされたバージョンの Lync Server 2013 を実行している場合、キャプチャ デバイス名は同じでない可能性があることに注意してください。米国英語で Aastra 6725ip Microphone (Aastra 6725ip)-V0 という名前のデバイスは、フランス語やスペイン語では名前が異なる可能性があります。


このレベルの詳細度が必要な場合は多くありますが、別の場合には、モデル番号にかかわらず Aastra マイクを使用した通話の数がわかればそれで良い可能性があります。そのような情報を得る 1 つの方法は、デバイス レポート データを Microsoft Excel にエクスポートし、そのデータをカンマ区切り値のファイル (たとえば、C:\\Data\\Devices\_Report.csv) に保存することです。その後、その .CSV ファイルを以下のような一連のコマンドを使用して Windows PowerShell にインポートし、Aastra キャプチャ デバイスを使用して行われた通話の合計数を戻します。

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

これは、Aastra キャプチャ デバイスを使用して行われた通話の合計数を表す単一の値を戻します。次に例を示します。

    384

## フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、デバイスレポートでは、通話の種類 (つまりクライアント通話かどうか)、電話会議、公衆交換電話網 (PSTN) 通話などに基づくフィルターを行えます。また、データをグループ化する方法を選択することもできます。この場合は、時間、日、週、または月を基準にデバイスがグループ化されます。

次の表に、デバイス レポートで使用できるフィルターを示します。

### デバイス レポートのフィルター

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
<td><p>[ <strong>開始</strong> ]</p></td>
<td><p>時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>07.07.12</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>03.07.12</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>終了</strong> ]</p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>07.07.12</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>03.07.12</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>音声切り替えの原因</strong> ]</p></td>
<td><p>エコーを防ぐために通話が半二重モードになった理由。半二重モードでは、トランシーバーで会話するときと同じように、通信は一方向ずつでのみ行えます。次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>なし</p>
</dd>
<dt><span></span></dt>
<dd><p>誤ったタイムスタンプ</p>
</dd>
<dt><span></span></dt>
<dd><p>エコー</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (Dynamic Nonlinear Processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>低い複雑度</p>
</dd>
<dt><span></span></dt>
<dd><p>不良なデバイス状態</p>
</dd>
<dt><span></span></dt>
<dd><p>AEC 後のエコー (アコーステック エコー キャンセレーション)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>[ <strong>エコーの原因</strong> ]</p></td>
<td><p>容認されるレベルを超えるエコーが検出された理由。(通信のエコーとは音の反響のことで、井戸の底に向かって叫んだときに聞こえるのと同じ現象です)。次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>なし</p>
</dd>
<dt><span></span></dt>
<dd><p>誤ったタイムスタンプ</p>
</dd>
<dt><span></span></dt>
<dd><p>AEC 後のエコー (アコーステック エコー キャンセレーション)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (Adaptive Nonlinear Processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (Dynamic Nonlinear Processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>マイクのクリッピング</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p>[ <strong>通話の種類</strong> ]</p></td>
<td><p>行われた通話の種類を示します。次のいずれかの値を選択します。</p>
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
<td><p>[ <strong>アクセスの種類</strong> ]</p></td>
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
<td><p>[ <strong>ネットワークの種類</strong> ]</p></td>
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
<td><p>[ <strong>VPN</strong> ]</p></td>
<td><p>通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>[すべて]</p>
</dd>
<dt><span></span></dt>
<dd><p>[VPN]</p>
</dd>
<dt><span></span></dt>
<dd><p>非 VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p>[ <strong>デバイスの種類</strong> ]</p></td>
<td><p>デバイスの種類を示します。次のいずれかを選択します。</p>
<dl>
<dt><span></span></dt>
<dd><p>キャプチャ デバイス</p>
</dd>
<dt><span></span></dt>
<dd><p>レンダー デバイス</p>
</dd>
<dt><span></span></dt>
<dd><p>キャプチャ/レンダー デバイスのペア</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>[ <strong>デバイス名</strong> ]</p></td>
<td><p>キャプチャまたはレンダー デバイスの名前。デバイス名の全体または一部を指定できます。たとえば、Microphone (Microsoft LifeCam VX-1000.) というデバイスを検索する場合には、次のように名前全体を指定できます。</p>
<p>Microphone (Microsoft LifeCam VX-1000.)</p>
<p>または、名前の一部のみを指定することもできます。次に例を示します。</p>
<p>LifeCam</p>
<p>上のフィルターでは、名前のどこかに文字列 &quot;LifeCam&quot; が含まれているデバイスがすべて返ります。</p></td>
</tr>
</tbody>
</table>


## 指標

次の表に、デバイス レポートで提供される情報を示します。

### デバイス レポートの指標

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
<td><p>[ <strong>キャプチャ デバイス</strong> ]</p></td>
<td><p>○</p></td>
<td><p>音声の送信に使用されたデバイス (たとえばマイクや Web カメラ)。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>レンダー デバイス</strong> ]</p></td>
<td><p>○</p></td>
<td><p>音声の受信に使用されたデバイス (たとえばヘッドセットやスピーカー)。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>通話ボリューム</strong> ]</p></td>
<td><p>○</p></td>
<td><p>発信された通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>低品質通話のパーセンテージ</strong> ]</p></td>
<td><p>○</p></td>
<td><p>&quot;低品質&quot; として分類された通話のパーセンテージ。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>一意なユーザー</strong> ]</p></td>
<td><p>○</p></td>
<td><p>デバイスを使用した一意なユーザーの数。同じユーザーがデバイスを 13 回使用した場合でも、デバイスを 1 回のみ使用したユーザーと同じように、1 人の一意なユーザーとしてカウントされます。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>音声切り替え時間の比率</strong> ]</p></td>
<td><p>○</p></td>
<td><p>エコーを防ぐために半二重モードでの実行が必要になった通話の比率。半二重モードでは、トランシーバーで会話するときと同じように、通信は一方向ずつでのみ行えます。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>動作していないマイクの比率</strong> ]</p></td>
<td><p>○</p></td>
<td><p>キャプチャ デバイスが容認可能なレベルで機能していなかった通話の比率。この値が大きい場合、通話品質の問題の主な原因は、キャプチャ デバイスが想定どおりに機能しなかったことにあります。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>動作していないスピーカーの比率</strong> ]</p></td>
<td><p>○</p></td>
<td><p>レンダー デバイスが容認可能なレベルで機能していなかった通話の比率。この値が大きい場合、通話品質の問題の主な原因は、レンダー デバイスが想定どおりに機能しなかったことにあります。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>音声切り替えが発生した通話 (%)</strong> ]</p></td>
<td><p>○</p></td>
<td><p>半二重モードへの移行が必要になった通話全体のパーセンテージ。半二重モードでは、トランシーバーで会話するときと同じように、通信は一方向ずつでのみ行えます。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>エコー マイク (%)</strong> ]</p></td>
<td><p>○</p></td>
<td><p>マイク キャプチャ ストリームでエコーが検出される時間の割合です。通常、ヘッドセットやハンドセットでは値が小さくなり、スピーカー フォンやスタンドアロンのスピーカーでは値が大きくなります。オンボードのアコーステック エコー キャンセレーションをサポートしているデバイスでの高い値は、エコー リークを示します。その他のデバイスでは、この指標をデバイス品質の評価に使用しないでください。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>エコー送信 (%)</strong> ]</p></td>
<td><p>○</p></td>
<td><p>他のユーザーに送信されたエコーのパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>エコーが発生した通話 (%)</strong> ]</p></td>
<td><p>○</p></td>
<td><p>容認可能なレベルを超えるエコーが発生した通話のパーセンテージ。</p>
<p></p></td>
</tr>
</tbody>
</table>

