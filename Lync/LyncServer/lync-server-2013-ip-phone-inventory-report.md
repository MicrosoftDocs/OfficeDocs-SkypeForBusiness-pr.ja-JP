---
title: 'Lync Server 2013: IP 電話インベントリレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5566f5e38608d2802c8ad699e3599f70c87be4e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Lync Server 2013 の IP 電話インベントリレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-12_

IP 電話インベントリ レポートは、組織で現在使われている IP 電話に関する情報をレポートします。IP インベントリ レポートには、指定したレポート期間に実際に使用された IP 電話の詳細な一覧が含まれます。このレポートを使用すると、たとえば、交換する必要がある古い電話機が使用されていないかどうかや、ほとんど使用されていない高価な電話機がないかどうかを調べることができます。この種の情報は、新しい電話機を購入したり既存の電話機を割り当てし直したりする際にとても役に立ちます (たとえば、ほとんど使用しないユーザーに割り当てられている高価な電話機を、電話を多用するユーザーの電話機と交換することができます)。

このレポートでは、実際のインベントリレポートとして使用されるときにいくつかの制限があることに注意してください。 1つの目的として、IP 電話レポートには、指定された期間中に Lync Server にログオンしたすべての電話の一覧が表示されます。これは、最終ログオン時刻で並べ替えられます。 電話が指定された期間中にログオンしなかった場合は、インベントリレポートに一覧表示されません。 これには、指定された期間中にログオンした後にログオンした電話機が含まれます。 たとえば、2012年7月のすべての電話番号を参照したいとします。 また、複数の電話が2012年6月30日に Lync Server にログオンしていて、7月1日の時点でまだログオンしていたとします。 これらの電話は7月1日のインベントリレポートには表示されません。

また、このインベントリ レポートには、既に組織で使用されていない電話機が含まれる可能性もあります。たとえば、2012 年 7 月 1 日にシステムにログオンした Fabrikam の電話機が、その 5 日後にすべて Contoso の新しいモデルに置き換えられた場合、それらの Fabrikam の電話機は、7 月中にシステムにログオンしたため "インベントリ" レポートに含まれます。

さらに、IP 電話インベントリ レポートには、電話機の機種別の集計は含まれません。たとえば、組織で Polycom CX600 を 105 台使用している場合、このレポートには、その電話機が 105 台あるという情報は含まれません。Polycom Cx600 のエントリが 105 件含まれるだけです。その数を調べるには、それらを手動で数えるしかありません。

<div>


> [!WARNING]  
> あるいは、データをエクスポートして、Microsoft Excel または Windows PowerShell で数を調べます。



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>IP 電話インベントリ レポートへのアクセス

IP 電話インベントリ レポートは、[監視レポート] ホーム ページからアクセスします。[ユーザー URI] 指標をクリックすると、そのユーザーのユーザー アクティビティ レポートにアクセスできます。ピアツーピア通話の [最後のアクティビティ] 指標をクリックすると、ピアツーピア セッション詳細レポートが表示されます。会議の同じ指標をクリックすると、会議詳細レポートが表示されます。

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>IP 電話インベントリ レポートの活用

1つの特定の種類の電話 (「ユーザーが Polycom CX600 電話を使用する頻度」など) の利用状況に関する情報のみが必要な場合は、その特定の種類の電話にフィルターを適用することによって、その情報を IP 電話インベントリレポートから直接取得できます。 ただし、すべての電話の概要情報 (Polycom CX600 を使用しているユーザーの数、LG-NORTEL の IP8540 など) を使用する場合は、そのデータをエクスポートして、別のアプリケーション (Windows PowerShell など) を使用してその種類のを実行する必要があります。analysis. たとえば、データをコンマ区切り値ファイル (\\C: data\\IP\_Phone\_Inventory\_Report .csv) にエクスポートするとします。 その場合は、次の2つのコマンドを使用して、すべての電話の概要データを提供できます。

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

これにより、次のようなデータが返されます。

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

同様に、次の 2 つのコマンドを使用すると、システムにログオンしたが電話をかけるために使用されていない電話機を調べることができます ("Last activity" メトリックの値が空白になっています。これは、最後のアクティビティがないことを表します)。

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

これにより、使用されていない電話機ごとに次のようなデータが返されます。

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

IP 電話インベントリレポートを使用するもう1つの興味深い方法は次のとおりです。 IP 電話の MAC アドレスを持っている場合は、[MAC アドレス] テキストボックスにそのアドレスを入力するだけで、その電話を最後に使用したユーザーを調べることができます。 その後、IP 電話インベントリレポートによって、その電話で最後にログオンしたユーザーの SIP アドレスが報告されます。 または、ユーザーの SIP アドレス ([ユーザー URI プレフィックス] ボックス) を入力して、そのユーザーが使用していたすべての電話を検索することもできます。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、IP 電話インベントリでは、特定の会社で製造された電話だけを表示したり、それらの電話の特定のバージョンだけを表示したりすることができます。また、データをグループ化する方法を選択することもできます。この場合は、登録情報が、時間、日、週、または月を基準にグループ化されます。

次の表に、IP 電話インベントリ レポートで使用できるフィルターを示します。

### <a name="ip-phone-inventory-report-filters"></a>IP 電話インベントリ レポートのフィルター

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
<p>7/7/2012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/7/2012 13:00</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>週は、常に日曜日から土曜日までです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>製造</strong></p></td>
<td><p>IP 電話を製造した会社の名前。このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ハードウェア バージョン</strong>]</p></td>
<td><p>IP 電話のバージョン番号。製造元とハードウェアバージョンフィルターを使用すると、特定の種類の電話を一意に識別することができます。 このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ユーザー エージェント</strong>]</p></td>
<td><p>IP 電話で使われているソフトウェアの識別子。このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>MAC アドレス</strong>]</p></td>
<td><p>IP 電話のネットワーク インターフェイスの一意の識別子。メディア アクセス制御 (MAC) アドレスは、通常、電話の製造時に割り当てられ、デバイス ハードウェアに組み込まれます。</p>
<p>特定の MAC アドレスに関係するレコードを検索するには、そのアドレスを入力します。次に例を示します。</p>
<p>00-08-5D-16-16-48</p>
<p>アドレスの全体を入力しなければなりません。アドレスの一部 (たとえば、00-08-5D) を入力してもデータは返されません。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>この日数より前の最後のアクティビティ</strong>]</p></td>
<td><p>次のいずれかの値を選択します。</p>
<ul>
<li><p>いずれ</p></li>
<li><p>10 </p></li>
<li><p>1280</p></li>
<li><p>31</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>[<strong>この日数より前の最後のログオフ時刻</strong>]</p></td>
<td><p>次のいずれかの値を選択します。</p>
<ul>
<li><p>いずれ</p></li>
<li><p>10 </p></li>
<li><p>1280</p></li>
<li><p>31</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>[<strong>ユーザー URI プレフィックス</strong>]</p></td>
<td><p>IP 電話を使用したユーザーの SIP アドレス。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、IP 電話インベントリ レポートで提供される情報を示します。

### <a name="ip-phone-inventory-report-metrics"></a>IP 電話インベントリ レポートの指標

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
<td><p><strong>製造</strong></p></td>
<td><p>はい</p></td>
<td><p>IP 電話を製造した会社の名前。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ハードウェア バージョン</strong>]</p></td>
<td><p>はい</p></td>
<td><p>IP 電話のバージョン番号。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>MAC アドレス</strong>]</p></td>
<td><p>はい</p></td>
<td><p>IP 電話のネットワーク インターフェイスの一意の識別子。MAC アドレスは、通常、電話の製造時に割り当てられ、デバイス ハードウェアに組み込まれます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ユーザー URI</strong>]</p></td>
<td><p>はい</p></td>
<td><p>IP 電話を使用したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ユーザー エージェント</strong>]</p></td>
<td><p>はい</p></td>
<td><p>IP 電話で使われているソフトウェアの識別子。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>最後にログオンした時刻</strong>]</p></td>
<td><p>はい</p></td>
<td><p>IP 電話が Lync Server に最後にログオンした日付と時刻。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>最後にログオフした時刻</strong>]</p></td>
<td><p>はい</p></td>
<td><p>IP 電話が Lync Server から前回ログオフした日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>最後のアクティビティ</strong>]</p></td>
<td><p>はい</p></td>
<td><p>IP 電話が最後に使われた日時。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

