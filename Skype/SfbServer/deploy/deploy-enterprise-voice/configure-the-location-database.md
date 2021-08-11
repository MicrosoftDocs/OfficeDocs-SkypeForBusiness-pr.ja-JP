---
title: 場所データベースを構成Skype for Business Server
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
description: E9-1-1 の場所データベースを構成、設定、発行Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 9e97c959af9dc88ff43fd93e734e21bae051583206be3dd89390dcae59c6ca0c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326603"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>場所データベースを構成Skype for Business Server
 
E9-1-1 の場所データベースを構成、設定、発行Skype for Business Server エンタープライズ VoIP。 
  
クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。 
  
場所データベースを構成するには、次のタスクを実行します。
  
- ネットワーク要素と場所のマッピングをデータベースに設定します。 緊急場所識別番号 (ELIN) ゲートウェイを使用する場合は、フィールドに ELIN を含める必要 \<CompanyName\> があります。
    
    場所データベースにデータを入力しない場合に、[場所ポリシーで必要な場所] が **[** はい] または [免責事項] に設定されている場合、クライアントはユーザーに手動で場所を入力するように求めるメッセージを表示します。
    
- E9-1-1 サービス プロバイダーで保持されている主要道路住所案内 (MSAG) と照らし合わせて住所を確認します。
    
- 更新したデータベースを公開します。
    
## <a name="populate-the-location-database"></a>場所データベースの設定

ネットワーク内のクライアントを自動的に検索するには、まずネットワーク ワイヤーマップを場所データベースに設定し、ネットワーク要素を市民 (つまり、ストリート) アドレスにマップする必要があります。 サブネット、ワイヤレス アクセス ポイント、スイッチ、ポートを使用してワイヤーマップを定義できます。
  
次の表に示す列形式を含む CSV ファイルを使用して、場所データベースにアドレスを個別に、または一括で追加できます。
  
緊急場所識別番号 (ELIN) ゲートウェイを使用する場合は、場所ごとに **[CompanyName]** フィールドに ELIN を含める必要があります。 各場所に複数の ELIN を含め、それぞれセミコロンで区切って指定できます。
  
|**Network 要素**|**必須の列**|
|:-----|:-----|
|**ワイヤレス アクセス ポイント** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Subnet** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…  <br/> …\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Switch** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>場所データベースにネットワーク要素を追加するには

1. 次のコマンドレットを実行して、場所データベースにサブネットの場所を追加します。
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    ELIN ゲートウェイの場合は、ELIN を [CompanyName] フィールドに入力します。 複数の ELIN を含めできます。 次に例を示します。
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    または、次のコマンドレットを実行し、"subnets.csv" という名前のファイルを使用してサブネットの場所を一括更新することもできます。
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. 次のコマンドレットを実行して、場所データベースにワイヤレスの場所を追加します。
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   または、次のコマンドレットを実行し、"waps.csv" という名前のファイルを使用してワイヤレスの場所を一括更新することもできます。
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 次のコマンドレットを実行して、場所データベースにスイッチの場所を追加します。
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   または、次のコマンドレットを実行し、"switches.csv" という名前のファイルを使用して、スイッチの場所を一括更新することもできます。
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 次のコマンドレットを実行して、場所データベースにポートの場所を追加する
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType の既定値は LocallyAssigned です。 InterfaceAlias または InterfaceName に設定することもできます。
    
   または、次のコマンドレットを実行し、"ports.csv" という名前のファイルを使用して、ポートの場所を一括更新することもできます。
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>アドレスの検証

### <a name="to-validate-addresses-located-in-the-location-database"></a>場所データベースにある住所を確認するには

1.  管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 次のコマンドレットを実行して、緊急サービス プロバイダーとの接続を構成します。
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. 次のコマンドレットを実行して、場所データベース内の住所を確認します。
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   また、**Test-CsLisCivicAddress** コマンドレットを使用して、個々の住所を確認することもできます。
    
## <a name="publish-the-location-database"></a>場所データベースを発行する

場所データベースに追加した新しい場所は、クライアントが公開されるまで使用できません。
  
緊急場所識別番号 (ELIN) ゲートウェイを使用する場合は、公衆交換電話網 (PSTN) 通信事業者の自動場所識別 (ALI) データベースに ELIN をアップロードする必要があります。 PSTN 通信事業者が ELIN レコードに特定の形式を使用する必要がある場合があります。 詳細については、PSTN 通信事業者にお問い合わせください。 場所情報サービス データベースからレコードをエクスポートし、必要に応じて書式設定できます。
  
### <a name="to-publish-the-location-database"></a>場所データベースを発行するには

-  管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
- 場所データベースを発行するには、次のコマンドレットを実行します。
    
  ```powershell
  Publish-CsLisConfiguration
  ```


