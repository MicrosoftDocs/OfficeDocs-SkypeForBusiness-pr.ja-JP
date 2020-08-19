---
title: Skype for Business Server で Microsoft Teams Rooms を展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: このトピックでは、Skype for Business Server を使用して Microsoft Teams Rooms を展開する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9e827f4d1fc020160b59f26dffde960394c3a69e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905269"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Skype for Business Server で Microsoft Teams Rooms を展開する
  
このトピックでは、単一フォレストのオンプレミス展開がある場合に Microsoft Teams Rooms のデバイス アカウントを追加する方法を説明します。
  
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
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   新しいリソース メールボックスを作成している場合:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. ユーザーの会議エクスペリエンスを改善するために、デバイス アカウントに対してさまざまなExchangeプロパティを設定することができます。 [Exchange プロパティ] セクションで設定する必要があるプロパティが表示されます。

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. パスワードを無期限にする場合は、Windows PowerShellコマンドレットでその設定を行うこともできます。 詳細については、「パスワードの管理」を参照してください。

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Active Directory でアカウントを有効にし、Microsoft Teams Rooms に対して認証できるようにします。

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Skype for Business Server のプールで、Microsoft Teams Rooms Active Directoryアカウントを有効にしてから、Skype for Business Server を使用して、でデバイスアカウントを有効にします。

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    プロジェクトのセッション開始プロトコル (SIP) アドレスとドメインコントローラーを使用する必要があります。

7. **オプション。** アカウントのEnterprise Voice を有効にすることで、Microsoft Teams Rooms を使用して、公衆交換電話網 (PSTN) 通話を発着信することもできます。 Enterprise Voice は、Microsoft Teams Rooms では必要ありませんが、Microsoft Teams Rooms クライアントにPSTNダイアル機能を持たせたい場合は、次のようにしてください。

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。パラメータ値 $true は同じままです。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>サンプル: Exchange およびオンプレミスの Skype for Business Serverの会議室アカウントのセットアップ

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
