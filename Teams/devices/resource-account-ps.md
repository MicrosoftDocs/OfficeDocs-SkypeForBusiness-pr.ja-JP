---
title: PowerShell を使用して Microsoft Teams のコラボレーションバー用の Microsoft Teams リソースアカウントを作成する
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
description: Microsoft Teams のコラボレーションバーを展開する方法については、このトピックを参照してください。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268051"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>PowerShell を使用して Microsoft 365 リソースアカウントを作成する

このトピックでは、PowerShell を使用して Microsoft Teams のコラボレーションバーのリソースアカウントを作成する方法について説明します。

リソースアカウントを作成するには、Microsoft 365 管理センターを使用するのが最も簡単な方法です。 [この方法については、この記事を参照して](resource-account-ui.md)ください。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>要件

Microsoft Teams のルームを Office 365 に展開する前に、要件を満たしていることを確認してください。 詳しくは、「 [Microsoft Teams のコラボレーションバーの展開](collab-bar-deploy.md)」をご覧ください。

- コラボレーションバーに PSTN 機能が必要な場合は、電話システムのライセンスが必要です。

- リソースアカウントには Exchange メールボックスが必要です。 これらはリソースアカウントであるため、Exchange のライセンスは必要ありません。 リソースアカウントの会議室ライセンスを使用することをお勧めします。


### <a name="add-a-resource-account"></a>リソースアカウントを追加する

1. Exchange Online PowerShell に接続します。 手順については、「 [Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)」を参照してください。

2. Exchange Online PowerShell で、新しい会議室のメールボックスを作成するか、既存の会議のメールボックスを変更します。

   - 新しい会議室のメールボックスを作成するには、次の構文を使用します。

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、次の設定で新しい会議室のメールボックスを作成します。

     - 名前: Huddle-01

     - エイリアス: HuddleRoom01

     - アカウント: huddleroom01@contoso.onmicrosoft.com

     - アカウントパスワード: P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - 既存の会議のメールボックスを変更するには、次の構文を使用します。

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     次の例では、エイリアス値 HuddleRoom02 を持つ既存のルームメールボックスのアカウントを有効にし、パスワードを 808P@ $ $W 0rd に設定します。 既存のエイリアス値が原因で、アカウントが HuddleRoom02@contoso.onmicrosoft.com されることに注意してください。

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   構文とパラメーターの詳細については、「[新しいメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)と[設定-](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)メールボックス」を参照してください。


3. Exchange Online PowerShell で、会議の操作性を向上させるために、会議室メールボックスで次の設定を構成します。

   - 自動的な処理: 自動承諾 (会議の開催者は、手動での介入なく、会議の開催者が会議室の予約を直接受け取ります: 無料 = accept; busy = 拒否。)

   - Addオーガナイザー Ertosubject: $false (会議の開催者は、会議出席依頼の件名に追加されません)。

   - DeleteComments: $false (入力した会議出席依頼のメッセージ本文に含まれるテキストを保持)

   - DeleteSubject: $false (入力した会議出席依頼の件名を保持)

   - RemovePrivateProperty: $false (元の会議出席依頼の開催者によって送信されたプライベートフラグが指定されたままになります)。

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます)

   - AdditionalResponse: "このルームには Microsoft Teams のコラボレーションバーがあります。" (会議出席依頼に追加する追加のテキスト)

   この例では、Huddle-01 という名前の会議室メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   構文とパラメーターの詳細については、「 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

4. MS Online PowerShell に接続して、powershell コマンドレットを実行して Active Directory の設定を行い `Connect-MsolService -Credential $cred` ます。   Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。 

5. 次の構文を使用して、huddleroom01@contoso.onmicrosoft.com のパスワードを無期限に設定します。

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. リソースアカウントには、有効な Office 365 ライセンスが必要です。必要に応じて会議室の SKU を指定する必要があります。 また、デバイスアカウントに使用場所を割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。 `Get-MsolAccountSku`Office 365 テナントで利用可能な sku のリストを取得するために使用できます。

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Set-msoluserlicense を使用してライセンスを割り当てることができます。 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   詳細な手順については、「 [Office 365 PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。




[PowerShell を使用して Microsoft Teams のコラボレーションバー用にアカウントを構成する](resource-account-ps.md)

[Microsoft Teams のコラボレーションバーの展開](collab-bar-deploy.md)

[Microsoft Teams のライセンスのコラボレーションバー](../rooms/rooms-licensing.md)


