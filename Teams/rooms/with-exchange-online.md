---
title: Exchange Online を使用して Microsoft Teams ミーティング を展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: このトピックでは、Microsoft Teams のルームを Exchange Online と共に展開する方法について説明します。
ms.openlocfilehash: e53fd2ebd25ef6b625ada84b60d58e42e8c13a28
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628423"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Exchange Online を使用して Microsoft Teams ミーティング を展開

このトピックでは、オンプレミスの Exchange Online と Skype for Business Server を使用して Microsoft Teams ルームを展開する方法について説明します。
  
組織にサービスが混在していて、オンプレミスのホストとオンラインでホストされているものがある場合、構成は各サービスがホストされている場所によって異なります。 このトピックでは、オンラインでホストされている Microsoft Teams ルームのハイブリッド展開について説明します。 この種類の展開にはさまざまなバリエーションがあるため、すべてについて詳しく説明することはできません。 次のプロセスは、さまざまな構成で動作します。 このプロセスが適切に設定されていない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ終了結果とその他の展開オプションを実現することをお勧めします。

ユーザーアカウントをセットアップする最も簡単な方法は、リモートの Windows PowerShell を使用してアカウントを構成することです。 Microsoft には、新しいユーザーアカウントを作成するのに役立つスクリプト、または既存のリソースアカウントを、互換性のある Microsoft Teams 室のユーザーアカウントに変換するために使用している既存のリソースアカウントを検証するための SkypeRoomProvisioningScript が用意されてい[ます](https://go.microsoft.com/fwlink/?linkid=870105)。 必要に応じて、次の手順に従って、Microsoft Teams の会議室のデバイスで使用するアカウントを構成することができます。

## <a name="requirements"></a>要件

Microsoft Teams のルームを Exchange Online に展開する前に、要件を満たしていることを確認してください。 詳細については、「 [Microsoft Teams の会議室の要件](requirements.md)」を参照してください。
  
Microsoft Teams のルームを Exchange Online と共に展開するには、次の手順を実行します。 関連するコマンドレットを実行するために適切な権限があることを確認します。 

   > [!NOTE]
   >  このセクションの[Windows PowerShell コマンドレット用 Azure Active Directory モジュール](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)(たとえば、Set-get-msoluser) は、Microsoft Teams 室デバイスのアカウントのセットアップでテストされています。 ただし、他のコマンドレットは動作する可能性がありますが、この特定のシナリオではテストされていません。
  
### <a name="create-an-account-and-set-exchange-properties"></a>アカウントを作成して Exchange プロパティを設定する

1. PC でリモート Windows PowerShell セッションを開始し、次の手順に従って Exchange Online に接続します。

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. セッションを確立したら、新しいメールボックスを作成して、RoomMailboxAccount として有効にするか、既存の会議のメールボックスの設定を変更します。 これにより、アカウントが Microsoft Teams のルームに認証されるようになります。

   既存のリソース メールボックスを変更している場合:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    新しいリソースメールボックスを作成する場合は、次の操作を行います。

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 会議のエクスペリエンスを向上させるには、次のようにして、ユーザーアカウントの Exchange プロパティを設定する必要があります。

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>オンプレミスのドメイン アカウントに電子メール アドレスを追加する

1. **Active Directory ユーザーとコンピューターの AD**ツールで、Microsoft Teams の会議室のアカウントが作成されるコンテナーまたは組織単位を右クリックし、[**新規**作成] をクリックして、[**ユーザー**] をクリックします。
2. 前のコマンドレットの表示名 (-Identity) を [**氏名**] ボックスに入力し、[**ユーザーのログオン名**] ボックスにエイリアスを入力します。 [**次へ**] をクリックします。
3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > [**パスワードを無期限**にする] を選ぶことは、Microsoft Teams のルームの Skype For business Server の要件です。 ドメイン ルールによって無期限のパスワードが禁止される場合があります。 そうである場合は、Microsoft Teams のルームユーザーアカウントごとに例外を作成する必要があります。
  
4. アカウントを作成するには、**[完了]** をクリックします。
5. アカウントを作成したら、ディレクトリ同期を実行します。 これは、PowerShell で[MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)を使うことで実現できます。 完了したら、[ユーザー] ページに移動し、前の手順で作成した2つのアカウントがマージされていることを確認します。

### <a name="assign-an-office-365-license"></a>Office 365 ライセンスを割り当てる

1. まず、[Azure AD に接続して、いくつかのアカウント設定を適用します] を選びます。 次のコマンドレットを実行して接続することができます。 Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。 

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. Exchange と Skype for Business Server が動作するためには、ユーザーアカウントが有効な Office 365 ライセンスを所有している必要があります。 ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。 課題は、次の手順で作成します。
3. 次に、`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> Office 365 テナントで利用可能な Sku の一覧を取得するには、こちらを参照してください。
4. Sku の一覧が表示されたら、`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> コマンドレット. この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。 

    ```PowerShell
      Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Skype for Business Server を使用してユーザーアカウントを有効にする

1. PC からリモート Windows PowerShell セッションを作成するには、次の手順を実行します。

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Skype for Business Server 用の Microsoft Teams ルームアカウントを有効にするには、次のコマンドを実行します。

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    環境の RegistrarPool パラメーターに使用する値がわからない場合は、このコマンドを使用して、既存の Skype for Business Server ユーザーから値を取得することができます。

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Skype for Business Server のライセンスを Microsoft Teams のルームアカウントに割り当てる

1. テナント管理者としてログインし、Office 365 管理ポータルを開いて、[管理者] アプリをクリックします。
2. [**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。
3. Microsoft Teams のルームアカウントをクリックし、ペンアイコンをクリックしてアカウント情報を編集します。
4. [**ライセンス**] をクリックします。
5. ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。 Microsoft Teams のルームでエンタープライズ Voip を使用する場合は、プラン3ライセンスを使用する必要があります。
6. **[保存]** をクリックします。

検証のために、Skype for Business クライアントを使用して、このアカウントにログインできるようにする必要があります。

> [!NOTE]
> 現在、電話会議、または Office 365 電話システムと通話プランを使って、Skype for Business プラン2で E1、E3、E4、または E5 Sku を使用している場合は、引き続き機能します。 ただし、現在のライセンスの有効期限が切れた後、 [Teams 会議室のライセンス更新](rooms-licensing.md)で説明されているように、よりシンプルなライセンスモデルに移行することを検討する必要があります。

> [!IMPORTANT]
> Skype for Business Plan 2 を使用している場合は、Skype for Business のみのモードで Microsoft Teams ルームのみを使用できます。つまり、すべての会議が Skype for Business 会議になります。 Microsoft Teams 会議の会議室を有効にするには、会議室のライセンスを購入することをお勧めします。
  
## <a name="see-also"></a>関連項目

[Microsoft Teams 室のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams のルームを計画する](rooms-plan.md)
  
[Microsoft Teams ルームの展開](rooms-deploy.md)
  
[Microsoft Teams 室コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
