---
title: "Skype for Business と Microsoft Teams のライセンスを割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "電話システム、電話会議、計画を呼び出し、および通信のクレジットのビジネス ライセンスを Skype に割り当てる方法について説明します。 "
ms.openlocfilehash: d60d637d3b904b98ee8600647c57062927fe9afc
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Skype for Business と Microsoft Teams のライセンスを割り当てる

この資料では、オーディオ会議、電話システム、および計画を呼び出すような機能をユーザーにライセンスを割り当てる方法のヒントを紹介します。一括でライセンスを割り当てるためのスクリプトも提供します。
  
 **重要**: どのようなライセンス供与を受ける方法についてを参照してください[Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md)する必要があります購入と**購入方法**にによっては、Office 365 の計画では、オーディオ会議、フリー ダイヤル番号を表示するようにし、業務外の電話番号を呼び出すことです。
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト

オーディオ会議、電話システム、および計画を呼び出してライセンスを割り当てる前に知っておく必要があります。

- **ハイブリッド ユーザー向けにオンプレミス PSTN 接続を使用している場合** 、 **電話システム**のライセンスのみをユーザーに割り当てる必要があります。通話プランを割り当てる必要は **ありません** 。
    
- **ライセンスの割り当て後の待機時間**: により、Office 365 とオンライン ビジネスの Skype との間の遅延時間、かかることが可能性のある割り当て計画を呼び出してライセンスを割り当てると、ユーザーには、最大で 24 時間です。 24 時間後に計画を呼び出すことがユーザーに割り当てされていない、[ビジネス製品の管理のヘルプのサポートに問い合わせてください](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。
    
- **エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。
    
- **次のステップ**: ユーザー ライセンスの計画を呼び出すことを割り当てた後、組織の電話番号を取得し、組織内のユーザーにこれらの番号を割り当てる必要があります。。 手順の説明については、[計画を呼び出す設定](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>電話システムおよび通話プランのライセンスを 1 人のユーザーに対して割り当てる方法

手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>電話システムおよび通話プランのライセンスを一括で割り当てる方法

1. **Microsoft オンライン サービス サインイン アシスタント RTW の IT プロフェッショナルのため**にインストールします。 モジュールがインストールされている必要はありませんか。 [Microsoft オンライン サービス サインイン アシスタントの IT プロフェッショナルの RTW](https://go.microsoft.com/fwlink/?LinkId=625123)をダウンロードして参照してください。
    
2. インストール、 **Windows Azure Active Directory のモジュール**。 モジュールがインストールされている必要はありませんか。 ダウンロードの手順とコマンドレットの構文については、 [Windows PowerShell を使用して AD を Azure の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。
    
3. モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。
    
  この例では、 **Enterprise E3 ライセンス** と、 **電話システム** および **国内通話プラン** ライセンスを割り当てています。
    
  スクリプト内のライセンスの名前または製品名は、斜体で表示されています (下記の例と、その次の「 **スクリプトで使用される電話システムと通話プランの製品名または SKU** 」をご覧ください)。
    
  ```
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
|国内通話プラン  <br/> |MCOPSTN1  <br/> |
|コミュニケーション クレジット  <br/> |MCOPSTNPP  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>電話会議: ライセンス割り当てのヒントとスクリプト

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>電話会議のライセンス割り当て前に知っておくべき情報

- **サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 **電話会議**ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。この設定を変更して、サードパーティ プロバイダーに戻すことができます。
    
- 次の手順:**オーディオ会議**のライセンスを割り当てると、する必要があります、オーディオ会議プロバイダーを割り当てます。 次のいずれかの操作を行います。
    
  - [Microsoft を電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - または、[サードパーティを電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>電話会議ライセンスを 1 人のユーザーに対して割り当てる方法

手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>電話会議ライセンスを一括で割り当てる方法

1. [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。
    
2. **Windows Azure Active Directory モジュール** をダウンロードしてインストールします。ダウンロードの手順とコマンドレットの構文については、「[Windows PowerShell による Azure AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」をご覧ください。
    
    モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。
    
    斜体のテキストでは、ライセンスの名前、またはスクリプト内で製品名が一覧表示されます。 [オーディオ会議の製品名やスクリプト作成に使用する製品](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)のすべての製品名を参照してください。
    
    この例では、Enterprise E3 ライセンスと電話会議ライセンスを割り当てています。
    
```
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
   
## <a name="communications-credits"></a>通信クレジット

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>通信クレジットのライセンス割り当て前に知っておくべき情報

- **E5 のエンタープライズのお客様**: ユーザーがエンタープライズ E5 のライセンスを割り当てられている場合でもをお勧めするユーザーを割り当てる**通信のクレジット**のライセンスです。
    
- **次の手順**: これらのライセンスを割り当てると後の組織では、自分の電話番号を取得し、組織内のユーザーにこれらの番号を割り当てる必要があります。。 手順の説明については、[計画を呼び出す設定](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>通信クレジットのライセンスを 1 人のユーザーに対して割り当てる方法

手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>大量の通信のクレジットのライセンスを割り当てる方法

**電話会議**ライセンスを割り当てるサンプル スクリプトを確認します。その情報を、 **通信クレジット**のライセンスを割り当てるための情報で更新します。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[通話プランのセットアップ](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[資金を追加し、通信のクレジットの管理](add-funds-and-manage-communications-credits.md)
  