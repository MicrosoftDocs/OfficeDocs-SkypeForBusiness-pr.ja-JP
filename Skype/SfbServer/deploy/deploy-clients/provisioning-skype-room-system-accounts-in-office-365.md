---
title: Microsoft 365 および Office 365 での Skype Room System アカウントのプロビジョニング
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
description: このトピックでは、Microsoft 365 または Office 365 での Skype Room System アカウントのプロビジョニングについて説明します。
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820847"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Microsoft 365 および Office 365 での Skype Room System アカウントのプロビジョニング
 
このトピックでは、Microsoft 365 または Office 365 での Skype Room System アカウントのプロビジョニングについて説明します。
  
次のセクションでは、Skype Room System アカウントのプロビジョニングについて説明します。
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 および Office 365 の前提条件

オンライン テナントは、次の要件を満たしている必要があります。
  
- Microsoft 365 または Office 365 プランには、Skype for Business Online プラン 2 または Office 365 E1、E3、E5 が含まれる必要があります。 <br/>Skype for Business Online プランの詳細については、Skype for Business Online サービスの説明 [を参照してください](https://technet.microsoft.com/library/jj822172.aspx)。
    
- テナントで Skype for Business の会議機能が有効になっている必要があります。
    
- テナントで Exchange Online が有効になっている必要があります。 
    
- テナントのリモート管理者は、次の PowerShell アクセス権を持っている必要があります。
    
  - Exchange リモート PowerShell アクセス
    
  - Skype for Business Online リモート PowerShell アクセス
    
  - Microsoft 365 または Windows PowerShell 365 ディレクトリ アクセスにアクセスOffice Windows Azure Active Directory モジュール
    
Skype Room アカウントでは、次のライセンスが必要です。
  
- Skype 会議を有効にするには、Skype for Business Online プラン 2 または Office 365 E1 または E3 ライセンスが必要です。
    
- 電話番号で有効にできるよう、エンタープライズ VoIP 機能を使用してルームに資格を与える場合は、電話システム ライセンスまたは Office 365 E5 を使用する Skype for Business Online プラン 2 (1) が必要です。
    
- 会議からダイヤルイン機能が必要な場合は、電話会議と電話システムのライセンスが必要です。  会議からダイヤルアウト機能が必要な場合は、国内または国内および国際通話プランが必要です。 
    
- Exchange Online ライセンスは、Skype Room アカウントには必要ありません。アカウントはリソース メールボックス アカウントとして構成する必要があります。
    
## <a name="provisioning-overview"></a>プロビジョニングの概要

次の図は、Skype Room System アカウントのプロビジョニング フローの概要を示しています。
  
![Skype Room System のプロビジョニング手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>新しい会議室を特定する

スケジュール機能を提供するリソース ルーム メールボックスが Exchange に既に存在する場合や、Skype Room System の展開を容易にするためにリソース メールボックスを初めて作成する場合があります。 いずれにしても、テナントで使用するルーム アカウントを特定する必要があります。 Exchange Online Provision セクションと Skype for Business Provision セクションでは、両方の種類のアカウントに関するガイダンスを提供します。 たとえば、次の 2 つのルームがある場合、両方のルームに Skype Room System を展開するとします。
  
- 既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com
    
- 新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online のプロビジョニング

まず、トピック「Exchange Online PowerShell に接続する」の手順に従って [、Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
  
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

前のコマンドでは、アカウントを有効にすることで、Skype Room System を使用するための新しい Exchange リソース メールボックス アカウントをセットアップまたは作成します。
  
メールボックスを作成した後、Exchange Online PowerShell で Set-CalendarProcessing コマンドレットを使用してメールボックスを構成できます。 詳細については、単一フォレストのオンプレミス展開の手順 3 . ~ 6. を参照してください。

## <a name="assigning-a-skype-for-business-online-license"></a>Skype for Business Online ライセンスの割り当て

Microsoft 365 管理ポータルを使用して、Skype for Business Online (プラン 2) または Skype for Business Online (プラン 3) のライセンスを割り当て [、Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) または [Skype for Business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)アドオン ライセンスの割り当てまたは削除を行う方法を説明します。 
  
Skype for Business Online のライセンスを割り当てると、任意の Skype for Business クライアントを使用してログインし、アカウントがアクティブな状態を検証できます。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online のプロビジョニング

前に示すようにリソース ルーム メールボックス アカウントを作成して有効にし、Skype For Business Online のアカウントのライセンスを取得すると、アカウントは Windows Azure Active Directory フォレストを使用して Exchange Online フォレストから Skype for Business Online フォレストに同期されます。 Skype for Business Online プールで Skype Room System アカウントをプロビジョニングするには、次の手順が必要です。 これらの手順は、既存のリソース メールボックス アカウントと新しく作成されたアカウント (confrm1 または confrm2) の両方で同じです。Exchange Online で有効にすると、両方のアカウントが同じ方法で Skype for Business Online に同期されます。
  
1. リモート PowerShell セッションを作成します。 Skype for Business Online Connector モジュールと Microsoft Online Services Sign-In アシスタントをダウンロードし、コンピューターが構成されていることを確認する必要があります。 詳細については、「コンピューターのセットアップ[」を参照Windows PowerShell。](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Skype for Business の Skype Room System アカウントを有効にするには、次のコマンドを実行します。
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    次のコマンドを使用してこのプロパティを返し、Skype for Business ユーザーが存在する RegistrarPool アドレスを既存のアカウントの 1 つから取得できます。
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>多要素認証 (MFA) は、Skype Room System アカウントではサポートされていません。 

## <a name="password-expiration"></a>パスワードの期限切れ

Microsoft 365 または Office 365 では、別のパスワード有効期限ポリシーを構成しない限り、すべてのユーザー アカウントの既定のパスワード有効期限ポリシーは 90 日間です。 Skype Room System アカウントの場合は、次の手順で [パスワードの有効期限が切れることはありません] 設定を選択できます。
  
1. テナントのグローバル管理者の資格情報を使用して、Windows Azure Active Directory セッションを作成します。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 次のコマンドを使用して、以前に作成した Skype Room System ルーム アカウントの [パスワードを期限切れにしない] 設定を設定します。
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

詳細については、「コンピューターのセットアップ[」を参照Windows PowerShell。](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  
## <a name="validate"></a>検証

検証のために、任意の Skype for Business クライアントを使用して、作成したアカウントにサインインできる必要があります。

