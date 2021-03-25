---
title: オンプレミスで Exchange を使用し Microsoft Teams Rooms を展開
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: このトピックでは、オンプレミスの Exchange が搭載されたハイブリッド環境に Microsoft Teams Rooms を展開する方法について説明します。
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117355"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>オンプレミスで Exchange を使用し Microsoft Teams Rooms を展開する

このトピックでは、オンプレミスのExchange およびMicrosoft Teams またはSkype for Business Online を使用したハイブリッド環境で Microsoft Teams Rooms を展開する方法について説明します。
  
組織にサービスが混在していて、オンプレミスとオンラインでホストされているものがある場合、構成は各サービスのホスト場所によって異なります。 このトピックでは Exchangeがオンラインでホストする、Microsoft Teams Rooms のハイブリッドな展開について説明します。 この種類の展開には、さまざまな違いがあるため、すべての手順を詳細に説明することはできません。 次のプロセスは、多くの構成で機能します。 このプロセスがユーザーのセットアップに適していない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ結果を達成するか、または他の展開オプションをお勧めします。

Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいユーザー アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams Rooms のユーザー アカウントに変換する助けとなります。 必要な場合は、次の手順に従って、Microsoft Teams Rooms のデバイスが使用するアカウントを構成できます。
  
## <a name="requirements"></a>要件

Microsoft Teams Rooms をオンプレミスの Exchangeで展開する前に、要件を満たしていることをご確認ください。 詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。
  
オンプレミスの Exchangeを使用してMicrosoft Teams Rooms を展開する場合は、Active Directory の管理ツールを使用してオンプレミス ドメイン アカウントの電子メール アドレスを追加します。 このアカウントは、Microsoft 365 または Office 365 に同期されます。 次の操作が必要です。
  
- アカウントを作成してアカウントを Active Directory と同期する。

- リモート メールボックスを有効にしてプロパティを設定する。

- Microsoft 365 または Office 365 ライセンスを割り当てる

- Skype for Business サーバーでデバイス アカウントを有効にする デバイスアカウントを有効にするには、お使いの環境が次の前提条件を満たしている必要があります。

  - Microsoft 365 または Office 365 プランの Skype for Business Online (プラン 2) 以降を使用する必要があります。 プランは会議機能をサポートする必要があります。
  
  - Microsoft Teams Rooms 向けテレフォニーサービスプロバイダーを使用して、エンタープライズ ボイス(PSTN テレフォニー) が必要な場合は、Skype for Business Online (プラン 3) が必要です。

  - Microsoft Teams または Skype for Business Online でルーム アカウントを構成する場合、そのアカウントをルーム アカウントとして有効にする前に、電話番号を割り当てる必要があります。
  
  - テナントユーザーには Exchange メールボックスが必要です。
  
  - Microsoft Teams Rooms のアカウントでは、少なくとも Skype for Business Online (プラン 2)またはSkype for Business Online （Plan 3） のライセンスが必要ですが、Exchange Online のライセンスは必要ありません。

- Microsoft Teams Rooms のアカウントに Skype for Business Server のライセンスを割り当てる

### <a name="create-an-account-and-synchronize-with-active-directory"></a>アカウントを作成し、Active Directory と同期します。

1. **Active Directoryユーザーおよびコンピューター** ツールで、フォルダーまたはMicrosoft Teams Rooms のアカウントの作成先となる組織単位を右クリックし、**新規** そして **ユーザー** の順にクリックします。

2. 前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。

3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > [**パスワードを無期限にする**] を選択すること は、Microsoft Teams Rooms 上で Skype for Business Serverを使用する要件です。  有効期限が切れないパスワードは、ドメインのルールで禁止されるかもしれません。 その場合は、Microsoft Teams Rooms のユーザーアカウントごとに例外を作成する必要があります。
  
4. アカウントを作成したら、ディレクトリの同期を実行します。 同期が完了したら、Microsoft 365管理センターの [ユーザー] ページに移動し、上記の手順で作成したアカウントがオンラインにマージされていることを確認します。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>リモートメールボックスを有効にしてプロパティを設定する

1. [Exchange 管理シェルを開く](/powershell/exchange/exchange-server/open-the-exchange-management-shell) または、[リモート PowerShellを使用して Exchange サーバーに接続し ます](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. Exchange PowerShell で次のコマンドを実行して、アカウントのメールボックスを作成します （アカウントのメールボックス有効化）アカウントを有効にします）。

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   構文およびパラメーターの詳細については、「[Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox)」を参照してください。

3. Exchange Online PowerShell で、会議機能を向上させるために、会議室メールボックスの次の設定を構成します。

   - AutomateProcessing: AutoAccept (会議の開催者は、手動での介入なしに部屋予約の決定を受け取ります: free = 同意; busy = 拒否。)

   - AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)

   - DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)

   - DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)

   - RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)

   - AdditionalResponse: "これは Skype 会議室です。" (会議出席依頼に追加するテキスト)。

   この例では、Project-Rigel-01という名前の会議室メールボックスでこれらの設定を構成します。

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   構文とパラメーターの詳細情報については、[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Microsoft 365 または Office 365 ライセンスを割り当てる

1. Azure Active Directoryに接続する Active Directory の詳細については、[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。 

2. デバイスアカウントには、Microsoft 365 または Office 365 の有効なライセンスが必要です。さもないと Exchange および Microsoft Teams は機能しません。 ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。 `Get-MsolAccountSku`を使用して <!-- Get-AzureADSubscribedSku --> 使用可能な SKUの一覧を取得できます。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 次に、以下の `Set-MsolUserLicense`を使用してライセンスを追加することができます。 <!-- Set-AzureADUserLicense --> することができます。 この例では、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。

### <a name="enable-the-device-account"></a>デバイスアカウントを有効にする

Skype for Business Online PowerShell は、Microsoft Teams および Skype for Business Online のサービスの管理に使用されます。

1. PC からリモートの Windows PowerShell セッションを作成するには、次のようにします。
> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。
>
> 最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. アカウントの SIP アドレスを取得します。

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **オプション。** アカウントに電話番号を割り当てる場合は、この時点で操作を実行する必要があります。 ダイレクト ルーティングの電話番号を割り当てる場合:

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    Microsoft 提供の電話番号を割り当てる場合は、通話プラン ライセンスでユーザーをプロビジョニングした後、次のコマンドレットを使用します。
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. Microsoft Teams Rooms を使用するには、次のコマンドを実行します。

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   お使いの環境の RegistrarPool パラメーターに使用する値が定かでない場合は、次のコマンドを実行して既存のユーザーから値を取得できます。

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Microsoft Teams Rooms のアカウントにライセンスを割り当てる

1. テナント管理者としてログインし、Microsoft 365 管理センターを開き、Admin アプリをクリックします。
2. [ **ユーザーとグループ**] をクリックし [ **ユーザーの追加]、[パスワードのリセット]、およびその他の** をクリックします。
3. Microsoft Teams Rooms アカウントをクリックし、ペン アイコンをクリックして、アカウント情報を編集します。
4. [**ライセンス**] をクリックします。
5. ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。 Microsoft Teams Rooms でエンタープライズ通話 を使用する場合は、プラン 3 のライセンスを使用する必要があります。
6. [**保存**] をクリックします。

検証を行う場合は、通常、どのクライアントを使用してもこのアカウントにログインできます。
  
## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)