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
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="76b2b-103">PowerShell を使用して Microsoft 365 リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="76b2b-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="76b2b-104">PowerShell を使用して Microsoft Teams のコラボレーション バーのリソース アカウントを作成する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b2b-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="76b2b-105">リソース アカウントを作成する最も簡単な方法は、Microsoft 365 管理センターを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="76b2b-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="76b2b-106">[この方法については、この記事を参照してください](resource-account-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="76b2b-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="76b2b-107">要件</span><span class="sxs-lookup"><span data-stu-id="76b2b-107">Requirements</span></span>

<span data-ttu-id="76b2b-108">Office 365 で Microsoft Teams Rooms を展開する前に、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="76b2b-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="76b2b-109">詳細については、「Microsoft Teams のコラボレーション [バーを展開する」を参照してください](collab-bar-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="76b2b-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="76b2b-110">コラボレーション バーに PSTN 機能が必要な場合は、電話システム ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="76b2b-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="76b2b-111">リソース アカウントに Exchange メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="76b2b-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="76b2b-112">これらはリソース アカウントです。Exchange ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="76b2b-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="76b2b-113">リソース アカウントの会議室ライセンスの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76b2b-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="76b2b-114">リソース アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="76b2b-114">Add a resource account</span></span>

1. <span data-ttu-id="76b2b-115">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="76b2b-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="76b2b-116">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b2b-116">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="76b2b-117">Exchange Online PowerShell で、新しい会議室メールボックスを作成するか、既存の会議室メールボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="76b2b-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="76b2b-118">新しい会議室メールボックスを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76b2b-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="76b2b-119">この例では、次の設定で新しい会議室メールボックスを作成します:</span><span class="sxs-lookup"><span data-stu-id="76b2b-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="76b2b-120">名前: Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="76b2b-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="76b2b-121">エイリアス: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="76b2b-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="76b2b-122">アカウント: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="76b2b-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="76b2b-123">アカウントパスワード: P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="76b2b-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="76b2b-124">既存の会議室メールボックスを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76b2b-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="76b2b-125">この例では、エイリアス値 HuddleRoom02 を持つ既存のルーム メールボックスのアカウントを有効にし、パスワードを 808P@$$W 0rd に設定します。</span><span class="sxs-lookup"><span data-stu-id="76b2b-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="76b2b-126">既存のエイリアス値が HuddleRoom02@contoso.onmicrosoft.com アカウントは削除される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="76b2b-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="76b2b-127">構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b2b-127">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="76b2b-128">Exchange Online PowerShell で、会議の操作性を向上させるために、次のように会議室メールボックスの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="76b2b-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="76b2b-129">AutomateProcessing: AutoAccept (会議の開催者は、人手を介さずに直接会議室の予約の決定を受け取ります: 利用可 = 承諾; 利用不可 = 辞退。)</span><span class="sxs-lookup"><span data-stu-id="76b2b-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="76b2b-130">AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)</span><span class="sxs-lookup"><span data-stu-id="76b2b-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="76b2b-131">DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)</span><span class="sxs-lookup"><span data-stu-id="76b2b-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="76b2b-132">DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)</span><span class="sxs-lookup"><span data-stu-id="76b2b-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="76b2b-133">RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)</span><span class="sxs-lookup"><span data-stu-id="76b2b-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="76b2b-134">AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)</span><span class="sxs-lookup"><span data-stu-id="76b2b-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="76b2b-135">AdditionalResponse: "このルームには Microsoft Teams のコラボレーション バーがあります"</span><span class="sxs-lookup"><span data-stu-id="76b2b-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="76b2b-136">(会議出席依頼に追加するテキスト)。</span><span class="sxs-lookup"><span data-stu-id="76b2b-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="76b2b-137">この例では、Huddle-Room-01 という名前のルーム メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="76b2b-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="76b2b-138">構文とパラメーターの詳細については、「[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b2b-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="76b2b-139">Powershell コマンドレット `Connect-MsolService -Credential $cred` を実行して、MS Online PowerShell に接続し、Active Directory の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="76b2b-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="76b2b-140">Active Directory の詳細については、「[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b2b-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="76b2b-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="76b2b-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="76b2b-142">次の構文を使用して huddleroom01@contoso.onmicrosoft.com パスワードを期限切れにしない設定します。</span><span class="sxs-lookup"><span data-stu-id="76b2b-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="76b2b-143">リソース アカウントには、365 ライセンスの有効なOffice (できれば会議室 SKU) が必要です。</span><span class="sxs-lookup"><span data-stu-id="76b2b-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="76b2b-144">また、使用場所をデバイス アカウントに割り当てる必要もあります。これにより、アカウントで使用できるライセンス SKU が決定されます。</span><span class="sxs-lookup"><span data-stu-id="76b2b-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="76b2b-145">365 テナントで使用可能な SKU の一覧Office `Get-MsolAccountSku` 取得できます。</span><span class="sxs-lookup"><span data-stu-id="76b2b-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="76b2b-146">Set-MsolUserLicense を使用してライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="76b2b-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="76b2b-147">詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b2b-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="76b2b-148">PowerShell を使用して Microsoft Teams のコラボレーション バーのアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="76b2b-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="76b2b-149">Microsoft Teams のコラボレーション バーを展開する</span><span class="sxs-lookup"><span data-stu-id="76b2b-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="76b2b-150">Microsoft Teams ライセンスのコラボレーション バー</span><span class="sxs-lookup"><span data-stu-id="76b2b-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)