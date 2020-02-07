---
title: オンプレミスで Exchange を使用し Microsoft Teams ミーティング を展開
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
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: このトピックでは、オンプレミスの Exchange を使用したハイブリッド環境で Microsoft Teams のルームを展開する方法について説明します。
ms.openlocfilehash: eb399eea64707e07d796ee36e85036e662ce8de1
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838187"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="3b4f3-103">オンプレミスで Exchange を使用し Microsoft Teams ミーティング を展開</span><span class="sxs-lookup"><span data-stu-id="3b4f3-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="3b4f3-104">このトピックでは、オンプレミスの Exchange と Microsoft Teams または Skype for Business Online のハイブリッド環境で Microsoft Teams のルームを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="3b4f3-105">組織にサービスが混在していて、オンプレミスのホストとオンラインでホストされているものがある場合、構成は各サービスがホストされている場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="3b4f3-106">このトピックでは、社内で Exchange をホストしている Microsoft Teams ルームのハイブリッド展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="3b4f3-107">この種類の展開にはさまざまなバリエーションがあるため、すべてについて詳しく説明することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="3b4f3-108">次のプロセスは、さまざまな構成で動作します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-108">The following process will work for many configurations.</span></span> <span data-ttu-id="3b4f3-109">このプロセスが適切に設定されていない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ終了結果とその他の展開オプションを実現することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="3b4f3-110">Microsoft には、新しいユーザーアカウントを作成するのに役立つスクリプト、または既存のリソースアカウントを、互換性のある Microsoft Teams 室のユーザーアカウントに変換するために使用している既存のリソースアカウントを検証するための SkypeRoomProvisioningScript が用意されてい[ます](https://go.microsoft.com/fwlink/?linkid=870105)。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="3b4f3-111">必要に応じて、次の手順に従って、Microsoft Teams の会議室のデバイスで使用するアカウントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3b4f3-112">要件</span><span class="sxs-lookup"><span data-stu-id="3b4f3-112">Requirements</span></span>

<span data-ttu-id="3b4f3-113">Exchange とオンプレミスの Microsoft Teams ルームを展開する前に、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="3b4f3-114">詳細については、「 [Microsoft Teams の会議室の要件](requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="3b4f3-115">オンプレミスの Exchange で Microsoft Teams のルームを展開している場合は、Active Directory 管理ツールを使用して、オンプレミスのドメインアカウントのメールアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="3b4f3-116">このアカウントは、Office 365 と同期されます。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="3b4f3-117">次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-117">You will need to:</span></span>
  
- <span data-ttu-id="3b4f3-118">アカウントを作成してアカウントを Active Directory と同期する。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="3b4f3-119">リモート メールボックスを有効にしてプロパティを設定する。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="3b4f3-120">Office 365 ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="3b4f3-121">Skype for Business Server でデバイスアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="3b4f3-122">デバイス アカウントを有効にするには、お使いの環境が次の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="3b4f3-123">Office 365 プランでは、Skype for Business Online (プラン 2) 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="3b4f3-124">このプランでは会議機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="3b4f3-125">Microsoft Teams 室のテレフォニーサービスプロバイダーを使用するエンタープライズ Voip (PSTN テレフォニー) が必要な場合は、Skype for Business Online (プラン 3) が必要です。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="3b4f3-126">テナントユーザーは Exchange メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="3b4f3-127">Microsoft Teams のルームアカウントでは、Skype for Business Online (プラン 2) または Skype for Business Online (Plan 3) ライセンスが必要ですが、Exchange Online ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="3b4f3-128">Skype for Business Server のライセンスを Microsoft Teams のルームアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="3b4f3-129">アカウントを作成して Active Directory と同期する</span><span class="sxs-lookup"><span data-stu-id="3b4f3-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="3b4f3-130">**Active Directory ユーザーとコンピューター**ツールで、Microsoft Teams の会議室のアカウントが作成されるフォルダーまたは組織単位を右クリックし、[**新規**作成] をクリックして、[**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="3b4f3-p107">前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="3b4f3-p108">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b4f3-136">[**パスワードを無期限**にする] を選ぶことは、Microsoft Teams のルームの Skype For business Server の要件です。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="3b4f3-137">ドメイン ルールによって無期限のパスワードが禁止される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="3b4f3-138">そうである場合は、Microsoft Teams のルームデバイスアカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="3b4f3-139">アカウントを作成したら、ディレクトリの同期を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="3b4f3-140">完了したら、Microsoft 365 管理センターの [ユーザー] ページに移動し、前の手順で作成したアカウントがオンラインに統合されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="3b4f3-141">リモート メールボックスを有効にしてプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="3b4f3-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="3b4f3-142">[Exchange 管理シェルを開くか、](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) [リモート PowerShell を使用して exchange server に接続](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="3b4f3-143">Exchange PowerShell で、次のコマンドを実行して、アカウントのメールボックスを作成します (メールボックスでアカウントを有効にします)。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-143">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="3b4f3-144">構文とパラメーターについて詳しくは、「[メールボックスを有効にする](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="3b4f3-145">Exchange PowerShell で、会議の操作性を向上させるために、会議室メールボックスで次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="3b4f3-146">自動的な処理: 自動承諾 (会議の開催者は、手動での介入なく、会議の開催者が会議室の予約を直接受け取ります: 無料 = accept; busy = 拒否。)</span><span class="sxs-lookup"><span data-stu-id="3b4f3-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="3b4f3-147">Addオーガナイザー Ertosubject: $false (会議の開催者は、会議出席依頼の件名に追加されません)。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="3b4f3-148">DeleteComments: $false (入力した会議出席依頼のメッセージ本文に含まれるテキストを保持)</span><span class="sxs-lookup"><span data-stu-id="3b4f3-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="3b4f3-149">DeleteSubject: $false (入力した会議出席依頼の件名を保持)</span><span class="sxs-lookup"><span data-stu-id="3b4f3-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="3b4f3-150">RemovePrivateProperty: $false (元の会議出席依頼の開催者によって送信されたプライベートフラグが指定されたままになります)。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="3b4f3-151">AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます)</span><span class="sxs-lookup"><span data-stu-id="3b4f3-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="3b4f3-152">AdditionalResponse: "これは Skype 会議室です。"</span><span class="sxs-lookup"><span data-stu-id="3b4f3-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="3b4f3-153">(会議出席依頼に追加する追加のテキスト)</span><span class="sxs-lookup"><span data-stu-id="3b4f3-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="3b4f3-154">この例では、Rigel-01 という名前の会議室メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="3b4f3-155">構文とパラメーターの詳細については、「 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="3b4f3-156">Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3b4f3-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="3b4f3-157">Azure Active Directory に接続します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="3b4f3-158">Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="3b4f3-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="3b4f3-160">デバイスアカウントには、有効な Office 365 ライセンスが必要です。または、Exchange と Microsoft Teams は動作しません。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="3b4f3-161">ライセンスを所有している場合は、使用場所をデバイスアカウントに割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="3b4f3-162">使用できる方法`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="3b4f3-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="3b4f3-163">利用可能な Sku の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="3b4f3-164">次に、次の方法を使用してライセンスを追加することができます。`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="3b4f3-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="3b4f3-165">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="3b4f3-165">cmdlet.</span></span> <span data-ttu-id="3b4f3-166">この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="3b4f3-167">詳細な手順については、「 [Office 365 PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="3b4f3-168">デバイスアカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="3b4f3-168">Enable the device account</span></span>

<span data-ttu-id="3b4f3-169">Skype for Business Online PowerShell は、Microsoft Teams と Skype for Business Online の両方のサービスを管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="3b4f3-170">PC からリモート Windows PowerShell セッションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="3b4f3-171">アカウントの SIP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-171">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="3b4f3-172">Microsoft Teams のルームアカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-172">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="3b4f3-173">環境内の RegistrarPool パラメーターに使用する値がわからない場合は、次のコマンドを使用して、既存のユーザーの値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-173">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="3b4f3-174">Microsoft Teams のルームアカウントにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3b4f3-174">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="3b4f3-175">テナント管理者としてログインし、Office 365 管理ポータルを開いて、[管理者] アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-175">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="3b4f3-176">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-176">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="3b4f3-177">Microsoft Teams のルームアカウントをクリックし、ペンアイコンをクリックしてアカウント情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-177">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="3b4f3-178">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-178">Click **Licenses**.</span></span>
5. <span data-ttu-id="3b4f3-179">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-179">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="3b4f3-180">Microsoft Teams のルームでエンタープライズ Voip を使用する場合は、プラン3ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-180">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="3b4f3-181">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-181">Click **Save**.</span></span>

<span data-ttu-id="3b4f3-182">検証のために、任意のクライアントを使用してこのアカウントにログインできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b4f3-182">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3b4f3-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b4f3-183">See also</span></span>

[<span data-ttu-id="3b4f3-184">Microsoft Teams 室のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="3b4f3-184">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="3b4f3-185">Microsoft Teams のルームを計画する</span><span class="sxs-lookup"><span data-stu-id="3b4f3-185">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="3b4f3-186">Microsoft Teams ルームの展開</span><span class="sxs-lookup"><span data-stu-id="3b4f3-186">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="3b4f3-187">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="3b4f3-187">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="3b4f3-188">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="3b4f3-188">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
