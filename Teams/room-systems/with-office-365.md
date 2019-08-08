---
title: Office 365 での Microsoft Teams ミーティングを展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: このトピックでは、Office 365 で Microsoft Teams のルームを展開する方法について説明します。
ms.openlocfilehash: 9c1e14e9e5e7b32aa6ba4a1b08a2ae6ee8453d93
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243236"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Office 365 での Microsoft Teams ミーティングを展開する

このトピックでは、microsoft teams または Skype for Business および Exchange が両方ともオンラインの Office 365 で Microsoft Teams ルームを展開する方法について説明します。

ユーザーアカウントをセットアップする最も簡単な方法は、リモートの Windows PowerShell を使用してアカウントを構成することです。 Microsoft には、新しいユーザーアカウントを作成するのに役立つスクリプト、または既存のリソースアカウントを、互換性のある Microsoft Teams 室のユーザーアカウントに変換するために使用している既存のリソースアカウントを検証するための SkypeRoomProvisioningScript が用意されてい[ます](https://go.microsoft.com/fwlink/?linkid=870105)。 必要に応じて、次の手順に従って、Microsoft Teams の会議室のデバイスで使用するアカウントを構成することができます。

## <a name="requirements"></a>要件

Microsoft Teams のルームを Office 365 に展開する前に、要件を満たしていることを確認してください。 詳細については、「 [Microsoft Teams の会議室の要件](requirements.md)」を参照してください。

Skype for Business を有効にするには、次のものが必要です。

- Office 365 プランで Skype for Business Online (プラン2、またはエンタープライズベースのプラン) 以上。 このプランでは、ダイヤルイン会議機能を許可する必要があります。

- 会議からダイヤルイン機能が必要な場合は、電話会議と電話システムのライセンスが必要です。  会議からダイヤルアウト機能が必要な場合は、国内または国内の通話プランが必要です。

- テナントユーザーは Exchange メールボックスを持っている必要があります。

- Microsoft Teams のルームアカウントには、少なくとも Skype for Business Online (プラン 2) ライセンスが必要ですが、Exchange Online のライセンスは必要ありません。 詳細については、「 [Microsoft Teams ルームライセンス](skype-room-systems-v2.md)」を参照してください。

Skype for Business Online プランの詳細については、「 [skype For Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。

### <a name="add-a-device-account"></a>デバイス アカウントを追加する

1. Exchange Online PowerShell に接続します。 手順については、「 [Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

2. Exchange Online PowerShell で、新しい会議室のメールボックスを作成するか、既存の会議のメールボックスを変更します。 既定では、会議室メールボックスにはアカウントが関連付けられていないため、Skype Room Systems v2 での認証を許可する会議室メールボックスを作成または変更する場合は、アカウントを追加する必要があります。

   - 新しい会議室のメールボックスを作成するには、次の構文を使用します。

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、次の設定で新しい会議室のメールボックスを作成します。

     - Name: Project-Rigel-01

     - エイリアス: ProjectRigel01

     - アカウント: ProjectRigel01@contoso.onmicrosoft.com

     - アカウントパスワード: P @ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 既存の会議のメールボックスを変更するには、次の構文を使用します。

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、エイリアス値 ProjectRigel02 を持つ既存のルームメールボックスのアカウントを有効にし、0rd に対してパスワードを 9898P @ $ $W に設定します。 既存のエイリアス値が原因で、アカウントが ProjectRigel02@contoso.onmicrosoft.com されることに注意してください。

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   構文とパラメーターの詳細については、「[新しいメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)と[設定-](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)メールボックス」を参照してください。


3. Exchange Online PowerShell で、会議の操作性を向上させるために、会議室メールボックスで次の設定を構成します。

   - 自動的な処理: 自動承諾 (会議の開催者は、手動での介入なく、会議の開催者が会議室の予約を直接受け取ります: 無料 = accept; busy = 拒否。)

   - Addオーガナイザー Ertosubject: $false (会議の開催者は、会議出席依頼の件名に追加されません)。

   - DeleteComments: $false (入力した会議出席依頼のメッセージ本文に含まれるテキストを保持)

   - DeleteSubject: $false (入力した会議出席依頼の件名を保持)

   - RemovePrivateProperty: $false (元の会議出席依頼の開催者によって送信されたプライベートフラグが指定されたままになります)。

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます)

   - AdditionalResponse: "これは Skype 会議室です。" (会議出席依頼に追加する追加のテキスト)

   この例では、Rigel-01 という名前の会議室メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   構文とパラメーターの詳細については、「 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

4. MS Online PowerShell に接続して、 `Connect-MsolService -Credential $cred` powershell コマンドレットを実行して Active Directory の設定を行います。   Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。 

5. パスワードを無期限にする場合は、次の構文を使用します。

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   次の例では、アカウント ProjectRigel01@contoso.onmicrosoft.com のパスワードを無期限に設定します。

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   次のコマンドを実行して、アカウントの電話番号を設定することもできます。

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. デバイスアカウントには、有効な Office 365 ライセンスが必要です。または、Exchange と Microsoft Teams、または Skype for Business が動作しません。 ライセンスを所有している場合は、使用場所をデバイスアカウントに割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。 使用できる方法`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> Office 365 テナントで利用可能な Sku の一覧を取得するには、次の手順を実行します。

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   次に、次の方法を使用してライセンスを追加することができます。`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> コマンドレット. この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。

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

   詳細な手順については、「 [Office 365 PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。

7. 次に、Skype for Business でデバイスアカウントを有効にする必要があります。 環境が、 [Microsoft Teams の会議室の要件](requirements.md)で定義されている要件を満たしていることを確認します。

   次の手順でリモート[Windows PowerShell セッション](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を開始します ( [Skype For business Online PowerShell コンポーネントをインストール](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)してください)。

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   次のコマンドレットを実行して、Skype for Business Server 用の Microsoft Teams ルームアカウントを有効にします。

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   次の例に示すように、セットアップ中の新しいユーザーアカウントから RegistrarPool 情報を取得します。

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > 新しいユーザーアカウントが、テナント内の既存のユーザーアカウントと同じレジストラープールに作成されていない可能性があります。 上のコマンドを実行すると、アカウント設定のエラーがこの状況で発生することはありません。

Microsoft teams または Skype for Business Online で Microsoft Teams のルームアカウントを有効にするための上記の手順を完了したら、Microsoft teams の会議デバイスにライセンスを割り当てる必要があります。 Office 365 管理ポータルを使用して、デバイスに Skype for Business Online (プラン 2) または Skype for Business Online (Plan 3) ライセンスを割り当てます。

### <a name="assign-a-license-to-your-account"></a>ライセンスをアカウントに割り当てる

1. テナント管理者としてログインし、Office 365 管理ポータルを開いて、[管理者] アプリをクリックします。

2. [**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。

3. Microsoft Teams のルームアカウントを選択し、ペンアイコンをクリックまたはタップします。これは編集を意味します。

4. [**ライセンス**] オプションをクリックします。

5. [**ライセンスの割り当て**] セクションで、ライセンスに応じて Skype For business Online (プラン 2) または Skype For business Online (プラン 3) を選択する必要があります。これは、使用しているライセンスと、エンタープライズボイスの必要条件によって決定された内容によって異なります。 Microsoft Teams のルームでクラウド PBX を使用する場合は、プラン3ライセンスを使用する必要があります。 最低でも、音声接続用に CloudPBX が必要です。 次に、PSTN の接続方法に基づきハイブリッド音声または PSTN 通話を構成します。 詳細については、「 [Microsoft Teams ルームライセンス](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)」を参照してください。

6. タスクを完了するには、**[保存]** をクリックします。

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>サンプル: Exchange Online と Skype for Business Online での会議室アカウントのセットアップ

Exchange Online PowerShell コマンド:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Azure Active Directory PowerShell コマンド:

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

Skype for Business PowerShell コマンド:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> この操作によって、CloudPBX および PSTNCallingDomesticAndInternational が追加されます。 さらに、管理インタフェースを使用して電話番号を割り当てる必要があります。

## <a name="validate"></a>有効性

検証のために、Skype for Business クライアントを使って、作成したアカウントにサインインできるようにする必要があります。

## <a name="see-also"></a>関連項目

[Microsoft Teams 室のアカウントを構成する](room-systems-v2-configure-accounts.md)

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)

[Microsoft Teams ルームの展開](room-systems-v2.md)

[Microsoft Teams 室コンソールを構成する](console.md)

[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)

[Microsoft Teams 会議室のライセンス](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
