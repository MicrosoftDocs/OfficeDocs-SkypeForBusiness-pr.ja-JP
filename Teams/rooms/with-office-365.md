---
title: 会議室と共有Teamsデバイスのリソース アカウントを作成する
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
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Microsoft Teams Rooms、Surface HubのTeams Rooms、Teams ディスプレイでのホット デスクなど、会議室と共有デバイスのリソース アカウントを作成する方法については、この記事を参照してください。
ms.openlocfilehash: e788ca2086faf86f602ef0938d520ea03dce4ef4
ms.sourcegitcommit: 5bfd2e210617e4388241500eeda7b50d5f2a0ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2022
ms.locfileid: "64885025"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>会議室と共有Teamsデバイスのリソース アカウントを作成および構成する

この記事では、共有スペースとデバイスのリソース アカウントを作成する手順と、Windows、Android でのTeams Rooms、Surface HubでのTeams Rooms、ホットデスクのMicrosoft Teams Rooms用のリソース アカウントを構成する手順について説明します。Teamsが表示されます。

Microsoft 365リソース アカウントは、会議室やプロジェクターなどの特定のリソース専用のメールボックスとTeams アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して会議出席依頼に自動的に応答できます。 たとえば、会議室などの共通リソースがある場合は、その会議室のリソース アカウントを設定し、予定表の可用性に応じて会議の招待を自動的に受け入れるか拒否します。 

すべてのリソース アカウントは、単一のMicrosoft Teams Roomsインストールに固有であるか、ホットデスク処理の実装を表示Teams。

> [!NOTE]
> Microsoft Teams パネルを使用している場合、Teams Rooms リソース アカウントは、Teams Rooms パネルと関連付けられたTeams パネルの両方にサインインします。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> リソース アカウントでSkype for Businessを操作できるようにする必要がある場合は、「Skype for Business Serverを使用[したMicrosoft Teams Roomsのデプロイ](with-skype-for-business-server-2015.md)」を参照してください。

## <a name="before-you-begin"></a>はじめに

### <a name="requirements"></a>要件

環境に応じて、リソース アカウントを作成するには、1 つ以上のロールが必要です。

|**環境**|**必要なロール**|
|-----|-----|
|Azure Active Directory  <br/> |グローバル管理者またはユーザー管理者  <br/> |
|Active Directory  <br/> |Active Directory Enterprise管理者、ドメイン管理者、またはユーザーを作成するための委任された権限を持っています。 同期権限をAzure Active Directory Connectします。  <br/> |
|Exchange Online  <br/> |グローバル管理者またはExchange管理者   <br/> |
|Exchange Server  <br/> |Exchange組織管理または受信者管理   <br/> |

Teams Roomsのリソース アカウントを作成する場合、UPN はリソース アカウントの SMTP アドレスと一致する必要があります。 [Teams Roomsをデプロイする](requirements.md)前に、Microsoft Teams Rooms要件を確認してください。

### <a name="what-license-do-you-need"></a>必要なライセンスは何ですか?

Microsoft 365 リソース アカウントを作成する前に、必要なライセンスの種類を確認します。

- **Teams会議** リソース アカウントを共有デバイス (Microsoft Teams 会議室やTeamsディスプレイなど) にホット デスクで関連付け、それを使用してTeams会議に参加し、出席者がそれを使用してビデオやオーディオをプレゼンテーションできるようにする場合は、ミーティング ルーム ライセンスが必要です。 会議室のライセンスの詳細については、「[Teams ミーティング ルーム ライセンス](rooms-licensing.md)」を参照してください。

- **PSTN 通話** リソースが外部電話番号 (公衆交換電話網または PSTN 通話と呼ばれる) との間で通話を発信または受信する場合は、Microsoft 365 電話システムまたはMicrosoft 365 Business Voiceライセンスが必要です。 次の概要の手順 1 を完了するだけで済みます。 次に、詳細については、[アドオン ライセンスMicrosoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。

- リソース アカウントのみを使用してリソース&mdash;を予約する場合は、リソースを会議に招待し、リソース アカウントにライセンスを割り当てる必要がなく、次の概要の手順 1 を完了するだけで済む招待&mdash;を自動的に承諾または拒否します。  

## <a name="overview"></a>概要

**手順 1 -** [新しいリソース アカウントを作成します](#create-a-resource-account)。 または、会議室メールボックスが既に存在し、リソース アカウントに変換する場合は、[既存のExchange会議室メールボックスを変更](?tabs=existing-account#create-a-resource-account)できます。

**手順 2 -** 次に、Teams会議用 [にアカウントを構成](#configure-mailbox-properties)します。

**手順 3 -** リソース アカウントが共有デバイスに関連付けられている場合 (ホット デスクが表示されるTeamsなど) は、[パスワードの有効期限を無効にします](#turn-off-password-expiration)。

**手順 4 -** 最後に、アカウントがMicrosoft Teamsにアクセスできるように [、会議室のライセンスを割り当てます](#assign-a-meeting-room-license)。

リソース アカウントを作成して構成したら、「 [次の手順に従](#next-steps) って、配布グループ、ネットワーク機能、通話などの追加のセットアップ タスクを確認する」を参照してください。

## <a name="create-a-resource-account"></a>リソース アカウントを作成する

> [!TIP]
> リソース アカウントに名前を付ける場合は、電子メール アドレスの先頭に標準の名前付け規則を使用することをお勧めします。 これは、Azure Active Directoryでの管理を容易にする動的グループの作成に役立ちます。 たとえば、Microsoft Teams Roomsに関連付けられるすべてのリソース アカウントに対して "mrt-" を使用できます。

> [!TIP]
> Exchange OnlineとAzure Active Directoryを使用して、すべてのリソース アカウントを作成することをお勧めします。

次のいずれかのタブからメソッドを使用してリソース アカウントを作成します。

#### <a name="in-microsoft-365-admin-center"></a>[**Microsoft 365 管理センター**](#tab/m365-admin-center)

1. Microsoft 365 管理センターにサインインします。

2. Microsoft 365 テナントの管理者資格情報を指定します。

3. 左側のパネルの **[リソース** ] に移動し、[ **Rooms & equipment**] を選択します。 これらのオプションが左側のパネルで使用できない場合は、最初に **[すべて表示** ] を選択することが必要になる場合があります。

4. [ **リソース メールボックスの追加]** を選択して、新しいルーム アカウントを作成します。 アカウントの表示名とメール アドレスを入力し、[ **追加**] を選択し、[ **閉じる**] を選択します。

5. 既定では、リソース アカウントは次の設定で構成されます。

    - 繰り返し会議を許可する
    - 次の制限外の会議を自動的に拒否する
      - 予約期間 (日): 180
      - 最大期間 (時間): 24
    - 会議出席依頼の自動承諾

    それらを変更する場合は、[**閉じる**] を選択する前に [**スケジュール オプションの設定**] を選択します。 後で変更する場合は、**ResourcesRooms** >  **&機器** に移動し、リソース アカウントを選択します。 次に、[ **予約オプション**] で [編集] を選択 **します**。

6. **UsersActive** >  **ユーザー** に移動し、作成したルームを選択してプロパティ パネルを開きます。

7. 次に、リソース アカウントにパスワードを割り当てます。 パネルで、[パスワードの **リセット**] を選択します。
 
8. 共有デバイスでユーザーにパスワードの変更を要求すると、サインインの問題が発生します。 [ **このユーザーが最初にサインインしたときにパスワードを変更するように要求** する] をオフにし、[リセット] を選択 **します**。

9. [ **ライセンスとアプリ]** セクションで、デバイスがインストールされる国または地域に **[場所の選択]** を設定します。 次に、割り当てるライセンス (ミーティング ルームなど) を選択し、[変更の **保存]** を選択します。 ライセンスは組織によって異なる場合があります。

リソース メールボックスの設定を変更するには、「メールボックスの[プロパティを構成](#configure-mailbox-properties)する」またはExchange管理センターを使用する方法に関するページを参照してください。

また、帯域幅ポリシーまたは会議ポリシーをこのアカウントに適用する必要がある場合もあります。 詳細については、「 [次の手順](#next-steps) 」を参照してください。

#### <a name="with-exchange-online"></a>[**Exchange Onlineを使用する**](#tab/exchange-online)

1. [PowerShell のExchange OnlineにConnect](/powershell/exchange/connect-to-exchange-online-powershell)します。

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 既定では、会議室メールボックスにはアカウントが関連付けられていない。 会議室メールボックスを作成するときに、Microsoft Teamsで認証できるようにアカウントを追加します。

    新しいリソース メールボックスを作成している場合:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    この例では、次の設定で新しい会議室メールボックスを作成します:

    - アカウント: ConferenceRoom01@contoso.com
          
    - 名前: ConferenceRoom01
        
     - エイリアス: ConferenceRoom01
        
     - アカウントのパスワード: P@ $ $W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Exchangeハイブリッド構成でない場合は、次の手順「[メールボックスのプロパティを構成する」](#configure-mailbox-properties)に進むことができます。

Exchangeハイブリッド構成の場合は、オンプレミス ドメイン アカウントの電子メール アドレスを追加する必要があります。 詳細については、「[オンプレミスとOffice 365ユーザー アカウントディレクトリの同期](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)」を参照してください。

#### <a name="with-exchange-server"></a>[**Exchange Serverを使用する**](#tab/exchange-server)

  1. Exchange Management Shell にConnectします。 [Exchange 管理シェルを開く](/powershell/exchange/exchange-server/open-the-exchange-management-shell) または、[リモート PowerShellを使用して Exchange サーバーに接続し ます](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

   2. 新しい会議室メールボックスを作成するには:

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

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**既存のExchange会議室メールボックスを変更する**](#tab/existing-account)

既存の会議室メールボックスを変更してリソース アカウントにするには、次の構文を使用します。

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

この例では、エイリアス値 ConferenceRoom02 を持つ既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@$$W 0rd に設定します。

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Exchangeハイブリッド構成の場合は、オンプレミス ドメイン アカウントの電子メール アドレスも追加する必要があります。 詳細については、「[オンプレミスとOffice 365ユーザー アカウントディレクトリの同期](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)」を参照してください。

構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。

> [!NOTE]
> Surface Hubの Teams Room に対してこのアカウントを作成する場合は、このアカウントで ActiveSync も有効にする必要があります。 これにより、ホワイトボードなどの機能に使用できるSurface Hubから直接電子メールを送信できます。 詳細については、「[デバイス アカウントへの ActiveSync ポリシーの適用 (Surface Hub)](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts)」を参照してください。

---

> [!IMPORTANT]
> このリソース アカウントのみを使用してスペースを予約し、招待を自動的に承諾または拒否する場合は、設定が完了しました。 PSTN 通話にこのリソース アカウントを使用している場合は、[アドオン ライセンスMicrosoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)参照して、必要なライセンスを確認してください。
>
> リソース アカウントがWindowsのTeams Rooms、Android でのTeams Rooms、Surface HubのTeams Rooms、ホット デスクが表示されたTeamsの場合にのみ、次のセクションに進みます。

## <a name="configure-mailbox-properties"></a>メールボックスのプロパティを構成する

Exchange PowerShell (オンラインまたはオンプレミス) で、会議室メールボックスで次の設定を構成して、会議のエクスペリエンスを向上させます。

- **AutomateProcessing: `AutoAccept`** 会議の開催者は、人間の介入なしに直接会議室予約の決定を受け取ります。

- **AddOrganizerToSubject: `$false`** 会議の開催者は、会議出席依頼の件名に追加されません。

- **DeleteComments: `$false`** 受信会議出席依頼のメッセージ本文にテキストを保持します。 これは、One Touch Join エクスペリエンスを提供するために、外部Teamsとサードパーティの会議を処理するために必要です。

- **DeleteSubject: `$false`** 受信した会議出席依頼の件名を保持します。

- **ProcessExternalMeetingMessages: `$true`** Exchange組織の外部から送信された会議出席依頼を処理するかどうかを指定します。 外部Teams会議と[サード パーティの会議に必要です](/microsoftteams/rooms/third-party-join)。

- **RemovePrivateProperty: `$false`** 元の会議出席依頼で会議の開催者によって送信されたプライベート フラグが指定されたとおりに保持されるようにします。

- **AddAdditionalResponse: `$true`** AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。

- **AdditionalResponse: "これはMicrosoft Teams会議室です。** 会議の承諾応答に追加する追加のテキスト。

次の使用例は、ConferenceRoom01 という名前の会議室メールボックスでこれらの設定を構成します。

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

構文とパラメーターの詳細については、「[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

## <a name="turn-off-password-expiration"></a>パスワードの有効期限を無効にする

リソース アカウントのパスワードの有効期限が切れた場合、デバイスは有効期限が切れた後はサインインしません。 その後、リソース アカウントのパスワードを変更し、各デバイスで更新する必要があります。 これを回避するには、パスワードの有効期限を無効にできます。
  
> [!NOTE]
> **パスワードを期限切れにしない** 設定は、共有Microsoft Teamsデバイスの要件です。 ドメイン 規則で有効期限が切れていないパスワードを禁止している場合は、Teamsデバイス リソース アカウントごとに例外を作成する必要があります。

次のいずれかのタブの手順に従って、パスワードの有効期限を無効にします。

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

まず、Active Directory PowerShell にConnectします。

```PowerShell
   Connect-AzureAD
```

次に、「 [パスワードを期限切れにならないように設定する」を](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire)参照してください。

次の使用例は、アカウント ConferenceRoom01@contoso.com のパスワードを無期限に設定します。

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. MSOnline PowerShell にConnect:

       ```PowerShell
       Connect-MsolService
       ```

       Active Directory の詳細については、「[Azure Active Directory (MSOnline)」を](/powershell/azure/active-directory/overview?view=azureadps-1.0)参照してください。

2. 次の構文を使用して、パスワードを期限切れにならないように設定します。

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    次の使用例は、アカウント ConferenceRoom01@contoso.com のパスワードを無期限に設定します。

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (オンプレミス)**](#tab/active-directory1-password/)

1. Active Directory PowerShell にConnectします。

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Active Directory PowerShell の詳細については、「 [ActiveDirectory」を](/powershell/module/activedirectory/?view=windowsserver2022-ps)参照してください。

2. 次の構文を使用して、パスワードを期限切れにならないように設定します。

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    次の使用例は、アカウント ConferenceRoom01@contoso.com のパスワードを無期限に設定します。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>会議室のライセンスを割り当てる

Microsoft Teamsにサインインするには、リソース アカウントにMicrosoft 365またはOffice 365ライセンスが必要です。

> [!NOTE]
> Microsoft Teams Rooms StandardとMicrosoft Teams Rooms Premiumは、Teams Roomsを含む共有会議室デバイスで使用できる 2 つの SKU です。 ホットデスクを使用するTeamsディスプレイには、会議室のライセンスが必要です。 詳細については、「[Teams会議室ライセンス](rooms-licensing.md)」を参照してください。

Microsoft 365 管理センターを使用してライセンスを割り[当てるには、「ユーザーにライセンスを割り当てる」を](/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。 Azure ADを使用してライセンスを割り当てるには、次のいずれかのタブを参照してください。

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Azure ADにConnectする
  
    ```PowerShell
    Connect-AzureAD
    ```

     Active Directory の詳細については、「[powerShell for GraphのAzure Active Directory」を](/powershell/azure/active-directory/overview?view=azureadps-2.0)参照してください。
    
2. コマンドレットを使用して、リソース アカウントに使用場所を `Set-AzureADUser` 割り当てます。 これにより、使用可能なライセンス SKU が決まります。

    この例では、ユーザーは米国 (米国) にあります。

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. 次に、Microsoft 365またはOffice 365組織で使用可能な SKU の一覧を取得するために使用`Get-AzureADSubscribedSku`します。

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. ライセンスを割り当てるには、コマンドレットを `Set-AzureADUser` 使用し、ライセンス SKU ID (手順 2 を参照) を PowerShell ライセンスの種類オブジェクトに変換します。 次に、そのオブジェクトをリソース アカウントに割り当てます。 次の例では、ライセンス SKU ID は 6070a4c8-34c6-4937-8dfb-39bbc6397a60 で、アカウント conferenceroom01@contoso.com に割り当てられます。

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. MSOnline PowerShell にConnectします。

   ```PowerShell
   Connect-MsolService
   ```

    Active Directory の詳細については、[Azure Active Directory (MSOnline) を](/powershell/azure/active-directory/overview?view=azureadps-1.0)参照してください。

2.  コマンドレットを使用して、リソース アカウントに使用場所を `Set-MsolUser` 割り当てます。 これにより、使用可能なライセンス SKU が決まります。

    この例では、ユーザーは米国 (米国) にあります。
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    その後`Get-MsolAccountSku`、Microsoft 365またはOffice 365組織で使用可能な SKU の一覧を取得できます。

4. ライセンスを割り当てるには、コマンドレットを使用します `Set-MsolUser` 。 この例では、"contoso:MEETING_ROOM" ライセンスがアカウント conferenceroom01@contoso.com に割り当てられます。

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

アカウントの作成とライセンスの割り当てを検証するには、作成したアカウントを使用してTeamsクライアントにサインインします。

## <a name="next-steps"></a>次の手順

### <a name="meeting-policies"></a>ミーティング ポリシー

このアカウントには、カスタム ネットワーク、帯域幅、または会議ポリシーを適用することが必要な場合があります。 ネットワーク ポリシーと帯域幅ポリシーの詳細については、「 [オーディオ & ビデオの会議ポリシー設定](/microsoftteams/meeting-policies-audio-and-video)」を参照してください。 Teams Roomsでは、会議ポリシーの帯域幅を 10 Mbps に設定することをお勧めします。

コラボレーションを目的として、PowerPoint Live、ホワイトボード、共有ノートを有効にします。 会議ポリシー設定を有効にすることをお勧めします。"今すぐプライベート会議に参加する" 設定を有効にすることをお勧めします。 会議ポリシーを作成して、Teams Roomsの参加者とゲストの設定を調整することができます。 たとえば、会議を自動的に許可する出席者など、ロビーの設定を確認します。 会議ポリシーのTeamsの詳細については、「[Microsoft Teamsでの会議ポリシーの管理](/microsoftteams/meeting-policies-overview)」を参照してください。

### <a name="calling"></a>通話

リソース アカウントでの呼び出しを有効にする一意の要件はありません。 通常のユーザーを有効にするのと同じ方法で、呼び出しに対してリソース アカウントを有効にします。

> [!NOTE]
> デバイス リソース アカウントに通話ポリシーを割り当てることで、共有デバイスのボイス メールをオフにすることをお勧めします。 詳細については、「[Teamsでの通話と通話転送](../teams-calling-policy.md)」を参照してください。

### <a name="configure-distribution-groups-for-teams-calendar"></a>Teams予定表の配布グループを構成する

会議室の場所を整理するには、デバイス リソース アカウントをExchange配布グループに追加します。 たとえば、3 つの異なる地理的な場所にオフィスがある場合は、3 つの配布グループを作成し、各場所に適切なリソース アカウントを追加できます。 詳細については、「 [ルームリストを作成する](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list)」を参照してください。

### <a name="configure-places-for-outlook-calendar"></a>Outlook カレンダーの場所を構成する
会議室の場所を Outlook 会議室検索に表示するには、Set-Place Exchange PowerShell コマンドレットを使用する必要があります。 Outlookに Room Finder を設定Set-Placeだけでなく、ルームの容量や、会議室の建物の床などのメタデータを追加することもできます。 詳細については、「 [Set-Place](/powershell/module/exchange/set-place)」を参照してください。

## <a name="related-articles"></a>関連記事

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)

[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)

[Microsoft Teams Rooms を管理する](rooms-manage.md)

[Microsoft Teams Rooms ライセンス](rooms-licensing.md)
