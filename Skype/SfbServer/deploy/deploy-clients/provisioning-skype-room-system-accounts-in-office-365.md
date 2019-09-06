---
title: Skype Room System アカウントの Office 365 でのプロビジョニング
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: d247983647641c91376c99bed3a13606027a7e11
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775391"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Skype Room System アカウントの Office 365 でのプロビジョニング
 
このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。
  
以下のセクションでは、Office 365 テナントでの Skype Room System アカウントのプロビジョニングについて説明します。
  
## <a name="office-365-prerequisites"></a>Office 365 の前提条件

オンライン テナントは、次の要件を満たしている必要があります。
  
- Office 365 プランには、Skype for Business Online Plan 2、または Office 365 E1、E3、または E5 が含まれている必要があります。 <br/>Skype for Business Online プランの詳細については、「 [skype For Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。
    
- テナントには、Skype for Business が有効になっている会議機能が含まれている必要があります。
    
- テナントで、Exchange Online を有効にしていること。 
    
- テナントのリモート管理者に次の PowerShell アクセス権があること。
    
  - Exchange Remote PowerShell へのアクセス権
    
  - Skype for Business Online のリモート PowerShell アクセス
    
  - Office 365 ディレクトリアクセスにアクセスするための windows PowerShell 用 windows Azure Active Directory モジュール
    
Skype Room アカウントの場合は、次のライセンスが必要です。
  
- Skype 会議を有効にするには、Skype for Business Online プラン2または Office 365 E1 または E3 ライセンスが必要です。
    
- エンタープライズ Voip 機能を使用して部屋を entitle し、会議室を電話番号で有効にできるようにするには、電話システムライセンスまたは Office 365 E5 が含まれる Skype for Business Online プラン2が必要です (1)。
    
- 会議からダイヤルイン機能が必要な場合は、電話会議と電話システムのライセンスが必要です。  会議からダイヤルアウト機能が必要な場合は、国内または国内の通話プランが必要です。 
    
- Skype Room アカウントの場合は、リソース メールボックス アカウントとして構成する必要があるため、Exchange Online ライセンスは不要です。
    
## <a name="provisioning-overview"></a>プロビジョニングの概要

次の図は、Office 365 での Skype Room System アカウントのプロビジョニングフローの概要を示しています。
  
![O365 の Skype Room System のプロビジョニング手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>新しい会議ルームを特定する

スケジュール機能を提供している Exchange のリソースルームメールボックスが既に存在する可能性があります。または、Skype Room System の展開を容易にするために初めてリソースメールボックスを作成している可能性があります。 いずれの場合も、テナントで使用するルーム アカウントを特定する必要があります。 Exchange Online のプロビジョニングと Skype for Business のプロビジョニングのセクションでは、両方のアカウントのガイダンスを提供します。 たとえば、次の2つのルームを持っていて、両方の部屋の Skype Room System を展開したいとします。
  
- 既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com
    
- 新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online のプロビジョニング

まず、「 [Exchange Online powershell に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)」の手順に従って、Exchange online powershell に接続します。
  
Skype Room System の既存のリソースルームメールボックスアカウントを設定するには、Exchange Online PowerShell で次のコマンドを実行します。
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Skype Room System の新しい Exchange リソースメールボックスアカウントを作成するには、Exchange Online PowerShell で次のコマンドを実行します。
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

前のコマンドでは、アカウントを有効にすることによって、Skype Room システムの使用を目的とした新しい Exchange リソースメールボックスアカウントのセットアップまたは作成を行うことができます。
  
メールボックスを作成した後で、Exchange Online PowerShell の設定-CalendarProcessing コマンドレットを使用して、メールボックスを構成することができます。 詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。

## <a name="assigning-a-skype-for-business-online-license"></a>Skype for Business Online ライセンスを割り当てる

「一般法人向け Office 365 または Skype for Business アドオン[のライセンスの割り当てまたは削除](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)」の説明に従って、office 365 管理ポータルを使用して、Skype For business Online (プラン 2) または Skype For business Online (プラン 3) ライセンスを割り当てることができます。 [ライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。 
  
Skype for Business Online のライセンスを割り当てると、ログインして、Skype for Business クライアントを使ってアカウントがアクティブであることを確認することができます。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online のプロビジョニング

前に説明したように、リソースルームメールボックスアカウントを作成して有効にした後、Skype for business Online のアカウントのライセンスが付与されている場合、アカウントは Exchange Online フォレストから Skype for Business Online フォレストに同期します。Windows Azure Active Directory フォレスト。 Skype for Business Online プールで Skype Room System アカウントをプロビジョニングするには、次の手順を実行する必要があります。 この手順は、既存のリソースメールボックスアカウントと新しく作成されたアカウント (confrm1 または confrm2) のどちらにも同じです。 Exchange Online で有効にすると、これらの両方のアカウントが同じ方法で Skype for Business Online と同期されるため、次のようになります。
  
1. リモート PowerShell セッションを作成します。 Skype for Business Online Connector モジュールと Microsoft Online Services サインインアシスタントをダウンロードして、コンピューターが構成されていることを確認する必要があることに注意してください。 詳細については、「 [Windows PowerShell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Skype for Business の Skype Room System アカウントを有効にするには、次のコマンドを実行します。
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    このプロパティを返すには、次のコマンドを使用して、Skype for Business ユーザーが既存のアカウントのいずれかに所属している RegistrarPool アドレスを取得できます。
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>パスワードの有効期限

Office 365 では、別のパスワードの有効期限ポリシーを構成しない限り、すべてのユーザー アカウントのパスワードの有効期限ポリシーは、既定で 90 日間です。 Skype Room System アカウントの場合は、次の手順に従って [無期限パスワード] 設定を選択できます。
  
1. 管理者のグローバル資格情報を使用して、Windows Azure Active Directory セッションを作成します。
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 次のコマンドを使用して、以前に作成した Skype Room System room アカウントのパスワードを無期限に設定します。
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

詳細については、「 [Windows PowerShell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。
  
## <a name="validate"></a>有効性

検証のために、Skype for Business クライアントを使って、作成したアカウントにサインインできるようにする必要があります。

