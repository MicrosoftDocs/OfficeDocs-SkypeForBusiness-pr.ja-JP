---
title: Skype Room Systems バージョン 2 と Exchange On-Premises を展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: 社内の Exchange とのハイブリッド環境で Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: a804ba6b1210efae8ed36630180f14ad367cb955
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645417"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Skype Room Systems バージョン 2 と Exchange On-Premises を展開する

オンライン ビジネスの社内の Exchange と Skype のハイブリッド環境で Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
  
設置型およびいくつかのホストがオンラインでホストされているいくつかのさまざまなサービスがある場合は、各サービスがホストされているによって、構成が決まります。 このトピックでは、社内設置型でホストされている Exchange と Skype ルーム システム v2 のハイブリッド展開を説明します。 この種類の展開で非常に多くのさまざまなバリエーションがあるため、それらのすべての詳細な説明を提供することはできません。 以下、処理の多くの構成です。 プロセスが、設定の適切でない場合は、ここでは、およびその他の展開オプションが記載されているように、同じ結果を達成するために Windows PowerShell を使用することをお勧めします。

マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または Skype ルーム システム v2 の互換性のあるユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。 場合は、Skype ルーム システム v2 デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。
  
## <a name="requirements"></a>要件

社内の Exchange と Skype ルーム システム v2 を展開する前に、要件を満たしていることを確認します。 詳細については、「[Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)」を参照してください。
  
社内の Exchange と Skype ルーム システム v2 を展開する場合、オンプレミス ドメイン アカウントの電子メール アドレスを追加するのには Active Directory 管理ツールを使用するは。 このアカウントを Office 365 に同期されます。 次の操作を実行する必要があります。
  
- アカウントを作成してアカウントを Active Directory と同期する。

- リモート メールボックスを有効にしてプロパティを設定する。

- Office 365 のライセンスを割り当てます。

- ビジネス サーバーでは、Skype でデバイスのアカウントを有効にします。 デバイス アカウントを有効にするには、お使いの環境が次の前提条件を満たしている必要があります。

  - Office 365 プランに Skype ビジネス online (プラン 2) またはそれ以上にする必要があります。 このプランでは会議機能をサポートする必要があります。
  
  - - エンタープライズ VoIP (PSTN テレフォニー) が必要な場合 Skype ルーム システム v2 のテレフォニー サービス プロバイダーを使用する必要があります Skype ビジネス online (プラン 3)。
  
  - - テナント ユーザーは、Exchange のメールボックスが必要です。
  
  - - Skype ルーム システム v2 アカウントが必要ですがビジネス オンライン (プラン 2) の Skype または Skype ビジネス オンライン (プラン 3) のライセンスが、Exchange のオンライン ・ ライセンスは必要ありません。

- Skype ルーム システム v2 アカウントに、Skype ビジネス サーバー ライセンスを割り当てます。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>アカウントを作成して Active Directory と同期する

1. **Active Directory ユーザーとコンピューターの AD**ツールで、フォルダーまたは Skype ルーム システムは、v2 のアカウントを作成するには [**新規**作成] をクリックし、**ユーザー**] をクリックし、組織の単位を右クリックします。

2. 前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。

3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > **パスワードを無期限にする**を選択することは、Skype ルーム システム v2 に Skype ビジネス サーバーのための必要条件です。 ドメイン ルールによって無期限のパスワードが禁止される場合があります。 その場合は、Skype ルーム システム v2 デバイスのアカウントごとに例外を作成する必要があります。
  
4. アカウントを作成したら、ディレクトリの同期を実行します。 それが完了すると、Office 365 の管理センターで [ユーザー] ページに移動しを前の手順で作成したアカウントは、マージ オンラインことを確認します。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>リモート メールボックスを有効にしてプロパティを設定する

1. [Exchange 管理シェルを開く](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)か、[リモート PowerShell を使用して Exchange サーバーに接続](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)します。

2. Exchange の PowerShell で次のコマンドを実行することによってアカウント (アカウントのメールボックスを有効に) 用のメールボックスを作成します。

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   詳細な構文やパラメーターの情報を[有効にするメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)を参照してください。

3. Exchange の PowerShell では、会議エクスペリエンスを向上させるために会議室メールボックスに次の設定を構成します。

   - AutomateProcessing: 自動承諾 (会議の開催者が人間の介入なしで直接ルーム予約の意思決定を受信: 無料 = 受け入れる; 時間 = 辞退)。

   - AddOrganizerToSubject: の $false (会議の開催者は会議出席依頼の件名にない追加)。

   - DeleteComments: $false (会議出席依頼のメッセージ本文に任意のテキストを保持)。

   - DeleteSubject: $false (まま会議出席依頼の件名)

   - RemovePrivateProperty: $false (ことを元の会議の会議の開催者から送信されたプライベート フラグの要求に指定されたままになります)。

   - (AdditionalResponse パラメーターで指定されたテキストは、会議出席依頼に追加されます)。 AddAdditionalResponse: $true

   - AdditionalResponse:「これは、Skype の会議室!」 (会議出席依頼に追加する追加のテキストです。)

   この例では、という名前のプロジェクト-Rigel-01 会議室メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   詳細な構文とパラメーター情報は、[一連の CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)を参照してください。

### <a name="assign-an-office-365-license"></a>Office 365 ライセンスを割り当てる

1. PowerShell の Azure Active Directory に接続します。 手順については、[グラフ モジュールの Azure Active Directory PowerShell を使用して接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)を参照してください。

2. デバイスのアカウントは、有効な Office 365 のライセンスでは、する必要があるか、Exchange およびビジネス用の Skype は機能しません。 ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。 Get AzureADSubscribedSku を使用して、次のように、Office 365 テナントの使用可能な Sku の一覧を取得できます。

   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```

   次に、セット AzureADUserLicense コマンドレットを使用してライセンスを追加することができます。 この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。

   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

   詳細については、 [Office 365 の PowerShell でのユーザー アカウントにライセンスを割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)を参照してください。

### <a name="enable-the-device-account-with-skype-for-business"></a>Skype for Business でデバイス アカウントを有効にする

1. 次のように PC からリモートの Windows PowerShell セッションを作成します。

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. ビジネスのサーバーでは、Skype の Skype ルーム システム v2 アカウントを有効にするには、このコマンドを実行します。

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   ビジネス サーバーのユーザーがこのコマンドを使用して既存の Skype から値を取得するには、環境内の RegistrarPool パラメーターを使用するのにはどのような値がわからない場合

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>Skype for Business のライセンスを Skype Room Systems バージョン 2 アカウントに割り当てる

1. テナント管理者としてログイン、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。
2. [**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。
3. Skype ルーム システム v2 のアカウント] をクリックし、アカウント情報を編集するのには [ペン] アイコンをクリックします。
4. [**ライセンス**] をクリックします。
5. ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。 Skype ルーム システム v2 でエンタープライズ VoIP を使用する場合は、計画の 3 ライセンスを使用する必要があります。
6. **[保存]** をクリックします。

検証、ビジネス クライアント用の Skype を使用してこのアカウントにログインできるように。
  
## <a name="see-also"></a>関連項目

[Skype ルーム システム v2 用のアカウントを構成します。](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Skype Room System バージョン 2 を展開する](room-systems-v2.md)
  
[Skype Room Systems バージョン 2 コンソールを構成する](console.md)
  
[Skype Room Systems バージョン 2 を管理する](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)