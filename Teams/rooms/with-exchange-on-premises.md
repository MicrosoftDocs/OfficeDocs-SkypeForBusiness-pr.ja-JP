---
title: オンプレミスで Exchange を使用し Microsoft Teams Rooms を展開
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: このトピックでは、オンプレミスの Exchange が搭載されたハイブリッド環境に Microsoft Teams Rooms を展開する方法について説明します。
ms.openlocfilehash: 96d8a49cd75e3413739d36a3c86a91daa72b22e6
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909538"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>オンプレミスで Exchange を使用し Microsoft Teams Rooms を展開する

このトピックでは、オンプレミスとオンプレミスのハイブリッド環境に Microsoft Teams Rooms をデプロイするExchange方法について説明Microsoft Teams。
  
組織に複数のサービスが混在し、一部がオンプレミスでホストされ、一部がオンラインでホストされている場合、構成は各サービスがホストされている場所によって異なります。 このトピックでは、オンプレミスでホストされている Microsoft Teams Rooms Exchangeハイブリッド デプロイについて説明します。 この種類の展開には、さまざまな違いがあるため、すべての手順を詳細に説明することはできません。 次のプロセスは、多くの構成で機能します。 このプロセスがユーザーのセットアップに適していない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ結果を達成するか、または他の展開オプションをお勧めします。

Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいユーザー アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams Rooms のユーザー アカウントに変換する助けとなります。 必要な場合は、次の手順に従って、Microsoft Teams Rooms のデバイスが使用するアカウントを構成できます。
  
## <a name="requirements"></a>要件

Microsoft Teams Rooms をオンプレミスの Exchangeで展開する前に、要件を満たしていることをご確認ください。 詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。
  
Microsoft Teams Rooms と Exchange をオンプレミスでデプロイする場合は、Active Directory 管理ツールを使用して、オンプレミス ドメイン アカウントのメール アドレスを追加します。 このアカウントは、Microsoft 365 または Office 365 に同期されます。 次の操作が必要です。
  
- アカウントを作成し、アカウントを Azure Active Directory。

- リモート メールボックスを有効にしてプロパティを設定する。

- ライセンスを割りMicrosoft 365またはOffice 365します。

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>アカウントを作成し、アカウントと同期Azure Active Directory

1. **Active Directoryユーザーおよびコンピューター** ツールで、フォルダーまたはMicrosoft Teams Rooms のアカウントの作成先となる組織単位を右クリックし、**新規** そして **ユーザー** の順にクリックします。

2. [氏名] ボックスに表示 **名を入力** し、[ユーザー ログオン名] ボックスにエイリアス **を入力** します。 **[次へ]** をクリックします。

3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > [パスワードの **有効期限がありません] を選択** すると、会議室Microsoft Teamsされます。 有効期限が切れないパスワードは、ドメインのルールで禁止されるかもしれません。 その場合は、Microsoft Teams Rooms のユーザーアカウントごとに例外を作成する必要があります。
  
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

   - AdditionalResponse: "This is a Microsoft Teams Meeting room!" (会議出席依頼に追加するテキスト)。

   この例では、Project-Rigel-01という名前の会議室メールボックスでこれらの設定を構成します。

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   構文とパラメーターの詳細情報については、[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Microsoft 365 または Office 365 ライセンスを割り当てる

1. Azure Active Directoryに接続する アプリケーションの詳細Azure Active Directory [Azure ActiveDirectory (MSOnline) 1.0 を参照してください](/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。 

2. デバイスアカウントには、Microsoft 365 または Office 365 の有効なライセンスが必要です。さもないと Exchange および Microsoft Teams は機能しません。 ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。 `Get-MsolAccountSku` を使用して、 <!-- Get-AzureADSubscribedSku --> 使用可能な SKUの一覧を取得できます。

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

   詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。

検証を行う場合は、通常、どのクライアントを使用してもこのアカウントにログインできます。
  
## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
