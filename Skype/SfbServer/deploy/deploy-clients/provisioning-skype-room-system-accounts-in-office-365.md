---
title: Microsoft 365 および Office 365 での Skype Room System アカウントのプロビジョニング
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: dd79081c690863a5851295ab48a950b3f7af66af
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221851"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Microsoft 365 および Office 365 での Skype Room System アカウントのプロビジョニング
 
このトピックでは、Microsoft 365 または Office 365 での Skype Room System アカウントのプロビジョニングについて説明します。
  
次のセクションでは、Skype Room System アカウントのプロビジョニングについて説明します。
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 および Office 365 の前提条件

オンラインテナントは、次の要件を満たしている必要があります。
  
- Microsoft 365 または Office 365 プランには、Skype for Business Online プラン2、または Office 365 E1、E3、または E5 を含める必要があります。 <br/>Skype for business Online プランの詳細については、「 [skype For Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。
    
- テナントには、Skype for Business が有効になっている会議機能が必要です。
    
- テナントでは、Exchange Online が有効になっている必要があります。 
    
- テナントのリモート管理者は、次の PowerShell アクセス権を持っている必要があります。
    
  - Exchange リモート PowerShell アクセス
    
  - Skype for Business Online のリモート PowerShell アクセス
    
  - Microsoft 365 または Office 365 のディレクトリアクセスにアクセスするための windows PowerShell 用 windows Azure Active Directory モジュール
    
Skype Room アカウントの場合は、次のライセンスが必要です。
  
- Skype 会議を有効にするには、Skype for Business Online プラン2または Office 365 E1 または E3 ライセンスが必要です。
    
- 電話番号で会議室を有効にできるように、エンタープライズ Voip 機能を使用して会議室を entitle するために、電話システムライセンスまたは Office 365 E5 がある Skype for Business Online プラン2が必要です (1)。
    
- 会議からダイヤルイン機能が必要な場合は、電話会議と電話システムのライセンスが必要です。  会議からのダイヤルアウト機能が必要な場合は、国内または国内および国際通話プランが必要です。 
    
- アカウントは、リソースメールボックスアカウントとして構成する必要があるため、Skype Room アカウントには Exchange Online ライセンスは必要ありません。
    
## <a name="provisioning-overview"></a>プロビジョニングの概要

次の図は、Skype Room System アカウントのプロビジョニングフローの概要を示しています。
  
![Skype Room System のプロビジョニング手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>新しい会議室を識別する

スケジュール機能を提供する Exchange のリソースルームメールボックスが既にあるか、Skype Room System の展開を容易にするために初めてリソースメールボックスを作成している可能性があります。 いずれの場合も、テナントで使用する会議室のアカウントを特定する必要があります。 「Exchange Online のプロビジョニング」および「Skype for Business のプロビジョニング」セクションでは、両方の種類のアカウントについてのガイダンスを提供します。 たとえば、次の2つのルームがあり、両方に対して Skype Room System を展開したいとします。
  
- 既存のリソースメールボックスアカウント: confrm1@contoso.onmicrosoft.com
    
- 新しいリソースメールボックスアカウント: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online のプロビジョニング

最初に、トピック「 [Exchange Online powershell に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)」の手順に従って Exchange online powershell に接続します。
  
Skype Room System の既存のリソース会議のメールボックスアカウントを設定するには、Exchange Online PowerShell で次のコマンドを実行します。
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Skype Room System の新しい Exchange リソースメールボックスアカウントを作成するには、Exchange Online PowerShell で次のコマンドを実行します。
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

上記のコマンドは、アカウントを有効にすることによって、Skype Room System の使用のための新しい Exchange リソースメールボックスアカウントをセットアップまたは作成します。
  
メールボックスを作成したら、Exchange Online PowerShell で、CalendarProcessing コマンドレットを使用してメールボックスを構成できます。 詳細については、単一フォレストのオンプレミス展開の手順 3 ~ 6 を参照してください。

## <a name="assigning-a-skype-for-business-online-license"></a>Skype for Business Online ライセンスの割り当て

「Microsoft 365 for business または[skype For business アドオンライセンス](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)[のライセンスを割り当てるまたは削除](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)する」に記載されているように、microsoft 365 管理ポータルを使用して skype For business online (プラン 2) または skype For business online (plan 3) ライセンスを割り当てることができるようになりました。 
  
Skype for business Online のライセンスを割り当てた後は、Skype for Business クライアントを使用してログインし、アカウントがアクティブであることを確認できます。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online のプロビジョニング

前に示したように、リソース会議のメールボックスのアカウントを作成して有効にした後、Skype For Business Online のアカウントのライセンスを取得した後、Windows Azure Active Directory フォレストを使用して Exchange Online フォレストから Skype for Business Online フォレストにアカウントが同期されます。 Skype for Business Online プールで Skype Room System アカウントをプロビジョニングするには、次の手順が必要です。 これらの手順は、既存のリソースメールボックスアカウントまたは新しく作成されたアカウント (confrm1 または confrm2) の両方で同じです。これらのアカウントは、Exchange Online で有効になると、同じ方法で Skype for Business Online と同期されます。
  
1. リモート PowerShell セッションを作成します。 Skype for Business Online Connector モジュールと Microsoft Online Services サインインアシスタントをダウンロードして、コンピューターが構成されていることを確認する必要があることに注意してください。 詳細については、「 [Windows PowerShell 用にコンピューター](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をセットアップする」を参照してください。
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Skype for business の Skype Room System アカウントを有効にするには、次のコマンドを実行します。
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    このプロパティを取得するには、次のコマンドを使用して、Skype for Business ユーザーが既存のアカウントのいずれかに所属している RegistrarPool アドレスを取得します。
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Skype Room System アカウントでは、多要素認証 (MFA) はサポートされていません。 

## <a name="password-expiration"></a>パスワードの期限切れ

Microsoft 365 または Office 365 では、ユーザーアカウントすべての既定のパスワードの有効期限ポリシーは、別のパスワードの有効期限ポリシーを構成しない限り、90日間です。 Skype Room System アカウントの場合は、次の手順を使用してパスワードを無期限に設定することができます。
  
1. テナント全体管理者の資格情報を使用して、Windows Azure Active Directory セッションを作成します。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 次のコマンドを使用して、以前に作成した Skype Room System room アカウントのパスワードを無期限に設定します。
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

詳細については、「 [Windows PowerShell 用にコンピューター](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をセットアップする」を参照してください。
  
## <a name="validate"></a>検証

検証のために、任意の Skype for Business クライアントを使用して、作成したアカウントにサインインできる必要があります。

