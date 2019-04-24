---
title: Skype でマイクロソフトのチームの会議室をビジネス サーバーの展開します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: ビジネス サーバー用 Skype でマイクロソフト チームの会議室を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: e5ba372a5990f7c63827f1f8b0426e67ae48b620
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207875"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Skype でマイクロソフトのチームの会議室をビジネス サーバーの展開します。
  
このトピックでは、マイクロソフト チームの会議室のデバイスのアカウントを追加する方法、単一フォレストでは、設置型の展開がある場合について説明します。
  
単一フォレスト、Exchange 2013 の sp1 またはそれ以降の設置型展開および Skype ビジネス サーバー 2015 またはそれ以降がある場合は場合、は、デバイスのアカウントを作成するのには、指定された Windows PowerShell スクリプトを使用できます。 マルチ フォレスト展開を使用する場合は、同じ結果を生成すると同等のコマンドレットを使用できます。 これらのコマンドレットは、このセクションで説明します。

  
マイクロソフト チームの会議室を展開する作業を開始する前に、関連付けられているコマンドレットを実行する適切なアクセス許可があることを確認します。
  

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

   $StrExchangeServer は、Exchange サーバーの完全修飾ドメイン名 (FQDN)、$strLyncFQDN は、ビジネスのサーバーの展開に、Skype の FQDN を確認します。

2. セッションを確立するには後、するが新しいメールボックスを作成して、RoomMailboxAccount、として有効にか既存の会議室メールボックスの設定を変更します。 これにより、マイクロソフトのチームの会議室への認証にアカウントが許可されます。

    既存のリソース メールボックスを変更している場合:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   : 新しいリソース メールボックスを作成する場合

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 人の会議エクスペリエンスを向上させるためにデバイスのアカウントには、Exchange のさまざまなプロパティを設定できます。 設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 無期限のパスワードを入力する場合も Windows PowerShell コマンドレットを設定できます。 詳細については、「パスワードの管理」を参照してください。

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. マイクロソフト チームの会議室に、認証は、Active Directory のアカウントを有効にします。

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. ビジネス サーバー プールのため、Skype でマイクロソフト チーム ルームの Active Directory アカウントを有効にすると、Business Server の Skype でデバイスのアカウントを有効にします。

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    セッション開始プロトコル (SIP) アドレスとプロジェクトのドメイン コントローラーを使用する必要があります。

7. **オプション。** マイクロソフト チームの会議室になり、公衆交換電話網 (PSTN) 電話でお使いのアカウントでエンタープライズ VoIP を有効にすることも可能です。 エンタープライズ VoIP がマイクロソフト チームの会議室の要件はありませんが、PSTN のダイヤル機能をマイクロソフト チームの会議室のクライアントの使用すると、それを有効にする方法です。

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。パラメータ値 $true は同じままです。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exchange およびビジネス上のサーバー設置型の Skype のサンプル: ルームのアカウントのセットアップ

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

## <a name="see-also"></a>関連項目

[マイクロソフト チームの会議室のアカウントを構成します。](room-systems-v2-configure-accounts.md)

[マイクロソフト チームの会議室のプラン](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[マイクロソフト チームの会議室を配置します。](room-systems-v2.md)
  
[マイクロソフト チームの会議室のコンソールを構成します。](console.md)
  
[Microsoft Teams Rooms を管理する](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)