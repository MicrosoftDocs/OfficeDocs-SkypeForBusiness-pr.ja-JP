---
title: チームのアドオンライセンスをユーザーに割り当てる
author: LanaChin
ms.author: v-lanac
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
description: 電話会議、電話システム、通話プランなどの機能をユーザーに割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868584"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>チームのアドオンライセンスをユーザーに割り当てる

アドオンライセンスは、電話会議、電話システム、通話プランなどの特定のチーム機能のライセンスです。 この記事では、個々のユーザーと、大量のユーザーにアドオンライセンスを割り当てる方法について説明します。

> [!NOTE]
> アドオンライセンスで利用できる Teams の[アドオンライセンス](microsoft-teams-add-on-licensing.md)については、こちらをご覧ください。 また、購入する必要があるライセンスと購入方法 (プランによって異なります) についての情報が表示されるので、ユーザーは電話会議、無料電話番号、組織外の電話番号への通話機能などの機能を利用できます。 ユーザーに必要な機能を決定したら、ライセンスを割り当てます。

Microsoft 365 管理センターまたは PowerShell を使用して、組織内のユーザーにライセンスを割り当てることができます。 ライセンスを管理するには、グローバル管理者またはユーザー管理者である必要があります。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>電話システム、通話プラン、および通信クレジットライセンスを割り当てる前に知っておくべきこと

始める前に、次のことを確認してください。

- ハイブリッドユーザー用にオンプレミスの公衆交換電話網 (PSTN) 接続を使用している場合は、電話システムのライセンスを割り当てる必要があります。 通話プランライセンスを割り当てないでください。

- Microsoft 365 と Microsoft Teams の間の待機時間のため、ライセンスを割り当てた後にユーザーが通話プランを割り当てられるまでに最大24時間かかることがあります。 24時間経過してもユーザーが通話プランを割り当てられていない場合は、[ビジネス製品のサポートにお問い合わせください。管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 適切な数のライセンスを購入していない場合は、エラーメッセージが表示されます。 追加の通話プランライセンスを購入する必要がある場合は、[追加購入] オプションを選択します。

- ユーザーに Enterprise E5 ライセンスが割り当てられている場合でも、PSTN から通話を発信または受信する場合は、そのユーザーに[通信クレジット](../what-are-communications-credits.md)ライセンスを割り当てる必要があります。

- 通話プランまたは通信クレジットのライセンスをユーザーに割り当てた後、組織の電話番号を取得して、それらの電話番号をユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](../set-up-calling-plans.md)」をご覧ください。

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用する

Microsoft 365 管理センターを使用して、個々のユーザーまたは少数のユーザーのライセンスを一度に割り当てることができます。 [**ライセンス**] ページ (一度に最大20人) または [**アクティブなユーザー** ] ページでライセンスを割り当てることができます。 選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザーライセンスを管理するかによって異なります。

詳細な手順については、「[ユーザーにライセンスを割り当てる](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。

数百または数千のユーザーなどの多数のユーザーのライセンスを割り当てる必要がある場合は、 [Azure Active Directory (AZURE AD) で Powershell またはグループベースのライセンス](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)を使用します。  

## <a name="using-powershell"></a>PowerShell を使用する場合

PowerShell を使用して、ユーザーにライセンスをまとめて割り当てます。  詳細については、「 [PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)」を参照してください。

### <a name="example-script"></a>スクリプトの例

スクリプトを使用してユーザーにライセンスを割り当てる方法の例を次に示します。

1. IT プロフェッショナル向けの64ビットバージョンの[Microsoft Online Services サインインアシスタントプロフェッショナル用 rtwhttp://go.microsoft.com/fwlink/?linkid=625123](https://go.microsoft.com/fwlink/p/?LinkId=286152)をインストールします。
2. Microsoft Azure Active Directory Module for Windows PowerShell をインストールします。
    1. 昇格した Windows PowerShell コマンドプロンプトを開きます (管理者として Windows PowerShell を実行します)。
    2. 次のコマンドを実行します。
        ```powershell
        Install-Module MSOnline
        ```
    3. NuGet プロバイダーをインストールするかどうかを確認するメッセージが表示されたら、「 **Y**」と入力して、enter キーを押します。
    4. PSGallery からモジュールをインストールするかどうかを確認するメッセージが表示されたら、「 **Y**」と入力して、enter キーを押します。
3. Windows PowerShell コマンドプロンプトで、次のスクリプトを実行して、ユーザーにライセンスを割り当て \<CompanyName:License> ます。ここでは、組織名と、割り当てるライセンスの識別子を指定します。 たとえば、litwareinc: MCOMEETADV のようになります。

    この識別子は、ライセンスのフレンドリ名とは異なります。 たとえば、電話会議の識別子は MCOMEETADV です。 詳細については、「[ライセンスの製品名と SKU 識別子](#product-names-and-sku-identifiers-for-licensing)」を参照してください。

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

    たとえば、Microsoft 365 のエンタープライズ1ライセンスと電話会議ライセンスを割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Microsoft ビジネスボイス (通話プランなし) ライセンスを割り当てるには、スクリプトで次の構文を使用します。

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>ライセンスの製品名と SKU 識別子

PowerShell を使用して Teams でライセンスを管理する場合に参照として使用できる製品名と、それに対応する SKU 部分名の一部を次に示します。

詳細については、「 [PowerShell を使用したライセンスとサービスの表示](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、[製品名とライセンスのサービス計画識別子](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)、および[教育 SKU リファレンス](../sku-reference-edu.md)」を参照してください。

| 製品名| SKU 部品名 |
|--------------|---------------|
| Microsoft Enterprise E5 (電話システムあり) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (電話会議なし) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (電話会議あり) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | リード|
| Microsoft ビジネス Voip (カナダ)| BUSINESS_VOICE_MED  |
| Microsoft ビジネス Voip (英国) | BUSINESS_VOICE  |
| Microsoft ビジネス Voip (米国) | BUSINESS_VOICE_MED2  |
| Microsoft ビジネスボイス (通話プランなし) | BUSINESS_VOICE_DIRECTROUTING  |
| 米国の Microsoft ビジネス Voip (通話プランなし)| BUSINESS_VOICE_DIRECTROUTING _MED |
| 電話会議 | MCOMEETADV | 
| 電話会議の1分あたりの料金 (プリペイド)</br>*通信クレジットを設定して有効にする必要があります。* | MCOMEETACPEA |
| 電話システム | MCOEV |
| 国内および国際通話プラン | MCOPSTN2 |
| 国内通話プラン (米国/PR/月額プランの場合はユーザーあたり、1ヶ月あたり3000分、EU 諸国の場合はユーザー/月あたり1200分) | MCOPSTN1 |
| 国内通話プラン (各国のユーザー/月あたり120分) </br>*このプランは、米国では利用できません。* | MCOPSTN5 |
| 国内通話プラン (各国のユーザー/月あたり240分) </br>*このプランは、米国では利用できません。* | MCOPSTN6 |
| コミュニケーション クレジット | MCOPSTNPP |

## <a name="related-topics"></a>関連項目

- [Teams アドオンのライセンス](microsoft-teams-add-on-licensing.md)
- [Teams へのユーザー アクセスを管理する](../user-access.md)
- [PowerShell でライセンスとサービスを表示する](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [エデュケーション SKU リファレンス](../sku-reference-edu.md)