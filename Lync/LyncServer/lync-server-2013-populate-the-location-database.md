---
title: 'Lync Server 2013: 場所データベースの設定'
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
ms.openlocfilehash: 0216cada44f2512e33a0b33b627ed9a6d6582cda
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="c5f33-102">Lync Server 2013 で場所データベースを設定する</span><span class="sxs-lookup"><span data-stu-id="c5f33-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5f33-103">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="c5f33-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="c5f33-104">ネットワーク内のクライアントを自動的に検索するには、まず、場所データベースにネットワークのアドレスマップを設定します。これに*より、ネットワーク*要素は、(つまり、ストリートの) 住所にマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-104">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="c5f33-105">サブネット、ワイヤレスアクセスポイント、スイッチ、およびポートを使用して、wiremap を定義できます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-105">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="c5f33-106">住所は場所データベースに個別に追加することも、次の表に示す列形式を含む CSV ファイルを使用して一括で追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="c5f33-107">緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、各場所の [ **CompanyName** ] フィールドに ELIN を含めます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-107">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="c5f33-108">各場所に複数の ELINs を含めることができます。それぞれはセミコロンで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="c5f33-108">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5f33-109">Network 要素</span><span class="sxs-lookup"><span data-stu-id="c5f33-109">Network Element</span></span></th>
<th><span data-ttu-id="c5f33-110">必要な列</span><span class="sxs-lookup"><span data-stu-id="c5f33-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5f33-111"><strong>ワイヤレスアクセスポイント</strong></span><span class="sxs-lookup"><span data-stu-id="c5f33-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="c5f33-112">&lt;BSSID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="c5f33-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="c5f33-113">...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;postdirectional&gt;、&lt;City&gt;、&lt;都道府県&gt;、&lt;郵便&gt;番号&lt;、国&gt;</span><span class="sxs-lookup"><span data-stu-id="c5f33-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5f33-114"><strong>サブネット</strong></span><span class="sxs-lookup"><span data-stu-id="c5f33-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="c5f33-115">&lt;Subnet&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="c5f33-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="c5f33-116">...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;postdirectional&gt;、&lt;City&gt;、&lt;都道府県&gt;、&lt;郵便&gt;番号&lt;、国&gt;</span><span class="sxs-lookup"><span data-stu-id="c5f33-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5f33-117"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="c5f33-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="c5f33-118">&lt;ChPortIDSubType sid&gt;、&lt;&gt;、&lt;PortID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;,...</span><span class="sxs-lookup"><span data-stu-id="c5f33-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="c5f33-119">...&lt;Predirectional&gt;、&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;postdirectional&gt;、&lt;City&gt;、&lt;都道府県&gt;、&lt;郵便&gt;番号&lt;、国&gt;</span><span class="sxs-lookup"><span data-stu-id="c5f33-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5f33-120"><strong>スイッチ</strong></span><span class="sxs-lookup"><span data-stu-id="c5f33-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="c5f33-121">&lt;ChHouseNumber sid&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;&gt;、&lt;HouseNumberSuffix&gt;、&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="c5f33-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="c5f33-122">...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;postdirectional&gt;、&lt;City&gt;、&lt;都道府県&gt;、&lt;郵便&gt;番号&lt;、国&gt;</span><span class="sxs-lookup"><span data-stu-id="c5f33-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c5f33-123">場所データベースにデータを設定せず、場所ポリシーで**必要な場所**が **[はい]** または [**免責事項**] に設定されている場合、クライアントはユーザーに手動で場所を入力するように求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5f33-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="c5f33-124">場所データベースの設定の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5f33-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="c5f33-125">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="c5f33-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="c5f33-126">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="c5f33-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="c5f33-127">CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="c5f33-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="c5f33-128">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="c5f33-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="c5f33-129">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="c5f33-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="c5f33-130">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="c5f33-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="c5f33-131">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="c5f33-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="c5f33-132">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="c5f33-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="c5f33-133">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="c5f33-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="c5f33-134">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="c5f33-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="c5f33-135">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="c5f33-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="c5f33-136">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="c5f33-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="c5f33-137">場所データベースにネットワーク要素を追加するには</span><span class="sxs-lookup"><span data-stu-id="c5f33-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="c5f33-138">次のコマンドレットを実行して、サブネットの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5f33-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="c5f33-139">ELIN ゲートウェイの場合は、ELIN を CompanyName フィールドに配置します。</span><span class="sxs-lookup"><span data-stu-id="c5f33-139">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="c5f33-140">複数の ELIN を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-140">You can include more than one ELIN.</span></span> <span data-ttu-id="c5f33-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5f33-141">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="c5f33-142">または、次のコマンドレットを実行して、"subnet. csv" という名前のファイルを使用して、サブネットの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="c5f33-143">次のコマンドレットを実行して、ワイヤレスの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5f33-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="c5f33-144">または、次のコマンドレットを実行して、"wap" という名前のファイルを使用して、ワイヤレスの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="c5f33-145">次のコマンドレットを実行して、スイッチの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5f33-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="c5f33-146">または、次のコマンドレットを実行して、スイッチの場所を一括で更新する "スイッチ" という名前のファイルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="c5f33-147">次のコマンドレットを実行して、ポートの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5f33-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="c5f33-148">PortIDSubType の既定値は、割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c5f33-148">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="c5f33-149">InterfaceAlias または InterfaceName に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-149">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="c5f33-150">または、次のコマンドレットを実行し、"ports. .csv" という名前のファイルを使用して、ポートの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5f33-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

