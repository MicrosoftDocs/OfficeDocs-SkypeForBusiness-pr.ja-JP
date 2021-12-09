---
title: Skype for Business Server で Microsoft Teams Rooms を展開する
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: このトピックでは、Skype for Business Server を使用して Microsoft Teams Rooms を展開する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 702eb2128dd37980fd3fc76548638102d45d7af9
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355626"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Skype for Business Server で Microsoft Teams Rooms を展開する
  
このトピックでは、単一フォレストのオンプレミスデプロイがある場合に Microsoft Teams Rooms のリソース アカウントを追加する方法について説明します。
  
単一つのフォレスト、Exchange 2013 SP1 以降のオンプレミス展開、および Skype for Business Server 2015 以降を使用している場合、提供されている Windows PowerShell スクリプトを使用してデバイスアカウントを作成できます。 複数のフォレストを使用している場合は、同じ結果を生成する同じコマンドレットを使用できます。 ここでは、これらのツールについて説明します。
  
Microsoft Teams Rooms の展開を開始する前に、関連するコマンドレットを実行するための適切な権限があることを確認します。
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   $strExchangeServer は Exchangeサーバー の完全修飾ドメイン名 (FQDN) で、$strLyncFQDN は Skype for Business Server展開のFQDNです。

2. セッションを確立したら、新しいメールボックスを作成して RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。 これにより、アカウントは、Microsoft Teams Rooms に認証されます。

    既存のリソースメールボックスを変更する場合：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   新しいリソース メールボックスを作成している場合:

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 会議室のリソース アカウントExchangeさまざまなプロパティTeams設定して、ユーザーの会議エクスペリエンスを向上できます。 [Exchange プロパティ] セクションで設定する必要があるプロパティが表示されます。

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. リソース アカウントでパスワードの有効期限をオフにします。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Active Directory でリソース アカウントを有効にして、会議室に対してMicrosoft Teamsします。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. リソース プールで Skype for Business Server Rooms Active Directory アカウントMicrosoft Teamsを有効にして、リソース アカウントを有効Skype for Business Serverします。

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    と 属性 `-DomainController` を `-RegistrarPool` 、環境に適した値に変更します。

7. **オプション。** アカウントのEnterprise Voice を有効にすることで、Microsoft Teams Rooms を使用して、公衆交換電話網 (PSTN) 通話を発着信することもできます。 エンタープライズ VoIP Microsoft Teams 会議室の要件ではないが、Microsoft Teams 会議室の PSTN ダイヤル機能が必要な場合は、次の方法で有効にします。

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。 パラメータ値 $true は同じままです。 また、音声ポリシーとダイヤル プラン ポリシー名を置き換える必要があります。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>サンプル: Exchange およびオンプレミスの Skype for Business Serverの会議室アカウントのセットアップ

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
