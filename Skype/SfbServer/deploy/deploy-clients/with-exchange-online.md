---
title: Skype Room Systems バージョン 2 と Exchange Online を展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Exchange オンラインで Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 51a1f4089dfb3453802e8d3241869c3c325c904c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883245"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Skype Room Systems バージョン 2 と Exchange Online を展開する 
 
ビジネス サーバー設置型の Exchange Online と Skype の Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
  
設置型およびいくつかのホストがオンラインでホストされているいくつかのさまざまなサービスがある場合は、各サービスがホストされているによって、構成が決まります。 このトピックでは、オンラインでホストされている Exchange と Skype ルーム システム v2 のハイブリッド展開について説明します。 この種類の展開で非常に多くのさまざまなバリエーションがあるため、それらのすべての詳細な説明を提供することはできません。 以下、処理の多くの構成です。 プロセスが、設定の適切でない場合は、ここでは、およびその他の展開オプションが記載されているように、同じ結果を達成するために Windows PowerShell を使用することをお勧めします。 

ユーザー アカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。 マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または Skype ルーム システム v2 の互換性のあるユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。 場合は、Skype ルーム システム v2 デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Skype Room Systems バージョン 2 と Exchange Online を展開する

Exchange オンラインで Skype ルーム システム v2 を展開する前に、要件を満たしていることを確認します。 詳細については、 [Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)を参照してください。
  
Exchange オンラインで Skype ルーム システム v2 を展開するには、以下の手順を実行します。 関連するコマンドレットを実行するために適切な権限があることを確認します。 
  
### <a name="create-an-account-and-set-exchange-properties"></a>アカウントを作成して Exchange プロパティを設定する

1. PC 上でリモートの Windows PowerShell セッションを開始し、Exchange Online への接続を次のようにします。
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
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

    
4. Azure AD に接続して、アカウント設定をいくつか適用する必要があります。次のコマンドレットを実行して接続することができます。
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>オンプレミスのドメイン アカウントに電子メール アドレスを追加する

1. **Active Directory ユーザーとコンピューターの AD**のツールでは、フォルダーまたは組織単位の**新規**作成] をクリックし**ユーザー**に Skype ルーム システムでは、v2 のアカウントを作成する] をクリックする右クリックします。
    
2. 前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。


3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。
    
    > [!NOTE]
    > **パスワードを無期限にする**を選択することは、Skype ルーム システム v2 に Skype ビジネス サーバーのための必要条件です。 ドメイン ルールによって無期限のパスワードが禁止される場合があります。 その場合は、Skype ルーム システム v2 のユーザー アカウントごとに例外を作成する必要があります。
  
4. アカウントを作成するには、**[完了]** をクリックします。
    
5. アカウントを作成したら、ディレクトリの同期を実行します。それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。
    
### <a name="assign-an-office-365-license"></a>Office 365 ライセンスを割り当てる

1. ユーザー アカウントは、Exchange と Skype のビジネス サーバーが動作することを確認するのには有効な Office 365 ライセンスを所有する必要があります。 ライセンスがあれば、利用場所を割り当てるユーザー アカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定です。
    
2. 次に、Get MsolAccountSku を使用して、Office 365 テナントの使用可能な Sku の一覧を取得します。
    
3. SKU のリストを取得したら、Set-MsolUserLicense コマンドレットを使用してライセンスを追加することができます。この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server"></a>ビジネス サーバーの Skype でのユーザー アカウントを有効にします。

1. 次のように PC からリモートの Windows PowerShell セッションを作成します。
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. ビジネスのサーバーでは、Skype の Skype ルーム システム v2 アカウントを有効にするには、このコマンドを実行します。
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    ビジネス サーバーのユーザーがこのコマンドを使用して既存の Skype から値を取得するには、環境内の RegistrarPool パラメーターを使用するのにはどのような値がわからない場合
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-skype-room-systems-v2-account"></a>ビジネス サーバー ライセンス、Skype アカウントに割り当てる、Skype ルーム システム v2

1. テナント管理者としてログイン、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。
    
2. [**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。
    
3. Skype ルーム システム v2 のアカウント] をクリックし、アカウント情報を編集するのには [ペン] アイコンをクリックします。
    
4. [**ライセンス**] をクリックします。
    
5. ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。 Skype ルーム システム v2 でエンタープライズ VoIP を使用する場合は、計画の 3 ライセンスを使用する必要があります。
    
6. [ **保存**] をクリックします。
    
検証、ビジネス クライアント用の Skype を使用してこのアカウントにログインできるように。
  
## <a name="see-also"></a>関連項目

[Skype ルーム システム v2 用のアカウントを構成します。](room-systems-v2-configure-accounts.md)

[Skype Room Systems バージョン 2 の計画](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Skype Room System バージョン 2 を展開する](room-systems-v2.md)
  
[Skype Room Systems バージョン 2 コンソールを構成する](console.md)
  
[Skype Room Systems バージョン 2 を管理する](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

