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
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="128b0-103">PowerShell を使用して Microsoft 365 リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="128b0-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="128b0-104">このトピックでは、PowerShell を使用して Microsoft Teams のコラボレーションバーのリソースアカウントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="128b0-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="128b0-105">リソースアカウントを作成するには、Microsoft 365 管理センターを使用するのが最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="128b0-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="128b0-106">[この方法については、この記事を参照して](resource-account-ui.md)ください。</span><span class="sxs-lookup"><span data-stu-id="128b0-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="128b0-107">要件</span><span class="sxs-lookup"><span data-stu-id="128b0-107">Requirements</span></span>

<span data-ttu-id="128b0-108">Microsoft Teams のルームを Office 365 に展開する前に、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="128b0-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="128b0-109">詳しくは、「 [Microsoft Teams のコラボレーションバーの展開](collab-bar-deploy.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="128b0-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="128b0-110">コラボレーションバーに PSTN 機能が必要な場合は、電話システムのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="128b0-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="128b0-111">リソースアカウントには Exchange メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="128b0-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="128b0-112">これらはリソースアカウントであるため、Exchange のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="128b0-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="128b0-113">リソースアカウントの会議室ライセンスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="128b0-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="128b0-114">リソースアカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="128b0-114">Add a resource account</span></span>

1. <span data-ttu-id="128b0-115">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="128b0-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="128b0-116">手順については、「 [Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="128b0-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="128b0-117">Exchange Online PowerShell で、新しい会議室のメールボックスを作成するか、既存の会議のメールボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="128b0-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="128b0-118">新しい会議室のメールボックスを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="128b0-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="128b0-119">この例では、次の設定で新しい会議室のメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="128b0-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="128b0-120">名前: Huddle-01</span><span class="sxs-lookup"><span data-stu-id="128b0-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="128b0-121">エイリアス: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="128b0-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="128b0-122">アカウント: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="128b0-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="128b0-123">アカウントパスワード: P@ $ $W 0rd242</span><span class="sxs-lookup"><span data-stu-id="128b0-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="128b0-124">既存の会議のメールボックスを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="128b0-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="128b0-125">次の例では、エイリアス値 HuddleRoom02 を持つ既存のルームメールボックスのアカウントを有効にし、パスワードを 808P@ $ $W 0rd に設定します。</span><span class="sxs-lookup"><span data-stu-id="128b0-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="128b0-126">既存のエイリアス値が原因で、アカウントが HuddleRoom02@contoso.onmicrosoft.com されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="128b0-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="128b0-127">構文とパラメーターの詳細については、「[新しいメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)と[設定-](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)メールボックス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="128b0-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="128b0-128">Exchange Online PowerShell で、会議の操作性を向上させるために、会議室メールボックスで次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="128b0-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="128b0-129">自動的な処理: 自動承諾 (会議の開催者は、手動での介入なく、会議の開催者が会議室の予約を直接受け取ります: 無料 = accept; busy = 拒否。)</span><span class="sxs-lookup"><span data-stu-id="128b0-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="128b0-130">Addオーガナイザー Ertosubject: $false (会議の開催者は、会議出席依頼の件名に追加されません)。</span><span class="sxs-lookup"><span data-stu-id="128b0-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="128b0-131">DeleteComments: $false (入力した会議出席依頼のメッセージ本文に含まれるテキストを保持)</span><span class="sxs-lookup"><span data-stu-id="128b0-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="128b0-132">DeleteSubject: $false (入力した会議出席依頼の件名を保持)</span><span class="sxs-lookup"><span data-stu-id="128b0-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="128b0-133">RemovePrivateProperty: $false (元の会議出席依頼の開催者によって送信されたプライベートフラグが指定されたままになります)。</span><span class="sxs-lookup"><span data-stu-id="128b0-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="128b0-134">AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます)</span><span class="sxs-lookup"><span data-stu-id="128b0-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="128b0-135">AdditionalResponse: "このルームには Microsoft Teams のコラボレーションバーがあります。"</span><span class="sxs-lookup"><span data-stu-id="128b0-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="128b0-136">(会議出席依頼に追加する追加のテキスト)</span><span class="sxs-lookup"><span data-stu-id="128b0-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="128b0-137">この例では、Huddle-01 という名前の会議室メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="128b0-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="128b0-138">構文とパラメーターの詳細については、「 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="128b0-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="128b0-139">MS Online PowerShell に接続して、powershell コマンドレットを実行して Active Directory の設定を行い `Connect-MsolService -Credential $cred` ます。</span><span class="sxs-lookup"><span data-stu-id="128b0-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="128b0-140">Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="128b0-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="128b0-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="128b0-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="128b0-142">次の構文を使用して、huddleroom01@contoso.onmicrosoft.com のパスワードを無期限に設定します。</span><span class="sxs-lookup"><span data-stu-id="128b0-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="128b0-143">リソースアカウントには、有効な Office 365 ライセンスが必要です。必要に応じて会議室の SKU を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="128b0-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="128b0-144">また、デバイスアカウントに使用場所を割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。</span><span class="sxs-lookup"><span data-stu-id="128b0-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="128b0-145">`Get-MsolAccountSku`Office 365 テナントで利用可能な sku のリストを取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="128b0-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="128b0-146">Set-msoluserlicense を使用してライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="128b0-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="128b0-147">詳細な手順については、「 [Office 365 PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="128b0-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="128b0-148">PowerShell を使用して Microsoft Teams のコラボレーションバー用にアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="128b0-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="128b0-149">Microsoft Teams のコラボレーションバーの展開</span><span class="sxs-lookup"><span data-stu-id="128b0-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="128b0-150">Microsoft Teams のライセンスのコラボレーションバー</span><span class="sxs-lookup"><span data-stu-id="128b0-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


