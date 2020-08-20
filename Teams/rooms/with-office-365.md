---
title: Microsoft 365 または Office 365 で Microsoft Teams Rooms を展開する
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: このトピックでは、Microsoft 365 または Office 365 を使用して Microsoft Teams Rooms を展開する方法について説明します。Teams または Skype for Business と Exchange はどちらもオンラインです。
ms.openlocfilehash: 440bf2f624bfd150f7e00f145770b0fda336deb4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756798"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="685f7-103">Microsoft 365 または Office 365 で Microsoft Teams Rooms を展開する</span><span class="sxs-lookup"><span data-stu-id="685f7-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="685f7-104">このトピックでは、Microsoft 365 または Office 365 を使用して Microsoft Teams Rooms を展開する方法について説明します。Microsoft Teams または Skype for Business と Exchange はどちらもオンラインです。</span><span class="sxs-lookup"><span data-stu-id="685f7-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="685f7-105">ユーザー アカウントをセットアップする最も簡単な方法は、リモート Windows PowerShell を使用して構成することです。</span><span class="sxs-lookup"><span data-stu-id="685f7-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="685f7-106">Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいユーザー アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams Rooms のユーザー アカウントに変換する助けとなります。</span><span class="sxs-lookup"><span data-stu-id="685f7-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="685f7-107">必要な場合は、次の手順に従って、Microsoft Teams Rooms のデバイスが使用するアカウントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="685f7-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="685f7-108">要件</span><span class="sxs-lookup"><span data-stu-id="685f7-108">Requirements</span></span>

<span data-ttu-id="685f7-109">Microsoft Teams Rooms を Microsoft 365 または Office 365 で展開する前に、要件を満たしていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="685f7-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="685f7-110">詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="685f7-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="685f7-111">Skype for Business を有効にするには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="685f7-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="685f7-112">Microsoft 365 または Office 365 プランに含まれる Skype for Business Online (プラン2、エンタープライズベースのプラン) 以上。</span><span class="sxs-lookup"><span data-stu-id="685f7-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="685f7-113">プランでは、ダイヤルイン会議機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="685f7-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="685f7-114">会議にダイヤルイン機能が必要な場合は、オーディオ会議および電話システムのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="685f7-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="685f7-115">会議にダイヤルアウト機能が必要な場合は、オーディオ会議のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="685f7-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="685f7-116">テナント ユーザーには Exchange メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="685f7-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="685f7-117">Microsoft Teams Rooms のアカウントでは、少なくとも Skype for Business Online (プラン 2) のライセンスが必要ですが、Exchange Online のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="685f7-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="685f7-118">詳細については、「[Microsoft Teams Rooms ライセンス](rooms-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="685f7-119">Skype for Business Online プランの詳細については、「[Skype for Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="685f7-120">デバイス アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="685f7-120">Add a device account</span></span>

1. <span data-ttu-id="685f7-121">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="685f7-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="685f7-122">手順については、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="685f7-123">Exchange Online PowerShell で、新しい会議室メールボックスを作成するか、既存の会議室メールボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="685f7-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="685f7-124">既定では、会議室メールボックスには関連付けられたアカウントが含まれていないため、会議室メールボックスを作成または変更するときにアカウントを追加する必要があります。これにより、Skype ミーティング システム v2 で認証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="685f7-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="685f7-125">新しい会議室メールボックスを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="685f7-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="685f7-126">この例では、次の設定で新しい会議室メールボックスを作成します:</span><span class="sxs-lookup"><span data-stu-id="685f7-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="685f7-127">名前: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="685f7-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="685f7-128">エイリアス: Rigel1</span><span class="sxs-lookup"><span data-stu-id="685f7-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="685f7-129">アカウント: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="685f7-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="685f7-130">アカウントのパスワード: P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="685f7-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="685f7-131">既存の会議室メールボックスを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="685f7-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="685f7-132">この例では、エイリアス値が Rigel2 である既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@ $ $W 0rd に設定します。</span><span class="sxs-lookup"><span data-stu-id="685f7-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="685f7-133">既存のエイリアス値により、アカウントが Rigel2@contoso.onmicrosoft.com であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="685f7-134">構文とパラメーターの詳細については、「[New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="685f7-135">Exchange Online PowerShell で、会議の操作性を向上させるために、次のように会議室メールボックスの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="685f7-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="685f7-136">AutomateProcessing: AutoAccept (会議の開催者は、人手を介さずに直接会議室の予約の決定を受け取ります: 利用可 = 承諾; 利用不可 = 辞退。)</span><span class="sxs-lookup"><span data-stu-id="685f7-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="685f7-137">AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)</span><span class="sxs-lookup"><span data-stu-id="685f7-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="685f7-138">DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)</span><span class="sxs-lookup"><span data-stu-id="685f7-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="685f7-139">DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)</span><span class="sxs-lookup"><span data-stu-id="685f7-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="685f7-140">RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)</span><span class="sxs-lookup"><span data-stu-id="685f7-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="685f7-141">AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)</span><span class="sxs-lookup"><span data-stu-id="685f7-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="685f7-142">AdditionalResponse: "これは Skype 会議室です。"</span><span class="sxs-lookup"><span data-stu-id="685f7-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="685f7-143">(会議出席依頼に追加するテキスト)。</span><span class="sxs-lookup"><span data-stu-id="685f7-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="685f7-144">この例では、Rigel-01 という名前の会議室メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="685f7-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="685f7-145">構文とパラメーターの詳細については、「[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="685f7-146">Powershell コマンドレット `Connect-MsolService -Credential $cred` を実行して、MS Online PowerShell に接続し、Active Directory の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="685f7-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="685f7-147">Active Directory の詳細については、「[Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="685f7-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="685f7-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="685f7-149">パスワードの有効期限が切れないようにするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="685f7-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```
   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="685f7-150">この例では、アカウント Rigel1@contoso.onmicrosoft.com のパスワードを無期限に設定します。</span><span class="sxs-lookup"><span data-stu-id="685f7-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="685f7-151">次のコマンドを実行して、アカウントの電話番号を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="685f7-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="685f7-152">デバイス アカウントには、有効な Microsoft 365 または Office 365 ライセンスが必要です。ライセンスがない場合は Exchange と Microsoft Teams または Skype for Business が動作しません。</span><span class="sxs-lookup"><span data-stu-id="685f7-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="685f7-153">ライセンスを所有している場合は、使用場所をデバイス アカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。</span><span class="sxs-lookup"><span data-stu-id="685f7-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="685f7-154">`Get-MsolAccountSku` を使用して、</span><span class="sxs-lookup"><span data-stu-id="685f7-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="685f7-155">次のように、Microsoft 365 または Office 365 組織で使用できる SKU の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="685f7-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```
   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="685f7-156">次に、`Set-MsolUserLicense` コマンドレットを使用してライセンスを追加 </span><span class="sxs-lookup"><span data-stu-id="685f7-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="685f7-157">することができます。</span><span class="sxs-lookup"><span data-stu-id="685f7-157">cmdlet.</span></span> <span data-ttu-id="685f7-158">この例では、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="685f7-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ``` 
   <!-- 
   ```Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="685f7-159">詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="685f7-160">次に、Skype for Business でデバイス アカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="685f7-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="685f7-161">お使いの環境が「[Microsoft Teams Rooms の要件](requirements.md)」で定義されている要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="685f7-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="685f7-162">次のようにしてリモート [Windows PowerShell セッション](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を開始します (必ず[Skype for Business Online の PowerShell コンポーネントのインストール](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)を行ってください)。</span><span class="sxs-lookup"><span data-stu-id="685f7-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="685f7-163">Skype for Business Server に対して Microsoft Teams Rooms のアカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="685f7-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   $rm="Rigel1@contoso.onmicrosoft.com"
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="685f7-164">次の例のように、セットアップ中の新しいユーザー アカウントの RegistrarPool 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="685f7-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    $rm="Rigel1@contoso.onmicrosoft.com"
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="685f7-165">テナントの既存のユーザー アカウントと同じレジストラー プールには、新しいユーザー アカウントを作成できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="685f7-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="685f7-166">上記のコマンドを実行すると、このような状況でもアカウント設定のエラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="685f7-166">The command above will prevent errors in account setup due to this situation.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="685f7-167">アカウントにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="685f7-167">Assign a license to your account</span></span>

1. <span data-ttu-id="685f7-168">テナント管理者としてログインし、Microsoft 365 管理センターを開き、Admin アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="685f7-168">Login as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>

2. <span data-ttu-id="685f7-169">[**ユーザーとグループ**] をクリックし、[**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685f7-169">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="685f7-170">Microsoft Teams Rooms アカウントを選択してから、編集を意味するペン アイコンをクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="685f7-170">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="685f7-171">[**ライセンス**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="685f7-171">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="685f7-172">[**ライセンスの割り当て**] セクションで、使用するライセンスと、エンタープライズ VoIP の必要性に関する決定に応じて、Skype for Business Online (プラン 2) または Skype for Business Online (プラン 3) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="685f7-172">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="685f7-173">Microsoft Teams Rooms でクラウド PBX を使用する場合は、プラン 3 ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="685f7-173">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="685f7-174">最低でも、音声接続用に CloudPBX が必要です。</span><span class="sxs-lookup"><span data-stu-id="685f7-174">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="685f7-175">次に、PSTN の接続方法に基づきハイブリッド音声または PSTN 通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="685f7-175">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="685f7-176">詳細については、「[Microsoft Teams Rooms ライセンス](rooms-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685f7-176">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for more details.</span></span>

6. <span data-ttu-id="685f7-177">[**保存**] をクリックしてタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="685f7-177">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="685f7-178">サンプル: Exchange Online および Skype for Business Online における ミーティング アカウントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="685f7-178">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="685f7-179">Exchange Online PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="685f7-179">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="685f7-180">Azure Active Directory PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="685f7-180">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="685f7-181">Skype for Business PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="685f7-181">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="685f7-182">これで CloudPBX と PSTNCallingDomesticAndInternational が追加されます。</span><span class="sxs-lookup"><span data-stu-id="685f7-182">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="685f7-183">さらに、管理者インターフェイスを使用して、電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="685f7-183">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="685f7-184">検証</span><span class="sxs-lookup"><span data-stu-id="685f7-184">Validate</span></span>

<span data-ttu-id="685f7-185">検証を行う場合は、通常、どの Skype for Business クライアントを使用しても作成したアカウントにログインできます。</span><span class="sxs-lookup"><span data-stu-id="685f7-185">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="685f7-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="685f7-186">See also</span></span>

[<span data-ttu-id="685f7-187">Microsoft Teams Rooms のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="685f7-187">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="685f7-188">Microsoft Teams Rooms を計画する</span><span class="sxs-lookup"><span data-stu-id="685f7-188">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="685f7-189">Microsoft Teams Rooms をデプロイする</span><span class="sxs-lookup"><span data-stu-id="685f7-189">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="685f7-190">Microsoft Teams Rooms コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="685f7-190">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="685f7-191">Microsoft Teams Rooms の管理</span><span class="sxs-lookup"><span data-stu-id="685f7-191">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="685f7-192">Microsoft Teams Rooms ライセンス</span><span class="sxs-lookup"><span data-stu-id="685f7-192">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
