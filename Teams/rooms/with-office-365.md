---
title: Microsoft 365 または Office 365 で Microsoft Teams Rooms を展開する
ms.author: v-cichur
author: cichur
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: このトピックでは、Microsoft 365 または Office 365 を使用して Microsoft Teams Rooms を展開する方法について説明します。Teams または Skype for Business と Exchange はどちらもオンラインです。
ms.openlocfilehash: b5cfaab64840fe72dc989f00ed41760058afc765
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117335"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="2a5c8-103">Microsoft 365 または Office 365 で Microsoft Teams Rooms を展開する</span><span class="sxs-lookup"><span data-stu-id="2a5c8-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="2a5c8-104">このトピックでは、Microsoft 365 または Office 365 を使用して Microsoft Teams Rooms を展開する方法について説明します。Microsoft Teams または Skype for Business と Exchange はどちらもオンラインです。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="2a5c8-105">ユーザー アカウントをセットアップする最も簡単な方法は、リモート Windows PowerShell を使用して構成することです。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="2a5c8-106">Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいユーザー アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams Rooms のユーザー アカウントに変換する助けとなります。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="2a5c8-107">必要な場合は、次の手順に従って、Microsoft Teams Rooms のデバイスが使用するアカウントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a5c8-108">要件</span><span class="sxs-lookup"><span data-stu-id="2a5c8-108">Requirements</span></span>

<span data-ttu-id="2a5c8-109">Microsoft Teams Rooms を Microsoft 365 または Office 365 で展開する前に、要件を満たしていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="2a5c8-110">詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="2a5c8-111">Skype for Business を有効にするには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="2a5c8-112">Microsoft 365 または Office 365 プランに含まれる Skype for Business Online (プラン2、エンタープライズベースのプラン) 以上。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="2a5c8-113">プランでは、ダイヤルイン会議機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="2a5c8-114">会議にダイヤルイン機能が必要な場合は、オーディオ会議および電話システムのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="2a5c8-115">会議にダイヤルアウト機能が必要な場合は、オーディオ会議のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="2a5c8-116">テナント ユーザーには Exchange メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="2a5c8-117">Microsoft Teams Rooms のアカウントでは、少なくとも Skype for Business Online (プラン 2) のライセンスが必要ですが、Exchange Online のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="2a5c8-118">詳細については、「[Microsoft Teams Rooms ライセンス](rooms-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="2a5c8-119">Skype for Business Online プランの詳細については、「[Skype for Business Online サービスの説明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="2a5c8-120">デバイス アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="2a5c8-120">Add a device account</span></span>

1. <span data-ttu-id="2a5c8-121">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="2a5c8-122">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2a5c8-123">Exchange Online PowerShell で、新しい会議室メールボックスを作成するか、既存の会議室メールボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="2a5c8-124">既定では、会議室メールボックスには関連付けられたアカウントが含まれていないため、会議室メールボックスを作成または変更するときにアカウントを追加する必要があります。これにより、Skype ミーティング システム v2 で認証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="2a5c8-125">新しい会議室メールボックスを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="2a5c8-126">この例では、次の設定で新しい会議室メールボックスを作成します:</span><span class="sxs-lookup"><span data-stu-id="2a5c8-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="2a5c8-127">名前: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="2a5c8-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="2a5c8-128">エイリアス: Rigel1</span><span class="sxs-lookup"><span data-stu-id="2a5c8-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="2a5c8-129">アカウント: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2a5c8-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="2a5c8-130">アカウントのパスワード: P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="2a5c8-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="2a5c8-131">既存の会議室メールボックスを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="2a5c8-132">この例では、エイリアス値が Rigel2 である既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@ $ $W 0rd に設定します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="2a5c8-133">既存のエイリアス値により、アカウントが Rigel2@contoso.onmicrosoft.com であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="2a5c8-134">構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-134">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="2a5c8-135">Exchange Online PowerShell で、会議の操作性を向上させるために、次のように会議室メールボックスの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="2a5c8-136">AutomateProcessing: AutoAccept (会議の開催者は、人手を介さずに直接会議室の予約の決定を受け取ります: 利用可 = 承諾; 利用不可 = 辞退。)</span><span class="sxs-lookup"><span data-stu-id="2a5c8-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="2a5c8-137">AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)</span><span class="sxs-lookup"><span data-stu-id="2a5c8-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="2a5c8-138">DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)</span><span class="sxs-lookup"><span data-stu-id="2a5c8-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="2a5c8-139">DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)</span><span class="sxs-lookup"><span data-stu-id="2a5c8-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="2a5c8-140">RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)</span><span class="sxs-lookup"><span data-stu-id="2a5c8-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="2a5c8-141">AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)</span><span class="sxs-lookup"><span data-stu-id="2a5c8-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="2a5c8-142">AdditionalResponse: "これは Skype 会議室です。"</span><span class="sxs-lookup"><span data-stu-id="2a5c8-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="2a5c8-143">(会議出席依頼に追加するテキスト)。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="2a5c8-144">この例では、Rigel-01 という名前の会議室メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="2a5c8-145">構文とパラメーターの詳細については、「[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="2a5c8-146">POWERShell コマンドレットを実行して、MS Online PowerShell に接続して Active Directory `Connect-MsolService -Credential $cred` の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="2a5c8-147">Active Directory の詳細については、「[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="2a5c8-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="2a5c8-149">パスワードの有効期限が切れないようにするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="2a5c8-150">この例では、アカウント Rigel1@contoso.onmicrosoft.com のパスワードを無期限に設定します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="2a5c8-151">次のコマンドを実行して、アカウントの電話番号を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> <span data-ttu-id="2a5c8-152">パスワードが [有効期限なし] に設定されていない場合、アカウントの有効期限が切れると、アカウントはデバイスにサインインしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="2a5c8-153">その後、アカウントのパスワードを変更する必要があります。また、ローカルの場合は、このパスワードも、ローカルの(または)、ローカルの(または)、(または)、()、パスワードを変更する必要があります。また</span><span class="sxs-lookup"><span data-stu-id="2a5c8-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="2a5c8-154">デバイス アカウントには、有効な Microsoft 365 または Office 365 ライセンスが必要です。ライセンスがない場合は Exchange と Microsoft Teams または Skype for Business が動作しません。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="2a5c8-155">ライセンスを所有している場合は、使用場所をデバイス アカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="2a5c8-156">`Get-MsolAccountSku` を使用して、</span><span class="sxs-lookup"><span data-stu-id="2a5c8-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="2a5c8-157">次のように、Microsoft 365 または Office 365 組織で使用できる SKU の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="2a5c8-158">次に、`Set-MsolUserLicense` コマンドレットを使用してライセンスを追加 </span><span class="sxs-lookup"><span data-stu-id="2a5c8-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="2a5c8-159">することができます。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-159">cmdlet.</span></span> <span data-ttu-id="2a5c8-160">この例では、会議室のライセンスをアカウントに追加します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="2a5c8-161">詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="2a5c8-162">このアカウントには電話システムの機能を追加することもできますが、最初に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="2a5c8-163">詳細 [については、「電話システムとは?」](../what-is-phone-system-in-office-365.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="2a5c8-164">この例では、PSTN 国内通話プランと国際通話プランを追加します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="2a5c8-165">次に、Skype for Business でデバイス アカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-165">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="2a5c8-166">お使いの環境が「[Microsoft Teams Rooms の要件](requirements.md)」で定義されている要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-166">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="2a5c8-167">次のようにしてリモート [Windows PowerShell セッション](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を開始します (必ず[Skype for Business Online の PowerShell コンポーネントのインストール](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)を行ってください)。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-167">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="2a5c8-168">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-168">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="2a5c8-169">最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-169">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   <span data-ttu-id="2a5c8-170">次の例のように、セットアップ中の新しいユーザー アカウントの RegistrarPool 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-170">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="2a5c8-171">Skype for Business Server に対して Microsoft Teams Rooms のアカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-171">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="2a5c8-172">テナントの既存のユーザー アカウントと同じレジストラー プールには、新しいユーザー アカウントを作成できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-172">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="2a5c8-173">上記のコマンドを実行すると、このような状況でもアカウント設定のエラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-173">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="2a5c8-174">検証</span><span class="sxs-lookup"><span data-stu-id="2a5c8-174">Validate</span></span>

<span data-ttu-id="2a5c8-175">検証を行う場合は、通常、どの Skype for Business クライアントを使用しても作成したアカウントにログインできます。</span><span class="sxs-lookup"><span data-stu-id="2a5c8-175">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a5c8-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a5c8-176">See also</span></span>

[<span data-ttu-id="2a5c8-177">Microsoft Teams Rooms のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="2a5c8-177">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="2a5c8-178">Microsoft Teams Rooms を計画する</span><span class="sxs-lookup"><span data-stu-id="2a5c8-178">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="2a5c8-179">Microsoft Teams Rooms をデプロイする</span><span class="sxs-lookup"><span data-stu-id="2a5c8-179">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="2a5c8-180">Microsoft Teams Rooms コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="2a5c8-180">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="2a5c8-181">Microsoft Teams Rooms の管理</span><span class="sxs-lookup"><span data-stu-id="2a5c8-181">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="2a5c8-182">Microsoft Teams Rooms ライセンス</span><span class="sxs-lookup"><span data-stu-id="2a5c8-182">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)