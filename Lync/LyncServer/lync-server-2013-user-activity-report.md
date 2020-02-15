---
title: 'Lync Server 2013: ユーザーアクティビティレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ad0297451c98851d156f088497db81345520b88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a>Lync Server 2013 のユーザーアクティビティレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-02-27_

ユーザー アクティビティ レポートは、特定の期間にユーザーによって実行されたピアツーピアおよび電話会議セッションの詳細な一覧を示します。多くの監視レポートとは異なり、ユーザー アクティビティ レポートは、各呼び出しを個別のユーザーに関連付けます。たとえば、ピアツーピアセッションでは、呼び出しを開始した人 (呼び出し元ユーザー) と呼び出しを受けた人 (呼び出し先ユーザー) の SIP URI が示されます。電話会議の情報を展開すると、すべての電話会議の参加者と、その電話会議における参加者の役割の一覧が表示されます。

ユーザー アクティビティ レポートは、"ヘルプ デスク" レポートと呼ばれることがあります。ヘルプデスク担当者が、特定のユーザーに関するセッション情報を取得するときによくこのレポートを利用するからです。個別のユーザーに対する、または個別のユーザーによる呼び出しは、[ユーザー URI プレフィックス] ボックスにユーザーの SIP URI を入力するだけでフィルターできます。

このようにすると、ユーザーアクティビティレポートは、指定された文字列で SIP URI が始まるすべてのユーザーに関する情報を返します。 たとえば、[URI] ボックスに「 **ken** 」と入力すると、ユーザーアクティビティレポートは**ken**を検索します。Myer@litwareinc.com。 ただし、次のユーザーも検索されます。

  - **ken**azi@litwareinc.com

  - **ken**burg@litwareinc.com

  - **Ken**。Sanchez@litwareinc.com

  - **Ken**nedy@litwareinc.com

Ken Myer の情報のみが返されるようにするには、検索ボックスに完全な URI (Ken.Myer@litwareinc.com) を入力するか、組織内の他のユーザーと個人を区別するために、少なくとも Ken の適切な種類の Ken の URI を入力します。 例:

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>ユーザー アクティビティ レポートにアクセスするには

ユーザー アクティビティ レポートには、[監視レポート] ホーム ページからアクセスします。 また、 [Lync Server 2013 の IP 電話インベントリレポート](lync-server-2013-ip-phone-inventory-report.md)でユーザー URI 指標をクリックして、ユーザーアクティビティレポートにアクセスすることもできます。 ユーザー アクティビティ レポートで [電話会議 URI] (電話会議の場合) をクリックすると、会議詳細レポートが表示されます。 同様に、ピアツーピア呼び出しの詳細指標をクリックすると、 [Lync Server 2013 のピアツーピアセッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)が表示されます。

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>ユーザーアクティビティレポートを最大限に活用する

ユーザーアクティビティレポートには多くの適切な情報がありますが、その情報を見つけるのが難しい場合があります。 たとえば、指定した期間中に組織内で発生するすべてのユーザーアクティビティが、ユーザーアクティビティレポートに含まれています。つまり、何らかの方法で Microsoft Lync Server 2013 を実際に使用したユーザーに関する情報をレポート内に埋め込むことができることを意味します。

<div>


> [!WARNING]  
> 技術的には、一部のユーザーアクティビティが記録になる可能性があります。 Lync Server は、すべての電話呼び出しに関する情報を保存しようとしていますが、その呼び出しについての情報がないと、データベースへの呼び出しが行われている可能性があります。 Lync Server は、非常に正確ですが、Lync Server 2013 がどのように使用されているかについては、必ずしもわかりません。 (つまり、すべての通話の100% が記録されるという保証はありません。 Lync Server の監視を課金システムとして使用してはならない理由について説明します)。<BR>また、監視レポートに表示できるのは最大でも 1,000 レコードです。これは、ユーザー アクティビティの量と作業時間によっては、データベースに実際に格納されたデータの一部がクエリでは返されない場合があることを意味します。



</div>

  - この期間内にシステムを実際に使用したのはどのユーザーか。

  - この期間内に最もアクティブだったのはどのユーザーか。

  - 通話数が最も多いユーザーが、最も多くのインスタント メッセージング セッションに参加しているユーザーでもあるかどうか。

このような情報を確認するには、監視レポートで取得されたデータを Excel スプレッドシートにエクスポートします。 次に、そのスプレッドシート/コンマ区切り値ファイルを使用して、ユーザー アクティビティ レポートのようなやり方でデータを分析します。 たとえば、レポートデータを Excel にエクスポートしてから、コンマ区切り値ファイルにエクスポートするとします。 その時点で、からデータをインポートできます。CSV ファイルを次のようなコマンドを使用して Windows PowerShell に渡します。

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

データがインポートされたら、簡単な Windows PowerShell コマンドを使用して質問に答えることができます。 たとえば、次のコマンドは、少なくとも 1 つのセッションで "呼び出し元" ユーザーとしての役割を果たす一意のユーザーの一覧を返します。

    $x | Group-Object "From user" | Select Name | Sort-Object Name

つまり、次のとおりです。

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

次のコマンドは、ユーザーが参加しているセッションの合計数に基づいて、一意のユーザーの一覧を表示します。

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

このコマンドは次のようなデータを返します。

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

次のコマンドは、報告されたセッションを、モダリティとしてオーディオが含まれるセッションに制限します。

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

レポートに表示されている診断 ID の上にマウスを置くと、その ID について説明するヒントが表示されます。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、ユーザー アクティビティ レポートを使用すると、取得したデータに動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などに基づいてフィルターを適用できます。また、ユーザーの SIP アドレスによってフィルターを適用することもできます (この場合、1 人のユーザーの動作状況を表示できます)。データをグループ化する方法を選択することもできます。この場合、使用状況は、時間単位、日単位、週単位、または月単位でグループ化されます。

次の表に、ユーザー アクティビティ レポートで使用できるフィルターを示します。

### <a name="user-activity-report-filters"></a>ユーザー アクティビティ レポートのフィルター

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
<td><p><strong>From</strong></p></td>
<td><p>時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</p>
<p>7/17/2012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/17/12012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/13/2012</p>
<p>週は、常に日曜日から土曜日までです。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/17/2012 1:00 PM</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/17/12012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/13/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>動作状況の種類</strong>]</p></td>
<td><p>動作状況の種類。次のいずれかを選択します。</p>
<ul>
<li><p>いずれ</p></li>
<li><p>ピアツーピア</p></li>
<li><p>室</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>モーダル</strong></p></td>
<td><p>利用可能なモダリティは、[アクティビティの種類の選択] によって異なります。 アクティビティの種類がピアツーピアの場合は、[IM] を選択できます。ファイル転送。アプリケーション共有。音声またはビデオをモダリティとして示します。</p>
<p>アクティビティの種類が [会議] の場合は、IM 電話会議を選択できます。Web 会議。アプリケーション共有。音声ビデオ会議または電話会議。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>セッション カテゴリ</strong>]</p></td>
<td><p>問題のアクティビティが成功したか失敗したかを示します。次のいずれかを選択します。</p>
<ul>
<li><p>いずれ</p></li>
<li><p>Success</p></li>
<li><p>[予期されたエラー]</p></li>
<li><p>[予期しないエラー]</p></li>
</ul>
<p>&quot;予期される&quot;エラーは、発生する可能性のあるエラーです。たとえば、ユーザーが自分の状態を [応答不可] に設定している場合、そのユーザーへの呼び出しが失敗することが予想されます。 &quot;予期しない&quot;エラーとは、正常なシステムとして表示されるエラーです。 たとえば、発信者が保留にされたときに、通話が終了してはなりません。 そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ユーザー URI プレフィックス</strong>]</p></td>
<td><p>ユーザーの SIP アドレス。たとえば、Ken Myer という名前のユーザーのレコードのみを表示するには、次のように、Ken Myer の SIP アドレスを入力する必要があります。</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>ピアツーピア セッションの指標

次の表に、ピアツーピア セッション (2 人の参加者だけで行うセッション) について、ユーザー アクティビティ レポートで提供される情報を示します。

### <a name="metrics-for-peer-to-peer-sessions"></a>ピアツーピア セッションの指標

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
<td><p><strong>詳細</strong></p></td>
<td><p>いいえ</p></td>
<td><p>この項目をクリックすると、選択されているセッションのピアツーピア セッション詳細レポートが表示されます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>移動元ユーザー</strong>]</p></td>
<td><p>はい</p></td>
<td><p>ピアツーピア セッションを開始したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>対象ユーザー</strong>]</p></td>
<td><p>はい</p></td>
<td><p>ピアツーピア セッションに参加したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p><strong>モダリティ</strong></p></td>
<td><p>はい</p></td>
<td><p>セッションで使用された通信の種類。たとえば、IM、音声、ファイル送信。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>招待時間</strong>]</p></td>
<td><p>はい</p></td>
<td><p>ピアツーピア セッションへの最初の招待が送信された日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>応答時間</strong>]</p></td>
<td><p>はい</p></td>
<td><p>&quot;ユーザーが&quot;セッションへの招待を受け入れた日時。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>終了時刻</strong>]</p></td>
<td><p>はい</p></td>
<td><p>ピアツーピア セッションが終了した日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>診断 ID</strong>]</p></td>
<td><p>はい</p></td>
<td><p>SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>電話会議セッションの指標

次の表に、電話会議セッション (3 人以上の参加者で行うセッション) について、ユーザー アクティビティ レポートで提供される情報を示します。

### <a name="metrics-for-conferencing-sessions"></a>電話会議セッションの指標

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
<td><p>[<strong>会議 URI</strong>]</p></td>
<td><p>はい</p></td>
<td><p>一意の電話会議 ID。 この項目をクリックすると、選択されているセッションの会議詳細レポートが表示されます。 この項目を展開すると、電話会議参加者に関する情報が表示されます。 詳細については&quot;、このトピックで&quot;後述する「電話会議の参加者の指標」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong></p></td>
<td><p>はい</p></td>
<td><p>会議を開催したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>はい</p></td>
<td><p>電話会議で使用されたエッジ サーバーの名前 (エッジ サーバーが使用された場合)。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>開始時刻</strong>]</p></td>
<td><p>はい</p></td>
<td><p>会議が開始された日時。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>終了時刻</strong>]</p></td>
<td><p>はい</p></td>
<td><p>会議が終了した日時。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a>電話会議参加者の指標

次の表に、各電話会議参加者についてユーザー アクティビティ レポートで提供される情報を示します。

### <a name="metrics-for-conference-participants"></a>電話会議参加者の指標

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
<td><p><strong>役割</strong></p></td>
<td><p>いいえ</p></td>
<td><p>電話会議におけるユーザーの役割 (発表者など)。</p></td>
</tr>
<tr class="even">
<td><p><strong>参加者</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>接続</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ネットワーク接続の種類。 たとえば&quot;、内部接続&quot;の場合は internal &quot;、ダイヤル&quot;インユーザーの場合は PSTN から。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>参加時間</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>ユーザーが電話会議に参加した日時。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>退場時間</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>ユーザーが電話会議から退場した日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>診断 ID</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

