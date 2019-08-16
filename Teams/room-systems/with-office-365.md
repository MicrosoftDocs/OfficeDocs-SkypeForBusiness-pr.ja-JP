---
title: Office 365 での Microsoft Teams ミーティングを展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: このトピックでは、Office 365 で Microsoft Teams のルームを展開する方法について説明します。
ms.openlocfilehash: 1d0bd8270671ba1a666d07fd2e7826704c309f01
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427739"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="b20f2-103">Office 365 での Microsoft Teams ミーティングを展開する</span><span class="sxs-lookup"><span data-stu-id="b20f2-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="b20f2-104">このトピックでは、microsoft teams または Skype for Business および Exchange が両方ともオンラインの Office 365 で Microsoft Teams ルームを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="b20f2-105">ユーザーアカウントをセットアップする最も簡単な方法は、リモートの Windows PowerShell を使用してアカウントを構成することです。</span><span class="sxs-lookup"><span data-stu-id="b20f2-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="b20f2-106">Microsoft には、新しいユーザーアカウントを作成するのに役立つスクリプト、または既存のリソースアカウントを、互換性のある Microsoft Teams 室のユーザーアカウントに変換するために使用している既存のリソースアカウントを検証するための SkypeRoomProvisioningScript が用意されてい[ます](https://go.microsoft.com/fwlink/?linkid=870105)。</span><span class="sxs-lookup"><span data-stu-id="b20f2-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="b20f2-107">必要に応じて、次の手順に従って、Microsoft Teams の会議室のデバイスで使用するアカウントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b20f2-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="b20f2-108">要件</span><span class="sxs-lookup"><span data-stu-id="b20f2-108">Requirements</span></span>

<span data-ttu-id="b20f2-109">Microsoft Teams のルームを Office 365 に展開する前に、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="b20f2-110">詳細については、「 [Microsoft Teams の会議室の要件](requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="b20f2-111">Skype for Business を有効にするには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="b20f2-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="b20f2-112">Office 365 プランで Skype for Business Online (プラン2、またはエンタープライズベースのプラン) 以上。</span><span class="sxs-lookup"><span data-stu-id="b20f2-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="b20f2-113">このプランでは、ダイヤルイン会議機能を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="b20f2-114">会議からダイヤルイン機能が必要な場合は、電話会議と電話システムのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b20f2-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="b20f2-115">会議からダイヤルアウト機能が必要な場合は、国内または国内の通話プランが必要です。</span><span class="sxs-lookup"><span data-stu-id="b20f2-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="b20f2-116">テナントユーザーは Exchange メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="b20f2-117">Microsoft Teams のルームアカウントには、少なくとも Skype for Business Online (プラン 2) ライセンスが必要ですが、Exchange Online のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b20f2-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="b20f2-118">詳細については、「 [Microsoft Teams ルームライセンス](skype-room-systems-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="b20f2-119">Skype for Business Online プランの詳細については、「 [skype For Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="b20f2-120">デバイス アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="b20f2-120">Add a device account</span></span>

1. <span data-ttu-id="b20f2-121">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="b20f2-122">手順については、「 [Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="b20f2-123">Exchange Online PowerShell で、新しい会議室のメールボックスを作成するか、既存の会議のメールボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="b20f2-124">既定では、会議室メールボックスにはアカウントが関連付けられていないため、Skype Room Systems v2 での認証を許可する会議室メールボックスを作成または変更する場合は、アカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="b20f2-125">新しい会議室のメールボックスを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="b20f2-126">この例では、次の設定で新しい会議室のメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="b20f2-127">Name: Project-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="b20f2-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="b20f2-128">エイリアス: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="b20f2-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="b20f2-129">アカウント: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b20f2-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="b20f2-130">アカウントパスワード: P @ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="b20f2-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="b20f2-131">既存の会議のメールボックスを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="b20f2-132">この例では、エイリアス値 ProjectRigel02 を持つ既存のルームメールボックスのアカウントを有効にし、0rd に対してパスワードを 9898P @ $ $W に設定します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="b20f2-133">既存のエイリアス値が原因で、アカウントが ProjectRigel02@contoso.onmicrosoft.com されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="b20f2-134">構文とパラメーターの詳細については、「[新しいメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)と[設定-](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)メールボックス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="b20f2-135">Exchange Online PowerShell で、会議の操作性を向上させるために、会議室メールボックスで次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="b20f2-136">自動的な処理: 自動承諾 (会議の開催者は、手動での介入なく、会議の開催者が会議室の予約を直接受け取ります: 無料 = accept; busy = 拒否。)</span><span class="sxs-lookup"><span data-stu-id="b20f2-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="b20f2-137">Addオーガナイザー Ertosubject: $false (会議の開催者は、会議出席依頼の件名に追加されません)。</span><span class="sxs-lookup"><span data-stu-id="b20f2-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="b20f2-138">DeleteComments: $false (入力した会議出席依頼のメッセージ本文に含まれるテキストを保持)</span><span class="sxs-lookup"><span data-stu-id="b20f2-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="b20f2-139">DeleteSubject: $false (入力した会議出席依頼の件名を保持)</span><span class="sxs-lookup"><span data-stu-id="b20f2-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="b20f2-140">RemovePrivateProperty: $false (元の会議出席依頼の開催者によって送信されたプライベートフラグが指定されたままになります)。</span><span class="sxs-lookup"><span data-stu-id="b20f2-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="b20f2-141">AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます)</span><span class="sxs-lookup"><span data-stu-id="b20f2-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="b20f2-142">AdditionalResponse: "これは Skype 会議室です。"</span><span class="sxs-lookup"><span data-stu-id="b20f2-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="b20f2-143">(会議出席依頼に追加する追加のテキスト)</span><span class="sxs-lookup"><span data-stu-id="b20f2-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="b20f2-144">この例では、Rigel-01 という名前の会議室メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="b20f2-145">構文とパラメーターの詳細については、「 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="b20f2-146">MS Online PowerShell に接続して、 `Connect-MsolService -Credential $cred` powershell コマンドレットを実行して Active Directory の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="b20f2-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="b20f2-147">Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="b20f2-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b20f2-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="b20f2-149">パスワードを無期限にする場合は、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-149">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="b20f2-150">次の例では、アカウント ProjectRigel01@contoso.onmicrosoft.com のパスワードを無期限に設定します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-150">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="b20f2-151">次のコマンドを実行して、アカウントの電話番号を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b20f2-151">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="b20f2-152">デバイスアカウントには、有効な Office 365 ライセンスが必要です。または、Exchange と Microsoft Teams、または Skype for Business が動作しません。</span><span class="sxs-lookup"><span data-stu-id="b20f2-152">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="b20f2-153">ライセンスを所有している場合は、使用場所をデバイスアカウントに割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。</span><span class="sxs-lookup"><span data-stu-id="b20f2-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="b20f2-154">使用できる方法`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="b20f2-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="b20f2-155">Office 365 テナントで利用可能な Sku の一覧を取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-155">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="b20f2-156">次に、次の方法を使用してライセンスを追加することができます。`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="b20f2-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="b20f2-157">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="b20f2-157">cmdlet.</span></span> <span data-ttu-id="b20f2-158">この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="b20f2-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="b20f2-159">詳細な手順については、「 [Office 365 PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="b20f2-160">次に、Skype for Business でデバイスアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="b20f2-161">環境が、 [Microsoft Teams の会議室の要件](requirements.md)で定義されている要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="b20f2-162">次の手順でリモート[Windows PowerShell セッション](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を開始します ( [Skype For business Online PowerShell コンポーネントをインストール](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)してください)。</span><span class="sxs-lookup"><span data-stu-id="b20f2-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="b20f2-163">次のコマンドレットを実行して、Skype for Business Server 用の Microsoft Teams ルームアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b20f2-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="b20f2-164">次の例に示すように、セットアップ中の新しいユーザーアカウントから RegistrarPool 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="b20f2-165">新しいユーザーアカウントが、テナント内の既存のユーザーアカウントと同じレジストラープールに作成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="b20f2-166">上のコマンドを実行すると、アカウント設定のエラーがこの状況で発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="b20f2-166">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="b20f2-167">Microsoft teams または Skype for Business Online で Microsoft Teams のルームアカウントを有効にするための上記の手順を完了したら、Microsoft teams の会議デバイスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-167">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="b20f2-168">Office 365 管理ポータルを使用して、デバイスに Skype for Business Online (プラン 2) または Skype for Business Online (Plan 3) ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b20f2-168">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="b20f2-169">ライセンスをアカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="b20f2-169">Assign a license to your account</span></span>

1. <span data-ttu-id="b20f2-170">テナント管理者としてログインし、Office 365 管理ポータルを開いて、[管理者] アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b20f2-170">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="b20f2-171">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b20f2-171">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="b20f2-172">Microsoft Teams のルームアカウントを選択し、ペンアイコンをクリックまたはタップします。これは編集を意味します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-172">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="b20f2-173">[**ライセンス**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b20f2-173">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="b20f2-174">[**ライセンスの割り当て**] セクションで、ライセンスに応じて Skype For business Online (プラン 2) または Skype For business Online (プラン 3) を選択する必要があります。これは、使用しているライセンスと、エンタープライズボイスの必要条件によって決定された内容によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-174">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="b20f2-175">Microsoft Teams のルームでクラウド PBX を使用する場合は、プラン3ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-175">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="b20f2-176">最低でも、音声接続用に CloudPBX が必要です。</span><span class="sxs-lookup"><span data-stu-id="b20f2-176">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="b20f2-177">次に、PSTN の接続方法に基づきハイブリッド音声または PSTN 通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="b20f2-177">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="b20f2-178">詳細については、「 [Microsoft Teams ルームライセンス](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f2-178">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="b20f2-179">タスクを完了するには、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b20f2-179">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="b20f2-180">サンプル: Exchange Online と Skype for Business Online での会議室アカウントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b20f2-180">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="b20f2-181">Exchange Online PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="b20f2-181">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="b20f2-182">Azure Active Directory PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="b20f2-182">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="b20f2-183">Skype for Business PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="b20f2-183">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="b20f2-184">この操作によって、CloudPBX および PSTNCallingDomesticAndInternational が追加されます。</span><span class="sxs-lookup"><span data-stu-id="b20f2-184">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="b20f2-185">さらに、管理インタフェースを使用して電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-185">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="b20f2-186">有効性</span><span class="sxs-lookup"><span data-stu-id="b20f2-186">Validate</span></span>

<span data-ttu-id="b20f2-187">検証のために、Skype for Business クライアントを使って、作成したアカウントにサインインできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f2-187">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="b20f2-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="b20f2-188">See also</span></span>

[<span data-ttu-id="b20f2-189">Microsoft Teams 室のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="b20f2-189">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="b20f2-190">Microsoft Teams のルームを計画する</span><span class="sxs-lookup"><span data-stu-id="b20f2-190">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="b20f2-191">Microsoft Teams ルームの展開</span><span class="sxs-lookup"><span data-stu-id="b20f2-191">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="b20f2-192">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="b20f2-192">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="b20f2-193">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="b20f2-193">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="b20f2-194">Microsoft Teams 会議室のライセンス</span><span class="sxs-lookup"><span data-stu-id="b20f2-194">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
