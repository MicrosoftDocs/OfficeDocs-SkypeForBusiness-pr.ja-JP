---
title: ユーザー Teamsアドオン ライセンスを割り当てる
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 電話会議、電話会議Teams通話プランなどについて、ユーザーにアドオン ライセンスを割り当てる電話システム説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 200e2bb36940bb4b447c4a46856c4e3ffa07f588
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846030"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>ユーザー Teamsアドオン ライセンスを割り当てる

アドオン ライセンスは、電話会議、電話会議Teams通話プランなどの特定の機能電話システムライセンスです。 この記事では、アドオン ライセンスを個々のユーザーと多数のユーザーに一括で割り当てる方法について説明します。

> [!NOTE]
> 追加[Teamsライセンスで使用できる](./microsoft-teams-add-on-licensing.md)Teams機能については、「Teams アドオン ライセンス」を参照してください。 また、購入する必要があるライセンスと購入方法に関する情報も表示されます。そのため、ユーザーは電話会議、無料電話番号、組織外の電話番号に通話する機能などの機能を利用できます。 ユーザーに必要な機能を決定した後、ユーザーにライセンスを割り当てる。

Microsoft 365 管理センター または PowerShell を使用して、組織内のユーザーにライセンスを割り当てできます。 ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>通話プラン、通信クレジットのライセンスを割り電話システム前に知る必要がある情報

開始する前に、次の要件を確認してください。

- ハイブリッド ユーザーに対してオンプレミスの公衆交換電話網 (PSTN) 接続を使用している場合は、ネットワーク ライセンスを割り当てる電話システムがあります。 通話プランライセンスを割り当てない。

- Microsoft 365 と Microsoft Teams の間の待ち時間のため、ライセンスを割り当てた後にユーザーに通話プランが割り当てられるまで最大 24 時間かかる場合があります。 ユーザーに 24 時間後に通話プランが割り当てられていない場合は、ビジネス製品のサポート ( 管理者向けヘルプ) にお [問い合わせください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 正しい数のライセンスを購入していない場合は、エラー メッセージが表示されます。 通話プランのライセンスを追加購入する必要がある場合は、さらに購入するオプションを選択します。

- ユーザーに E5 ライセンスが割り当Enterprise場合でも、PSTN から通話[](../what-are-communications-credits.md)を発信または受信する場合は、通信クレジット ライセンスを割り当てる必要があります。

- 通話プランまたはコミュニケーション クレジットライセンスをユーザーに割り当てると、組織の電話番号を取得し、その番号をユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](../set-up-calling-plans.md)」をご覧ください。

## <a name="using-the-microsoft-365-admin-center"></a>コマンドを使用Microsoft 365 管理センター

一度にMicrosoft 365 管理センターユーザーまたは小規模なユーザーセットにライセンスを割り当てるには、次のコマンドを使用します。 ライセンスの割り当ては、[**ライセンス**] ページ (一度に最大 20 人のユーザー) または [アクティブ なユーザー] ページ (一度に最大 40 人のユーザー) に割り当てる場合です。  選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。

詳細な手順については、「ユーザーにライセンスを割り当 [てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

数百または数千人のユーザーなど、多数のユーザーにライセンスを割り当てる必要がある場合は[、Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign)で PowerShell またはグループベースのライセンスを使用します。  

## <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用して、ユーザーにライセンスを一括で割り当てる。  詳細については、「PowerShell を使用して [ユーザー アカウントにライセンスを割り当てる」を参照してください](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>サンプル スクリプト

スクリプトを使用してライセンスをユーザーに割り当てる方法の例を次に示します。

1. IT プロフェッショナル向けサインイン アシスタント RTW Microsoft Online Services 64 ビット [版をインストールします](/collaborate/connect-redirect?DownloadID=59185)。
2. 次の手順にMicrosoft Azure Active Directory モジュールをインストールWindows PowerShell。
    1. 管理者特権のコマンド プロンプトWindows PowerShell開きます (管理者としてWindows PowerShellを実行します)。
    2. 次のコマンドを実行します。
        ```powershell
        Install-Module MSOnline
        ```
    3. プロバイダーをインストールするように求めるメッセージが表示されたら **、「Y」** とNuGet Enter キーを押します。
    4. PSGallery からモジュールをインストールするように求めるメッセージが表示されたら **、「Y」と入力** し、Enter キーを押します。
3. コマンド プロンプトWindows PowerShell、次のスクリプトを実行してユーザーにライセンスを割り当て、ここで、割り当てるライセンスの組織名と識別子を \<CompanyName:License> 指定します。 たとえば、litwareinc:MCOMEETADV などです。

    識別子は、ライセンスの表示名とは異なります。 たとえば、電話会議の識別子は MCOMEETADV です。 詳細については、「ライセンスの製品 [名と SKU 識別子」を参照してください](#product-names-and-sku-identifiers-for-licensing)。

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    たとえば、1 と電話Microsoft 365 Enterpriseライセンスを割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Microsoft Business Voice (通話プランなし) ライセンスを割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>ライセンスの製品名と SKU 識別子

PowerShell を使用して Teams でライセンスを管理するときに参照として使用できる製品名とそれに対応する SKU パーツ名の一部を次に示します。

詳細については[、「PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)を使用したライセンスとサービスの[](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)表示」、ライセンスの製品名とサービス プラン識別子、および Education SKU リファレンスに関[するページを参照してください](../sku-reference-edu.md)。

| 製品名| SKU 部品名 |
|--------------|---------------|
| Microsoft Enterprise E5 (電話システム) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (電話会議なし) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (電話会議を使用) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (カナダ)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (英国) | BUSINESS_VOICE  |
| Microsoft Business Voice (米国) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (通話プランなし) | BUSINESS_VOICE_DIRECTROUTING  |
| 米国向け Microsoft Business Voice (通話プランなし)| BUSINESS_VOICE_DIRECTROUTING _MED |
| 電話会議 | MCOMEETADV | 
| 電話会議の 1 分あたりの支払い (移動に合った支払い)</br>*通信クレジットを設定して有効にする必要があります。* | MCOMEETACPEA |
| 電話システム | MCOEV |
| 国内通話プランと国際通話プラン | MCOPSTN2 |
| 国内通話プラン (米国/PR/CA の場合はユーザー/月あたり 3000 分、EU 各国の場合はユーザー/月あたり 1200 分) | MCOPSTN1 |
| 国内通話プラン (国ごとにユーザー/月あたり 120 分) </br>*このプランは米国では利用できません。* | MCOPSTN5 |
| 国内通話プラン (国ごとにユーザー/月あたり 240 分) </br>*このプランは米国では利用できません。* | MCOPSTN6 |
| コミュニケーション クレジット | MCOPSTNPP |

## <a name="related-topics"></a>関連項目

- [Teams アドオンのライセンス](./microsoft-teams-add-on-licensing.md)
- [Teams へのユーザー アクセスを管理する](../user-access.md)
- [PowerShell を使用してライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU リファレンス](../sku-reference-edu.md)
