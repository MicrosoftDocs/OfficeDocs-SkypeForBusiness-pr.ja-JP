---
title: Microsoft 365 または Office 365 で Microsoft Teams ミーティングを展開する
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: このトピックでは、Microsoft 365 または Office 365 を使用して Microsoft Teams ミーティングを展開する方法について説明します。Teams または Skype for Business と Exchange はどちらもオンラインです。
ms.openlocfilehash: 440bf2f624bfd150f7e00f145770b0fda336deb4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756798"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Microsoft 365 または Office 365 で Microsoft Teams ミーティングを展開する

このトピックでは、Microsoft 365 または Office 365 を使用して Microsoft Teams ミーティングを展開する方法について説明します。Microsoft Teams または Skype for Business と Exchange はどちらもオンラインです。

ユーザー アカウントをセットアップする最も簡単な方法は、リモート Windows PowerShell を使用して構成することです。 Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいユーザー アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams ミーティングのユーザー アカウントに変換する助けとなります。 必要な場合は、次の手順に従って、Microsoft Teams ミーティングのデバイスが使用するアカウントを構成できます。

## <a name="requirements"></a>要件

Microsoft Teams ミーティングを Microsoft 365 または Office 365 で展開する前に、要件を満たしていることをご確認ください。 詳細については、「[Microsoft Teams ミーティングの要件](requirements.md)」をご覧ください。

Skype for Business を有効にするには、次のものが必要です。

- Microsoft 365 または Office 365 プランに含まれる Skype for Business Online (プラン2、エンタープライズベースのプラン) 以上。 プランでは、ダイヤルイン会議機能を有効にする必要があります。

- 会議にダイヤルイン機能が必要な場合は、オーディオ会議および電話システムのライセンスが必要です。  会議にダイヤルアウト機能が必要な場合は、オーディオ会議のライセンスが必要です。

- テナント ユーザーには Exchange メールボックスが必要です。

- Microsoft Teams ミーティングのアカウントでは、少なくとも Skype for Business Online (プラン 2) のライセンスが必要ですが、Exchange Online のライセンスは必要ありません。 詳細については、「[Microsoft Teams ミーティング ライセンス](rooms-licensing.md)」を参照してください。

Skype for Business Online プランの詳細については、「[Skype for Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。

### <a name="add-a-device-account"></a>デバイス アカウントを追加する

1. Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

2. Exchange Online PowerShell で、新しい会議室メールボックスを作成するか、既存の会議室メールボックスを変更します。 既定では、会議室メールボックスには関連付けられたアカウントが含まれていないため、会議室メールボックスを作成または変更するときにアカウントを追加する必要があります。これにより、Skype ミーティング システム v2 で認証を行うことができます。

   - 新しい会議室メールボックスを作成するには、次の構文を使用します。

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、次の設定で新しい会議室メールボックスを作成します:

     - 名前: Rigel-01

     - エイリアス: Rigel1

     - アカウント: Rigel1@contoso.onmicrosoft.com

     - アカウントのパスワード: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 既存の会議室メールボックスを変更するには、次の構文を使用します。

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、エイリアス値が Rigel2 である既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@ $ $W 0rd に設定します。 既存のエイリアス値により、アカウントが Rigel2@contoso.onmicrosoft.com であることに注意してください。

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   構文とパラメーターの詳細については、「[New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。


3. Exchange Online PowerShell で、会議の操作性を向上させるために、次のように会議室メールボックスの設定を構成します。

   - AutomateProcessing: AutoAccept (会議の開催者は、人手を介さずに直接会議室の予約の決定を受け取ります: 利用可 = 承諾; 利用不可 = 辞退。)

   - AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)

   - DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)

   - DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)

   - RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)

   - AdditionalResponse: "これは Skype 会議室です。" (会議出席依頼に追加するテキスト)。

   この例では、Rigel-01 という名前の会議室メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   構文とパラメーターの詳細については、「[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

4. Powershell コマンドレット `Connect-MsolService -Credential $cred` を実行して、MS Online PowerShell に接続し、Active Directory の設定を行います。   Active Directory の詳細については、「[Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。 

5. パスワードの有効期限が切れないようにするには、次の構文を使用します。

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```
   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   この例では、アカウント Rigel1@contoso.onmicrosoft.com のパスワードを無期限に設定します。

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   次のコマンドを実行して、アカウントの電話番号を設定することもできます。

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. デバイス アカウントには、有効な Microsoft 365 または Office 365 ライセンスが必要です。ライセンスがない場合は Exchange と Microsoft Teams または Skype for Business が動作しません。 ライセンスを所有している場合は、使用場所をデバイス アカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。 `Get-MsolAccountSku` を使用して、 <!-- Get-AzureADSubscribedSku --> 次のように、Microsoft 365 または Office 365 組織で使用できる SKU の一覧を取得できます。

   ```Powershell
   Get-MsolAccountSku
   ```
   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   次に、`Set-MsolUserLicense` コマンドレットを使用してライセンスを追加  <!--Set-AzureADUserLicense --> することができます。 この例では、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ``` 
   <!-- 
   ```Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。

7. 次に、Skype for Business でデバイス アカウントを有効にする必要があります。 お使いの環境が「[Microsoft Teams ミーティングの要件](requirements.md)」で定義されている要件を満たしていることを確認します。

   次のようにしてリモート [Windows PowerShell セッション](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を開始します (必ず[Skype for Business Online の PowerShell コンポーネントのインストール](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)を行ってください)。

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Skype for Business Server に対して Microsoft Teams ミーティングのアカウントを有効にするには、次のコマンドを実行します。

   ``` Powershell
   $rm="Rigel1@contoso.onmicrosoft.com"
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   次の例のように、セットアップ中の新しいユーザー アカウントの RegistrarPool 情報を取得します。

    ``` Powershell
    $rm="Rigel1@contoso.onmicrosoft.com"
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > テナントの既存のユーザー アカウントと同じレジストラー プールには、新しいユーザー アカウントを作成できない可能性があります。 上記のコマンドを実行すると、このような状況でもアカウント設定のエラーは発生しません。

### <a name="assign-a-license-to-your-account"></a>アカウントにライセンスを割り当てる

1. テナント管理者としてログインし、Microsoft 365 管理センターを開き、Admin アプリをクリックします。

2. [**ユーザーとグループ**] をクリックし、[**ユーザーの追加、パスワードのリセットなど**] をクリックします。

3. Microsoft Teams ミーティング アカウントを選択してから、編集を意味するペン アイコンをクリックまたはタップします。

4. [**ライセンス**] オプションをクリックします。

5. [**ライセンスの割り当て**] セクションで、使用するライセンスと、エンタープライズ VoIP の必要性に関する決定に応じて、Skype for Business Online (プラン 2) または Skype for Business Online (プラン 3) を選択する必要があります。 Microsoft Teams ミーティングでクラウド PBX を使用する場合は、プラン 3 ライセンスを使用する必要があります。 最低でも、音声接続用に CloudPBX が必要です。 次に、PSTN の接続方法に基づきハイブリッド音声または PSTN 通話を構成します。 詳細については、「[Microsoft Teams ミーティング ライセンス](rooms-licensing.md)」を参照してください。

6. [**保存**] をクリックしてタスクを完了します。

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>サンプル: Exchange Online および Skype for Business Online における ミーティング アカウントのセットアップ

Exchange Online PowerShell コマンド:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Azure Active Directory PowerShell コマンド:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Skype for Business PowerShell コマンド:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> これで CloudPBX と PSTNCallingDomesticAndInternational が追加されます。 さらに、管理者インターフェイスを使用して、電話番号を割り当てる必要があります。

## <a name="validate"></a>検証

検証を行う場合は、通常、どの Skype for Business クライアントを使用しても作成したアカウントにログインできます。

## <a name="see-also"></a>関連項目

[Microsoft Teams ミーティングのアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)

[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)

[Microsoft Teams Rooms コンソールを構成する](console.md)

[Microsoft Teams Rooms の管理](rooms-manage.md)

[Microsoft Teams ミーティング ライセンス](rooms-licensing.md)
