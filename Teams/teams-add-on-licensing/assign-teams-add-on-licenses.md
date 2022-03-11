---
title: ユーザー Teamsアドオン ライセンスを割り当てる
author: SerdarSoysal
ms.author: serdars
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
description: 電話会議、Teams通話プランなど、機能のためにユーザーにアドオン ライセンスを割り当てる電話システム説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8668b31caf0dc10e8585a518a9c4c9be890d1d0d
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435841"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>ユーザー Teamsアドオン ライセンスを割り当てる

アドオン ライセンスは、電話会議、電話会議Teams通話プランなど、特定の電話システムライセンスです。 この記事では、個々のユーザーと多数のユーザーにアドオン ライセンスを一括で割り当てる方法について説明します。

> [!NOTE]
> アドオン [ライセンスTeams使用できる](./microsoft-teams-add-on-licensing.md)機能については、「Teamsライセンス」を参照してください。 また、プランに応じて、購入する必要があるライセンスと購入方法に関する情報も表示されます。 ユーザーに必要な機能を決定した後、そのユーザーにライセンスを割り当てる必要があります。

Microsoft 365 管理センター または PowerShell を使用して、組織内のユーザーにライセンスを割り当てできます。 ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>通話プラン、通信クレジットのライセンスを割り電話システム前に知る必要がある情報

開始する前に、次の要件を確認してください。

- ユーザーにオンプレミスの公衆交換電話網 (PSTN) 接続を使用している場合は、Teams 電話 Standard ライセンスのみを割り当てる必要があります。 通話プランライセンスを割り当てない。

- Microsoft 通話プランをユーザーに割り当てると、クライアントにダイヤル パッドが表示されるまで、最大で 24 時間かかるTeamsがあります。 24 時間以内にダイヤル パッドが表示されていない場合は、ダイヤル パッドの構成 [を確認します](../dial-pad-configuration.md)。 必要に応じて、サポートに [問い合わせもできます](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 正しい数のライセンスを購入していない場合は、エラー メッセージが表示されます。 通話プランのライセンスを追加購入する必要がある場合は、さらに購入するオプションを選択します。

- ユーザーに E5 ライセンスが割り当Enterprise場合でも、PSTN に接続する必要があります。 PSTN 接続には、[通話プラン、](../pstn-connectivity.md)直接ルーティング、オペレーター Microsoft Teamsなど、いくつかの PSTN 接続オプションConnect。

- 通話プランまたはコミュニケーション クレジットライセンスをユーザーに割り当てると、組織の電話番号を取得し、その番号をユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](../set-up-calling-plans.md)」をご覧ください。

## <a name="using-the-microsoft-365-admin-center"></a>コマンドを使用Microsoft 365 管理センター

一度にMicrosoft 365 管理センターユーザーまたは小規模なユーザーにライセンスを割り当てるには、このオプションを使用します。

ライセンスの割り当ては、[**ライセンス**] ページ (一度に最大 20 人のユーザー) または [アクティブ なユーザー] ページ (一度に最大 40 人のユーザー) に割り当てる場合です。 選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。

詳細な手順については、「ユーザーにライセンスを割り当 [てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

数百または数千人のユーザーなど、多数のユーザーにライセンスを割り当てる必要がある場合は、[Azure Active Directory (Azure AD) で PowerShell](/azure/active-directory/users-groups-roles/licensing-groups-assign) またはグループベースのライセンスを使用します。

## <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用して、ユーザーにライセンスを一括で割り当てる。 詳細については、「PowerShell を使用して [ユーザー アカウントにライセンスを割り当てる」を参照してください](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>サンプル スクリプト

スクリプトを使用してライセンスをユーザーに割り当てる方法の例を次に示します。

1. IT プロフェッショナル向けサインイン アシスタント RTW Microsoft Online Services 64 ビット [版をインストールします](/collaborate/connect-redirect?DownloadID=59185)。
2. 次の手順にMicrosoft Azure Active Directory モジュールをインストールWindows PowerShell。
    1. 管理者特権Windows PowerShellコマンド プロンプトを開きます (管理者としてWindows PowerShellを実行します)。
    2. 次のコマンドを実行します。
        ```powershell
        Install-Module MSOnline
        ```
    3. プロバイダーをインストールするように求めるメッセージが表示NuGet **Y** と入力し、Enter キーを押します。
    4. PSGallery からモジュールをインストールするように求めるメッセージが表示されたら、「 **Y**」と入力し、Enter キーを押します。
3. コマンド プロンプトWindows PowerShell\<CompanyName:License>、次のスクリプトを実行してユーザーにライセンスを割り当て、ここで、割り当てるライセンスの組織名と識別子を指定します。 たとえば、litwareinc:MCOMEETADV などです。

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

    たとえば、E1 ライセンスと電話Microsoft 365 Enterpriseライセンスを割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    通話プラン のライセンスTeams 電話を割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>ライセンスの製品名と SKU 識別子

PowerShell を使用してライセンスを管理するときに参照できる製品名と対応する SKU パーツ名の一部を次に示Teams。

詳細については、「 [PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell) を使用したライセンスとサービスの表示」、ライセンスの製品名とサービス プラン [識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)、 [および Education SKU リファレンスに関するページを参照してください](../sku-reference-edu.md)。

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
| 電話会議 | MCOMEETADV |
| 電話会議の 1 分あたりの支払い (移動に合った支払い) 通信クレジットを設定して有効にする必要があります。* | MCOMEETACPEA |
| Teams 電話 Standard | MCOEV |
| 通話プランが設定された Teams 電話 | MCOTEAMS_ESSENTIALS |
| 国内通話プランと国際通話プラン | MCOPSTN2 |
| 国内通話プラン (米国/PR/CA の場合はユーザー/月あたり 3000 分、EU 各国の場合はユーザー/月あたり 1200 分) | MCOPSTN1 |
| 国内通話プラン (国ごとにユーザー/月あたり 120 分) </br>*このプランは米国では利用できません。* | MCOPSTN5 |
| 国内通話プラン (国ごとにユーザー/月あたり 240 分) </br>*このプランは米国では利用できません。* | MCOPSTN6 |
| コミュニケーション クレジット | MCOPSTNPP |

## <a name="related-content"></a>関連コンテンツ

- [Teams アドオンのライセンス](./microsoft-teams-add-on-licensing.md)
- [Teams へのユーザー アクセスを管理する](../user-access.md)
- [PowerShell を使用してライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU リファレンス](../sku-reference-edu.md)
