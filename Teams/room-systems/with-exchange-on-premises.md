---
title: オンプレミスで Exchange を使用し Microsoft Teams ミーティング を展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: このトピックでは、オンプレミスの Exchange を使用したハイブリッド環境で Microsoft Teams のルームを展開する方法について説明します。
ms.openlocfilehash: 7e855ece643d3412047b4d01a9250b17f699ac98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288484"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>オンプレミスで Exchange を使用し Microsoft Teams ミーティング を展開

このトピックでは、オンプレミスの Exchange と Microsoft Teams または Skype for Business Online のハイブリッド環境で Microsoft Teams のルームを展開する方法について説明します。
  
組織にサービスが混在していて、オンプレミスのホストとオンラインでホストされているものがある場合、構成は各サービスがホストされている場所によって異なります。 このトピックでは、社内で Exchange をホストしている Microsoft Teams ルームのハイブリッド展開について説明します。 この種類の展開にはさまざまなバリエーションがあるため、すべてについて詳しく説明することはできません。 次のプロセスは、さまざまな構成で動作します。 このプロセスが適切に設定されていない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ終了結果とその他の展開オプションを実現することをお勧めします。

Microsoft には、新しいユーザーアカウントを作成するのに役立つスクリプト、または既存のリソースアカウントを、互換性のある Microsoft Teams 室のユーザーアカウントに変換するために使用している既存のリソースアカウントを検証するための SkypeRoomProvisioningScript が用意されてい[ます](https://go.microsoft.com/fwlink/?linkid=870105)。 必要に応じて、次の手順に従って、Microsoft Teams の会議室のデバイスで使用するアカウントを構成することができます。
  
## <a name="requirements"></a>要件

Exchange とオンプレミスの Microsoft Teams ルームを展開する前に、要件を満たしていることを確認してください。 詳細については、「 [Microsoft Teams の会議室の要件](requirements.md)」を参照してください。
  
オンプレミスの Exchange で Microsoft Teams のルームを展開している場合は、Active Directory 管理ツールを使用して、オンプレミスのドメインアカウントのメールアドレスを追加します。 このアカウントは、Office 365 と同期されます。 次の操作を実行する必要があります。
  
- アカウントを作成してアカウントを Active Directory と同期する。

- リモート メールボックスを有効にしてプロパティを設定する。

- Office 365 ライセンスを割り当てます。

- Skype for Business Server でデバイスアカウントを有効にします。 デバイス アカウントを有効にするには、お使いの環境が次の前提条件を満たしている必要があります。

  - Office 365 プランでは、Skype for Business Online (プラン 2) 以上が必要です。 このプランでは会議機能をサポートする必要があります。
  
  - - Microsoft Teams 室のテレフォニーサービスプロバイダーを使用するエンタープライズ Voip (PSTN テレフォニー) が必要な場合は、Skype for Business Online (プラン 3) が必要です。
  
  - - テナントユーザーは Exchange メールボックスを持っている必要があります。
  
  - - Microsoft Teams のルームアカウントでは、Skype for Business Online (プラン 2) または Skype for Business Online (Plan 3) ライセンスが必要ですが、Exchange Online ライセンスは必要ありません。

- Skype for Business Server のライセンスを Microsoft Teams のルームアカウントに割り当てます。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>アカウントを作成して Active Directory と同期する

1. **Active Directory ユーザーとコンピューター**ツールで、Microsoft Teams の会議室のアカウントが作成されるフォルダーまたは組織単位を右クリックし、[**新規**作成] をクリックして、[**ユーザー**] をクリックします。

2. 前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。

3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > [**パスワードを無期限**にする] を選ぶことは、Microsoft Teams のルームの Skype For business Server の要件です。 ドメイン ルールによって無期限のパスワードが禁止される場合があります。 そうである場合は、Microsoft Teams のルームデバイスアカウントごとに例外を作成する必要があります。
  
4. アカウントを作成したら、ディレクトリの同期を実行します。 完了したら、Microsoft 365 管理センターの [ユーザー] ページに移動し、前の手順で作成したアカウントがオンラインに統合されていることを確認します。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>リモート メールボックスを有効にしてプロパティを設定する

1. [Exchange 管理シェルを開くか、](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) [リモート PowerShell を使用して exchange server に接続](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)します。

2. Exchange PowerShell で、次のコマンドを実行して、アカウントのメールボックス (メールボックスでアカウントを有効にします) を探します。

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   構文とパラメーターについて詳しくは、「[メールボックスを有効にする](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)」をご覧ください。

3. Exchange PowerShell で、会議の操作性を向上させるために、会議室メールボックスで次の設定を構成します。

   - 自動的な処理: 自動承諾 (会議の開催者は、手動での介入なく、会議の開催者が会議室の予約を直接受け取ります: 無料 = accept; busy = 拒否。)

   - Addオーガナイザー Ertosubject: $false (会議の開催者は、会議出席依頼の件名に追加されません)。

   - DeleteComments: $false (入力した会議出席依頼のメッセージ本文に含まれるテキストを保持)

   - DeleteSubject: $false (入力した会議出席依頼の件名を保持)

   - RemovePrivateProperty: $false (元の会議出席依頼の開催者によって送信されたプライベートフラグが指定されたままになります)。

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます)

   - AdditionalResponse: "これは Skype 会議室です。" (会議出席依頼に追加する追加のテキスト)

   この例では、Rigel-01 という名前の会議室メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   構文とパラメーターの詳細については、「 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

### <a name="assign-an-office-365-license"></a>Office 365 ライセンスを割り当てる

1. Azure Active Directory に接続します。 Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。 

2. デバイスアカウントには、有効な Office 365 ライセンスが必要です。または、Exchange と Microsoft Teams は動作しません。 ライセンスを所有している場合は、使用場所をデバイスアカウントに割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。 使用できる方法`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 利用可能な Sku の一覧を取得します。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 次に、次の方法を使用してライセンスを追加することができます。`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> コマンドレット. この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。

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

   詳細な手順については、「 [Office 365 PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。

### <a name="enable-the-device-account"></a>デバイスアカウントを有効にする

Skype for Business Online PowerShell は、Microsoft Teams と Skype for Business Online の両方のサービスを管理するために使用されます。

1. PC からリモート Windows PowerShell セッションを作成するには、次の手順を実行します。

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Microsoft Teams のルームアカウントを有効にするには、次のコマンドを実行します。

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   環境内の RegistrarPool パラメーターに使用する値がわからない場合は、次のコマンドを使用して、既存のユーザーの値を取得できます。

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Microsoft Teams のルームアカウントにライセンスを割り当てる

1. テナント管理者としてログインし、Office 365 管理ポータルを開いて、[管理者] アプリをクリックします。
2. [**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。
3. Microsoft Teams のルームアカウントをクリックし、ペンアイコンをクリックしてアカウント情報を編集します。
4. [**ライセンス**] をクリックします。
5. ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。 Microsoft Teams のルームでエンタープライズ Voip を使用する場合は、プラン3ライセンスを使用する必要があります。
6. [**保存**] をクリックします。

検証のために、任意のクライアントを使用してこのアカウントにログインできるようにする必要があります。
  
## <a name="see-also"></a>関連項目

[Microsoft Teams 室のアカウントを構成する](room-systems-v2-configure-accounts.md)

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)
  
[Microsoft Teams ルームの展開](room-systems-v2.md)
  
[Microsoft Teams 室コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)
