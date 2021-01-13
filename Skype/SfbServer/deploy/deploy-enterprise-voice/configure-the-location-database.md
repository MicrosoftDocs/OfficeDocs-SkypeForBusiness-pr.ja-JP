---
title: Skype for Business Server で場所データベースを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configure, populate, and publish the E9-1-1 location database in Skype for Business Server エンタープライズ VoIP.
ms.openlocfilehash: 70158864446c12b2e7636a2962aced05d87c49a0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804087"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="dd1c4-103">Skype for Business Server で場所データベースを構成する</span><span class="sxs-lookup"><span data-stu-id="dd1c4-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="dd1c4-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server エンタープライズ VoIP.</span><span class="sxs-lookup"><span data-stu-id="dd1c4-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="dd1c4-105">クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="dd1c4-106">場所データベースを構成するには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="dd1c4-107">ネットワーク要素と場所のマッピングをデータベースに設定します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="dd1c4-108">緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、フィールドに ELIN を含める必要 \<CompanyName\> があります。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="dd1c4-109">場所データベースにデータを入力しない場合に、[場所のポリシーで必要な場所] が[はい] または [免責事項] に設定されている場合、クライアントはユーザーに場所を手動で入力するように求めるメッセージを表示します。 </span><span class="sxs-lookup"><span data-stu-id="dd1c4-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="dd1c4-110">E9-1-1 サービス プロバイダーで保持されている主要道路住所案内 (MSAG) と照らし合わせて住所を確認します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="dd1c4-111">更新したデータベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="dd1c4-112">場所データベースにデータを設定する</span><span class="sxs-lookup"><span data-stu-id="dd1c4-112">Populate the location database</span></span>

<span data-ttu-id="dd1c4-113">ネットワーク内のクライアントを自動的に見つけるには、まず、場所データベースにネットワーク ワイヤマップを設定する必要があります。ネットワーク要素は、ネットワーク要素を公の住所 (番地) にマップします。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="dd1c4-114">サブネット、ワイヤレス アクセス ポイント、スイッチ、およびポートを使用して、ワイヤーマップを定義できます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="dd1c4-115">場所データベースにアドレスを個別に追加するか、次の表に示す列形式を含む CSV ファイルを使用して一括で追加できます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="dd1c4-116">緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、各場所の **CompanyName** フィールドに ELIN を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-116">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="dd1c4-117">場所ごとに複数の ELIN を含め、各 ELIN をセミコロンで区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-117">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="dd1c4-118">**Network 要素**</span><span class="sxs-lookup"><span data-stu-id="dd1c4-118">**Network Element**</span></span>|<span data-ttu-id="dd1c4-119">**必須の列**</span><span class="sxs-lookup"><span data-stu-id="dd1c4-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd1c4-120">**ワイヤレス アクセス ポイント**</span><span class="sxs-lookup"><span data-stu-id="dd1c4-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="dd1c4-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="dd1c4-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="dd1c4-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="dd1c4-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="dd1c4-123">**Subnet**</span><span class="sxs-lookup"><span data-stu-id="dd1c4-123">**Subnet**</span></span> <br/> |<span data-ttu-id="dd1c4-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="dd1c4-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="dd1c4-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="dd1c4-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="dd1c4-126">**Port**</span><span class="sxs-lookup"><span data-stu-id="dd1c4-126">**Port**</span></span> <br/> |<span data-ttu-id="dd1c4-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span><span class="sxs-lookup"><span data-stu-id="dd1c4-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="dd1c4-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="dd1c4-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="dd1c4-129">**スイッチ**</span><span class="sxs-lookup"><span data-stu-id="dd1c4-129">**Switch**</span></span> <br/> |<span data-ttu-id="dd1c4-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="dd1c4-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="dd1c4-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="dd1c4-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="dd1c4-132">ネットワーク要素を場所データベースに追加するには</span><span class="sxs-lookup"><span data-stu-id="dd1c4-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="dd1c4-133">次のコマンドレットを実行して、場所データベースにサブネットの場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="dd1c4-134">ELIN ゲートウェイの場合は、ELIN を CompanyName フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-134">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="dd1c4-135">複数の ELIN を含めできます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-135">You can include more than one ELIN.</span></span> <span data-ttu-id="dd1c4-136">例:</span><span class="sxs-lookup"><span data-stu-id="dd1c4-136">For example:</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="dd1c4-137">または、次のコマンドレットを実行し、"subnets.csv" という名前のファイルを使用してサブネットの場所を一括更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="dd1c4-138">次のコマンドレットを実行して、場所データベースにワイヤレスの場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="dd1c4-139">または、次のコマンドレットを実行し、"waps.csv" という名前のファイルを使用してワイヤレスの場所を一括更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="dd1c4-140">次のコマンドレットを実行して、スイッチの場所を場所データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="dd1c4-141">または、次のコマンドレットを実行し、"switches.csv" という名前のファイルを使用して、切り替え場所を一括更新できます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="dd1c4-142">次のコマンドレットを実行して、場所データベースにポートの場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="dd1c4-143">PortIDSubType の既定値は LocallyAssigned です。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-143">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="dd1c4-144">InterfaceAlias または InterfaceName に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-144">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="dd1c4-145">または、次のコマンドレットを実行し、"ports.csv" という名前のファイルを使用してポートの場所を一括更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="dd1c4-146">住所を検証する</span><span class="sxs-lookup"><span data-stu-id="dd1c4-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="dd1c4-147">場所データベースにある住所を確認するには</span><span class="sxs-lookup"><span data-stu-id="dd1c4-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="dd1c4-148">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="dd1c4-149">次のコマンドレットを実行して、緊急サービス プロバイダーとの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="dd1c4-150">次のコマンドレットを実行して、場所データベース内の住所を確認します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="dd1c4-151">また、**Test-CsLisCivicAddress** コマンドレットを使用して、個々の住所を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="dd1c4-152">場所データベースを発行する</span><span class="sxs-lookup"><span data-stu-id="dd1c4-152">Publish the location database</span></span>

<span data-ttu-id="dd1c4-153">場所データベースに追加した新しい場所は、公開されるまでクライアントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="dd1c4-154">緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、ELIN を公衆交換電話網 (PSTN) 通信事業者の自動ロケーション識別 (ALI) データベースにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="dd1c4-155">PSTN 通信事業者は、ELIN レコードに特定の形式を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="dd1c4-156">詳細については、PSTN 通信事業者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="dd1c4-157">場所情報サービス データベースからレコードをエクスポートし、必要に応じて書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="dd1c4-158">場所データベースを発行するには</span><span class="sxs-lookup"><span data-stu-id="dd1c4-158">To publish the location database</span></span>

-  <span data-ttu-id="dd1c4-159">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="dd1c4-160">場所データベースを発行するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd1c4-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```powershell
  Publish-CsLisConfiguration
  ```


