---
title: 'Lync Server 2013: 失敗の配布レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06481be824f6c51975431aeea2efe27e41eadabc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a>Lync Server 2013 でのエラー配布レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-21_

エラー分布レポートは、問題の発生したセッションを以下のカテゴリに分類します。

  - トップの診断理由

  - トップのモダリティ

  - トップのプール

  - トップのソース

  - トップのコンポーネント

  - トップの発信元ユーザー

  - トップの発信先ユーザー

  - 送信元ユーザー エージェント

これらのカテゴリを使用して、どこに問題が発生しているか、場合によっては、問題が発生している理由を正確に確認できます。たとえば特定の日に、242 個のオーディオ/ビデオ セッションの障害が記録されたとします。エラー分布レポートを調べてみると、これらの問題の発生したセッションのうち、237 個が Dublin プールで発生しているかもしれません。これらの問題の背後にある原因を調べて診断するには、このような情報が役に立ちます。[**トップのプール**] カテゴリの下の Dublin プールをクリックすると、そのプールのエラー分布レポートのみが表示されます。次に Dublin プールでこれほど多くの問題が発生している理由の分析を開始できます。

<div>

## <a name="viewing-the-failure-distribution-report"></a>エラー分布レポートを表示する

以下の任意のレポートで、[**予期されるエラー ボリューム**] または [**予期しないエラー ボリューム**] の指標をクリックすると、エラー分布レポートにアクセスできます。

  - [Lync Server 2013 の上位エラーレポート](lync-server-2013-top-failures-report.md)

  - [Lync Server 2013 での会議の診断レポート](lync-server-2013-conference-diagnostic-report.md)

  - [Lync Server 2013 のピアツーピアアクティビティ診断レポート](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

エラー配布レポートでは、次のいずれかの指標をクリックして、 [Lync Server 2013 でエラー一覧レポート](lync-server-2013-failure-list-report.md)を表示できます。

  - トップの診断理由 (セッション)

  - トップのモダリティ (セッション)

  - トップのプール (セッション)

  - トップのソース (セッション)

  - トップのコンポーネント (セッション)

  - トップの発信元ユーザー (セッション)

  - トップの発信先ユーザー (セッション)

  - トップの発信元ユーザー エージェント (セッション)

</div>

<div>

## <a name="using-the-failure-distribution-report"></a>エラー分布レポートを使用する

モニターの大きさと画面解像度によっては、エラー分布レポートを画面上で表示するとき、表示されるデータの一部が切り捨てられることがあります。これは特に、ユーザー エージェントのような非常に長いラベルを持つことがある指標で発生します。たとえば、"UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) " のような名前のユーザー エージェントは、以下のように一部分のみが画面上に表示されることがあります。

UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...

この場合、切り捨てられた値の上にマウス ポインターを置くだけでラベル全体を表示できます。

エラー分布レポートを使用してフィルター処理できる、役立つ指標の 1 つが診断 ID です。さまざまなレポートで同じ診断 ID が表示される場合、エラー分布レポートでその ID をフィルター処理して、問題の発生したセッション中に、その ID が報告された正確な場所と頻度について非常に詳細な情報を得られます。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、エラー分布レポートを使用すると、動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などにフィルターを適用できます。また、失敗した各セッションに添付される診断 ID によってフィルターを適用することもできます。

次の表に、エラー分布レポートで使用できるフィルターを示します。

### <a name="failure-distribution-report-filters"></a>エラー分布レポートのフィルター

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
<td><p><strong>プール</strong></p></td>
<td><p>レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[動作状況の種類]</strong></p></td>
<td><p>フィルターを適用する動作状況の種類。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>ピアツーピア</p></li>
<li><p>電話会議</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション カテゴリ]</strong></p></td>
<td><p>問題のアクティビティが成功したか失敗したかを示します。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>成功</p></li>
<li><p>予期されたエラー</p></li>
<li><p>予期しないエラー</p></li>
</ul>
<p>&quot;予期される&quot;エラーは、発生する可能性のあるエラーです。 たとえば、ユーザーが応答不可のステータスを設定した場合、そのユーザーへの呼び出しはエラーとなることが予期されます。 &quot;予期しない&quot;エラーとは、正常に動作していると思われるエラーです。 たとえば、発信者が保留にされたときに、通話が終了してはなりません。 そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[診断 ID]</strong></p></td>
<td><p>SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が発生したセッションについてのみ報告されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a>トップの診断理由の指標

次の表に、最も報告される頻度が高い診断 ID に基づいて、エラー分布レポートで提供される情報を示します。

### <a name="metrics-for-top-diagnostic-reasons"></a>トップの診断理由の指標

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
<td><p><strong>[ランク]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>診断 ID に基づく、失敗したセッションの相対的なランク付け。診断 ID は、エラーのトラブルシューティングに役立つ情報の得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</p></td>
</tr>
<tr class="even">
<td><p><strong>[トップの診断理由]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションで生成される診断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>指定された診断 ID が生成された、失敗したセッションの総数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a>トップのモダリティの指標

次の表に、最もエラーが発生したセッション モダリティに基づいて、エラー分布レポートで提供される情報を示します。

### <a name="metrics-for-top-modalities"></a>トップのモダリティの指標

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
<td><p><strong>[ランク]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションの種類 (たとえば、音声ビデオ会議、ピアツーピアのファイル送信セッション) に基づく、失敗したセッションの相対的なランク付け。</p></td>
</tr>
<tr class="even">
<td><p><strong>[トップのモダリティ]</strong></p></td>
<td><p>不可</p></td>
<td><p>セッションの種類。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション]</strong></p></td>
<td><p>不可</p></td>
<td><p>指定されたモダリティが含まれる失敗したセッションの総数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a>トップのプールの指標

次の表に、最もエラーが発生したプールに基づいて、エラー分布レポートで提供される情報を示します。

### <a name="metrics-for-top-pools"></a>トップのプールの指標

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
<td><p><strong>[ランク]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションが実行されたレジストラープールまたはエッジサーバーに基づいて、失敗したセッションの相対的なランクを指定します。</p></td>
</tr>
<tr class="even">
<td><p><strong>[トップのプール]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>レジストラープールまたはエッジサーバーの名前。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>登録プールまたはエッジサーバーあたりの失敗したセッションの合計数です。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a>トップのソースの指標

次の表に、最もエラーが発生したコンピューターに基づいて、エラー分布レポートで提供される情報を示します。

### <a name="metrics-for-top-sources"></a>トップのソースの指標

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
<td><p><strong>[ランク]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>コンピューターごとの失敗したセッションの相対的なランク付け。</p></td>
</tr>
<tr class="even">
<td><p><strong>[トップのソース]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>失敗したセッションに含まれるコンピューターの名前。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>コンピューターごとの失敗したセッションの総数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a>トップ コンポーネントの指標

次の表に、障害が発生した Microsoft Lync Server 2010 コンポーネントに基づいたエラー分散レポートに記載されている情報を示します。

### <a name="metrics-for-top-components"></a>トップのコンポーネントの指標

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
<td><p><strong>[ランク]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>Lync Server 2010 コンポーネント (ExumRouting、GroupChat、MediationServer など) に基づく、失敗したセッションの相対的なランク。</p></td>
</tr>
<tr class="even">
<td><p><strong>[トップのコンポーネント]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>失敗したセッションに含まれるコンポーネントの名前。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>コンポーネントごとの失敗したセッションの総数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a>トップの発信元ユーザーの指標

次の表に、他のユーザーを呼び出したときに最もエラーが発生したユーザー ("発信元" ユーザーと呼ばれる) に基づいて、エラー分布レポートで提供される情報を示します。

### <a name="metrics-for-top-from-users"></a>トップの発信元ユーザーの指標

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
<td><p><strong>[ランク]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションに招待されたユーザーに基づく、失敗したセッションの相対的なランク付け。</p></td>
</tr>
<tr class="even">
<td><p><strong>[トップの発信元ユーザー]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションに招待されたユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ユーザーごとの失敗したセッションの総数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a>トップの発信先ユーザーの指標

次の表に、ユーザーが他のユーザーを呼び出したときに最もエラーが発生したユーザー ("発信先" ユーザーと呼ばれる) に基づいて、エラー分布レポートで提供される情報を示します。


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
<td><p><strong>[ランク]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションを開始したユーザーに基づく、失敗したセッションの相対的なランク付け。</p></td>
</tr>
<tr class="even">
<td><p><strong>[トップの発信先ユーザー]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションを開始したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ユーザーごとの失敗したセッションの総数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a>トップ ユーザー エージェントの指標

次の表に、最もエラーが発生したエンドポイント ソフトウェアに基づいて、エラー分布レポートで提供される情報を示します。

### <a name="metrics-for-top-user-agents"></a>トップ ユーザー エージェントの指標

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
<td><p><strong>[ランク]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションに含まれるユーザー エージェント (ソフトウェア) に基づく、失敗したセッションの相対的なランク付け。例: RTCC/4.0.0.0 Inbound Routing/4.0.0.0。</p></td>
</tr>
<tr class="even">
<td><p><strong>[トップ ユーザー エージェント]</strong></p></td>
<td><p>不可</p></td>
<td><p>失敗したセッションに含まれるユーザー エージェントの名前。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[セッション]</strong></p></td>
<td><p>不可</p></td>
<td><p>ユーザー エージェントごとの失敗したセッションの総数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

