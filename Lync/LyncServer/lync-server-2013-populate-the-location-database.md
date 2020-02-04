---
title: 'Lync Server 2013: 場所データベースを設定する'
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
ms.openlocfilehash: a93cee85afec1e3943af692d598d0d02ab678d58
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>Lync Server 2013 で位置情報データベースを設定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-17_

ネットワーク内のクライアントを自動で検出するために、まず、ネットワーク要素を正式な住所にマップする、ネットワークの*ワイヤマップ*を場所データベースに読み込む必要があります。ワイヤマップの定義には、サブネット、ワイヤレス アクセス ポイント、スイッチ、およびポートを使用できます。

住所は場所データベースに個別に追加することも、次の表に示す列形式を含む CSV ファイルを使用して一括で追加することもできます。

緊急位置識別番号 (ELIN) ゲートウェイを使用している場合、各場所の **[CompanyName]** フィールドに ELIN を含めます。各場所に複数の ELIN をセミコロンで区切って含めることができます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ネットワーク要素</th>
<th>必要な列</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ワイヤレス アクセス ポイント</strong></p></td>
<td><p>&lt;BSSID&gt;、&lt;説明&gt;、&lt;場所&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、&lt;predirectional&gt;,...</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;postdirectional&gt;、&lt;市区&gt;町村&lt;、&gt;都道府県&lt;、&gt;郵便&lt;番号、国&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnet</strong></p></td>
<td><p>&lt;サブ&gt;ネット&lt;、&gt;説明&lt;、&gt;場所&lt;、&gt;CompanyName&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix&lt;、predirectional&gt;,...</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;postdirectional&gt;、&lt;市区&gt;町村&lt;、&gt;都道府県&lt;、&gt;郵便&lt;番号、国&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>ポート</strong></p></td>
<td><p>&lt;ChPortIDSubType sid&gt;、&lt;&gt;、&lt;PortID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;,...</p>
<p>...&lt;Predirectional&gt;、&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;&gt;postdirectional&lt;市区町村&gt;、&lt;都道府県&gt;、&lt;郵便&gt;番号&lt;、国&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>スイッチ</strong></p></td>
<td><p>&lt;ChHouseNumber sid&gt;、&lt;説明&gt;、&lt;場所&gt;、&lt;CompanyName&gt;、&lt;&gt;、&lt;HouseNumberSuffix&gt;、&lt;predirectional&gt;,...</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;postdirectional&gt;、&lt;市区&gt;町村&lt;、&gt;都道府県&lt;、&gt;郵便&lt;番号、国&gt;</p></td>
</tr>
</tbody>
</table>


場所のデータベースに情報を読み込んでいない場合に、場所のポリシーの **[場所 (必須)]** を **[はい]** または **[免責事項]** に設定すると、クライアントから場所の情報を手動で入力するように指示されます。

場所データベースの設定の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - **Get-CsLisSubnet**

  - **Set-CsLisSubnet**

  - Remove-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Set-CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **Get-CsLisPort**

  - **Set-CsLisPort**

  - **Remove-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>ネットワーク要素を場所のデータベースに追加するには

1.  次のコマンドレットを実行して、サブネットの場所を場所データベースに追加します。
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    ELIN ゲートウェイでは、ELIN を CompanyName フィールドに入れます。複数の ELIN を含めることもできます。次に例を示します。
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    また、"subnets.csv" という名前のファイルを使用して、次のコマンドレットでサブネットの場所を一括で更新することができます。
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  次のコマンドレットを実行して、ワイヤレスの場所を場所データベースに追加します。
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    また、"waps.csv" という名前のファイルを使用して、次のコマンドレットでワイヤレスの場所を一括で更新することもできます。
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  次のコマンドレットを実行して、スイッチの場所を場所データベースに追加します。
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    また、"switches.csv" という名前のファイルを使用して、次のコマンドレットでスイッチの場所を一括で更新することもできます。
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  次のコマンドレットを実行して、ポートの場所を場所データベースに追加します。
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    PortIDSubType の既定値は、LocallyAssigned です。これを、InterfaceAlias または InterfaceName に設定することもできます。
    
    また、"ports.csv" という名前のファイルを使用して、次のコマンドレットでポートの場所を一括で更新することもできます。
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

