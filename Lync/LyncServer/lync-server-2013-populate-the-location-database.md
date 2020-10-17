---
title: 'Lync Server 2013: 場所データベースの設定'
description: 'Lync Server 2013: 場所データベースにデータを設定します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cf3204795ae2c4f8248517b84d7a5ac1bad0d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543173"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a>Lync Server 2013 で場所データベースを設定する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

ネットワーク内のクライアントを自動的に検索するには、まず、場所データベースにネットワークのアドレスマップを設定します。これに *より、ネットワーク*要素は、(つまり、ストリートの) 住所にマッピングされます。 サブネット、ワイヤレスアクセスポイント、スイッチ、およびポートを使用して、wiremap を定義できます。

住所は場所データベースに個別に追加することも、次の表に示す列形式を含む CSV ファイルを使用して一括で追加することもできます。

緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、各場所の [ **CompanyName** ] フィールドに ELIN を含めます。 各場所に複数の ELINs を含めることができます。それぞれはセミコロンで区切って指定します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Network 要素</th>
<th>必要な列</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ワイヤレスアクセスポイント</strong></p></td>
<td><p>&lt;BSSID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; predirectional &gt; ,...</p>
<p>... &lt;StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; postdirectional &gt; 、 &lt; City &gt; 、 &lt; 都道府県 &gt; 、 &lt; 郵便 &gt; &lt; 番号、国&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnet</strong></p></td>
<td><p>&lt;Subnet &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; predirectional &gt; ,...</p>
<p>... &lt;StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; postdirectional &gt; 、 &lt; City &gt; 、 &lt; 都道府県 &gt; 、 &lt; 郵便 &gt; &lt; 番号、国&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChPortIDSubType Sid &gt; 、 &lt; &gt; 、 &lt; PortID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; ,...</p>
<p>... &lt;PreDirectional &gt; 、 &lt; StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; postdirectional &gt; 、 &lt; City &gt; 、 &lt; 都道府県 &gt; 、 &lt; 郵便 &gt; &lt; 番号、国&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>スイッチ</strong></p></td>
<td><p>&lt;ChHouseNumber Sid &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; predirectional &gt; ,...</p>
<p>... &lt;StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; postdirectional &gt; 、 &lt; City &gt; 、 &lt; 都道府県 &gt; 、 &lt; 郵便 &gt; &lt; 番号、国&gt;</p></td>
</tr>
</tbody>
</table>


場所データベースにデータを設定せず、場所ポリシーで **必要な場所** が **[はい]** または [ **免責事項**] に設定されている場合、クライアントはユーザーに手動で場所を入力するように求めるメッセージを表示します。

場所データベースの設定の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - **CsLisSubnet**

  - **CsLisSubnet**

  - Remove-CsLisSubnet

  - **CsLisWirelessAccessPoint**

  - **CsLisWirelessAccessPoint**

  - **CsLisWirelessAccessPoint**

  - **CsLisSwitch**

  - **CsLisSwitch**

  - **CsLisSwitch**

  - **CsLisPort**

  - **CsLisPort**

  - **CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>場所データベースにネットワーク要素を追加するには

1.  次のコマンドレットを実行して、サブネットの場所を場所データベースに追加します。
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    ELIN ゲートウェイの場合は、ELIN を CompanyName フィールドに配置します。 複数の ELIN を含めることができます。 以下に例を示します。
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    または、次のコマンドレットを実行して、"subnets.csv" という名前のファイルを使用して、サブネットの場所を一括で更新することもできます。
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  次のコマンドレットを実行して、ワイヤレスの場所を場所データベースに追加します。
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    または、次のコマンドレットを実行して、"waps.csv" という名前のファイルを使用して、ワイヤレスの場所を一括で更新することもできます。
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  次のコマンドレットを実行して、スイッチの場所を場所データベースに追加します。
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    または、次のコマンドレットを実行して、"switches.csv" という名前のファイルを使用して、スイッチの場所を一括で更新することもできます。
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  次のコマンドレットを実行して、ポートの場所を場所データベースに追加します。
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    PortIDSubType の既定値は、割り当てられています。 InterfaceAlias または InterfaceName に設定することもできます。
    
    または、次のコマンドレットを実行して、"ports.csv" という名前のファイルを使用して、ポートの場所を一括で更新することもできます。
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

