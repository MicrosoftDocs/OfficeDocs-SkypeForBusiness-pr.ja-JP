---
title: Skype Room Systems バージョン 2 と Office 365 を展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Office 365 で Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 05288842a54fd8be7487181582fcc7bd4780fd2e
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800125"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="19a43-103">Skype Room Systems バージョン 2 と Office 365 を展開する </span><span class="sxs-lookup"><span data-stu-id="19a43-103">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="19a43-104">Skype ビジネスと Exchange の両方がオンラインで、Office 365 で Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="19a43-105">ユーザー アカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。</span><span class="sxs-lookup"><span data-stu-id="19a43-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="19a43-106">マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または Skype ルーム システム v2 の互換性のあるユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="19a43-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="19a43-107">場合は、Skype ルーム システム v2 デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="19a43-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="19a43-108">要件</span><span class="sxs-lookup"><span data-stu-id="19a43-108">Requirements</span></span>

<span data-ttu-id="19a43-109">Office 365 で Skype ルーム システム v2 を展開する前に、要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19a43-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="19a43-110">詳細については、「[Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

<span data-ttu-id="19a43-111">ビジネス用の Skype を有効にするには、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="19a43-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="19a43-112">(プラン 2 の場合、または企業レベルの計画)、オンライン ビジネスの Skype 以降、Office 365 のプランで。</span><span class="sxs-lookup"><span data-stu-id="19a43-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="19a43-113">計画では、ダイヤルイン会議機能を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="19a43-114">会議にダイヤルイン機能が必要な場合は、音声会議や電話システムのライセンスを必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="19a43-115">会議からのダイヤル ・ アウト機能が必要な場合、国内または国内および海外を呼び出すことを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="19a43-116">テナント ユーザーは、Exchange のメールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="19a43-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="19a43-117">Skype ルーム システム v2 アカウントにする必要が最低限、Skype ビジネス オンライン (プラン 2) のライセンスが、Exchange Online のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="19a43-117">Your Skype Room Systems v2 account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="19a43-118">詳細については、 [Skype ルーム システム v2 のライセンス](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-118">See [Skype Room Systems v2 Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="19a43-119">Skype のビジネスのオンラインの計画の詳細については、 [Skype](https://technet.microsoft.com/library/jj822172.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="19a43-120">デバイス アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="19a43-120">Add a device account</span></span>

1. <span data-ttu-id="19a43-121">オンライン PowerShell を交換するために接続します。</span><span class="sxs-lookup"><span data-stu-id="19a43-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="19a43-122">手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="19a43-123">Exchange オンラインの PowerShell では、新しい会議室メールボックスを作成または既存の会議室メールボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="19a43-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="19a43-124">既定では、室メールボックスはありません関連付けられているアカウントは、作成または Skype ルーム システム v2 を認証することを許可する会議室メールボックスを変更するときにアカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="19a43-125">新しい会議室メールボックスを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="19a43-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="19a43-126">この例では、次の設定で新しい会議室メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="19a43-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="19a43-127">名前: プロジェクト-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="19a43-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="19a43-128">別名: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="19a43-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="19a43-129">アカウント: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="19a43-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="19a43-130">アカウントのパスワード: P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="19a43-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="19a43-131">既存の会議室メールボックスを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="19a43-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="19a43-132">この例では、ProjectRigel02、エイリアスの値があり、9898P@$$W0rd にパスワードを設定する既存の会議室メールボックスのアカウントが有効にします。</span><span class="sxs-lookup"><span data-stu-id="19a43-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="19a43-133">アカウントが既存のエイリアス値が ProjectRigel02@contoso.onmicrosoft.com をすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="19a43-134">詳細な構文とパラメーター情報は、[新規メールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)および[セットのメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="19a43-135">Exchange オンラインの PowerShell では、会議エクスペリエンスを向上させるために会議室メールボックスに次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="19a43-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="19a43-136">AutomateProcessing: 自動承諾 (会議の開催者が人間の介入なしで直接ルーム予約の意思決定を受信: 無料 = 受け入れる; 時間 = 辞退)。</span><span class="sxs-lookup"><span data-stu-id="19a43-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="19a43-137">AddOrganizerToSubject: の $false (会議の開催者は会議出席依頼の件名にない追加)。</span><span class="sxs-lookup"><span data-stu-id="19a43-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="19a43-138">DeleteComments: $false (会議出席依頼のメッセージ本文に任意のテキストを保持)。</span><span class="sxs-lookup"><span data-stu-id="19a43-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="19a43-139">DeleteSubject: $false (まま会議出席依頼の件名)</span><span class="sxs-lookup"><span data-stu-id="19a43-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="19a43-140">RemovePrivateProperty: $false (ことを元の会議の会議の開催者から送信されたプライベート フラグの要求に指定されたままになります)。</span><span class="sxs-lookup"><span data-stu-id="19a43-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="19a43-141">(AdditionalResponse パラメーターで指定されたテキストは、会議出席依頼に追加されます)。 AddAdditionalResponse: $true</span><span class="sxs-lookup"><span data-stu-id="19a43-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="19a43-142">AdditionalResponse:「これは、Skype の会議室!」</span><span class="sxs-lookup"><span data-stu-id="19a43-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="19a43-143">(会議出席依頼に追加する追加のテキストです。)</span><span class="sxs-lookup"><span data-stu-id="19a43-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="19a43-144">この例では、という名前のプロジェクト-Rigel-01 会議室メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="19a43-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="19a43-145">詳細な構文とパラメーター情報は、[一連の CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="19a43-146">MS オンラインの PowerShell を実行して、Active Directory の設定を行うことへの接続、 `Connect-MsolService -Credential $cred` powershell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="19a43-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="19a43-147">詳細については、Active Directory は、 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. <span data-ttu-id="19a43-148">パスワードを期限切れにしたくない場合は、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="19a43-148">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="19a43-149">この例では、アカウントの有効期限なしに ProjectRigel01@contoso.onmicrosoft.com のパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="19a43-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="19a43-150">次のコマンドを実行することによってアカウントの電話番号を設定することも。</span><span class="sxs-lookup"><span data-stu-id="19a43-150">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="19a43-151">デバイスのアカウントは、有効な Office 365 のライセンスでは、する必要があるか、Exchange およびビジネス用の Skype は機能しません。</span><span class="sxs-lookup"><span data-stu-id="19a43-151">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="19a43-152">ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。</span><span class="sxs-lookup"><span data-stu-id="19a43-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="19a43-153">使用することができます。`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="19a43-153">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="19a43-154">次のように、Office 365 テナントの使用可能な Sku の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="19a43-154">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="19a43-155">使用して、ライセンスを追加する次に、`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="19a43-155">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="19a43-156">コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="19a43-156">cmdlet.</span></span> <span data-ttu-id="19a43-157">この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="19a43-157">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="19a43-158">詳細については、 [Office 365 の PowerShell でのユーザー アカウントにライセンスを割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-158">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="19a43-159">次に、ビジネスの Skype でデバイスのアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-159">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="19a43-160">お使いの環境が [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md) で定義されている要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19a43-160">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

   <span data-ttu-id="19a43-161">( [Skype オンライン PowerShell のビジネス コンポーネントをインストール](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)することを確認する) 次のように、リモートの[Windows PowerShell セッション](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を開始します。</span><span class="sxs-lookup"><span data-stu-id="19a43-161">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="19a43-162">次に、アカウント有効にする、Skype ルーム システム v2 Skype のビジネス サーバーの次のコマンドレットを実行することによって。</span><span class="sxs-lookup"><span data-stu-id="19a43-162">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="19a43-163">次の使用例に示すように、新しいユーザー アカウントのセットアップの中から RegistrarPool 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="19a43-163">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="19a43-164">テナント内の既存のユーザー アカウントとして同じレジストラー プールに新しいユーザー アカウントを作成できません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-164">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="19a43-165">上記のコマンドは、このような状況が発生したため、アカウントのセットアップでエラーをできなくなります。</span><span class="sxs-lookup"><span data-stu-id="19a43-165">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="19a43-166">オンライン ビジネスの Skype の Skype ルーム システム v2 アカウントを有効にするのには、上記の手順を完了した後は、Skype の部屋のシステムのバージョン 2 のデバイスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-166">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="19a43-167">Office 365 管理ポータルを使用して、オンライン ビジネス (プラン 2) またはデバイスにライセンスをオンライン ビジネス (3 の計画)、Skype のいずれか、Skype を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="19a43-167">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="19a43-168">ライセンスをアカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="19a43-168">Assign a license to your account</span></span>

1. <span data-ttu-id="19a43-169">ログイン テナント管理者は、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19a43-169">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="19a43-170">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19a43-170">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="19a43-171">Skype ルーム システム v2 アカウントを選択] をクリックするか、手段の編集 [ペン] アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="19a43-171">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="19a43-172">[**ライセンス**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19a43-172">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="19a43-173">[**ライセンスの割り当て**] セクションではビジネス オンライン (3 の計画)、によっては、ライセンスおよびエンタープライズ VoIP を必要とする点で決めたものは、ビジネス オンライン (プラン 2) または Skype の Skype を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-173">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="19a43-174">Skype ルーム システム v2 のクラウド PBX を使用する場合は、計画の 3 ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-174">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="19a43-175">最低でも、音声接続用に CloudPBX が必要です。</span><span class="sxs-lookup"><span data-stu-id="19a43-175">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="19a43-176">次に、PSTN の接続方法に基づきハイブリッド音声または PSTN 通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="19a43-176">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="19a43-177">詳細については、 [Skype ルーム システム v2 のライセンス](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a43-177">See [Skype Room Systems v2 licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="19a43-178">タスクを完了するには、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19a43-178">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="19a43-179">サンプル: ルームのアカウント セットアップの Exchange オンラインと Skype のオンライン ビジネス</span><span class="sxs-lookup"><span data-stu-id="19a43-179">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="19a43-180">Exchange オンラインの PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="19a43-180">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="19a43-181">Azure Active Directory の PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="19a43-181">Azure Active Directory PowerShell commands:</span></span>

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

<span data-ttu-id="19a43-182">ビジネスの PowerShell コマンドの Skype。</span><span class="sxs-lookup"><span data-stu-id="19a43-182">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="19a43-183">この操作によって、CloudPBX および PSTNCallingDomesticAndInternational が追加されます。</span><span class="sxs-lookup"><span data-stu-id="19a43-183">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="19a43-184">さらに、電話番号を割り当てるには、管理インターフェイスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a43-184">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="19a43-185">検証</span><span class="sxs-lookup"><span data-stu-id="19a43-185">Validate</span></span>

<span data-ttu-id="19a43-186">検証、ビジネス クライアント用の Skype を使用して作成したアカウントにサインインできるように。</span><span class="sxs-lookup"><span data-stu-id="19a43-186">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="19a43-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="19a43-187">See also</span></span>

[<span data-ttu-id="19a43-188">Skype ルーム システム v2 用のアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="19a43-188">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="19a43-189">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="19a43-189">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="19a43-190">Skype Room System バージョン 2 を展開する</span><span class="sxs-lookup"><span data-stu-id="19a43-190">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)

[<span data-ttu-id="19a43-191">Skype Room Systems バージョン 2 コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="19a43-191">Configure a Skype Room Systems v2 console</span></span>](console.md)

[<span data-ttu-id="19a43-192">Skype Room Systems バージョン 2 を管理する</span><span class="sxs-lookup"><span data-stu-id="19a43-192">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[<span data-ttu-id="19a43-193">Skype ルーム システム v2 のライセンス</span><span class="sxs-lookup"><span data-stu-id="19a43-193">Skype Room Systems v2 Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
