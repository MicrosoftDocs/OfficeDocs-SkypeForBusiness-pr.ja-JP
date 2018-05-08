---
title: Skype for Business Server 2015 で場所データベースを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 構成、設定、および公開 ~ 9-1-1 場所データベース Skype のビジネス サーバーのエンタープライズ VoIP の。
ms.openlocfilehash: 0a08d248c5eb7ec406a86f8357c565507bb10ed6
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="configure-the-location-database-in-skype-for-business-server-2015"></a><span data-ttu-id="1a7f6-103">Skype for Business Server 2015 で場所データベースを構成する</span><span class="sxs-lookup"><span data-stu-id="1a7f6-103">Configure the location database in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1a7f6-104">構成、設定、および公開 ~ 9-1-1 場所データベース Skype のビジネス サーバーのエンタープライズ VoIP の。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="1a7f6-105">クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="1a7f6-106">場所データベースを構成するには、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="1a7f6-107">ネットワーク要素と場所のマッピングをデータベースに設定します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="1a7f6-108">ELIN が含まれてする必要があります、緊急位置識別番号 (ELIN) ゲートウェイを使用する場合、 \<[得意先名]\>フィールドです。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="1a7f6-109">場所のデータベースに情報を読み込んでいない場合に、場所のポリシーの **[場所 (必須)]** を **[はい]** または **[免責事項]** に設定すると、クライアントから場所の情報を手動で入力するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="1a7f6-110">~ 9-1-1 のサービス プロバイダーによって管理されている住所のマスター ガイド (MSAG) に対してアドレスを検証します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="1a7f6-111">更新したデータベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="1a7f6-112">場所データベースの設定</span><span class="sxs-lookup"><span data-stu-id="1a7f6-112">Populate the location database</span></span>

<span data-ttu-id="1a7f6-113">ネットワーク内のクライアントを自動的に検索するには、するには、まず、都市へのネットワーク要素をマップするネットワーク wiremap の場所のデータベースを設定する必要が (つまり、会社の住所) アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="1a7f6-114">ワイヤマップの定義には、サブネット、ワイヤレス アクセス ポイント、スイッチ、およびポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="1a7f6-115">住所は場所データベースに個別に追加することも、次の表に示す列形式を含む CSV ファイルを使用して一括で追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="1a7f6-p103">緊急位置識別番号 (ELIN) ゲートウェイを使用している場合、各場所の **[CompanyName]** フィールドに ELIN を含めます。各場所に複数の ELIN をセミコロンで区切って含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="1a7f6-118">**ネットワーク要素**</span><span class="sxs-lookup"><span data-stu-id="1a7f6-118">**Network Element**</span></span>|<span data-ttu-id="1a7f6-119">**必須の列**</span><span class="sxs-lookup"><span data-stu-id="1a7f6-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a7f6-120">**ワイヤレス アクセス ポイント**</span><span class="sxs-lookup"><span data-stu-id="1a7f6-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="1a7f6-121">\<BSSID\>、\<の説明\>、\<の場所\>、\<[得意先名]\>、\<HouseNumber\>、\<HouseNumberSuffix\>、\<PreDirectional\>、.</span><span class="sxs-lookup"><span data-stu-id="1a7f6-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="1a7f6-122">.\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<市\>、\<の状態\>、\<[郵便番号]\>、\<国\></span><span class="sxs-lookup"><span data-stu-id="1a7f6-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="1a7f6-123">**サブネット**</span><span class="sxs-lookup"><span data-stu-id="1a7f6-123">**Subnet**</span></span> <br/> |<span data-ttu-id="1a7f6-124">\<サブネット\>、\<の説明\>、\<の場所\>、\<[得意先名]\>、\<HouseNumber\>、\<HouseNumberSuffix\>、\<PreDirectional\>、.</span><span class="sxs-lookup"><span data-stu-id="1a7f6-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="1a7f6-125">.\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<市\>、\<の状態\>、\<[郵便番号]\>、\<国\></span><span class="sxs-lookup"><span data-stu-id="1a7f6-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="1a7f6-126">**ポート**</span><span class="sxs-lookup"><span data-stu-id="1a7f6-126">**Port**</span></span> <br/> |<span data-ttu-id="1a7f6-127">\<ChassisID\>、\<PortIDSubType\>、\<PortID\>、\<の説明\>、\<の場所\>、\<[得意先名]\>、\<HouseNumber\>、\<HouseNumberSuffix\>、.</span><span class="sxs-lookup"><span data-stu-id="1a7f6-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="1a7f6-128">.\<PreDirectional\>、\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<市\>、\<の状態\>、\<[郵便番号]\>、\<国\></span><span class="sxs-lookup"><span data-stu-id="1a7f6-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="1a7f6-129">**スイッチ**</span><span class="sxs-lookup"><span data-stu-id="1a7f6-129">**Switch**</span></span> <br/> |<span data-ttu-id="1a7f6-130">\<ChassisID\>、\<の説明\>、\<の場所\>、\<[得意先名]\>、\<HouseNumber\>、\<HouseNumberSuffix\>、\<PreDirectional\>、.</span><span class="sxs-lookup"><span data-stu-id="1a7f6-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="1a7f6-131">.\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<市\>、\<の状態\>、\<[郵便番号]\>、\<国\></span><span class="sxs-lookup"><span data-stu-id="1a7f6-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="1a7f6-132">ネットワーク要素を場所のデータベースに追加するには</span><span class="sxs-lookup"><span data-stu-id="1a7f6-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="1a7f6-133">次のコマンドレットを実行して、サブネットの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="1a7f6-p104">ELIN ゲートウェイでは、ELIN を CompanyName フィールドに入れます。複数の ELIN を含めることもできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="1a7f6-137">また、"subnets.csv" という名前のファイルを使用して、次のコマンドレットでサブネットの場所を一括で更新することができます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet

   ```

2. <span data-ttu-id="1a7f6-138">次のコマンドレットを実行して、ワイヤレスの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="1a7f6-139">また、"waps.csv" という名前のファイルを使用して、次のコマンドレットでワイヤレスの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="1a7f6-140">次のコマンドレットを実行して、スイッチの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="1a7f6-141">また、"switches.csv" という名前のファイルを使用して、次のコマンドレットでスイッチの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="1a7f6-142">次のコマンドレットを実行して、ポートの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="1a7f6-p105">PortIDSubType の既定値は、LocallyAssigned です。これを、InterfaceAlias または InterfaceName に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="1a7f6-145">また、"ports.csv" という名前のファイルを使用して、次のコマンドレットでポートの場所を一括で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="1a7f6-146">住所の確認</span><span class="sxs-lookup"><span data-stu-id="1a7f6-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="1a7f6-147">場所データベースにある住所を確認するには</span><span class="sxs-lookup"><span data-stu-id="1a7f6-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="1a7f6-148">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1a7f6-149">次のコマンドレットを実行して、緊急サービス プロバイダーとの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

   ```

3. <span data-ttu-id="1a7f6-150">次のコマンドレットを実行して、場所データベース内の住所を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="1a7f6-151">個々 のアドレスを検証するのに**テスト CsLisCivicAddress**コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="1a7f6-152">場所データベースの公開</span><span class="sxs-lookup"><span data-stu-id="1a7f6-152">Publish the location database</span></span>

<span data-ttu-id="1a7f6-153">場所データベースに追加した新しい場所は、公開されるまでクライアントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="1a7f6-154">緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、公衆交換電話網 (PSTN) の通信事業者の自動ロケーション識別 (ALI) データベースに ELIN をアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="1a7f6-155">ELIN レコードに特定の形式を使用するように PSTN の通信事業者が求める場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="1a7f6-156">詳細については、PSTN の通信事業者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="1a7f6-157">場所情報サービス データベースからレコードをエクスポートし、必要に応じて書式を設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="1a7f6-158">場所データベースを公開するには</span><span class="sxs-lookup"><span data-stu-id="1a7f6-158">To publish the location database</span></span>

-  <span data-ttu-id="1a7f6-159">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="1a7f6-160">場所データベースを公開するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a7f6-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration

  ```


