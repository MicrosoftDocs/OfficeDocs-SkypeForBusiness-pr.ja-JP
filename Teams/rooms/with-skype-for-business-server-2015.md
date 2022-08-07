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
- Teams_ITAdmin_Rooms
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: このトピックでは、Skype for Business Server を使用して Microsoft Teams Rooms を展開する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 53903052efe28a85400ba8b418bd8869ef2dec4e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271682"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Skype for Business Server で Microsoft Teams Rooms を展開する
  
このトピックでは、単一フォレストのオンプレミスデプロイがある場合に、Microsoft Teams Roomsのリソース アカウントを追加する方法について説明します。
  
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

3. Teams Rooms リソース アカウントにさまざまな Exchange プロパティを設定して、ユーザーの会議エクスペリエンスを向上させることができます。 [Exchange プロパティ] セクションで設定する必要があるプロパティが表示されます。

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. リソース アカウントでパスワードの有効期限を無効にします。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Microsoft Teams Roomsに対して認証されるように、Active Directory でリソース アカウントを有効にします。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. Skype for Business Server プールでMicrosoft Teams Rooms Active Directory アカウントを有効にして、Skype for Business Serverでリソース アカウントを有効にします。

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    環境に `-DomainController` 適した値に属性と `-RegistrarPool` 属性を変更します。

7. **オプション。** アカウントのEnterprise Voice を有効にすることで、Microsoft Teams Rooms を使用して、公衆交換電話網 (PSTN) 通話を発着信することもできます。 エンタープライズ VoIPはMicrosoft Teams Roomsの要件ではありませんが、Microsoft Teams Roomsの PSTN ダイヤル機能が必要な場合は、有効にする方法を次に示します。

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。 パラメータ値 $true は同じままです。 また、音声ポリシーとダイヤル プラン のポリシー名を置き換える必要もあります。

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
