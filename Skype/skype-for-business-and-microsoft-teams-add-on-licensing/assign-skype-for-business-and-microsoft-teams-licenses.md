---
title: "Skype for Business と Microsoft Teams のライセンスを割り当てる"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/20/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
description: "Learn how to assign Skype for Business licenses for Cloud PBX, PSTN Conferencing, PSTN Calling, and PSTN Consumption. "
---

# Skype for Business と Microsoft Teams のライセンスを割り当てる

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「免責事項」をお読みください。 
  
この記事では、音声会議、電話システムでは、プランの呼び出しなどの機能をユーザーにライセンスを割り当てに関するヒントを紹介します。一括のライセンスを割り当てるスクリプトも提供します。
  
 **重要**:」をご覧ください[Skype for Business と Microsoft Teams のアドオン ライセンス](skype-for-business-and-microsoft-teams-add-on-licensing.md)についてはどのようなライセンスをする必要があります購入し、 **購入する方法** にによっては、Office 365 プランのため、ユーザーは、音声会議、フリー ダイヤルの番号を取得し、組織外の電話番号を呼び出す機能。
  
## 電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト

### 音声会議、電話システムやライセンスの割り当ての呼び出しを計画する前に知っておくべきこと

- **重要**: Skype for Business 管理センターの左のナビゲーションに [ **音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、 **電話システム**アドオン ライセンス、または **電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。
    
- **ハイブリッド ユーザー向けにオンプレミス PSTN 接続を使用している場合** 、 **電話システム**のライセンスのみをユーザーに割り当てる必要があります。通話プランを割り当てる必要は **ありません** 。
    
- **ライセンスの割り当て後の待機時間**: の理由により、Office 365 とSkype for Business Online間、待機時間かかることが可能性のある最大 24 時間が割り当てられている呼び出し計画ライセンスの割り当て後にします。24 時間後にユーザーに割り当てるいない呼び出し計画、[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)ください。
    
- **エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。
    
- **次の手順**: ユーザーに通話プランのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。詳しい手順については、「[通話プランのセットアップ](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)」をご覧ください。
    
### 電話システムおよび通話プランのライセンスを 1 人のユーザーに対して割り当てる方法

手順は、 Office 365ライセンスを割り当てると同じです。[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。
  
### 電話システムおよび通話プランのライセンスを一括で割り当てる方法

1. **IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW** をインストールします。モジュールがインストールされていない場合は、「[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123)」を参照して、モジュールをダウンロードします。
    
2. **Windows Azure Active Directory モジュール** をインストールします。モジュールがインストールされていない場合は、「[Windows PowerShell による Azure AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」を参照して、実行手順とコマンドレット構文をダウンロードします。
    
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
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and International Calling.
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 

  ```

### スクリプトで使用される電話システムと通話プランの製品名または SKU

|**製品名**|**SKU 部品名**|
|:-----|:-----|
|エンタープライズ E5 (電話システムあり)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business オンライン スタンドアロンプラン 2  <br/> |MCOSTANDARD  <br/> |
|電話システム  <br/> |MCOEV  <br/> |
|国際通話プラン  <br/> |MCOPSTN2  <br/> |
|国内通話プラン  <br/> |MCOPSTN1  <br/> |
|通信クレジット  <br/> |MCOPSTNPP  <br/> |
   
## 電話会議: ライセンス割り当てのヒントとスクリプト

### 電話会議のライセンス割り当て前に知っておくべき情報

- **サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 **電話会議**ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。この設定を変更して、サードパーティ プロバイダーに戻すことができます。
    
- 次の手順: **電話会議**ライセンスを割り当てたら、電話会議プロバイダーを割り当てるする必要があります。次のいずれかの操作を行います。
    
  - [Microsoft を電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - または、[サードパーティを電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### 電話会議ライセンスを 1 人のユーザーに対して割り当てる方法

手順は、 Office 365ライセンスを割り当てると同じです。[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。
  
### 電話会議ライセンスを一括で割り当てる方法

1. [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。
    
2. **Windows Azure Active Directory モジュール** をダウンロードしてインストールします。ダウンロードの手順とコマンドレットの構文については、「[Windows PowerShell による Azure AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」をご覧ください。
    
    モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。
    
    斜体のテキストのスクリプトの商品名またはライセンスの名前が表示されます。[スクリプトで使用される音声会議の製品名または SKU](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#sku)のすべての製品名を参照してください。
    
    この例では、Enterprise E3 ライセンスと電話会議ライセンスを割り当てています。
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### スクリプトで使用される音声会議の製品名または SKU
<a name="sku"> </a>

|**製品名**|**SKU 部品名**|
|:-----|:-----|
|電話会議  <br/> |MCOMEETADV  <br/> |
|Skype for Business オンライン スタンドアロンプラン 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (電話会議なし)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (電話会議あり)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## 通信クレジット

### 通信クレジットのライセンス割り当て前に知っておくべき情報

- **エンタープライズ E5 顧客**: 場合でも、ユーザーには、エンタープライズ E5 ライセンスが割り当てられているが、まだをお勧めするライセンスを割り当てることに **コミュニケーションを加算したもの**です。
    
- **次のステップ**: これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。詳しい手順については、「[通話プランのセットアップ](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)」をご覧ください。
    
### 通信クレジットのライセンスを 1 人のユーザーに対して割り当てる方法

手順は、 Office 365ライセンスを割り当てると同じです。[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。
  
### 一括で通信クレジットのライセンスを割り当てる方法

 **電話会議**ライセンスを割り当てるサンプル スクリプトを確認します。その情報を、 **通信クレジット**のライセンスを割り当てるための情報で更新します。
  
## 関連記事

[Skype for Business および Microsoft Teams の電話会議のセットアップ](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[通話プランのセットアップ](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[利用可能残高を追加して、通信クレジットを管理する](add-funds-and-manage-communications-credits.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  

