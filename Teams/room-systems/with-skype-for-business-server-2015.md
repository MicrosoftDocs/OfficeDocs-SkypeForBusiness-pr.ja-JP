---
title: Microsoft Teams のルームを Skype for Business Server に展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: このトピックでは、Skype for Business Server で Microsoft Teams のルームを展開する方法について説明します。
ms.openlocfilehash: 25a9759d4f61082f30a54b130d52d8fef0f9d299
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573475"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Microsoft Teams のルームを Skype for Business Server に展開する
  
このトピックでは、単一フォレストのオンプレミス展開を使用しているときに、Microsoft Teams ルームのデバイスアカウントを追加する方法について説明します。
  
フォレストが1つのフォレスト、Exchange 2013 SP1 以降、および Skype for Business Server 2015 以降を搭載している場合は、提供されている Windows PowerShell スクリプトを使用して、デバイスアカウントを作成することができます。 複数フォレストの展開を使用している場合は、同じ結果を生成する同等のコマンドレットを使うことができます。 これらのコマンドレットについては、このセクションで説明します。

  
Microsoft Teams ルームの展開を開始する前に、関連付けられたコマンドレットを実行する適切な権限があることを確認します。
  

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

   $StrExchangeServer は Exchange server の完全修飾ドメイン名 (FQDN) であり、$strLyncFQDN は Skype for Business Server の展開の FQDN です。

2. セッションを確立したら、新しいメールボックスを作成して、RoomMailboxAccount として有効にするか、既存の会議のメールボックスの設定を変更します。 これにより、アカウントは Microsoft Teams のルームに対して認証されます。

    既存のリソース メールボックスを変更している場合:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   新しいリソースメールボックスを作成する場合は、次の操作を行います。

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. デバイスアカウントのさまざまな Exchange プロパティを設定して、ユーザーの会議の操作性を向上させることができます。 設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. パスワードの有効期限が切れないと判断した場合は、Windows PowerShell コマンドレットを使用して設定できます。 詳細については、「パスワードの管理」を参照してください。

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Active Directory でアカウントを有効にして、Microsoft Teams のルームに対して認証されるようにします。

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Skype for business Server プールで Microsoft Teams 会議の Active Directory アカウントを有効にして、Skype for Business Server でデバイスアカウントを有効にします。

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    セッション開始プロトコル (SIP) アドレスとプロジェクトのドメイン コントローラーを使用する必要があります。

7. **オプション。** また、アカウントのエンタープライズ Voip を有効にすることで、Microsoft Teams の会議通話の発信や受信を行うことができます。 エンタープライズ Voip は Microsoft Teams のルームでは必要ありませんが、Microsoft Teams のルームクライアントで PSTN ダイヤル機能を使用する場合は、次のようにして有効にすることができます。

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。パラメータ値 $true は同じままです。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>サンプル: Exchange および Skype for Business Server on it での room アカウントのセットアップ

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

[Microsoft Teams 室のアカウントを構成する](room-systems-v2-configure-accounts.md)

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)
  
[Microsoft Teams ルームの展開](room-systems-v2.md)
  
[Microsoft Teams 室コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)
