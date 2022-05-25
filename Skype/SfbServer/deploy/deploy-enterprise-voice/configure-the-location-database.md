---
title: Skype for Business Serverで場所データベースを構成する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Skype for Business Server エンタープライズ VoIPで E9-1-1 の場所データベースを構成、設定、発行します。
ms.openlocfilehash: fc7f53e1b62ec23e8075a9eac0d1158ee0143a5b
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671563"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Skype for Business Serverで場所データベースを構成する
 
Skype for Business Server エンタープライズ VoIPで E9-1-1 の場所データベースを構成、設定、発行します。 
  
クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。 
  
場所データベースを構成するには、次のタスクを実行します。
  
- ネットワーク要素と場所のマッピングをデータベースに設定します。 緊急場所識別番号 (ELIN) ゲートウェイを使用する場合は、フィールドに ELIN \<CompanyName\> を含める必要があります。
    
    場所データベースを設定せず、場所ポリシーの **[必要な場所]** が **[はい** ] または [ **免責事項**] に設定されている場合、クライアントはユーザーに手動で場所の入力を求めるメッセージを表示します。
    
- E9-1-1 サービス プロバイダーで保持されている主要道路住所案内 (MSAG) と照らし合わせて住所を確認します。
    
- 更新したデータベースを公開します。
    
## <a name="populate-the-location-database"></a>場所データベースを設定する

ネットワーク内でクライアントを自動的に検索するには、まず、ネットワーク要素を市民 (つまり番地) アドレスにマップするネットワーク ワイヤマップを、場所データベースに設定する必要があります。 サブネット、ワイヤレス アクセス ポイント、スイッチ、ポートを使用して、ワイヤマップを定義できます。
  
次の表に示す列形式を含む CSV ファイルを使用して、アドレスを場所データベースに個別に追加することも、一括で追加することもできます。
  
緊急場所識別番号 (ELIN) ゲートウェイを使用する場合は、各場所の **CompanyName** フィールドに ELIN を含めます。 場所ごとに複数の ELIN を含めることができます。それぞれをセミコロンで区切ります。
  
|**Network 要素**|**必須列**|
|:-----|:-----|
|**ワイヤレス アクセス ポイント** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Subnet** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**ポート** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...  <br/> ...\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**スイッチ** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>場所データベースにネットワーク要素を追加するには

1. 次のコマンドレットを実行して、サブネットの場所を場所データベースに追加します。
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    ELIN ゲートウェイの場合は、ELIN を CompanyName フィールドに配置します。 複数の ELIN を含めることができます。 例として以下のようなものがあります。
    
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

   または、次のコマンドレットを実行し、"switches.csv" という名前のファイルを使用してスイッチの場所を一括更新することもできます。
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 次のコマンドレットを実行して、場所データベースにポートの場所を追加します
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType の既定値は LocallyAssigned です。 また、InterfaceAlias または InterfaceName に設定することもできます。
    
   または、次のコマンドレットを実行し、"ports.csv" という名前のファイルを使用してポートの場所を一括更新することもできます。
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>アドレスを検証する

### <a name="to-validate-addresses-located-in-the-location-database"></a>場所データベースにある住所を確認するには

1.  Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。
    
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

場所データベースに追加した新しい場所は、発行されるまでクライアントが使用できなくなります。
  
緊急場所識別番号 (ELIN) ゲートウェイを使用する場合は、公衆交換電話網 (PSTN) 通信事業者の自動位置情報識別 (ALI) データベースにも ELIN をアップロードする必要があります。 PSTN 通信事業者では、ELIN レコードに特定の形式を使用することが求められる場合があります。 詳細については、PSTN 通信事業者にお問い合わせください。 場所情報サービス データベースからレコードをエクスポートし、必要に応じて書式設定できます。
  
### <a name="to-publish-the-location-database"></a>場所データベースを発行するには

-  Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。
    
- 次のコマンドレットを実行して、場所データベースを発行します。
    
  ```powershell
  Publish-CsLisConfiguration
  ```


