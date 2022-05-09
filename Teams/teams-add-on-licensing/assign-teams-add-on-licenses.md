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
description: 電話会議、電話システム、通話プランなどの機能で、Teams アドオン ライセンスをユーザーに割り当てる方法について説明します。
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

アドオン ライセンスは、電話会議、電話システム、通話プランなどの特定のTeams機能のライセンスです。 この記事では、アドオン ライセンスを個々のユーザーと大規模なユーザー セットに一括で割り当てる方法について説明します。

> [!NOTE]
> [アドオン ライセンスで](./microsoft-teams-add-on-licensing.md)使用できるTeams機能については、アドオン ライセンスTeamsを参照してください。 プランに応じて、購入する必要があるライセンスと購入方法に関する情報も表示されます。 ユーザーに必要な機能を決定したら、そのユーザーにライセンスを割り当てます。

Microsoft 365 管理センターまたは PowerShell を使用して、組織内のユーザーにライセンスを割り当てることができます。 ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>電話システム、通話プラン、コミュニケーション クレジットのライセンスを割り当てる前に知っておくべきこと

作業を開始する前に、次の要件を確認してください。

- ユーザーに対してオンプレミスの公衆交換電話網 (PSTN) 接続を使用している場合は、Teams 電話 Standard ライセンスのみを割り当てる必要があります。 通話プラン ライセンスを割り当てないでください。

- Microsoft 通話プランをユーザーに割り当てた後、Teams クライアントにダイヤル パッドが表示されるまでに最大 24 時間かかることがあります。 24 時間以内にダイヤル パッドが表示されない場合は、 [ダイヤル パッドの構成](../dial-pad-configuration.md)を確認します。 必要に応じて、 [サポートにお問い合わせください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 正しいライセンス数を購入していない場合は、エラー メッセージが表示されます。 通話プランライセンスをさらに購入する必要がある場合は、さらに購入するオプションを選択します。

- ユーザーに E5 ライセンスEnterprise割り当てられている場合でも、PSTN に接続する必要があります。 MICROSOFT TEAMS CALLING プラン、ダイレクト ルーティング、オペレーター接続など、いくつかの [PSTN 接続オプション](../pstn-connectivity.md)があります。

- 通話プランまたは通信クレジットのライセンスをユーザーに割り当てた後、組織の電話番号を取得し、それらの番号をユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](../set-up-calling-plans.md)」をご覧ください。

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

Microsoft 365 管理センターを使用して、一度に個々のユーザーまたは小規模なユーザー セットにライセンスを割り当てます。

ライセンスは、[ **ライセンス** ] ページ (一度に最大 20 人のユーザー) または **[アクティブ ユーザー** ] ページ (一度に最大 40 人のユーザー) に割り当てます。 選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。

詳細な手順については、「 [ユーザーにライセンスを割り当てる」を](/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。

数百または数千のユーザーなど、多数のユーザーにライセンスを割り当てる必要がある場合は、[Azure Active Directory (Azure AD) で Powershell またはグループ ベースのライセンスを](/azure/active-directory/users-groups-roles/licensing-groups-assign)使用します。

## <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用して、ライセンスをユーザーに一括で割り当てます。 詳細については、「 [PowerShell を使用してユーザー アカウントにライセンスを割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)」を参照してください。

### <a name="example-script"></a>スクリプトの例

スクリプトを使用してユーザーにライセンスを割り当てる方法の例を次に示します。

1. [IT プロフェッショナル向け Microsoft Online Services サインイン アシスタント RTW](/collaborate/connect-redirect?DownloadID=59185) の 64 ビット バージョンをインストールします。
2. Windows PowerShell用のMicrosoft Azure Active Directory モジュールをインストールします。
    1. 管理者特権のWindows PowerShellコマンド プロンプトを開きます (管理者としてWindows PowerShellを実行します)。
    2. 次のコマンドを実行します。
        ```powershell
        Install-Module MSOnline
        ```
    3. NuGet プロバイダーのインストールを求めるメッセージが表示されたら、「**Y**」と入力し、Enter キーを押します。
    4. PSGallery からモジュールをインストールするように求められた場合は、「 **Y**」と入力し、Enter キーを押します。
3. Windows PowerShellコマンド プロンプトで、次のスクリプトを実行してユーザーにライセンスを割り当てます。ここで\<CompanyName:License>、組織名と割り当てるライセンスの識別子を指定します。 たとえば、litwareinc:MCOMEETADV です。

    識別子は、ライセンスのフレンドリ名とは異なります。 たとえば、電話会議の識別子は MCOMEETADV です。 詳細については、「 [ライセンスの製品名と SKU 識別子」を](#product-names-and-sku-identifiers-for-licensing)参照してください。

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

    たとえば、E1 ライセンスと電話会議ライセンスMicrosoft 365 Enterprise割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    プランの呼び出しライセンスでTeams 電話を割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>ライセンスの製品名と SKU 識別子

PowerShell を使用してTeamsでライセンスを管理するときに参照できる製品名とその対応する SKU パーツ名の一部を次に示します。

詳細については、「 [PowerShell を使用したライセンスとサービスの表示](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)」、ライセンス [の製品名とサービス プラン識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)、 [Education SKU リファレンスを参照](../sku-reference-edu.md)してください。

| 製品名| SKU 部品名 |
|--------------|---------------|
| Microsoft Enterprise E5 (電話システム) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (電話会議なし) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (電話会議あり) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| 電話会議 | MCOMEETADV |
| 電話会議の 1 分あたりの支払い (従量課金) 通信クレジットを設定して有効にする必要があります。* | MCOMEETACPEA |
| Teams 電話 Standard | MCOEV |
| 通話プランが設定された Teams 電話 | MCOTEAMS_ESSENTIALS |
| 国内および国際通話プラン | MCOPSTN2 |
| 国内通話プラン (米国/PR/CA の場合はユーザー/月あたり 3000 分、EU 各国の場合はユーザー/月あたり 1200 分) | MCOPSTN1 |
| 国内通話プラン (各国のユーザー/月あたり 120 分) </br>*このプランは、米国では使用できません。* | MCOPSTN5 |
| 国内通話プラン (各国のユーザー/月あたり 240 分) </br>*このプランは、米国では使用できません。* | MCOPSTN6 |
| コミュニケーション クレジット | MCOPSTNPP |

## <a name="related-content"></a>関連コンテンツ

- [Teams アドオンのライセンス](./microsoft-teams-add-on-licensing.md)
- [Teams へのユーザー アクセスを管理する](../user-access.md)
- [PowerShell を使用してライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU リファレンス](../sku-reference-edu.md)
