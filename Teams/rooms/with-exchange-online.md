---
title: Exchange Online を使用して Microsoft Teams Rooms を展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: このトピックでは、Exchange OnlineとSkype for Business Serverオンプレミス を使用して Microsoft Teams Rooms を展開する方法について説明します。
ms.openlocfilehash: 03999e5717f784166387c823c95af1e333d4f942
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666149"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Exchange Online を使用して Microsoft Teams Rooms を展開

このトピックでは、Exchange OnlineとSkype for Business Serverオンプレミス を使用して Microsoft Teams Rooms を展開する方法について説明します。
  
組織にサービスが混在していて、オンプレミスとオンラインでホストされているものがある場合、構成は各サービスのホスト場所によって異なります。 このトピックでは Exchangeがオンラインでホストする、Microsoft Teams Rooms のハイブリッドな展開について説明します。 この種類の展開には、さまざまな違いがあるため、すべての手順を詳細に説明することはできません。 次のプロセスは、多くの構成で機能します。 このプロセスがユーザーのセットアップに適していない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ結果を達成するか、または他の展開オプションをお勧めします。

ユーザー アカウントをセットアップする最も簡単な方法は、リモート Windows PowerShell を使用して構成することです。 Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいユーザー アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams Rooms のユーザー アカウントに変換する助けとなります。 必要な場合は、次の手順に従って、Microsoft Teams Rooms のデバイスが使用するアカウントを構成できます。

## <a name="requirements"></a>要件

Microsoft Teams Rooms を Exchange Onlineで展開する前に、要件を満たしていることをご確認ください。 詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。
  
Exchange Online を使用して Microsoft Teams Rooms を展開するには、次の手順に従います。 関連するコマンドレットを実行する適切なアクセス許可があることを確認します。 

   > [!NOTE]
   >  このセクションで説明されている [「Windows PowerShell コマンドレット用の Azure Active Directory モジュール](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」 (たとえば  Set-MsolUser)  は、Microsoft Teams Rooms デバイスのアカウントを設定するためにテストされました。 他のコマンドレットでも機能することがありますが、この特定のシナリオではテストされていません。

Active Directory フェデレーションサービス (AD FS) を展開した場合は、次の手順を実行する前に、ユーザーアカウントを管理されているユーザーに変換し、この手順を実行した後にユーザーをフェデレーションユーザーに戻す必要があります。
  
### <a name="create-an-account-and-set-exchange-properties"></a>アカウントを作成して、Exchange のプロパティを設定する

1. PC でリモートの Windows PowerShell セッションを開始し、次のように Exchange Online に接続します。

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. セッションを確立したら、新しいメールボックスを作成して、それを RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。 これにより、アカウントは、Microsoft Teams Roomsに認証されます。

   既存のリソースメールボックスを変更する場合：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    新しいリソース メールボックスを作成している場合:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 会議のエクスペリエンスを改善するには、ユーザー アカウントで、次のように Exchangeプロパティを設定する必要があります。

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>オンプレミスのドメインアカウントのメールアドレスを追加する

1. **Active Directory UsersおよびComputers AD**ツールで、コンテナーまたMicrosoft Teams Rooms のアカウントの作成先となる組織単位を右クリックし、**新規**そして**ユーザー**の順にクリックします。
2. 前のコマンドレット(Set-MailboxまたはNew-Mailbox)の表示名 (- Identity )を**フルネーム**ボックスに入力し、次にアリアスを **ユーザーログイン名**ボックスに入力します。 **[次へ]** をクリックします。
3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > [**パスワードを無期限にする**] を選択すること は、Microsoft Teams Rooms 上で Skype for Business Serverを使用する要件です。  有効期限が切れないパスワードは、ドメインのルールで禁止されるかもしれません。 その場合は、Microsoft Teams Rooms のユーザーアカウントごとに例外を作成する必要があります。
  
4. [ **完了**] をクリックしてアカウントを作成します。
5. アカウントを作成したら、ディレクトリの同期を実行します。 これを行うには、PowerShell で[Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)を使用します。 それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Microsoft 365 または Office 365 ライセンスを割り当てる

1. 最初にAzure AD に接続して、アカウント設定をいくつか適用する必要があります。 このコマンドレットを実行して接続できます。 Active Directory の詳細については、[Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)を参照してください。

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. ユーザーアカウントは、Exchange と Skype for Business Serverが正常に機能するように、有効な Microsoft 365 または Office 365 ライセンスを持っている必要があります。 ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。 課題は次の手順で行います。
3. 次に、`Get-MsolAccountSku`を使用します。  <!--Get-AzureADSubscribedSku--> Microsoft 365 または Office 365の 組織で使用でき SKU の一覧を取得します。
4. SKUの一覧が表示された場合は、`Set-MsolUserLicense`を使用してライセンスを追加できます <!-- Set-AzureADUserLicense--> コマンドレット この例では、表示される SKU コードは$strLicenseです (たとえば、contoso: STANDARDPACK )。 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Skype for Business Server でユーザー アカウントを有効にする

1. PC からリモートの Windows PowerShell セッションを作成するには、次のようにします。

    ``` Powershell
    Import-Module SkypeOnlineConnector
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Skype for Business Serverに対して Microsoft Teams Rooms を有効にするには、次のコマンドを実行します。

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    お使いの環境のRegistrarPool パラメーターに使用する値が定かでない場合は、次のコマンドを実行して既存のSkype for Business Serverユーザーから値を取得できます。

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Microsoft Teams Rooms のアカウントに Skype for Business Server のライセンスを割り当てる

1. テナント管理者としてログインし、Microsoft 365 管理センターを開き、Admin アプリをクリックします。
2. [ **ユーザーとグループ**] をクリックし [ **ユーザーの追加]、[パスワードのリセット]、およびその他の**をクリックします。
3. Microsoft Teams Rooms アカウントをクリックし、ペン アイコンをクリックして、アカウント情報を編集します。
4. [**ライセンス**] をクリックします。
5. ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。 Microsoft Teams Rooms でエンタープライズ通話 を使用する場合は、プラン 3 のライセンスを使用する必要があります。
6. [**保存**] をクリックします。

検証を行う場合は、通常、どの Skype for Businessクライアントを使用してもこのアカウントにログインできます。

> [!NOTE]
> 電話会議、または電話システム、通話プランが含まれる Skype for Business プラン 2で、E1、E3、E4、E5 SKU を現在お使いの場合、これらは引き続き機能します。 現在のライセンスの有効期限が切れている場合は、[Teams ミーティングルームのライセンスアップデート](rooms-licensing.md)の説明にあるように、簡単なライセンスモデルへの移行をお勧めします。

> [!IMPORTANT]
> Skype for Business プラン 2 を使用している場合、[Skype for Business のみ] のモードで Microsoft Teams Rooms をご利用いただけます。つまり、すべての会議が Skype for Business の会議になります。 Microsoft Teams ミーティングの会議室を使用できるようにするため、ミーティング ルーム ライセンスのご購入をお勧めします。
  
## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
