---
title: 'Lync Server 2013: IP 電話のインベントリレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335b74b742f3b32437892e27f7db3ecadc5f3b3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Lync Server 2013 の IP 電話インベントリレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-12_

IP 電話在庫レポートは、組織で現在使われている IP 電話に関する情報をレポートします。このレポートには、指定したレポート期間に実際に使用された IP 電話の詳細な一覧が含まれます。このレポートを使用すると、たとえば、交換する必要がある以前の電話機が使用されていないかどうかや、ほとんど使用されていない高価な電話機がないかどうかを調べることができます。この種の情報は、新しい電話機を購入したり既存の電話機を割り当てし直したりする際にとても役に立ちます (たとえば、ほとんど使用しないユーザーに割り当てられている高価な電話機を、電話を多用するユーザーの電話機と交換することができます)。

このレポートは、実際のインベントリレポートとして使用されるときに、いくつかの制限があります。 1つの例として、[IP 電話] レポートには、指定された期間中に Lync Server にログオンしたすべての電話が一覧表示されます。これは、前回のログオン時間で並べ替えられます。 指定された期間中に電話がログオンしなかった場合は、[インベントリ] レポートには表示されません。 これには、期間が開始される前にログオンしていて、指定した期間内にログオンした電話が含まれます。 たとえば、2012年7月のすべての電話インベントリを確認する必要があるとします。 また、複数の電話が2012年6月30日に Lync Server にログオンしていて、まだ7月1日にログオンしたことがあるとします。 これらの電話は、7月1日のインベントリレポートには表示されません。

また、インベントリレポートには、組織で使用されなくなった電話が含まれている場合もあることに注意する必要があります。 たとえば、2012年7月1日にシステムにログオンしている Fabrikam の電話番号が複数あるとします。5日後に、組織がすべての Fabrikam 電話を削除して、新しい Contoso モデルに置き換えます。 Fabrikam の電話は、7月にシステムにログオンしたため、「インベントリ」レポートに引き続き表示されます。

さらに、IP 電話在庫レポートには、電話機の機種別の集計は含まれません。たとえば、組織で Polycom CX600 を 105 台使用している場合、このレポートには、その電話機が 105 台あるという情報は含まれません。Polycom Cx600 のエントリが 105 件含まれるだけです。その数を調べるには、それらを手動で数えるしかありません。

<div>


> [!WARNING]  
> あるいは、データをエクスポートして、Microsoft Excel または Windows PowerShell で数を調べます。



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>IP 電話在庫レポートへのアクセス

IP 電話在庫レポートは、[監視レポート] ホーム ページからアクセスします。[ユーザー URI] 指標をクリックすると、そのユーザーのユーザー アクティビティ レポートにアクセスできます。ピアツーピア通話の [最後のアクティビティ] 指標をクリックすると、ピアツーピア セッション詳細レポートが表示されます。会議の同じ指標をクリックすると、会議詳細レポートが表示されます。

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>IP 電話在庫レポートの活用

1つの特定の種類の電話の使用状況に関する情報のみが必要な場合 (たとえば、"Polycom CX600 携帯電話を使っているユーザーは何人ですか?" など)、その特定の種類の電話をフィルター処理して、その情報を IP 電話のインベントリレポートから直接取得できます。 ただし、すべての携帯電話の概要情報 (Polycom CX600 を使用しているユーザ数、LG-Nortel IP8540 などを使用しているユーザ数など) が必要な場合は、データをエクスポートして、別のアプリケーション (Windows PowerShell など) を使用してその種類の分析. たとえば、データをコンマ区切り値ファイル (\\C: data\\IP\_電話\_インベントリ\_レポート .csv) にエクスポートするとします。 その場合は、次の2つのコマンドを使用して、すべての電話の概要データを提供できます。

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

この結果、次のようなデータが返されます。

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

同様に、次の 2 つのコマンドを使用すると、システムにログオンしたが電話をかけるために使用されていない電話機を調べることができます ("Last activity (最後のアクティビティ)" という指標の値が空白になっています。これは、最後のアクティビティがないことを表します)。

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

この結果、使用されていない電話機ごとに次のようなデータが返されます。

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

IP 電話のインベントリレポートを使用するもう1つの興味深い方法は、IP 電話の MAC アドレスを使っている場合に、その電話を直前に使用したユーザーを確認するには、[MAC アドレス] ボックスにアドレスを入力します。 その後、IP 電話のインベントリレポートは、その電話で最後にログオンしたユーザーの SIP アドレスを報告します。 または、ユーザー SIP アドレス ([ユーザーの URI プレフィックス] ボックス) を入力して、そのユーザーが使用したすべての電話を検索することもできます。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。たとえば、IP 電話在庫では、特定の会社で製造された電話だけを表示したり、それらの電話の特定のバージョンだけを表示したりすることができます。また、データをグループ化する方法を選択することもできます。この場合は、登録情報が、時間、日、週、または月を基準にグループ化されます。

次の表に、IP 電話在庫レポートで使用できるフィルターを示します。

### <a name="ip-phone-inventory-report-filters"></a>IP 電話在庫レポートのフィルター

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
<td><p><strong>[製造元]</strong></p></td>
<td><p>IP 電話を製造した会社の名前。このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[ハードウェア バージョン]</strong></p></td>
<td><p>IP 電話のバージョン番号。メーカーとハードウェアのバージョンフィルターを使用すると、特定の種類の電話番号を一意に識別することができます。 このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[ユーザー エージェント]</strong></p></td>
<td><p>IP 電話で使われているソフトウェアの識別子。このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[MAC アドレス]</strong></p></td>
<td><p>IP 電話のネットワーク インターフェイスの一意の識別子。メディア アクセス制御 (MAC) アドレスは、通常、電話の製造時に割り当てられ、デバイス ハードウェアに組み込まれます。</p>
<p>特定の MAC アドレスに関係するレコードを検索するには、そのアドレスを入力します。次に例を示します。</p>
<p>00-08-5D-16-16-48</p>
<p>アドレスの全体を入力しなければなりません。アドレスの一部 (たとえば、00-08-5D) を入力してもデータは返されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[この日数より前の最後のアクティビティ]</strong></p></td>
<td><p>次のいずれかの値を選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>常用</p></li>
<li><p>超える</p></li>
<li><p>求める</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[この日数より前の最後のログオフ時刻]</strong></p></td>
<td><p>次のいずれかの値を選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>常用</p></li>
<li><p>超える</p></li>
<li><p>求める</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>[ユーザー URI プレフィックス]</strong></p></td>
<td><p>IP 電話を使用したユーザーの SIP アドレス。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、IP 電話在庫レポートで提供される情報を示します。

### <a name="ip-phone-inventory-report-metrics"></a>IP 電話在庫レポートの指標

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
<td><p><strong>[製造元]</strong></p></td>
<td><p>はい</p></td>
<td><p>IP 電話を製造した会社の名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>[ハードウェア バージョン]</strong></p></td>
<td><p>はい</p></td>
<td><p>IP 電話のバージョン番号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[MAC アドレス]</strong></p></td>
<td><p>はい</p></td>
<td><p>IP 電話のネットワーク インターフェイスの一意の識別子。MAC アドレスは、通常、電話の製造時に割り当てられ、デバイス ハードウェアに組み込まれます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[ユーザー URI]</strong></p></td>
<td><p>はい</p></td>
<td><p>IP 電話を使用したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[ユーザー エージェント]</strong></p></td>
<td><p>はい</p></td>
<td><p>IP 電話で使われているソフトウェアの識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>[最後にログオンした時刻]</strong></p></td>
<td><p>はい</p></td>
<td><p>IP 電話が前回 Lync Server にログオンした日付と時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[最後にログオフした時刻]</strong></p></td>
<td><p>はい</p></td>
<td><p>IP 電話が Lync Server から最後にログオフした日付と時刻です。</p></td>
</tr>
<tr class="even">
<td><p><strong>[最後のアクティビティ]</strong></p></td>
<td><p>可</p></td>
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

