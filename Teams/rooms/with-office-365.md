---
title: 会議室と共有デバイスのリソース アカウントTeamsする
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
description: Microsoft Teams Rooms、Teams Rooms on Surface Hub、Teams ディスプレイでのホット デスクなど、会議室と共有デバイスのリソース アカウントを作成する方法については、この記事を参照してください。
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514548"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>会議室と共有デバイスのリソース アカウントを作成Teams構成する

この記事では、共有スペースとデバイスのリソース アカウントを作成する手順について説明します。また、Microsoft Teams Rooms on Windows、Teams Rooms on Android、Teams Rooms on Surface Hub、および Teams ディスプレイでのホットデスクを構成する手順について説明します。

Microsoft 365アカウントは、会議室Teamsプロジェクターなどの特定のリソース専用のメールボックス アカウントとリソース アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して、会議出席招待に自動的に応答できます。 たとえば、会議室などの一般的なリソースがある場合は、予定表の空き時間に応じて会議出席招待を自動的に承諾または拒否する、その会議室のリソース アカウントを設定できます。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> リソース アカウントでリソース アカウントを使用する必要がある場合は、「Skype for Business を使用して会議室をデプロイするMicrosoft Teams[」を参照Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>はじめに

### <a name="requirements"></a>要件

環境によっては、リソース アカウントを作成するために 1 つ以上のロールが必要です。

|**環境**|**必要なロール**|
|-----|-----|
|Azure Active Directory  <br/> |グローバル管理者またはユーザー管理者  <br/> |
|Active Directory  <br/> |Active Directory Enterprise管理者、ドメイン管理者、またはユーザーを作成する委任された権限を持っています。 Azure Active Directory Connectを選択します。  <br/> |
|Exchange Online  <br/> |グローバル管理者またはExchange管理者   <br/> |
|Exchange Server  <br/> |Exchange管理または受信者管理   <br/> |

TEAMS Rooms のリソース アカウントを作成する場合、UPN はリソース アカウントの SMTP アドレスと一致する必要があります。 会議室[をMicrosoft Teamsする前に、「](requirements.md)会議室の要件」Teamsしてください。

### <a name="what-license-do-you-need"></a>どのようなライセンスが必要ですか?

リソース アカウントを作成Microsoft 365、必要なライセンスの種類を確認してください。

- **Teams** 会議 Microsoft Teams 会議室や Teams ディスプレイなどの共有デバイスにリソース アカウントを関連付け、それを使用して Teams 会議に参加し、出席者が会議を通じてビデオや音声を表示するには、ミーティング ルーム ライセンスが必要です。 会議室のライセンスの詳細については、「Teams ミーティング ルーム[」を参照してください](rooms-licensing.md)。

- **PSTN 通話** リソースが外部の電話番号 (公衆交換電話網または PSTN 通話と呼ばれる) との間で通話を発信または受信するには、Microsoft 365 電話システム または Microsoft 365 Business Voice ライセンスが必要です。 手順 1 を完了する必要があるのは、次の概要のみです。 詳細については、「[Microsoft Teamsライセンスの追加」](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。

- &mdash;&mdash;リソース アカウントのみを使用してリソースを予約している場合は、リソースを会議に招待し、招待を自動的に承諾または拒否します。リソース アカウントにライセンスを割り当てる必要は一切ないので、次の概要の手順 1 を完了する必要があります。  

## <a name="overview"></a>概要

**手順 1 - 新**[しいリソース アカウントを作成します](#create-a-resource-account)。 または、ルーム メールボックスが既に存在し、それをリソース アカウントに変換する場合は、既存のルーム メールボックスExchange[変更できます](?tabs=existing-account#create-a-resource-account)。

**手順 2 -** 次に [、会議用に](#configure-mailbox-properties)アカウントTeamsします。

**手順 3 -** リソース アカウントが共有デバイスに関連付けられる場合 (Teams など)、パスワードの有効期限を [オフにします](#turn-off-password-expiration)。

**手順 4 -** 最後に、[アカウントが会議にアクセスできるよう](#assign-a-meeting-room-license)会議室のライセンスを割り当Microsoft Teams。

リソース アカウントを作成して構成した後は、「[](#next-steps)次の手順」を参照して、配布グループ、ネットワーク機能、呼び出しなどの追加のセットアップ タスクを確認します。

## <a name="create-a-resource-account"></a>リソース アカウントを作成する

> [!TIP]
> リソース アカウントに名前を付ける場合は、電子メール アドレスの先頭に標準の名前付け規則を使用することをお勧めします。 これは、動的グループの作成に役立ち、動的グループの管理を容易Azure Active Directory。 たとえば、会議室に関連付けられるすべてのリソース アカウントに "Microsoft Teamsできます。

> [!TIP]
> リソース アカウントとリソース アカウントを使用して、すべてのリソース Exchange Online作成Azure Active Directory。

次のいずれかのタブのメソッドを使用してリソース アカウントを作成します。

#### <a name="in-microsoft-365-admin-center"></a>[**[in Microsoft 365 管理センター**](#tab/m365-admin-center)

1. Microsoft 365 管理センターにサインインします。

2. テナントの管理者資格情報をMicrosoft 365します。

3. 左側のパネル **で [** リソース] に移動し、[会議室] を選択& **します**。 これらのオプションが左側のパネルで使用できない場合は、[すべて表示] を最初に選択 **する必要** があります。

4. [ **リソース メールボックスの追加] を選択** して、新しいルーム アカウントを作成します。 アカウントの表示名とメール アドレスを入力し、[追加] を **選択して**、[閉じる] を **選択します**。

5. 既定では、リソース アカウントは次の設定で構成されます。

    - 繰り返し会議を許可する
    - 次の制限を超え、会議を自動的に拒否する
      - 予約期間 (日): 180
      - 最大期間 (時間): 24
    - 会議出席依頼を自動承諾する

    変更する場合は、[閉じる] を選択する **前に [** スケジュール オプションの設定] を **選択します**。 後で変更する場合は、[**リソース** > ]**Rooms &、** リソース アカウントを選択します。 次に、[ **予約オプション] で [** 編集] を **選択します**。

6. [ユーザー **]アクティブ** >  **ユーザーに移動** し、作成したルームを選択してプロパティ パネルを開きます。

7. 次に、リソース アカウントにパスワードを割り当てる。 パネルで、[パスワードのリセット] **を選択します**。
 
8. ユーザーに共有デバイスのパスワードの変更を要求すると、サインインの問題が発生します。 [ **このユーザーが初めてサインインするときにパスワードを変更する] をオフにし、[** リセット] を **選択します**。

9. [ライセンス **とアプリ] セクション** で **、[場所の** 選択] をデバイスがインストールされる国または地域に設定します。 次に、割り当てるライセンス (例: ミーティング ルーム選択し、[変更の保存] **を選択します**。 ライセンスは組織によって異なる場合があります。

リソース メールボックスの設定を変更するには、「メールボックスの[](#configure-mailbox-properties)プロパティを構成する」または「管理センターでExchangeを使用する」を参照してください。

また、このアカウントに帯域幅ポリシーまたは会議ポリシーを適用する必要がある場合があります。 詳細については [、「次のステップ](#next-steps) 」を参照してください。

#### <a name="with-exchange-online"></a>[**次のExchange Online**](#tab/exchange-online)

1. Connect [PowerShell をExchange Onlineします](/powershell/exchange/connect-to-exchange-online-powershell)。

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 既定では、ルーム メールボックスにはアカウントが関連付けされません。 ルーム メールボックスを作成するときにアカウントを追加し、そのアカウントをMicrosoft Teams。

    新しいリソース メールボックスを作成している場合:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    この例では、次の設定で新しい会議室メールボックスを作成します:

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

ハイブリッド構成を構成Exchange場合は、次の手順「メールボックスのプロパティを構成[する」に進みます](#configure-mailbox-properties)。

ハイブリッド構成を使用Exchange場合は、オンプレミス ドメイン アカウントのメール アドレスを追加する必要があります。 詳細[については、「オンプレミスとユーザー アカウントのディレクトリOffice 365同期する](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)」を参照してください。

#### <a name="with-exchange-server"></a>[**このExchange Server**](#tab/exchange-server)

  1. Connect管理シェルExchangeにアクセスします。 [Exchange 管理シェルを開く](/powershell/exchange/exchange-server/open-the-exchange-management-shell) または、[リモート PowerShellを使用して Exchange サーバーに接続し ます](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

   2. 新しいルーム メールボックスを作成するには:

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

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**既存のルーム メールボックスExchange変更する**](#tab/existing-account)

既存のルーム メールボックスをリソース アカウントに変更するには、次の構文を使用します。

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

この例では、エイリアス値 ConferenceRoom02 を持つ既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@$$W 0rd に設定します。

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

ハイブリッド構成Exchange場合は、オンプレミス ドメイン アカウントのメール アドレスも追加する必要があります。 詳細[については、「オンプレミスとユーザー アカウントのディレクトリOffice 365同期する](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)」を参照してください。

構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。

> [!NOTE]
> このアカウントを Teams Room on Surface Hub作成する場合は、このアカウントで ActiveSync も有効にする必要があります。 これにより、Whiteboard のような機能に使用できる Surface Hubから直接メールを送信できます。 詳細[については、「デバイス アカウントへの ActiveSync ポリシーの適用 (Surface Hub)」](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts)を参照してください。

---

> [!IMPORTANT]
> このリソース アカウントを使用してスペースを予約し、招待を自動的に承諾または拒否する場合は、設定が完了しています。 PSTN 通話にこのリソース アカウントを使用している場合は、「Microsoft Teams[アドオン](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) ライセンス」を参照して、必要なライセンスを確認してください。
>
> リソース アカウントが Teams Rooms on Windows、Teams Rooms on Android、Teams Rooms on Surface Hub、または Teams ディスプレイ (ホットデスク付き) の場合にのみ、次のセクションに進む。

## <a name="configure-mailbox-properties"></a>メールボックスのプロパティを構成する

オンラインまたはExchange PowerShell では、会議室メールボックスで次の設定を構成して、会議のエクスペリエンスを向上します。

- **AutomateProcessing: `AutoAccept`** 会議の開催者は、人の介入なしに直接会議室の予約決定を受け取る。

- **AddOrganizerToSubject: `$false`** 会議の開催者は、会議出席依頼の件名に追加されません。

- **DeleteComments: `$false`** 受信した会議出席依頼のメッセージ本文にテキストを保存します。 これは、One Touch Join エクスペリエンスを提供Teams外部の会議やサード パーティの会議を処理するために必要です。

- **DeleteSubject: `$false`** 受信した会議出席依頼の件名を保持します。

- **ProcessExternalMeetingMessages: `$true`** 組織外の会議出席依頼を処理するかどうかをExchangeします。 外部の会議Teamsサードパーティ[の会議に必要です](/microsoftteams/rooms/third-party-join)。

- **RemovePrivateProperty: `$false`** 元の会議出席依頼で会議開催者によって送信されたプライベート フラグが指定されたままに維持されます。

- **AddAdditionalResponse: `$true`** AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。

- **AdditionalResponse: "This is a Microsoft Teams Meeting room!"** 会議の承諾応答に追加する追加テキスト。

この例では、ConferenceRoom01 という名前の会議室メールボックスでこれらの設定を構成します。

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

構文とパラメーターの詳細については、「[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

## <a name="turn-off-password-expiration"></a>パスワードの有効期限をオフにする

リソース アカウントのパスワードの有効期限が切れた場合、有効期限が過ぎると、デバイスはサインインしません。 その後、リソース アカウントのパスワードを変更し、各デバイスで更新する必要があります。 これを回避するには、パスワードの有効期限をオフにします。
  
> [!NOTE]
> パスワード **の有効期限が切れない設定** は、共有デバイスMicrosoft Teamsです。 有効期限が切れないパスワードがドメイン ルールで禁止されている場合は、デバイス リソース アカウントの各ドメインTeams作成する必要があります。

次のいずれかのタブの手順に従って、パスワードの有効期限をオフにします。

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

最初に、Connect Active Directory PowerShell に移動します。

```PowerShell
   Connect-AzureAD
```

次に、「 [パスワードを有効期限切れに設定する」を参照してください](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire)。

この例では、アカウントアカウントのパスワードを ConferenceRoom01@contoso.com に設定します。

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Connect MSOnline PowerShell に接続します。

       ```PowerShell
       Connect-MsolService
       ```

       Active Directory の詳細については、「Azure Active Directory [(MSOnline)」を参照してください](/powershell/azure/active-directory/overview?view=azureadps-1.0)。

2. 次の構文を使用して、パスワードの有効期限を決して設定します。

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    この例では、アカウントアカウントのパスワードを ConferenceRoom01@contoso.com に設定します。

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (オンプレミス)**](#tab/active-directory1-password/)

1. Connect Active Directory PowerShell に移動します。

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Active Directory PowerShell の詳細については、「 [ActiveDirectory」を参照してください](/powershell/module/activedirectory/?view=windowsserver2022-ps)。

2. 次の構文を使用して、パスワードの有効期限を決して設定します。

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    この例では、アカウントアカウントのパスワードを ConferenceRoom01@contoso.com に設定します。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>会議室のライセンスを割り当てる

リソース アカウントにサインインするには、Microsoft 365またはOffice 365ライセンスが必要Microsoft Teams。

> [!NOTE]
> Microsoft Teams会議室 Standard と Microsoft Teams 会議室 プレミアムは、会議室を含む共有会議室デバイスで使用できる 2 Teams SKU です。 会議室のライセンスは、ホットデスクTeamsディスプレイに必要です。 詳細については、「会議室の[ライセンスTeamsを参照してください](rooms-licensing.md)。

ライセンスを割り当てるには、Microsoft 365 管理センターにライセンスを[割り当てるに関するページを参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。 ライセンスを割り当てるにはAzure AD次のいずれかのタブを参照してください。

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. ConnectにAzure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Active Directory の詳細については、「[PowerShell for Azure Active Directory」を参照Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0)。
    
2. コマンドレットを使用して、リソース アカウントに使用場所を割り当 `Set-AzureADUser` てる。 これにより、使用可能なライセンス SKU が決定されます。

    この例では、ユーザーは米国 (米国) に位置しています。

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. 次に、 `Get-AzureADSubscribedSku` を使用して、組織または組織で使用可能な SKU Microsoft 365取得Office 365します。

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. ライセンスを割り当 `Set-AzureADUser` てるには、 コマンドレットを使用し、ライセンス SKU ID (手順 2 を参照) を PowerShell ライセンスタイプ オブジェクトに変換します。 次に、そのオブジェクトをリソース アカウントに割り当てる。 次の例では、ライセンス SKU ID は 6070a4c8-34c6-4937-8dfb-39bbc6397a60 であり、アカウント conferenceroom01@contoso.com に割り当てられます。

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

1. Connect MSOnline PowerShell に接続します。

   ```PowerShell
   Connect-MsolService
   ```

    Active Directory の詳細については、「Azure Active Directory [(MSOnline)」を参照してください。](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  コマンドレットを使用して、リソース アカウントに使用場所を割り当 `Set-MsolUser` てる。 これにより、使用可能なライセンス SKU が決定されます。

    この例では、ユーザーは米国 (米国) に位置しています。
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    その後、 を`Get-MsolAccountSku`使用して、組織または組織で使用できる SKU のMicrosoft 365取得Office 365できます。

4. ライセンスを割り当てるには、 コマンドレットを使用 `Set-MsolUser` します。 この例では、"contoso:MEETING_ROOM" ライセンスがアカウント アカウントに割り当 conferenceroom01@contoso.com。

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

アカウントの作成とライセンスの割り当てを検証するには、作成したアカウントをTeamsクライアントにサインインします。

## <a name="next-steps"></a>次のステップ

### <a name="network-and-bandwidth"></a>ネットワークと帯域幅

このアカウントには、カスタム ネットワーク、帯域幅、または会議ポリシーの適用が必要な場合があります。 ネットワークポリシーと帯域幅ポリシーの詳細については、「ビデオのオーディオと帯域幅の会議 [ポリシー設定」を&してください](/microsoftteams/meeting-policies-audio-and-video)。 会議室Teams、会議ポリシーの帯域幅を 10 Mbps に設定することをお勧めします。

共同作業の目的で、Live、Whiteboard、PowerPoint共有ノートを有効にしてください。 会議ポリシーを作成して、会議室の参加者とゲスト設定を調整Teamsがあります。 たとえば、会議に自動的に参加を認める出席者などのロビー設定を確認します。 会議ポリシーの詳細については、「Teamsで会議ポリシーを[管理する」をMicrosoft Teams](/microsoftteams/meeting-policies-overview)。

### <a name="calling"></a>通話

リソース アカウントでの呼び出しを有効にする固有の要件はありません。 通常のユーザーを有効にするのと同じ方法で、 を呼び出すリソース アカウントを有効にできます。

> [!NOTE]
> 通話ポリシーをデバイス リソース アカウントに割り当て、共有デバイスのボイス メールをオフにすることをお勧めします。 詳細[については、「Teams での](../teams-calling-policy.md)通話と転送」を参照してください。

### <a name="configure-distribution-groups"></a>配布グループを構成する

会議室の場所を整理するには、デバイス リソース アカウントを配布グループExchange追加できます。 たとえば、3 つの異なる地理的な場所にオフィスがある場合は、3 つの配布グループを作成し、適切なリソース アカウントを各場所に追加できます。 詳細については、「会議室リストを [作成する」を参照してください](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list)。

## <a name="related-articles"></a>関連記事

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)

[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)

[Microsoft Teams Rooms を管理する](rooms-manage.md)

[Microsoft Teams Rooms ライセンス](rooms-licensing.md)
