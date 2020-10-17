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
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="bb3e6-103">Lync Server 2013 で場所データベースを設定する</span><span class="sxs-lookup"><span data-stu-id="bb3e6-103">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb3e6-104">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="bb3e6-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="bb3e6-105">ネットワーク内のクライアントを自動的に検索するには、まず、場所データベースにネットワークのアドレスマップを設定します。これに *より、ネットワーク*要素は、(つまり、ストリートの) 住所にマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-105">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="bb3e6-106">サブネット、ワイヤレスアクセスポイント、スイッチ、およびポートを使用して、wiremap を定義できます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-106">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="bb3e6-107">住所は場所データベースに個別に追加することも、次の表に示す列形式を含む CSV ファイルを使用して一括で追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-107">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="bb3e6-108">緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、各場所の [ **CompanyName** ] フィールドに ELIN を含めます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-108">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="bb3e6-109">各場所に複数の ELINs を含めることができます。それぞれはセミコロンで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-109">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb3e6-110">Network 要素</span><span class="sxs-lookup"><span data-stu-id="bb3e6-110">Network Element</span></span></th>
<th><span data-ttu-id="bb3e6-111">必要な列</span><span class="sxs-lookup"><span data-stu-id="bb3e6-111">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb3e6-112"><strong>ワイヤレスアクセスポイント</strong></span><span class="sxs-lookup"><span data-stu-id="bb3e6-112"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="bb3e6-113">&lt;BSSID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; predirectional &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="bb3e6-113">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="bb3e6-114">... &lt;StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; postdirectional &gt; 、 &lt; City &gt; 、 &lt; 都道府県 &gt; 、 &lt; 郵便 &gt; &lt; 番号、国&gt;</span><span class="sxs-lookup"><span data-stu-id="bb3e6-114">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb3e6-115"><strong>Subnet</strong></span><span class="sxs-lookup"><span data-stu-id="bb3e6-115"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="bb3e6-116">&lt;Subnet &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; predirectional &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="bb3e6-116">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="bb3e6-117">... &lt;StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; postdirectional &gt; 、 &lt; City &gt; 、 &lt; 都道府県 &gt; 、 &lt; 郵便 &gt; &lt; 番号、国&gt;</span><span class="sxs-lookup"><span data-stu-id="bb3e6-117">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb3e6-118"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="bb3e6-118"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="bb3e6-119">&lt;ChPortIDSubType Sid &gt; 、 &lt; &gt; 、 &lt; PortID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="bb3e6-119">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="bb3e6-120">... &lt;PreDirectional &gt; 、 &lt; StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; postdirectional &gt; 、 &lt; City &gt; 、 &lt; 都道府県 &gt; 、 &lt; 郵便 &gt; &lt; 番号、国&gt;</span><span class="sxs-lookup"><span data-stu-id="bb3e6-120">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb3e6-121"><strong>スイッチ</strong></span><span class="sxs-lookup"><span data-stu-id="bb3e6-121"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="bb3e6-122">&lt;ChHouseNumber Sid &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; predirectional &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="bb3e6-122">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="bb3e6-123">... &lt;StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; postdirectional &gt; 、 &lt; City &gt; 、 &lt; 都道府県 &gt; 、 &lt; 郵便 &gt; &lt; 番号、国&gt;</span><span class="sxs-lookup"><span data-stu-id="bb3e6-123">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bb3e6-124">場所データベースにデータを設定せず、場所ポリシーで **必要な場所** が **[はい]** または [ **免責事項**] に設定されている場合、クライアントはユーザーに手動で場所を入力するように求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-124">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="bb3e6-125">場所データベースの設定の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-125">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="bb3e6-126">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-126">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="bb3e6-127">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-127">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="bb3e6-128">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="bb3e6-128">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="bb3e6-129">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-129">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="bb3e6-130">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-130">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="bb3e6-131">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-131">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="bb3e6-132">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-132">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="bb3e6-133">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-133">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="bb3e6-134">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-134">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="bb3e6-135">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-135">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="bb3e6-136">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-136">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="bb3e6-137">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="bb3e6-137">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="bb3e6-138">場所データベースにネットワーク要素を追加するには</span><span class="sxs-lookup"><span data-stu-id="bb3e6-138">To add network elements to the location database</span></span>

1.  <span data-ttu-id="bb3e6-139">次のコマンドレットを実行して、サブネットの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-139">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="bb3e6-140">ELIN ゲートウェイの場合は、ELIN を CompanyName フィールドに配置します。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-140">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="bb3e6-141">複数の ELIN を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-141">You can include more than one ELIN.</span></span> <span data-ttu-id="bb3e6-142">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-142">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="bb3e6-143">または、次のコマンドレットを実行して、"subnets.csv" という名前のファイルを使用して、サブネットの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-143">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="bb3e6-144">次のコマンドレットを実行して、ワイヤレスの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-144">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="bb3e6-145">または、次のコマンドレットを実行して、"waps.csv" という名前のファイルを使用して、ワイヤレスの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-145">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="bb3e6-146">次のコマンドレットを実行して、スイッチの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-146">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="bb3e6-147">または、次のコマンドレットを実行して、"switches.csv" という名前のファイルを使用して、スイッチの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-147">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="bb3e6-148">次のコマンドレットを実行して、ポートの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-148">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="bb3e6-149">PortIDSubType の既定値は、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-149">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="bb3e6-150">InterfaceAlias または InterfaceName に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-150">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="bb3e6-151">または、次のコマンドレットを実行して、"ports.csv" という名前のファイルを使用して、ポートの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb3e6-151">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

