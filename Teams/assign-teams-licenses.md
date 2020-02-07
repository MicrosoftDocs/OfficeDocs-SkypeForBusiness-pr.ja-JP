---
title: Teams のライセンスを割り当てる
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 電話会議、電話システム、通話プランなどの機能にライセンスを割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 967b67c1d8bc92009e1319260373c9b8abc52b99
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826315"
---
# <a name="assign-microsoft-teams-licenses"></a>Microsoft Teams ライセンスを割り当てる

電話会議、電話システム、通話プランなどの機能については、ユーザーにライセンスを割り当てることができます。 この記事では、これらのライセンスを一括で追加する方法と個々のユーザー用に追加する方法について説明します。 

> [!IMPORTANT]
> 購入する必要があるライセンスと購入方法の詳細については、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。 Office 365 プランによっては、電話会議、無料電話番号、ビジネス以外の電話番号への通話が可能です。

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト

電話会議、電話システム、通話プランのライセンスを割り当てる前に知っておくべきことを以下に示します。

- **ハイブリッドユーザー用にオンプレミスの PSTN 接続を使用している場合** その場合は、電話システムのライセンスを割り当てる必要があります。 通話プランを割り当てることはできません。

- **ライセンスの割り当て後の待機時間**: Office 365 と Microsoft Teams の間の待機時間のため、ライセンスを割り当てた後にユーザーが通話プランを割り当てられるまでに最大24時間かかることがあります。 24時間後にユーザーに通話プランが割り当てられていない場合は、「一般[法人向け製品サポートへのお問い合わせ-管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」を参照してください。

- **エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。

- **次の手順**: ユーザーに通話プランのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>電話システムと通話プランのライセンスを1人のユーザーに割り当てる

手順は Office 365 ライセンスを割り当てる場合と同じです。 「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>電話システムと通話プランのライセンスを一括で割り当てる

1. IT プロフェッショナル向け Microsoft Online Service サインインアシスタントプロフェッショナル用 RTWHTTP://GO.MICROSOFT.COM/FWLINK/?LINKID=625123 をインストールします。 このモジュールがインストールされていない場合は、 [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) を参照してダウンロードしてください。

2. Windows Azure Active Directory モジュールをインストールします。 このモジュールがインストールされていない場合は、 ダウンロード手順とコマンドレットの構文については、「 [Windows PowerShell を使用した AZURE AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」を参照してください。

3. モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。

この例では、 Enterprise E3 ライセンス と、 電話システム および 国内通話プラン ライセンスを割り当てています。

スクリプトに含まれているライセンス名または製品名が斜体で表示されます (「[電話システムと通話プランの製品名、または](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)、例の後にスクリプトで使用される sku を参照してください)。

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
| 国内 & 国際通話プラン | MCOPSTN2 |
| 国内通話プラン (米国/PR/月額プランの場合はユーザーあたり、1ヶ月あたり3000分、EU 諸国の場合はユーザー/月あたり1200分) | MCOPSTN1 |
| 国内通話プラン (各国のユーザー/月あたり120分) </br>*注: このプランはご利用いただけません*。 | MCOPSTN5 |
| 国内通話プラン (各国のユーザー/月あたり240分) </br>*注: このプランはご利用いただけません*。 | MCOPSTN6 |
| コミュニケーション クレジット | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>電話会議: ライセンスを割り当てるためのヒントとスクリプト

電話会議ライセンスを割り当てる前に知っておく必要があることを以下に示します。

- **サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 電話会議ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。 この設定を変更して、サードパーティ プロバイダーに戻すことができます。

- **次の手順**: 電話会議ライセンスを割り当てると、電話会議プロバイダーを割り当てる必要があります。 「 [Microsoft を電話会議プロバイダーとして割り当てる](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>電話会議ライセンスを1人のユーザーに割り当てる

手順は Office 365 ライセンスを割り当てる場合と同じです。 「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>電話会議ライセンスを一括で割り当てる

1. [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。

2. Windows Azure Active Directory モジュール をダウンロードしてインストールします。 ダウンロード手順とコマンドレットの構文については、「 [Windows PowerShell を使用した AZURE AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」を参照してください。

モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。

スクリプト内のライセンス名または製品名が斜体で表示されます。 すべての製品名の[スクリプトに使用されている電話会議の製品名または sku](#audio-conferencing-product-names-or-skus-used-for-scripting)を参照してください。

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>スクリプトで使用される電話会議の製品名または SKU

| 製品名 | SKU 部品名 |
|--------------|---------------|
| 電話会議 (サブスクリプション) | MCOMEETADV | 
| 電話会議の1分あたりの料金 (プリペイド)</br>*注: 通信クレジットを設定して有効にする必要があり*ます。 | MCOMEETACPEA |
| エンタープライズ E1 | STANDARDPACK | 
| エンタープライズ E3 | ENTERPRISEPACK |
| Enterprise E5 (電話会議なし) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (電話会議あり) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>コミュニケーション クレジット

通信クレジットのライセンスを割り当てる前に知っておくべきことを以下に示します。

- **Enterprise e5 のお客様**: ユーザーに enterprise e5 ライセンスが割り当てられている場合でも、通信クレジットのライセンスを割り当てることをお勧めします。

- **次のステップ**: これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。

## <a name="assign-a-communications-credits-license-to-one-user"></a>1人のユーザーに通信クレジットのライセンスを割り当てる

手順は Office 365 ライセンスを割り当てる場合と同じです。 「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

## <a name="assign-communications-credits-licenses-in-bulk"></a>通信クレジットのライセンスを一括で割り当てる

電話会議ライセンスを割り当てるサンプル スクリプトを確認します。 その情報を、 通信クレジットのライセンスを割り当てるための情報で更新します。

## <a name="related-topics"></a>関連トピック

[通話プランの設定](set-up-calling-plans.md)
</br>
[資金を追加してコミュニケーション クレジットを管理する](add-funds-and-manage-communications-credits.md)
