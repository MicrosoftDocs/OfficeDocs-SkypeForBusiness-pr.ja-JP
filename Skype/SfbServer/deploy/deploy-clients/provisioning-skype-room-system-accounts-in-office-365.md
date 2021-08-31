---
title: '[Skypeのルーム システム アカウントMicrosoft 365プロビジョニングOffice 365'
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: このトピックを参照して、SkypeまたはSkypeの Room System アカウントのプロビジョニングMicrosoft 365説明Office 365。
ms.openlocfilehash: e3976d5763128354c934f477003532bf6bbcd3f6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731106"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>[Skypeのルーム システム アカウントMicrosoft 365プロビジョニングOffice 365
 
このトピックを参照して、SkypeまたはSkypeの Room System アカウントのプロビジョニングMicrosoft 365説明Office 365。
  
以下のセクションでは、Room System Skypeプロビジョニングについて説明します。
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365とOffice 365前提条件

オンライン テナントは、次の要件を満たしている必要があります。
  
- オンライン Microsoft 365またはOffice 365プランには、オンライン Skype for Business 2、または E3 または E5 Office 365 E1含める必要があります。 <br/>オンライン プランのSkype for Business詳細については、「オンライン サービスの[Skype for Business」を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。
    
- テナントの会議機能が有効になっているSkype for Businessがあります。
    
- テナントが有効になっているExchange Online必要があります。 
    
- テナントのリモート管理者は、次の PowerShell アクセス権を持っている必要があります。
    
  - Exchangeリモート PowerShell アクセス
    
  - Skype for Businessオンライン のリモート PowerShell アクセス
    
  - Windows Azure Active Directoryディレクトリ アクセスWindows PowerShellアクセスMicrosoft 365モジュールOffice 365モジュール
    
Room アカウントSkype、次のライセンスが必要です。
  
- 会議Skype for Business有効にするには、オンライン プラン 2 または Office 365 E1 E3 ライセンスがSkypeです。
    
- 電話番号で部屋を有効にできるよう、エンタープライズ VoIP 機能を持つ部屋に資格を与えるには、電話システム ライセンスまたは Office 365 E5 を持つ Skype for Business Online Plan 2 が必要です (1)。
    
- 会議からダイヤルイン機能が必要な場合は、電話会議と会議ライセンス電話システムがあります。  会議からダイヤルアウト機能が必要な場合は、国内または国内および国際通話プランが必要です。 
    
- アカウントExchange Onlineリソース メールボックス アカウントとして構成する必要Skype Room アカウントのライセンスは必要ありません。
    
## <a name="provisioning-overview"></a>プロビジョニングの概要

次の図は、Room System アカウントのプロビジョニング フロー Skype概要を示しています。
  
![SkypeRoom System Provisioning の手順。](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>新しい会議室を特定する

スケジュール機能を提供するリソース ルーム メールボックスが Exchange に既に存在している場合や、Room System の展開を容易にするためにリソース メールボックスを初めて作成Skype可能性があります。 いずれにしても、テナントで使用するルーム アカウントを特定する必要があります。 [プロビジョニングExchange OnlineおよびSkype for Businessのセクションでは、両方の種類のアカウントに関するガイダンスを提供します。 たとえば、次の 2 つのルームがある場合、両方のルーム システムSkype展開するとします。
  
- 既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com
    
- 新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Onlineプロビジョニング

最初に、トピックExchange Online手順に従って PowerShell に接続し、PowerShell Connect[をExchange Onlineします](/powershell/exchange/connect-to-exchange-online-powershell)。
  
ルーム システムの既存のリソース ルーム メールボックス アカウントをSkype、PowerShell で次のコマンドExchange Onlineします。
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Room System 用の新Exchangeリソース メールボックス アカウントをSkypeするには、PowerShell で次のコマンドExchange Onlineします。
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

前のコマンドは、アカウントを有効にすることで、Exchange Room System の使用状況にSkypeリソース メールボックス アカウントをセットアップまたは作成します。
  
メールボックスを作成した後、PowerShell で Set-CalendarProcessingコマンドレットExchange Onlineメールボックスを構成できます。 詳細については、「単一フォレストのオンプレミス展開」の手順 3 ~ 6 を参照してください。

## <a name="assigning-a-skype-for-business-online-license"></a>オンライン ライセンスSkype for Business割り当てる

Skype for Business Online (プラン 2) または Skype for Business Online (プラン 3) ライセンスを割り当てるには、「ビジネス向けまたは Skype for Business アドオン ライセンスの Microsoft 365 のライセンスを割り当[](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)てるまたは削除する」の説明に従って[、Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)管理ポータルを使用します。 
  
Skype for Business Online のライセンスを割り当てると、任意のクライアントを使用してアカウントがアクティブSkype for Businessできます。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Businessオンライン プロビジョニング

前に示すようにリソース ルーム メールボックス アカウントを作成して有効にし、Skype For Business Online のアカウントのライセンスを取得すると、Windows Azure Active Directory フォレストを使用してアカウントが Exchange Online フォレストから Skype for Business Online フォレストに同期されます。 次の手順は、オンライン プールで Skype Room System アカウントをプロビジョニングSkype for Business必要です。 これらの手順は、Exchange Online で有効になると、両方のアカウントが同じ方法で Skype for Business Online に同期されるので、既存のリソース メールボックス アカウントまたは新しく作成されたアカウント (confrm1 または confrm2) の両方で同じです。
  
1. リモート PowerShell セッションを作成します。 PowerShell モジュールをダウンロードする[必要Teams注意してください](/microsoftteams/teams-powershell-install)。
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. ルーム システム アカウントをSkypeするには、次Skype for Businessコマンドを実行します。
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    次のコマンドを使用して、Skype for Businessユーザーが既存のアカウントの 1 つからアクセスしている RegistrarPool アドレスを取得できます。
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>多要素認証 (MFA) は、ルーム システム アカウントSkypeサポートされていません。 

## <a name="password-expiration"></a>パスワードの期限切れ

このMicrosoft 365またはOffice 365、別のパスワード有効期限ポリシーを構成しない限り、すべてのユーザー アカウントの既定のパスワード有効期限ポリシーは 90 日間です。 ルーム Skypeアカウントの場合は、次の手順で [パスワードの有効期限が切れることはありません] 設定を選択できます。
  
1. テナントのグローバルWindows Azure Active Directory資格情報を使用して、新しいセッションを作成します。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 次のコマンドを使用して、以前に作成Skypeルーム システム ルーム アカウントの [パスワードの有効期限が切れることはありません] 設定を設定します。
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

詳細については、「コンピューターのセットアップ[」を参照Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="validate"></a>検証

検証のために、作成したアカウントにサインインするために、Skype for Businessクライアントを使用できる必要があります。