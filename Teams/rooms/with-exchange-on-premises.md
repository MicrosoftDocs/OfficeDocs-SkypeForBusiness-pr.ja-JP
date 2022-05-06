---
title: Exchangeオンプレミス (ハイブリッド) を使用してMicrosoft Teams Roomsをデプロイする
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
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767230"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>オンプレミスのExchangeを使用してMicrosoft Teams Roomsをデプロイする (ハイブリッド)

オンプレミスとMicrosoft TeamsをExchangeハイブリッド環境にMicrosoft Teams Roomsをデプロイする方法については、このトピックを参照してください。
  
組織にサービスが混在していて、一部がオンプレミスでホストされ、一部がオンラインでホストされている場合、構成は各サービスがホストされる場所によって異なります。 このトピックでは、オンプレミスでホストExchange Microsoft Teams Roomsのハイブリッド展開について説明します。 この種類の展開には、さまざまな違いがあるため、すべての手順を詳細に説明することはできません。 次のプロセスは、多くの構成で機能します。 このプロセスがユーザーのセットアップに適していない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ結果を達成するか、または他の展開オプションをお勧めします。
  
## <a name="requirements"></a>要件

Microsoft Teams Rooms をオンプレミスの Exchangeで展開する前に、要件を満たしていることをご確認ください。 詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>リモートメールボックスを有効にしてプロパティを設定する

1. [Exchange 管理シェルを開く](/powershell/exchange/exchange-server/open-the-exchange-management-shell) または、[リモート PowerShellを使用して Exchange サーバーに接続し ます](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. Exchange PowerShell で、新しい会議室メールボックスを作成するか、既存の会議室メールボックスを変更します。 既定では、会議室メールボックスにはアカウントが関連付けられていないため、会議室メールボックスを作成または変更するときに、Microsoft Teamsでの認証を許可するアカウントを追加する必要があります。

   - 新しい会議室メールボックスを作成するには、次の構文を使用します。

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     この例では、次の設定で新しい会議室メールボックスを作成します:

     - アカウント: ConferenceRoom01@contoso.com
  
     - 名前: ConferenceRoom01

     - エイリアス: ConferenceRoom01

     - アカウントのパスワード: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 既存の会議室メールボックスを変更するには、次の構文を使用します。

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、エイリアス値 ConferenceRoom02 を持つ既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@$$W 0rd に設定します。 アカウントは、既存のエイリアス値が原因で ConferenceRoom02@contoso.com されることに注意してください。

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。

3. Exchange Online PowerShell で、会議機能を向上させるために、会議室メールボックスの次の設定を構成します。

   - AutomateProcessing: AutoAccept (会議の開催者は、人の介入なしに直接会議室の予約の決定を受け取ります。

   - AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)

   - DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)

   - DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)

   - RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)

   - AdditionalResponse: "これはMicrosoft Teams会議室です。 (会議出席依頼に追加するテキスト)。

   この例では、ConferenceRoom01 という名前の会議室メールボックスでこれらの設定を構成します。

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   構文とパラメーターの詳細については、「[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

### <a name="set-password-to-never-expire"></a>パスワードを期限切れにならないように設定する

1. **Active Directory ユーザーとコンピューター** ツールで、Microsoft Teams Rooms アカウントを見つけて右クリックし、[**プロパティ**] を選択します。

2. [ **パスワードの有効期限が切れない** ] チェック ボックスをオンにし、[OK] をクリック **します**。

   > [!NOTE]
   > **[パスワードの有効期限が切れない**] を選択することは、Microsoft Teams Roomsの要件です。 有効期限が切れないパスワードは、ドメインのルールで禁止されるかもしれません。 その場合は、Microsoft Teams Rooms アカウントごとに例外を作成する必要があります。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Microsoft 365 または Office 365 ライセンスを割り当てる

1. Azure Active Directoryに接続する Azure Active Directoryの詳細については、[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0) を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。 

2. リソース アカウントに有効なMicrosoft 365またはOffice 365ライセンスが必要です。または、ExchangeとMicrosoft Teamsは機能しません。 ライセンスがある場合は、リソース アカウントに使用場所を割り当てる必要があります。これにより、アカウントで使用できるライセンス SKU が決まります。 `Get-MsolAccountSku` を使用して、 <!-- Get-AzureADSubscribedSku --> 使用可能な SKUの一覧を取得できます。

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. 次に、以下の `Set-MsolUserLicense`を使用してライセンスを追加することができます。 <!--Set-AzureADUserLicense --> することができます。 この例では、ミーティング ルーム ライセンスをアカウントに追加します。

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。

検証を行う場合は、通常、どのクライアントを使用してもこのアカウントにログインできます。
  
## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
