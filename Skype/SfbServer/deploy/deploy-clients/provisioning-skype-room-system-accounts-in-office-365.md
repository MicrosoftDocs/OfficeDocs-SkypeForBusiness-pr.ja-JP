---
title: Microsoft 365 および Microsoft 365 および Office 365 での Skype ルーム システム アカウントのプロビジョニング
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Microsoft 365 または Office 365 での Skype Room System アカウントのプロビジョニングについて説明します。
ms.openlocfilehash: 94390effb246a37745d797289c1146ed3d347604
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093521"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Microsoft 365 および Microsoft 365 および Office 365 での Skype ルーム システム アカウントのプロビジョニング
 
Microsoft 365 または Office 365 での Skype Room System アカウントのプロビジョニングについて説明します。
  
次のセクションでは、Skype Room System アカウントのプロビジョニングについて説明します。
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 および Office 365 の前提条件

オンライン テナントは、次の要件を満たしている必要があります。
  
- Microsoft 365 または Office 365 プランには、Skype for Business Online プラン 2、または Office 365 E1、E3、E5 が含まれる必要があります。 <br/>Skype for Business Online プランの詳細については [、「Skype for Business Online Service Description」を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。
    
- テナントで Skype for Business の会議機能が有効になっている必要があります。
    
- テナントで Exchange Online が有効になっている必要があります。 
    
- テナントのリモート管理者は、次の PowerShell アクセス権を持っている必要があります。
    
  - Exchange リモート PowerShell アクセス
    
  - Skype for Business Online リモート PowerShell アクセス
    
  - Microsoft 365 または 365 ディレクトリ アクセスWindows PowerShellアクセスする Windows Azure Active Directory モジュールOffice Windows Azure Active Directory モジュール
    
Skype Room アカウントでは、次のライセンスが必要です。
  
- Skype 会議を有効にするには、Skype for Business Online プラン 2 または Office 365 E1 または E3 ライセンスが必要です。
    
- 電話番号で部屋を有効にできるよう、エンタープライズ VoIP 機能を持つ部屋に資格を与えるには、電話システム ライセンスまたは Office 365 E5 を持つ Skype for Business Online プラン 2 が必要です (1)。
    
- 会議からダイヤルイン機能が必要な場合は、電話会議と電話システム ライセンスが必要です。  会議からダイヤルアウト機能が必要な場合は、国内または国内および国際通話プランが必要です。 
    
- アカウントをリソース メールボックス アカウントとして構成する必要がある場合、Exchange Online ライセンスは Skype Room アカウントには必要ありません。
    
## <a name="provisioning-overview"></a>プロビジョニングの概要

次の図は、Skype Room System アカウントのプロビジョニング フローの概要を示しています。
  
![Skype Room System Provisioning の手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>新しい会議室を特定する

スケジュール機能を提供するリソース ルーム メールボックスが Exchange に既に存在している場合や、Skype Room System の展開を容易にするためにリソース メールボックスを初めて作成する場合があります。 いずれにしても、テナントで使用するルーム アカウントを特定する必要があります。 Exchange Online Provision セクションと Skype for Business Provision セクションでは、両方の種類のアカウントに関するガイダンスを提供します。 たとえば、次の 2 つのルームがある場合、両方に Skype Room System を展開するとします。
  
- 既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com
    
- 新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online プロビジョニング

最初に、「Exchange Online PowerShell に接続する」の手順に従って [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。
  
Skype Room System の既存のリソース ルーム メールボックス アカウントを設定するには、Exchange Online PowerShell で次のコマンドを実行します。
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Skype Room System 用の新しい Exchange リソース メールボックス アカウントを作成するには、Exchange Online PowerShell で次のコマンドを実行します。
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

前のコマンドでは、アカウントを有効にすることで、Skype Room System の使用状況に合った新しい Exchange リソース メールボックス アカウントを設定または作成します。
  
メールボックスを作成した後、Exchange Online PowerShell の Set-CalendarProcessingコマンドレットを使用してメールボックスを構成できます。 詳細については、「単一フォレストのオンプレミス展開」の手順 3 ~ 6 を参照してください。

## <a name="assigning-a-skype-for-business-online-license"></a>Skype for Business Online ライセンスの割り当て

これで、「ビジネス向け Microsoft 365 または Skype for Business アドオン ライセンスのライセンスの割り当てまたは削除」の説明に従って [、Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) 管理ポータルを使用して、Skype for Business Online (プラン 2) または [Skype for Business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Online (プラン 3) ライセンスを割り当てできます。 
  
Skype for Business Online のライセンスを割り当てると、Skype for Business クライアントを使用してアカウントがアクティブな状態でログインして検証できます。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online プロビジョニング

前に示すようにリソース ルーム メールボックス アカウントを作成して有効にし、Skype For Business Online のアカウントをライセンスした後、アカウントは Windows Azure Active Directory フォレストを使用して Exchange Online フォレストから Skype for Business Online フォレストに同期します。 Skype for Business Online プールで Skype Room System アカウントをプロビジョニングするには、次の手順が必要です。 これらの手順は、既存のリソース メールボックス アカウントまたは新しく作成されたアカウント (confrm1 または confrm2) の両方で同じです。Exchange Online で有効にすると、両方のアカウントが同じ方法で Skype for Business Online に同期されます。
  
1. リモート PowerShell セッションを作成します。 Teams [PowerShell](/microsoftteams/teams-powershell-install)モジュールをダウンロードする必要があります。
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Skype for Business の Skype Room System アカウントを有効にするには、次のコマンドを実行します。
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    次のコマンドを使用して、Skype for Business ユーザーが既存のアカウントの 1 つからホームである RegistrarPool アドレスを取得するには、次のコマンドを使用してこのプロパティを返します。
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>多要素認証 (MFA) は、Skype Room System アカウントではサポートされていません。 

## <a name="password-expiration"></a>パスワードの期限切れ

Microsoft 365 または Office 365 では、異なるパスワード有効期限ポリシーを構成しない限り、すべてのユーザー アカウントの既定のパスワード有効期限ポリシーは 90 日間です。 Skype Room System アカウントの場合は、次の手順で [パスワードの有効期限が切れることはありません] 設定を選択できます。
  
1. テナントのグローバル管理者資格情報を使用して、Windows Azure Active Directory セッションを作成します。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 次のコマンドを使用して、以前に作成した Skype Room System ルーム アカウントの [パスワードの有効期限が切れることはありません] 設定を設定します。
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

詳細については、「コンピューターの[セットアップ」を参照Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="validate"></a>検証

検証のために、Skype for Business クライアントを使用して、作成したアカウントにサインインできる必要があります。