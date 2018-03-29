---
title: Skype Room Systems バージョン 2 と Exchange Online を展開する (ハイブリッド)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Exchange オンラインで Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 59724ae9b0fc77f16a072e0e08b125407c6e43e3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online-hybrid"></a>Skype Room Systems バージョン 2 と Exchange Online を展開する (ハイブリッド)
 
Exchange オンラインで Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
  
設置型およびいくつかのホストがオンラインでホストされているいくつかのさまざまなサービスがある場合は、各サービスがホストされているによって、構成が決まります。 このトピックでは、オンラインでホストされている Exchange と Skype ルーム システム v2 のハイブリッド展開について説明します。 この種類の展開で非常に多くのさまざまなバリエーションがあるため、それらのすべての詳細な説明を提供することはできません。 以下、処理の多くの構成です。 Windows PowerShell を使用することをお勧めできない場合は、プロセスのセットアップに適した、(付録を参照してください: PowerShell) ここでは、およびその他の展開オプションが記載されているように、同じ結果を達成するためにします。 提供されている Windows PowerShell スクリプトを使用して、Skype ルーム システム v2 のセットアップを確認します。 (詳しくは、アカウントの確認スクリプトを参照してください)。
  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Skype Room Systems バージョン 2 と Exchange Online を展開する

Exchange オンラインで Skype ルーム システム v2 を展開する前に、要件を満たしていることを確認します。 詳細については、 [Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)を参照してください。
  
Exchange オンラインで Skype ルーム システム v2 を展開するには、以下の手順を実行します。 関連するコマンドレットを実行するために適切な権限があることを確認します。 
  
### <a name="create-an-account-and-set-exchange-properties"></a>アカウントを作成して Exchange プロパティを設定する

1. PC 上でリモートの Windows PowerShell セッションを開始し、Exchange Online への接続を次のようにします。
    
  ```
  Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic 
-AllowRedirection

  ```

2. セッションを確立するには後、するが新しいメールボックスを作成して、RoomMailboxAccount、として有効にか既存の会議室メールボックスの設定を変更します。 これにより、Skype ルーム システム v2 を認証するためにアカウントが許可されます。
    
   既存のリソース メールボックスを変更している場合:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    : 新しいリソース メールボックスを作成する場合
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 会議エクスペリエンスを向上させるため、次のようにユーザー アカウントに Exchange のプロパティを設定する必要があります。
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。
    
    > [!NOTE]
    > **パスワードを無期限にする**を選択することは、Skype ルーム システム v2 のビジネス サーバー 2015 の Skype の要件です。 ドメイン ルールによって無期限のパスワードが禁止される場合があります。 その場合は、Skype ルーム システム v2 のユーザー アカウントごとに例外を作成する必要があります。
  
5. アカウントを作成するには、**[完了]** をクリックします。
    
6. アカウントを作成したら、ディレクトリの同期を実行します。それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。
    
7. Azure AD に接続して、アカウント設定をいくつか適用する必要があります。次のコマンドレットを実行して接続することができます。
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>オンプレミスのドメイン アカウントに電子メール アドレスを追加する

1. **Active Directory ユーザーとコンピューターの AD**のツールでは、フォルダーまたは組織単位の**新規**作成] をクリックし**ユーザー**に Skype ルーム システムでは、v2 のアカウントを作成する] をクリックする右クリックします。
    
2. 前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。
    
### <a name="assign-an-office-365-license"></a>Office 365 ライセンスを割り当てる

1. ユーザー アカウントは、Exchange およびビジネス サーバー 2015 の Skype が動作することを確認するのには有効な Office 365 ライセンスを所有する必要があります。 ライセンスがあれば、利用場所を割り当てるユーザー アカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定です。
    
2. 次に、Get MsolAccountSku を使用して、Office 365 テナントの使用可能な Sku の一覧を取得します。
    
3. SKU のリストを取得したら、Set-MsolUserLicense コマンドレットを使用してライセンスを追加することができます。この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a>Skype for Business Server 2015 でユーザー アカウントを有効にする

1. 次のように PC からリモートの Windows PowerShell セッションを作成します。
    
  ```
  Import-Module LyncOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber

  ```

2. ビジネス サーバー 2015 の Skype の Skype ルーム システム v2 アカウントを有効にするするには、このコマンドを実行します。
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    このコマンドを使用してサーバー 2015 のビジネス ユーザーの既存の Skype から値を取得するには、環境内の RegistrarPool パラメーターを使用するのにはどのような値がわからない場合
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a>Skype for Business Server 2015 のライセンスを Skype Room Systems バージョン 2 アカウントに割り当てる

1. テナント管理者としてログイン、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。
    
2. [**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。
    
3. Skype ルーム システム v2 のアカウント] をクリックし、アカウント情報を編集するのには [ペン] アイコンをクリックします。
    
4. [**ライセンス**] をクリックします。
    
5. ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。 Skype ルーム システム v2 でエンタープライズ VoIP を使用する場合は、計画の 3 ライセンスを使用する必要があります。
    
6. [ **保存**] をクリックします。
    
検証、ビジネス クライアント用の Skype を使用してこのアカウントにログインできるように。
  
## <a name="see-also"></a>関連項目

#### 

[Skype ルームの計画システム v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Skype の部屋を配置するシステム v2](room-systems-v2.md)
  
[Skype ルーム システム v2 のコンソールを構成します。](console.md)
  
[Skype ルームの管理システム v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

