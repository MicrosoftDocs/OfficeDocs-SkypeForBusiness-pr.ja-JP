---
title: Skype Room System アカウントの Office 365 でのプロビジョニング
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: a1b24e25236f221d280631efd83c0e83b7ae44f2
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839234"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Skype Room System アカウントの Office 365 でのプロビジョニング
 
このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。
  
次のセクションでは、Skype の部屋のシステム アカウントが、Office 365 テナントのプロビジョニングについて説明します。
  
## <a name="office-365-prerequisites"></a>Office 365 の前提条件

オンライン テナントは、次の要件を満たしている必要があります。
  
- Office 365 のプランは、プラン 2 のオンライン ビジネス、または Office 365 の E1、E3 E5 の Skype を含める必要があります。 <br/>Skype のビジネスのオンラインの計画の詳細については、 [Skype](https://technet.microsoft.com/library/jj822172.aspx)を参照してください。
    
- テナントには、会議の機能を有効にするビジネスのための Skype が必要です。
    
- テナントで、Exchange Online を有効にしていること。 
    
- テナントのリモート管理者に次の PowerShell アクセス権があること。
    
  - Exchange Remote PowerShell へのアクセス権
    
  - Skype ビジネス オンライン リモート PowerShell アクセス
    
  - Windows Azure Active ディレクトリ モジュールの Windows PowerShell に Office 365 のディレクトリ アクセス
    
Skype Room アカウントの場合は、次のライセンスが必要です。
  
- ビジネス オンライン計画 2 または Office 365 の E1、E3 のライセンスは、Skype は、Skype 会議を有効にする必要があります。
    
- 電話番号、部屋を有効にすることができますので、エンタープライズ VoIP 機能を備えた部屋を entitle、ビジネス オンライン プラン 2 には、電話システムのライセンスの Office 365 の E5、Skype は、必要な (1) です。
    
- 会議にダイヤルイン機能が必要な場合は、音声会議や電話システムのライセンスを必要があります。  会議からのダイヤル ・ アウト機能が必要な場合、国内または国内および海外を呼び出すことを計画する必要があります。 
    
- Skype Room アカウントの場合は、リソース メールボックス アカウントとして構成する必要があるため、Exchange Online ライセンスは不要です。
    
## <a name="provisioning-overview"></a>プロビジョニングの概要

次の図は、Office 365 のフローを提供する Skype の部屋のシステム アカウントの概要を説明します。
  
![O365 の Skype Room System のプロビジョニング手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>新しい会議ルームを特定する

すでにリソースの会議室メールボックス Exchange スケジュールの機能を提供するか、Skype ルーム システムの展開を容易にするために最初にリソース メールボックスを作成することがあります。 いずれの場合も、テナントで使用するルーム アカウントを特定する必要があります。 Exchange のオンライン提供とビジネスの準備セクションの Skype は、両方の種類のアカウントのためのガイダンスを提供します。 、たとえば次の 2 つの部屋があり、それらの両方に対して Skype ルームのシステムを導入したいと思います。
  
- 既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com
    
- 新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online のプロビジョニング

最初に、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」の手順に従って、Exchange オンライン PowerShell に接続します。
  
Skype ルーム システムの既存のリソース ルーム メールボックス アカウントを設定するには、Exchange オンライン PowerShell で次のコマンドを実行します。
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Skype ルーム システムの新しい Exchange リソース メールボックスのアカウントを作成するには、Exchange オンライン PowerShell で次のコマンドを実行します。
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

上記のコマンドは、設定または Skype ルームのシステムを使用するためには、新しい Exchange リソース メールボックス アカウントを作成するには、アカウントを有効にするとします。
  
メールボックスを作成するは、メールボックスを構成するのには Exchange のオンライン PowerShell でセット CalendarProcessing コマンドレットを使用することができます。 詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。

## <a name="assigning-a-skype-for-business-online-license"></a>Skype for Business Online ライセンスを割り当てる

割り当てるには、Skype または Skype のオンライン ビジネス (プラン 2) のオンライン ビジネス (プラン 3) のライセンスの[割り当てまたはビジネス向けの Office 365 のライセンスを削除](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)またはビジネスのアドオンの[Skype で説明したように Office 365 管理ポータルを使用して、ライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。 
  
ビジネス オンラインの Skype のライセンスを割り当てた後は、ログインして、Skype を使用してビジネスのクライアントのアクティブなアカウントであることを検証することができます。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online のプロビジョニング

Skype のビジネス オンライン アカウントはオンラインの Exchange フォレストから Skype をオンライン ビジネスのフォレストを使用して同期のアカウントに制限があるとリソース ルーム後メールボックス アカウントが作成され、以前に示すように、有効になっている、Windows Azure Active Directory フォレストです。 次の手順は、オンライン ビジネスのプールの Skype の Skype ルームのシステム アカウントを準備する必要があります。 この手順は、それらが有効な Exchange オンラインと両方のこれらのアカウントと同期されます Skype オンライン ビジネスのと同じ方法であるため既存のリソース メールボックスのアカウントまたは (confrm1 または confrm2) に、新しく作成したアカウントの両方に対して同じです。
  
1. リモート PowerShell セッションを作成します。 コネクタ モジュールのオンライン ビジネスおよび Microsoft オンライン サービス サインイン アシスタントの Skype をダウンロードし、コンピューターが構成されているかどうかを確認する必要があります注意してください。 詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. ビジネス用の Skype で Skype ルームのシステム アカウントを有効にするのには、次のコマンドを実行します。
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    ビジネス ユーザー向けに、Skype が置かれている既存のアカウントのいずれかから次のコマンドを使用してアドレスを取得する RegistrarPool にこのプロパティを取得できます。
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>パスワードの有効期限

Office 365 では、別のパスワードの有効期限ポリシーを構成しない限り、すべてのユーザー アカウントのパスワードの有効期限ポリシーは、既定で 90 日間です。 Skype ルームのシステム アカウント、パスワードを選択できます次の手順で設定を有効期限はありません。
  
1. 管理者のグローバル資格情報を使用して、Windows Azure Active Directory セッションを作成します。
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. パスワードの設定は、次のコマンドを使用して、以前作成した Skype ルーム システム ルームのアカウントの設定を有効期限なし。
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。
  
## <a name="validate"></a>検証

検証、ビジネス クライアント用の Skype を使用して作成したアカウントにサインインできるように。

