---
title: Office 365 での Microsoft Teams ミーティングを展開する
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: このトピックでは、会議室と会議室をデプロイするMicrosoft Teams方法についてOffice 365。
ms.openlocfilehash: d4c66fb863c5c41a717808ddca43002752510fb5
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056027"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Office 365 での Microsoft Teams ミーティングを展開する

このトピックでは、会議室と会議室をデプロイするMicrosoft Teams方法についてOffice 365。

## <a name="requirements"></a>要件

会議室と会議室をMicrosoft TeamsするOffice 365、要件を満たしていることを確認してください。 詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。

### <a name="add-a-resource-account"></a>リソース アカウントを追加する

1. Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

2. Exchange Online PowerShell で、新しい会議室メールボックスを作成するか、既存の会議室メールボックスを変更します。 既定では、ルーム メールボックスにはアカウントが関連付けされません。 認証を許可するルーム メールボックスを作成または変更する場合は、アカウントを追加する必要があります。

   - 新しい会議室メールボックスを作成するには、次の構文を使用します。

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、次の設定で新しい会議室メールボックスを作成します:

     - 名前: 会議室 01

     - エイリアス: ConferenceRoom01

     - アカウント: ConferenceRoom01@contoso.com

     - アカウントのパスワード: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 既存の会議室メールボックスを変更するには、次の構文を使用します。

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、ConferenceRoom02 というエイリアス値を持つ既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@$$W 0rd に設定します。

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。


3. Exchange Online PowerShell で、会議の操作性を向上させるために、次のように会議室メールボックスの設定を構成します。

   - AutomateProcessing: AutoAccept (メールボックスは、人の介入なしに、部屋の予約を直接自動的に決定します)。

   - AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)

   - DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)

   - DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)

   - RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)

   - AdditionalResponse: "This is a Microsoft Teams Meeting Room!" (会議出席依頼に追加するテキスト)。

   この例では、Project-Rigel-01という名前の会議室メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   構文とパラメーターの詳細情報については、[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。
   
4. Connect MS Online PowerShell にアクセスするには、'Connect-MsolService -Credential $cred' powershell コマンドレットを実行して Active Directory の値を設定します。 Active Directory の詳細については、「[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。 

5. 会議室アカウントでパスワードの有効期限を無効にTeams強く推奨されます。 アカウント ConferenceRoom01 のパスワードの有効期限を無効にする方法の例を次に示します。

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. リソース アカウントに接続するには、リソース アカウントOffice 365有効なライセンスが必要Microsoft Teams。 また、使用場所をデバイス アカウントに割り当てる必要があります。これにより、アカウントで使用できるライセンス SKU が決されます。 を使用 `Get-MsolAccountSku` して、テナントに対して使用可能な SKU の一Office 365できます。 コマンドレットを使用してライセンスを追加 `Set-MsolUserLicense` できます。

   この例では、ミーティング ルームに米国に拠点を置くユーザーにライセンスを割り当てします。

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。


## <a name="validate"></a>検証

検証の場合は、任意のクライアント クライアントMicrosoft Teamsして、作成したアカウントにサインインできます。

## <a name="see-also"></a>関連項目
[検索とルームの候補エクスペリエンスを向上するために、追加のメタデータでルーム メールボックスを更新する](/powershell/module/exchange/set-place)

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)

[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)

[Microsoft Teams Rooms コンソールを構成する](console.md)

[Microsoft Teams Rooms を管理する](rooms-manage.md)

[Microsoft Teams Rooms ライセンス](rooms-licensing.md)
