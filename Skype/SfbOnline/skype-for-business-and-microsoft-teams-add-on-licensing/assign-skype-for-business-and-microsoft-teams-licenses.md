---
title: ユーザーに会議 ID を割り当てる
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '電話システム、電話会議、通話プランやコミュニケーション クレジットを使用するために Skype for Business  のライセンスを割り当てる方法について説明します。 '
ms.openlocfilehash: f2b2e2ad4952b55fade7e0b8eddb1755ea3f2cea
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887816"
---
# <a name="assign-skype-for-business-licenses"></a>ユーザーに会議 ID を割り当てる

この記事では、電話会議、電話システム、通話プランなどの機能のライセンスをユーザーに割り当てる方法について説明します。 また、ライセンスを一括で割り当てるスクリプトも提供します。

> [!IMPORTANT]
> 購入する必要のあるライセンスと**購入方法**については、「 [Skype for business アドオンのライセンス](skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。 Office 365 プランによっては、電話会議、無料電話番号、および社外の電話番号に通話を発信する機能を利用できるようになっています。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト

電話会議、電話システム、通話プランのライセンスを割り当てる前に知っておくべきこと

- **ハイブリッド ユーザー向けにオンプレミス PSTN 接続を使用している場合** 、 **電話システム**のライセンスのみをユーザーに割り当てる必要があります。通話プランを割り当てる必要は **ありません** 。

- **ライセンス割り当て後の遅延**: Office 365 と Skype for Business Online の間に遅延時間があるため、ユーザーにライセンスを割り当てた後、そのユーザーに通話プランが割り当てられるまでに、最大で 24 時間かかる可能性があります。 24時間後にユーザーに通話プランが割り当てられていない場合は、「一般[法人向け製品サポートへのお問い合わせ-管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」を参照してください。

- **エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。
    
- **次の手順**: ユーザーに通話プランのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](/microsoftteams/set-up-calling-plans)」をご覧ください。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>電話システムおよび通話プランのライセンスを 1 人のユーザーに対して割り当てる方法

手順は Office 365 ライセンスを割り当てる場合と同じです。 「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>電話システムおよび通話プランのライセンスを一括で割り当てる方法

1. **IT プロフェッショナル向け Microsoft Online Service サインインアシスタントプロフェッショナル用 rtwhttp://go.microsoft.com/fwlink/?linkid=625123 を**インストールします。 このモジュールがインストールされていない場合は、 [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) を参照してダウンロードしてください。

2. **Windows Azure Active Directory モジュールをインストールします。** このモジュールがインストールされていない場合は、 ダウンロード手順とコマンドレットの構文については、「 [Windows PowerShell を使用した AZURE AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」を参照してください。

3. モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。

   この例では、 **Enterprise E3 ライセンス** と、 **電話システム** および **国内通話プラン** ライセンスを割り当てています。

   スクリプト内のライセンスの名前または製品名は、斜体で表示されています (下記の例と、その次の「 **スクリプトで使用される電話システムと通話プランの製品名または SKU** 」をご覧ください)。

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

   #Example of text file:
   #user1@domain.com
   #user2@domain.com

   #Import Module
   ipmo MSOnline
   #Authenticate to MSOLservice.
   Connect-MSOLService
   #File prompt to select the userlist txt file.
   [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
   $OFD = New-Object System.Windows.Forms.OpenFileDialog
   $OFD.filter = "text files (*.*)| *.txt"
   $OFD.ShowDialog() | Out-Null
   $OFD.filename
   If ($OFD.filename -eq '')
   {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
   }
   #Create a variable of all users.
   $users = Get-Content $OFD.filename
   #License each user in the $users variable.
   #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
   International Calling.
   for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    }
   ```
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>スクリプトで使用される電話システムと通話プランの製品名または SKU

|**製品名**|**SKU 部品名**|
|:-----|:-----|
|エンタープライズ E5 (電話システムあり)  <br/> |ENTERPRISEPREMIUM  <br/> |
|エンタープライズ E3  <br/> |ENTERPRISEPACK  <br/> |
|エンタープライズ E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business オンライン スタンドアロンプラン 2  <br/> |MCOSTANDARD  <br/> |
|電話システム  <br/> |MCOEV  <br/> |
|国際通話プラン  <br/> |MCOPSTN2  <br/> |
|国内通話プラン (3000 分間/1200 分の EU プラン)  <br/> |MCOPSTN1  <br/> |
|国内通話プラン (120 分間通話プラン)  <br/> |MCOPSTN5  <br/> |
|国内通話プラン (240 分間通話プラン)  <br/> |MCOPSTN6  <br/> |
|コミュニケーション クレジット  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>電話会議: ライセンス割り当てのヒントとスクリプト

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>電話会議のライセンス割り当て前に知っておくべき情報

- **サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 **電話会議**ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。この設定を変更して、サードパーティ プロバイダーに戻すことができます。

- 次の手順:**電話会議**ライセンスを割り当てると、電話会議プロバイダーを割り当てる必要があります。 [Microsoft を電話会議プロバイダーとして割り当てる]を参照してください。

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>電話会議ライセンスを 1 人のユーザーに対して割り当てる方法

手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>電話会議ライセンスを一括で割り当てる方法

1. [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。

2. **Windows Azure Active Directory モジュール** をダウンロードしてインストールします。ダウンロードの手順とコマンドレットの構文については、「[Windows PowerShell による Azure AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」をご覧ください。

    モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。

    スクリプト内のライセンスまたは製品名は、斜体で表示されています。 すべての製品名の[スクリプトに使用されている電話会議の製品名または sku](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)を参照してください。

    この例では、Enterprise E3 ライセンスと電話会議ライセンスを割り当てています。

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
    #Example of text file:
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
        }
    ```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>スクリプトで使用される音声会議の製品名または SKU
<a name="sku"> </a>

|**製品名**|**SKU 部品名**|
|:-----|:-----|
|電話会議  <br/> |MCOMEETADV  <br/> |
|Skype for Business オンライン スタンドアロンプラン 2  <br/> |MCOSTANDARD  <br/> |
|エンタープライズ E1  <br/> |STANDARDPACK  <br/> |
|エンタープライズ E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (電話会議なし)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (電話会議あり)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>コミュニケーション クレジット

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>通信クレジットのライセンス割り当て前に知っておくべき情報

- **Enterprise e5 のお客様**: ユーザーに enterprise e5 ライセンスが割り当てられている場合でも、**通信クレジット**のライセンスを割り当てることをお勧めします。
    
- **次のステップ**: これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](/microsoftteams/set-up-calling-plans)」をご覧ください。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>通信クレジットのライセンスを 1 人のユーザーに対して割り当てる方法

手順は Office 365 ライセンスを割り当てる場合と同じです。 「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>通信クレジットのライセンスを一括で割り当てる方法

**電話会議**ライセンスを割り当てるサンプル スクリプトを確認します。 その情報を、 **通信クレジット**のライセンスを割り当てるための情報で更新します。

## <a name="related-topics"></a>関連トピック
  
[通話プランの設定](/microsoftteams/set-up-calling-plans)
  
[資金を追加してコミュニケーション クレジットを管理する](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
