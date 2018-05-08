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
# <a name="configure-the-location-database-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で場所データベースを構成する
 
構成、設定、および公開 ~ 9-1-1 場所データベース Skype のビジネス サーバーのエンタープライズ VoIP の。 
  
クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。 
  
場所データベースを構成するには、次の作業を行います。
  
- ネットワーク要素と場所のマッピングをデータベースに設定します。 ELIN が含まれてする必要があります、緊急位置識別番号 (ELIN) ゲートウェイを使用する場合、 \<[得意先名]\>フィールドです。
    
    場所のデータベースに情報を読み込んでいない場合に、場所のポリシーの **[場所 (必須)]** を **[はい]** または **[免責事項]** に設定すると、クライアントから場所の情報を手動で入力するように指示されます。
    
- ~ 9-1-1 のサービス プロバイダーによって管理されている住所のマスター ガイド (MSAG) に対してアドレスを検証します。
    
- 更新したデータベースを公開します。
    
## <a name="populate-the-location-database"></a>場所データベースの設定

ネットワーク内のクライアントを自動的に検索するには、するには、まず、都市へのネットワーク要素をマップするネットワーク wiremap の場所のデータベースを設定する必要が (つまり、会社の住所) アドレスです。 ワイヤマップの定義には、サブネット、ワイヤレス アクセス ポイント、スイッチ、およびポートを使用できます。
  
住所は場所データベースに個別に追加することも、次の表に示す列形式を含む CSV ファイルを使用して一括で追加することもできます。
  
緊急位置識別番号 (ELIN) ゲートウェイを使用している場合、各場所の **[CompanyName]** フィールドに ELIN を含めます。各場所に複数の ELIN をセミコロンで区切って含めることができます。
  
|**ネットワーク要素**|**必須の列**|
|:-----|:-----|
|**ワイヤレス アクセス ポイント** <br/> |\<BSSID\>、\<の説明\>、\<の場所\>、\<[得意先名]\>、\<HouseNumber\>、\<HouseNumberSuffix\>、\<PreDirectional\>、.  <br/> .\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<市\>、\<の状態\>、\<[郵便番号]\>、\<国\>  <br/> |
|**サブネット** <br/> |\<サブネット\>、\<の説明\>、\<の場所\>、\<[得意先名]\>、\<HouseNumber\>、\<HouseNumberSuffix\>、\<PreDirectional\>、.  <br/> .\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<市\>、\<の状態\>、\<[郵便番号]\>、\<国\>  <br/> |
|**ポート** <br/> |\<ChassisID\>、\<PortIDSubType\>、\<PortID\>、\<の説明\>、\<の場所\>、\<[得意先名]\>、\<HouseNumber\>、\<HouseNumberSuffix\>、.  <br/> .\<PreDirectional\>、\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<市\>、\<の状態\>、\<[郵便番号]\>、\<国\>  <br/> |
|**スイッチ** <br/> |\<ChassisID\>、\<の説明\>、\<の場所\>、\<[得意先名]\>、\<HouseNumber\>、\<HouseNumberSuffix\>、\<PreDirectional\>、.  <br/> .\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<市\>、\<の状態\>、\<[郵便番号]\>、\<国\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>ネットワーク要素を場所のデータベースに追加するには

1. 次のコマンドレットを実行して、サブネットの場所を場所データベースに追加します。
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    ELIN ゲートウェイでは、ELIN を CompanyName フィールドに入れます。複数の ELIN を含めることもできます。次に例を示します。
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    また、"subnets.csv" という名前のファイルを使用して、次のコマンドレットでサブネットの場所を一括で更新することができます。
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet

   ```

2. 次のコマンドレットを実行して、ワイヤレスの場所を場所データベースに追加します。
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   また、"waps.csv" という名前のファイルを使用して、次のコマンドレットでワイヤレスの場所を一括で更新することもできます。
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 次のコマンドレットを実行して、スイッチの場所を場所データベースに追加します。
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   また、"switches.csv" という名前のファイルを使用して、次のコマンドレットでスイッチの場所を一括で更新することもできます。
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 次のコマンドレットを実行して、ポートの場所を場所データベースに追加します。
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType の既定値は、LocallyAssigned です。これを、InterfaceAlias または InterfaceName に設定することもできます。
    
   また、"ports.csv" という名前のファイルを使用して、次のコマンドレットでポートの場所を一括で更新することもできます。
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>住所の確認

### <a name="to-validate-addresses-located-in-the-location-database"></a>場所データベースにある住所を確認するには

1.  Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを実行して、緊急サービス プロバイダーとの接続を構成します。
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

   ```

3. 次のコマンドレットを実行して、場所データベース内の住所を確認します。
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   個々 のアドレスを検証するのに**テスト CsLisCivicAddress**コマンドレットを使用することもできます。
    
## <a name="publish-the-location-database"></a>場所データベースの公開

場所データベースに追加した新しい場所は、公開されるまでクライアントで使用できません。
  
緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、公衆交換電話網 (PSTN) の通信事業者の自動ロケーション識別 (ALI) データベースに ELIN をアップロードする必要があります。 ELIN レコードに特定の形式を使用するように PSTN の通信事業者が求める場合があります。 詳細については、PSTN の通信事業者に問い合わせてください。 場所情報サービス データベースからレコードをエクスポートし、必要に応じて書式を設定したりできます。
  
### <a name="to-publish-the-location-database"></a>場所データベースを公開するには

-  Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
- 場所データベースを公開するには、次のコマンドレットを実行します。
    
  ```
  Publish-CsLisConfiguration

  ```


