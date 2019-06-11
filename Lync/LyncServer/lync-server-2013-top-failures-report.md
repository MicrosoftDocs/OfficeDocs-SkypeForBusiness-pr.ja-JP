---
title: 'Lync Server 2013: 上位エラーレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 094f5034951e20d48b05c8772698ae2983492509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a>Lync Server 2013 の上位エラーレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

トップ エラー レポートは、最もよく報告されているエラーに関する情報と、そのエラーの推移を示します。エラーは、次の 2 つのメトリックの組み合わせに基づいています。

  - **診断 ID**。SIP メッセージに添付された一意の識別子 (ms-diagnostics ヘッダーの形式)。診断 ID は、呼び出し関連のエラーのトラブルシューティングに役立つ情報を提供します。

  - **応答コード**。 応答コードは SIP 通信セッションで使用され、SIP 要求に応答します。 たとえば、Ken によって INVITE 要求が Pilar Ackerman に送信されたとします (つまり、Ken Myer が Pilar Ackerman を呼び出したとします)。 Pilar の回答がある場合、彼女の電話には応答コード 200 (OK) が送信され、Ken の電話では Pilar が応答したことが通知されます。 上位のエラーレポートには、通話の失敗に応じて送信された応答コードのみが含まれます。通話中に発行されたすべての応答コードは、Lync Server によって追跡されません。

このレポートでは、エラーが発生したセッションの合計数だけでなく、エラーの影響を受けた合計ユーザー数に関する情報も報告されます。

<div>

## <a name="accessing-the-top-failures-report"></a>トップ エラー レポートにアクセスする

トップ エラー レポートには、[監視レポート] ホーム ページからアクセスします。 報告されたセッションメトリックをクリックすると、 [Lync Server 2013 の [エラーの配布] レポート](lync-server-2013-failure-distribution-report.md)に移動します。

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>トップ エラー レポートを最大限に利用する

トップ エラー レポートは、一度に最大 5 つの診断 ID に基づいてフィルターできるという点で他とは異なります (通常は、一度の 1 つの項目 (1 つのユーザー SIP アドレスなど) でしかフィルターできません)。複数の診断 ID に基づいてフィルターするには、[診断 ID] ボックスに各 ID をコンマで区切って入力します (コンマの後ろに空白を挿入することもできます)。次に例を示します。

1011, 2412, 1033, 52116, 1008

このように指定すると、この 5 つの診断 ID の少なくとも 1 つを報告した通話エラーのみが表示されます。

応答コードの上にマウスを置くと、その応答コードについて説明するヒントが表示されます。たとえば、応答コード 486 の上にマウスを置くと、次のメッセージが表示されます。

ここはビジー状態

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、トップ エラー レポートを使用すると、取得したデータに動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などに基づいてフィルターを適用できます。また、エラーが発生したセッションに付属する SIP 応答コードによってフィルターを適用することもできます。データをグループ化する方法を選択することもできます。この場合、使用状況は、時間単位、日単位、週単位、または月単位でグループ化されます。

次の表に、トップ エラー レポートで使用できるフィルターを示します。

### <a name="top-failures-report-filters"></a>トップ エラー レポートのフィルター

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
<td><p><strong>[動作状況の種類]</strong></p></td>
<td><p>動作状況の種類。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>ピアツーピア</p></li>
<li><p>電話会議</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[モダリティ]</strong></p></td>
<td><p>この場合、唯一使用できるオプションは [<strong>すべて</strong>] です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[プール]</strong></p></td>
<td><p>レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[カテゴリ]</strong></p></td>
<td><p>発生したエラーの種類。次のいずれかを選択します。</p>
<ul>
<li><p>予期されたエラーと予期しないエラーの両方</p></li>
<li><p>予期しないエラー</p></li>
</ul>
<p>&quot;予期される&quot;エラーは、発生する可能性のあるエラーです。 たとえば、ユーザーが応答不可のステータスを設定した場合、そのユーザーへの呼び出しはエラーとなることが予期されます。 &quot;予期しない&quot;エラーとは、正常に動作していると思われるエラーです。 たとえば、発信者が保留にされたときに、通話が終了してはなりません。 そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[応答コード]</strong></p></td>
<td><p>会議が失敗したときに送信された SIP 応答コードです。次の例のように、応答コード全体を入力します。</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>[診断 ID]</strong></p></td>
<td><p>SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、トップ エラー レポートで提供される情報を示します。

### <a name="top-failures-report-metrics"></a>トップ エラー レポートの指標

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
<td><p>はい</p></td>
<td><p>報告されたセッションの数に基づく相対的なランク。</p></td>
</tr>
<tr class="even">
<td><p><strong>[報告されたセッション]</strong></p></td>
<td><p>はい</p></td>
<td><p>診断 ID と SIP 応答コードに基づく、失敗したセッションの総数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[影響を受けたユーザー]</strong></p></td>
<td><p>可</p></td>
<td><p>失敗したセッションの影響を受けたユーザーの総数。</p></td>
</tr>
<tr class="even">
<td><p><strong>[エラー情報]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>診断 ID、SIP 応答コード、セッションの失敗理由など、失敗の詳細情報。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[過去の傾向]</strong></p></td>
<td><p>不可</p></td>
<td><p>失敗したセッションの推移をグラフで示します。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

