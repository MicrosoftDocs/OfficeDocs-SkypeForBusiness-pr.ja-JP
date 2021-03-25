---
title: Teams アドオン ライセンスをユーザーに割り当てる
author: cichur
ms.author: v-cichur
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
description: Teams アドオン ライセンスをユーザーに割り当て、電話会議、電話システム、通話プランのような機能をユーザーに割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116935"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Teams アドオン ライセンスをユーザーに割り当てる

アドオン ライセンスは、電話会議、電話システム、通話プランなどの特定の Teams 機能のライセンスです。 この記事では、アドオン ライセンスを個々のユーザーと多数のユーザーに一括で割り当てる方法について説明します。

> [!NOTE]
> アドオン [ライセンスで利用できる](./microsoft-teams-add-on-licensing.md) Teams 機能の Teams アドオン ライセンスを参照してください。 また、購入する必要があるライセンスと購入方法 (プランに応じて異なります) に関する情報も表示され、ユーザーは電話会議、無料電話番号、組織外の電話番号に電話する機能などの機能を利用できます。 ユーザーに必要な機能を決めたら、ライセンスを割り当てる必要があります。

Microsoft 365 管理センターまたは PowerShell を使用して、組織内のユーザーにライセンスを割り当てできます。 ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>電話システム、通話プラン、および通信クレジットのライセンスを割り当てる前に知る必要がある情報

始める前に、次の要件を確認してください。

- ハイブリッド ユーザーにオンプレミスの公衆交換電話網 (PSTN) 接続を使用している場合は、電話システム ライセンスのみを割り当てる必要があります。 通話プランライセンスを割り当てない。

- Microsoft 365 と Microsoft Teams の間に遅延時間が生じ、ライセンスの割り当て後にユーザーに通話プランが割り当てられるまで、最大で 24 時間かかる場合があります。 ユーザーに通話プランが 24 時間割り当てられていない場合は、ビジネス製品のサポートに問い合 [わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 正しい数のライセンスを購入していない場合は、エラー メッセージが表示されます。 追加の通話プラン ライセンスを購入する必要がある場合は、追加購入するオプションを選択します。

- ユーザーに Enterprise E5 ライセンスが割り当てられている場合でも[](../what-are-communications-credits.md)、PSTN から通話を発信または受信する場合は、通信クレジット ライセンスを割り当てる必要があります。

- 通話プランまたはコミュニケーション クレジットのライセンスをユーザーに割り当てると、組織の電話番号を取得し、その番号をユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](../set-up-calling-plans.md)」をご覧ください。

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用する

Microsoft 365 管理センターを使用して、一度に個別のユーザーまたは小規模なユーザー セットにライセンスを割り当てる。 ライセンスの割り当ては、[ **ライセンス]** ページ (一度に最大 20 人のユーザー) または [アクティブなユーザー] **ページで行** います。 選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。

詳しい手順については、「ライセンスをユーザーに割り当てる [」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

数百から数千のユーザーなど、多数のユーザーにライセンスを割り当てる必要がある場合は [、Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign)で PowerShell またはグループベースのライセンスを使用します。  

## <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用して、ライセンスをユーザーに一括で割り当てる。  詳細については、「PowerShell でライセンスを [ユーザー アカウントに割り当てる」を参照してください](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>スクリプトの例

スクリプトを使用してユーザーにライセンスを割り当てる方法の例を次に示します。

1. IT プロフェッショナル向けサインイン アシスタント RTW Microsoft Online Services [64 ビット版をインストールします](/collaborate/connect-redirect?DownloadID=59185)。
2. 次の手順に合った Microsoft Azure Active Directory モジュールをWindows PowerShell。
    1. 管理者特権のコマンド プロンプトWindows PowerShell開きます (管理者としてWindows PowerShell実行します)。
    2. 次のコマンドを実行します。
        ```powershell
        Install-Module MSOnline
        ```
    3. NuGet プロバイダーをインストールするように求めるメッセージが表示されたら **、「Y」** と入力し、Enter キーを押します。
    4. PSGallery からモジュールをインストールするように求めるメッセージが表示されたら **、「Y」** と入力し、Enter キーを押します。
3. コマンド プロンプトWindows PowerShell、次のスクリプトを実行してユーザーにライセンスを割り当て、組織名と割り当てるライセンスの識別子を \<CompanyName:License> 割り当てる必要があります。 たとえば、litwareinc:MCOMEETADV などです。

    識別子は、ライセンスの表示名とは異なります。 たとえば、電話会議の識別子は MCOMEETADV です。 詳細については、ライセンスの [製品名と SKU 識別子を参照してください](#product-names-and-sku-identifiers-for-licensing)。

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

    たとえば、Microsoft 365 Enterprise 1 および電話会議ライセンスを割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Microsoft Business Voice (通話プランなし) ライセンスを割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>ライセンスの製品名と SKU 識別子

ここでは、PowerShell を使用して Teams でライセンスを管理するときに参照として使用できる製品名とそれに対応する SKU パーツ名の一覧の一部を示します。

詳細については[、「PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)でライセンスとサービスを表示する[](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)」、ライセンスの製品名とサービス プラン識別子[、Education SKU](../sku-reference-edu.md)リファレンスを参照してください。

| 製品名| SKU 部品名 |
|--------------|---------------|
| Microsoft Enterprise E5 (電話システムを使用) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (電話会議なし) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (電話会議付き) | ENTERPRISEPREMIUM |
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
| 電話会議の分単位支払い (移動に合った支払い)</br>*通信クレジットを設定して有効にする必要があります。* | MCOMEETACPEA |
| 電話システム | MCOEV |
| 国内通話と国際通話プラン | MCOPSTN2 |
| 国内通話プラン (米国/PR/CA の場合はユーザー/月あたり 3000 分、EU 各国の場合はユーザー/月あたり 1200 分) | MCOPSTN1 |
| 国内通話プラン (各国のユーザー/月あたり 120 分) </br>*このプランは、米国ではご利用になられません。* | MCOPSTN5 |
| 国内通話プラン (国ごとにユーザー/月あたり 240 分) </br>*このプランは、米国ではご利用になられません。* | MCOPSTN6 |
| コミュニケーション クレジット | MCOPSTNPP |

## <a name="related-topics"></a>関連項目

- [Teams アドオンのライセンス](./microsoft-teams-add-on-licensing.md)
- [Teams へのユーザー アクセスを管理する](../user-access.md)
- [PowerShell でライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU リファレンス](../sku-reference-edu.md)