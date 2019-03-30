---
title: オンライン Exchange とマイクロソフトのチームの会議室を配置します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Exchange オンラインでマイクロソフト チームの会議室を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 09a9cf6ed01ea4b523e6f790d30a586e92b5c4f5
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012885"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>オンライン Exchange とマイクロソフトのチームの会議室を配置します。

マイクロソフト チーム会議室と、Exchange オンライン Skype ビジネス サーバー設置型の展開方法の詳細については、このトピックを参照してください。
  
設置型およびいくつかのホストがオンラインでホストされているいくつかのさまざまなサービスがある場合は、各サービスがホストされているによって、構成が決まります。 このトピックでは、オンラインでホストされている Exchange と Microsoft チームの会議室のハイブリッド展開について説明します。 この種類の展開で非常に多くのさまざまなバリエーションがあるため、それらのすべての詳細な説明を提供することはできません。 以下、処理の多くの構成です。 プロセスが、設定の適切でない場合は、ここでは、およびその他の展開オプションが記載されているように、同じ結果を達成するために Windows PowerShell を使用することをお勧めします。

ユーザー アカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。 マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または互換性のある Microsoft チームの会議室のユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。 場合は、マイクロソフト チームの会議室デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。

## <a name="requirements"></a>要件

Exchange オンラインでマイクロソフト チームの会議室を展開する前に、要件を満たしていることを確認します。 詳細については、[マイクロソフト チームの会議室の要件](../../plan-your-deployment/clients-and-devices/requirements.md)を参照してください。
  
Exchange オンラインでマイクロソフト チームの会議室を配置するには、以下の手順を実行します。 関連するコマンドレットを実行するために適切な権限があることを確認します。
  
### <a name="create-an-account-and-set-exchange-properties"></a>アカウントを作成して Exchange プロパティを設定する

1. PC 上でリモートの Windows PowerShell セッションを開始し、Exchange Online への接続を次のようにします。

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. セッションを確立するには後、するが新しいメールボックスを作成して、RoomMailboxAccount、として有効にか既存の会議室メールボックスの設定を変更します。 これにより、マイクロソフトのチームの会議室に認証するためにアカウントが許可されます。

   既存のリソース メールボックスを変更している場合:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    : 新しいリソース メールボックスを作成する場合

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 会議エクスペリエンスを向上させるため、次のようにユーザー アカウントに Exchange のプロパティを設定する必要があります。

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Azure AD に接続して、アカウント設定をいくつか適用する必要があります。 次のコマンドレットを実行して接続することができます。

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>オンプレミスのドメイン アカウントに電子メール アドレスを追加する

1. **Active Directory ユーザーとコンピューターの AD**ツールで、フォルダーまたはアカウントを作成するのには、マイクロソフト チーム ルームは、[**新規**作成] をクリックし、] をクリックして**ユーザー**の組織単位を右クリックします。
2. 前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。
3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > Skype マイクロソフト チームの部屋にサーバーをビジネスのための要件は、**パスワードを無期限にする**を選択します。 ドメイン ルールによって無期限のパスワードが禁止される場合があります。 その場合は、マイクロソフト チームの会議室のユーザー アカウントごとに例外を作成する必要があります。
  
4. アカウントを作成するには、**[完了]** をクリックします。
5. アカウントを作成したら、ディレクトリの同期を実行します。それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。

### <a name="assign-an-office-365-license"></a>Office 365 ライセンスを割り当てる

1. ユーザー アカウントは、Exchange と Skype のビジネス サーバーが動作することを確認するのには有効な Office 365 ライセンスを所有する必要があります。 ライセンスがあれば、利用場所を割り当てるユーザー アカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定です。
2. 次を使用して、`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> Office 365 テナントの使用可能な Sku の一覧を取得します。
3. ライセンスを使用してを追加するには、Sku を一覧表示すると、`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> コマンドレットです。 この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>ビジネス サーバーの Skype でのユーザー アカウントを有効にします。

1. 次のように PC からリモートの Windows PowerShell セッションを作成します。

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. ビジネスのサーバーでは、Skype のマイクロソフト チームの会議室のアカウントを有効にするには、このコマンドを実行します。

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    ビジネス サーバーのユーザーがこのコマンドを使用して既存の Skype から値を取得するには、環境内の RegistrarPool パラメーターを使用するのにはどのような値がわからない場合

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>チームの会議室を Microsoft アカウントに、Skype ビジネス サーバー ライセンスを割り当てる

1. テナント管理者としてログイン、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。
2. [**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。
3. マイクロソフト チームの会議室のアカウント] をクリックし、アカウント情報を編集するのには [ペン] アイコンをクリックします。
4. [**ライセンス**] をクリックします。
5. ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。 マイクロソフト チームの会議室でエンタープライズ VoIP を使用する場合は、計画の 3 ライセンスを使用する必要があります。
6. **[保存]** をクリックします。

検証、ビジネス クライアント用の Skype を使用してこのアカウントにログインできるように。
  
## <a name="see-also"></a>関連項目

[マイクロソフト チームの会議室のアカウントを構成します。](room-systems-v2-configure-accounts.md)

[マイクロソフト チームの会議室のプラン](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[マイクロソフト チームの会議室を配置します。](room-systems-v2.md)
  
[マイクロソフト チームの会議室のコンソールを構成します。](console.md)
  
[マイクロソフト チームの会議室を管理します。](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
