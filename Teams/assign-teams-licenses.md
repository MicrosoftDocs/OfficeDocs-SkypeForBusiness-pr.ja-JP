---
title: チームのライセンスを割り当てる
author: lolaj
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: mikedav
description: オーディオ会議、電話システムのような機能や、通話プランは、ライセンスを割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 078db13179f0e33cb950c00ea58e76f11c8eb405
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30127631"
---
# <a name="assign-microsoft-teams-licenses"></a>マイクロソフトのチームのライセンスを割り当てる

オーディオ会議、電話システム、および計画を呼び出すような機能をユーザーにライセンスを割り当てることができます。 この資料では、一括では個々 のユーザーに対してこれらのライセンスを追加する方法について説明します。 

> [!IMPORTANT]
> 参照してください[マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)についてはどのようなライセンスを購入する必要があり、Office 365 によって、それらを購入する方法を計画、オーディオ会議、フリー ダイヤル番号、および社内外の電話番号を呼び出すこと、ユーザーが取得するためです。

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト

ここでは、オーディオ会議、電話システム、および計画を呼び出してライセンスを割り当てる前に知っておく必要があります。

- **使用してオンプレミス ハイブリッド ユーザーに PSTN 接続しますか。** その場合は、のみ、電話システムのライセンスを割り当てる必要があります。 割り当てる必要がありますいない呼び出して計画します。

- **ライセンスの割り当て後の待機時間**: Office 365 とマイクロソフトのチームとの間の遅延時間のために割り当てる計画を呼び出してライセンスを割り当てると、ユーザーには、最大で 24 時間をかかることができます。 24 時間後に計画を呼び出すことがユーザーに割り当てされていない、[ビジネス製品の管理のヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。

- **エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。

- **次の手順**: ユーザーに通話プランのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>1 人のユーザーを呼び出すことを計画し、電話システムのライセンスを割り当てる

手順は Office 365 ライセンスを割り当てる場合と同じです。 「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>一括を呼び出すことを計画し、電話システムのライセンスを割り当てる

1. Microsoft オンライン サービス サインイン アシスタント RTW の IT プロフェッショナルのためにインストールします。 このモジュールがインストールされていない場合は、 [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) を参照してダウンロードしてください。

2. Windows Azure Active Directory のモジュールをインストールします。 このモジュールがインストールされていない場合は、 ダウンロードの手順とコマンドレットの構文については、 [Windows PowerShell を使用して AD を Azure の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。

3. モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。

この例では、 Enterprise E3 ライセンス と、 電話システム および 国内通話プラン ライセンスを割り当てています。

斜体が (を参照してください、[電話システムおよび製品名の計画を呼び出すまたは Sku のスクリプト作成に使用](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)することも、例の後) では、ライセンスの名前、またはスクリプト内で製品名が一覧表示されます。

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>スクリプトで使用される電話システムと通話プランの製品名または SKU

| 製品名 | SKU 部品名 |
|--------------|---------------|
| エンタープライズ E5 (電話システムあり) | ENTERPRISEPREMIUM |
| エンタープライズ E3 | ENTERPRISEPACK | 
| エンタープライズ E1 | STANDARDPACK | 
| 電話システム | MCOEV |
| 国内 & の国際通話プラン | MCOPSTN2 |
| 国内の呼び出し (u. s./PR/CA で、eu 加盟国のユーザーまたは 1 か月あたりの 1200 分のユーザーまたは 1 か月あたり 3000 分) の計画 | MCOPSTN1 |
| 国内の呼び出し (120 分単位/月単位のユーザーのそれぞれの国) の計画 </br>*注: この計画では米国で*。 | MCOPSTN5 |
| 国内の呼び出し (240 分単位/月単位のユーザーのそれぞれの国) の計画 </br>*注: この計画では米国で*。 | MCOPSTN6 |
| コミュニケーション クレジット | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>オーディオ会議: ヒントとライセンスの割り当てのためのスクリプト

ここでは、オーディオ会議のライセンスを割り当てる前に知っておく必要があります。

- **サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 電話会議ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。 この設定を変更して、サードパーティ プロバイダーに戻すことができます。

- **次の手順**: オーディオ会議のライセンスを割り当てると、する必要があります、オーディオ会議プロバイダーを割り当てます。 [オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>オーディオ会議のライセンスを 1 つのユーザーに割り当てる

手順は Office 365 ライセンスを割り当てる場合と同じです。 「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>一括で電話会議のライセンスを割り当てる

1. [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。

2. Windows Azure Active Directory モジュール をダウンロードしてインストールします。 ダウンロードの手順とコマンドレットの構文については、 [Windows PowerShell を使用して AD を Azure の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。

モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。

イタリック体では、ライセンスの名前、またはスクリプト内で製品名が一覧表示されます。 [オーディオ会議の製品名やスクリプト作成に使用する製品](#audio-conferencing-product-names-or-skus-used-for-scripting)のすべての製品名を参照してください。

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>オーディオ会議の製品名または SKU のスクリプト作成に使用

| 製品名 | SKU 部品名 |
|--------------|---------------|
| オーディオ会議 (サブスクリプション) | MCOMEETADV | 
| オーディオ会議を支払うあたり 1 分 (従量)</br>*注: 通信のクレジットを設定し、有効にする必要があります*。 | MCOMEETACPEA |
| エンタープライズ E1 | STANDARDPACK | 
| エンタープライズ E3 | ENTERPRISEPACK |
| Enterprise E5 (電話会議なし) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (電話会議あり) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>コミュニケーション クレジット

ここでは、通信のクレジットのライセンスを割り当てる前に知っておく必要があります。

- **E5 のエンタープライズのお客様**: ユーザーがエンタープライズ E5 のライセンスを割り当てられている場合でもをお勧めするユーザーを割り当てる通信のクレジットのライセンスです。

- **次のステップ**: これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。

## <a name="assign-a-communications-credits-license-to-one-user"></a>通信のクレジットのライセンスを 1 つのユーザーに割り当てる

手順は Office 365 ライセンスを割り当てる場合と同じです。 「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

## <a name="assign-communications-credits-licenses-in-bulk"></a>大量の通信のクレジットのライセンスを割り当てる

電話会議ライセンスを割り当てるサンプル スクリプトを確認します。 その情報を、 通信クレジットのライセンスを割り当てるための情報で更新します。

## <a name="related-topics"></a>関連トピック

[通話プランの設定](set-up-calling-plans.md)
</br>
[資金を追加してコミュニケーション クレジットを管理する](add-funds-and-manage-communications-credits.md)
