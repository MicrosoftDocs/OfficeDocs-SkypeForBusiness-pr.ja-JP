---
title: "ライセンスのビジネスと Microsoft チームの Skype を割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Skype を電話システムで、音声会議、プランの呼び出し] との通信を加算したものビジネス ライセンスを割り当てる方法について説明します。 "
ms.openlocfilehash: a5cbc36d1b5ce5a7d79587df369b2d3bf3caacd6
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>ライセンスのビジネスと Microsoft チームの Skype を割り当てる

この記事では、音声会議、電話システムでは、プランの呼び出しなどの機能をユーザーにライセンスを割り当てに関するヒントを紹介します。一括のライセンスを割り当てるスクリプトも提供します。
  
 **重要**:」をご覧ください[Skype for Business や Microsoft チーム アドオンのライセンス](skype-for-business-and-microsoft-teams-add-on-licensing.md)についてはどのようなライセンスをする必要があります購入し、**購入する方法**にによっては、Office 365 プランのため、ユーザーは、音声会議、フリー ダイヤルの番号を取得し、組織外の電話番号を呼び出す機能。
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話システムとプランの呼び出し: のヒントとライセンスの割り当てについてスクリプト

音声会議、電話システムやライセンスの割り当ての呼び出しを計画する前に知っておくべきこと

- **ハイブリッド ユーザーの内部設置型 PSTN への接続を使用してよいですか?**必要な場合は、のみ、**電話システムで**ライセンスを割り当てる必要があります。呼び出し計画割り当て**いない**する必要があります。
    
- **ライセンスの割り当て後の待機時間**: の理由により、Office 365 と Skype for Business Online の間、待機時間かかることがおそらくまで 24 時間が割り当てられている呼び出し計画ライセンスの割り当て後にします。24 時間後に通話プランがユーザーに割り当てされていない、 [business 製品 - 管理者向けヘルプのサポートに問い合わせてください](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。
    
- **エラー メッセージ**: 適切なライセンス数を購入していない場合、エラー メッセージが表示されます。その他のプランの呼び出しのライセンスを購入する必要がある場合は、**さらに購入**] を選びます。
    
- **次のステップ**: 通話プランのライセンスの割り当てをユーザーに後、を組織の電話番号を取得し、[これらの数値を組織のユーザーに割り当てる必要があります。詳しい手順については、[プランの呼び出しを設定する](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>1 人のユーザーに電話システムとプランの呼び出しのライセンスを割り当てる方法

手順は、Office 365 のライセンスを割り当てると同じです。[割り当てまたは一般法人向け Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>一括電話システムとプランの呼び出しのライセンスを割り当てる方法

1. **Microsoft Online Services サインイン アシスタント IT プロフェッショナル向け RTW**をインストールします。インストールされているモジュールを作成されていない場合[Microsoft Online Services サインイン アシスタント IT プロフェッショナル RTW の](https://go.microsoft.com/fwlink/?LinkId=625123)ダウンロードを参照してください。
    
2. インストール、 **Windows Azure Active Directory モジュール**。インストールされているモジュールを作成されていない場合ダウンロードの手順とコマンドレットの書式には、[管理 Windows PowerShell を使用して Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。
    
3. インストールされているモジュールを取得するには、ユーザーのライセンスを割り当てる Windows PowerShell コマンド プロンプトと、次の構文を使用します。
    
  この例では、**電話システム**と、**国内通話プラン**のライセンスと**Enterprise E3 ライセンス**を割り当てます。
    
  ライセンスの名前や、スクリプトで製品名斜体のテキストに表示されます (例の後、**電話システムでは、製品名のプランの呼び出しまたは Sku のスクリプトの実行に使用**することを参照)。
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>電話システムとプランの呼び出しの製品名や Sku のスクリプトの実行を使用します。

|**製品名**|**SKU 部品名**|
|:-----|:-----|
|[エンタープライズの E5 (された電話システムで対応)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business Online スタンドアロン プラン 2  <br/> |MCOSTANDARD  <br/> |
|電話システム  <br/> |MCOEV  <br/> |
|国際通話プラン  <br/> |MCOPSTN2  <br/> |
|国内通話プラン  <br/> |MCOPSTN1  <br/> |
|通信を加算したもの  <br/> |MCOPSTNPP  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>電話会議の場合: のヒントとライセンスの割り当てについてスクリプト

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>電話会議ライセンスを割り当てる前に知っておくべきこと

- **サードパーティ電話会議プロバイダー**:**電話会議**のライセンスを割り当てると、サードパーティ電話会議プロバイダーを使用するようにセットアップする他のユーザーが既にと、この電話会議として Microsoft を使用することを変更します。プロバイダーです。サードパーティ プロバイダーに戻るには、これらを変更できます。
    
- 次の手順:**電話会議**ライセンスを割り当てたら、電話会議プロバイダーを割り当てるする必要があります。{次のいずれかを行います。}
    
  - [電話会議プロバイダーとして Microsoft を割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - または、[電話会議プロバイダーとしてサードパーティの割り当て](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>1 人のユーザーに電話会議のライセンスを割り当てる方法

手順は、Office 365 のライセンスを割り当てると同じです。[割り当てまたは一般法人向け Office 365 のライセンスを削除する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>一括で電話会議ライセンスを割り当てる方法

1. ダウンロードして、 [Microsoft Online Services サインイン アシスタント IT プロフェッショナル RTW を](https://go.microsoft.com/fwlink/?LinkId=625123)インストールします。
    
2. ダウンロード、インストール、 **Windows Azure Active Directory モジュール**。ダウンロードの手順とコマンドレットの書式には、[管理 Windows PowerShell を使用して Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。
    
    インストールされているモジュールを取得するには、ユーザーのライセンスを割り当てる Windows PowerShell コマンド プロンプトと、次の構文を使用します。
    
    斜体のテキストのスクリプトの商品名またはライセンスの名前が表示されます。[電話会議の製品名または Sku のスクリプトの実行するため](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)のすべての製品名を参照してください。
    
    この例では、音声会議ライセンスをと共に Enterprise E3 ライセンスを割り当てます。
    
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>音声会議製品名または Sku のスクリプトの実行を使用します。
<a name="sku"> </a>

|**製品名**|**SKU 部品名**|
|:-----|:-----|
|電話会議  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online スタンドアロン プラン 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|エンタープライズの E5 (せずに電話会議の場合)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|(電話会議) がエンタープライズ E5  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## <a name="communications-credits"></a>通信を加算したもの

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>通信クレジットのライセンスを割り当てる前に知っておくべきこと

- **エンタープライズ E5 顧客**: 場合でも、ユーザーには、エンタープライズ E5 ライセンスが割り当てられているが、まだをお勧めするライセンスを割り当てることに**コミュニケーションを加算したもの**です。
    
- **次のステップ**: これらのライセンスの割り当て後を組織の電話番号を取得し、[これらの数値を組織のユーザーに割り当てる必要があります。詳しい手順については、[プランの呼び出しを設定する](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>1 人のユーザーに通信クレジットのライセンスを割り当てる方法

手順は、Office 365 のライセンスを割り当てると同じです。[割り当てまたは一般法人向け Office 365 のライセンスを削除する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>一括で通信クレジットのライセンスを割り当てる方法

**電話会議**ライセンスを割り当てるためのサンプル スクリプトを参照してください。**通信クレジット**のライセンスの割り当てについての情報を更新します。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[プランの呼び出しを設定します。](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[金を追加およびクレジットの通信を管理します。](add-funds-and-manage-communications-credits.md)
  