---
title: PowerShell を使用して Microsoft Teams のコラボレーション バーの Microsoft Teams リソース アカウントを作成する
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Microsoft Teams のコラボレーション バーを展開する方法については、このトピックを参照してください。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115605"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>PowerShell を使用して Microsoft 365 リソース アカウントを作成する

PowerShell を使用して Microsoft Teams のコラボレーション バーのリソース アカウントを作成する方法については、このトピックを参照してください。

リソース アカウントを作成する最も簡単な方法は、Microsoft 365 管理センターを使用する方法です。 [この方法については、この記事を参照してください](resource-account-ui.md)。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>要件

Office 365 で Microsoft Teams Rooms を展開する前に、要件を満たしていることを確認してください。 詳細については、「Microsoft Teams のコラボレーション [バーを展開する」を参照してください](collab-bar-deploy.md)。

- コラボレーション バーに PSTN 機能が必要な場合は、電話システム ライセンスが必要です。

- リソース アカウントに Exchange メールボックスが必要です。 これらはリソース アカウントです。Exchange ライセンスは必要ありません。 リソース アカウントの会議室ライセンスの使用をお勧めします。


### <a name="add-a-resource-account"></a>リソース アカウントを追加する

1. Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)」を参照してください。

2. Exchange Online PowerShell で、新しい会議室メールボックスを作成するか、既存の会議室メールボックスを変更します。

   - 新しい会議室メールボックスを作成するには、次の構文を使用します。

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、次の設定で新しい会議室メールボックスを作成します:

     - 名前: Huddle-Room-01

     - エイリアス: HuddleRoom01

     - アカウント: huddleroom01@contoso.onmicrosoft.com

     - アカウントパスワード: P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - 既存の会議室メールボックスを変更するには、次の構文を使用します。

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、エイリアス値 HuddleRoom02 を持つ既存のルーム メールボックスのアカウントを有効にし、パスワードを 808P@$$W 0rd に設定します。 既存のエイリアス値が HuddleRoom02@contoso.onmicrosoft.com アカウントは削除される点に注意してください。

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。


3. Exchange Online PowerShell で、会議の操作性を向上させるために、次のように会議室メールボックスの設定を構成します。

   - AutomateProcessing: AutoAccept (会議の開催者は、人手を介さずに直接会議室の予約の決定を受け取ります: 利用可 = 承諾; 利用不可 = 辞退。)

   - AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)

   - DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)

   - DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)

   - RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)

   - AdditionalResponse: "このルームには Microsoft Teams のコラボレーション バーがあります" (会議出席依頼に追加するテキスト)。

   この例では、Huddle-Room-01 という名前のルーム メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   構文とパラメーターの詳細については、「[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

4. Powershell コマンドレット `Connect-MsolService -Credential $cred` を実行して、MS Online PowerShell に接続し、Active Directory の設定を行います。   Active Directory の詳細については、「[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。 

5. 次の構文を使用して huddleroom01@contoso.onmicrosoft.com パスワードを期限切れにしない設定します。

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. リソース アカウントには、365 ライセンスの有効なOffice (できれば会議室 SKU) が必要です。 また、使用場所をデバイス アカウントに割り当てる必要もあります。これにより、アカウントで使用できるライセンス SKU が決定されます。 365 テナントで使用可能な SKU の一覧Office `Get-MsolAccountSku` 取得できます。

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Set-MsolUserLicense を使用してライセンスを割り当てできます。 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。




[PowerShell を使用して Microsoft Teams のコラボレーション バーのアカウントを構成する](resource-account-ps.md)

[Microsoft Teams のコラボレーション バーを展開する](collab-bar-deploy.md)

[Microsoft Teams ライセンスのコラボレーション バー](../rooms/rooms-licensing.md)