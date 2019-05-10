---
title: Office 365 での Microsoft Teams ミーティングを展開する
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Microsoft Office 365 でのチーム会議室を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 05b6bc05200bd6664fc597b937d2a45fba1c9e2b
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835256"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Office 365 での Microsoft Teams ミーティングを展開する

マイクロソフト、マイクロソフトのチームまたは Skype ビジネスと Exchange の両方がオンラインで、Office 365 でのチーム会議室を展開する方法の詳細については、このトピックを参照してください。

ユーザー アカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。 マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または互換性のある Microsoft チームの会議室のユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。 場合は、マイクロソフト チームの会議室デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。

## <a name="requirements"></a>要件

Microsoft Office 365 でのチーム会議室を展開する前に、要件を満たしていることを確認します。 詳細については、[マイクロソフト チームの会議室の要件](requirements.md)を参照してください。

ビジネス用の Skype を有効にするには、以下が必要です。

- (プラン 2 の場合、または企業レベルの計画)、オンライン ビジネスの Skype 以降、Office 365 のプランで。 計画では、ダイヤルイン会議機能を許可する必要があります。

- 会議にダイヤルイン機能が必要な場合は、音声会議や電話システムのライセンスを必要があります。  会議からのダイヤル ・ アウト機能が必要な場合、国内または国内および海外を呼び出すことを計画する必要があります。

- テナント ユーザーは、Exchange のメールボックスが必要です。

- チームの会議室を Microsoft アカウントにする必要が最低限、Skype ビジネス オンライン (プラン 2) のライセンスが、Exchange Online のライセンスは必要ありません。 詳細については、[マイクロソフト チームの会議室のライセンス](skype-room-systems-v2.md)を参照してください。

Skype のビジネスのオンラインの計画の詳細については、 [Skype](https://technet.microsoft.com/library/jj822172.aspx)を参照してください。

### <a name="add-a-device-account"></a>デバイス アカウントを追加する

1. オンライン PowerShell を交換するために接続します。 手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。

2. Exchange オンラインの PowerShell では、新しい会議室メールボックスを作成または既存の会議室メールボックスを変更します。 既定では、室メールボックスはありません関連付けられているアカウントは、作成または Skype ルーム システム v2 を認証することを許可する会議室メールボックスを変更するときにアカウントを追加する必要があります。

   - 新しい会議室メールボックスを作成するには、次の構文を使用します。

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、次の設定で新しい会議室メールボックスを作成します。

     - 名前: プロジェクト-Rigel-01

     - 別名: ProjectRigel01

     - アカウント: ProjectRigel01@contoso.onmicrosoft.com

     - アカウントのパスワード: P@$$W0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 既存の会議室メールボックスを変更するには、次の構文を使用します。

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、ProjectRigel02、エイリアスの値があり、9898P@$$W0rd にパスワードを設定する既存の会議室メールボックスのアカウントが有効にします。 アカウントが既存のエイリアス値が ProjectRigel02@contoso.onmicrosoft.com をすることに注意してください。

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   詳細な構文とパラメーター情報は、[新規メールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)および[セットのメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)を参照してください。


3. Exchange オンラインの PowerShell では、会議エクスペリエンスを向上させるために会議室メールボックスに次の設定を構成します。

   - AutomateProcessing: 自動承諾 (会議の開催者が人間の介入なしで直接ルーム予約の意思決定を受信: 無料 = 受け入れる; 時間 = 辞退)。

   - AddOrganizerToSubject: の $false (会議の開催者は会議出席依頼の件名にない追加)。

   - DeleteComments: $false (会議出席依頼のメッセージ本文に任意のテキストを保持)。

   - DeleteSubject: $false (まま会議出席依頼の件名)

   - RemovePrivateProperty: $false (ことを元の会議の会議の開催者から送信されたプライベート フラグの要求に指定されたままになります)。

   - (AdditionalResponse パラメーターで指定されたテキストは、会議出席依頼に追加されます)。 AddAdditionalResponse: $true

   - AdditionalResponse:「これは、Skype の会議室!」 (会議出席依頼に追加する追加のテキストです。)

   この例では、という名前のプロジェクト-Rigel-01 会議室メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   詳細な構文とパラメーター情報は、[一連の CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)を参照してください。

4. MS オンラインの PowerShell を実行して、Active Directory の設定を行うことへの接続、 `Connect-MsolService -Credential $cred` powershell コマンドレットです。   詳細については、Active Directory は、 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。 

5. パスワードを期限切れにしたくない場合は、次の構文を使用します。

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   この例では、アカウントの有効期限なしに ProjectRigel01@contoso.onmicrosoft.com のパスワードを設定します。

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   次のコマンドを実行することによってアカウントの電話番号を設定することも。

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. デバイスのアカウントは、有効な Office 365 のライセンスでは、する必要があるか、Exchange およびマイクロソフトのチームまたはビジネス用の Skype は動作しません。 ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。 使用することができます。`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 次のように、Office 365 テナントの使用可能な Sku の一覧を取得します。

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   使用して、ライセンスを追加する次に、`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> コマンドレットです。 この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   詳細については、 [Office 365 の PowerShell でのユーザー アカウントにライセンスを割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)を参照してください。

7. 次に、ビジネスの Skype でデバイスのアカウントを有効にする必要があります。 お客様の環境は、[マイクロソフト チームの会議室の要件](requirements.md)に定義されている要件を満たしていることを確認します。

   ( [Skype オンライン PowerShell のビジネス コンポーネントをインストール](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)することを確認する) 次のように、リモートの[Windows PowerShell セッション](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を開始します。

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   次に、アカウント有効にする、マイクロソフトのチーム会議室 Skype のビジネス サーバーの次のコマンドレットを実行しています。

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   次の使用例に示すように、新しいユーザー アカウントのセットアップの中から RegistrarPool 情報を取得します。

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > テナント内の既存のユーザー アカウントとして同じレジストラー プールに新しいユーザー アカウントを作成できません可能性があります。 上記のコマンドは、このような状況が発生したため、アカウントのセットアップでエラーをできなくなります。

オンライン ビジネスのマイクロソフトのチームまたは Skype で、マイクロソフト チームの会議室のアカウントを有効にするのには、上記の手順を完了した後は、マイクロソフト チームの会議室のデバイスにライセンスを割り当てる必要があります。 Office 365 管理ポータルを使用して、オンライン ビジネス (プラン 2) またはデバイスにライセンスをオンライン ビジネス (3 の計画)、Skype のいずれか、Skype を割り当てます。

### <a name="assign-a-license-to-your-account"></a>ライセンスをアカウントに割り当てる

1. ログイン テナント管理者は、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。

2. [**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。

3. チームの会議室を Microsoft アカウントを選択またはクリックして方法の編集 [ペン] アイコンをタップします。

4. [**ライセンス**] オプションをクリックします。

5. [**ライセンスの割り当て**] セクションではビジネス オンライン (3 の計画)、によっては、ライセンスおよびエンタープライズ VoIP を必要とする点で決めたものは、ビジネス オンライン (プラン 2) または Skype の Skype を選択する必要があります。 マイクロソフト チームの会議室でクラウド PBX を使用する場合は、計画の 3 ライセンスを使用する必要があります。 最低でも、音声接続用に CloudPBX が必要です。 次に、PSTN の接続方法に基づきハイブリッド音声または PSTN 通話を構成します。 詳細については、[マイクロソフト チームの会議室のライセンス](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)を参照してください。

6. タスクを完了するには、**[保存]** をクリックします。

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>サンプル: ルームのアカウント セットアップの Exchange オンラインと Skype のオンライン ビジネス

Exchange オンラインの PowerShell コマンド:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Azure Active Directory の PowerShell コマンド:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

ビジネスの PowerShell コマンドの Skype。

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> この操作によって、CloudPBX および PSTNCallingDomesticAndInternational が追加されます。 さらに、電話番号を割り当てるには、管理インターフェイスを使用する必要があります。

## <a name="validate"></a>検証

検証、ビジネス クライアント用の Skype を使用して作成したアカウントにサインインできるように。

## <a name="see-also"></a>関連項目

[マイクロソフト チームの会議室のアカウントを構成します。](room-systems-v2-configure-accounts.md)

[マイクロソフト チームの会議室のプラン](skype-room-systems-v2-0.md)

[マイクロソフト チームの会議室を配置します。](room-systems-v2.md)

[マイクロソフト チームの会議室のコンソールを構成します。](console.md)

[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)

[ライセンス マイクロソフト チーム会議室](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
