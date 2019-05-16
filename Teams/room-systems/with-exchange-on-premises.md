---
title: オンプレミスで Exchange を使用し Microsoft Teams ミーティング を展開
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: 社内の Exchange とのハイブリッド環境でマイクロソフト チームの会議室を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 7ab9a582e26db15159677343d9edddd6bd9c45f9
ms.sourcegitcommit: 751035e1d35fc79a6b74955d7c6c46ecea0645e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2019
ms.locfileid: "34082723"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="6fa4b-103">オンプレミスで Exchange を使用し Microsoft Teams ミーティング を展開</span><span class="sxs-lookup"><span data-stu-id="6fa4b-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="6fa4b-104">マイクロソフト チームの会議室を設置型およびマイクロソフトのチームでの Exchange または Skype のハイブリッド環境でオンライン ビジネスの展開方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="6fa4b-105">設置型およびいくつかのホストがオンラインでホストされているいくつかのさまざまなサービスがある場合は、各サービスがホストされているによって、構成が決まります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="6fa4b-106">このトピックでは、社内設置型でホストされている Exchange と Microsoft チームの会議室のハイブリッド展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="6fa4b-107">この種類の展開で非常に多くのさまざまなバリエーションがあるため、それらのすべての詳細な説明を提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="6fa4b-108">以下、処理の多くの構成です。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-108">The following process will work for many configurations.</span></span> <span data-ttu-id="6fa4b-109">プロセスが、設定の適切でない場合は、ここでは、およびその他の展開オプションが記載されているように、同じ結果を達成するために Windows PowerShell を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="6fa4b-110">マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または互換性のある Microsoft チームの会議室のユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="6fa4b-111">場合は、マイクロソフト チームの会議室デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6fa4b-112">要件</span><span class="sxs-lookup"><span data-stu-id="6fa4b-112">Requirements</span></span>

<span data-ttu-id="6fa4b-113">社内の Exchange と Microsoft チームの会議室を展開する前に、要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="6fa4b-114">詳細については、[マイクロソフト チームの会議室の要件](requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="6fa4b-115">社内の Exchange と Microsoft チームの会議室を配置する場合、オンプレミス ドメイン アカウントの電子メール アドレスを追加するのには Active Directory 管理ツールを使用するが。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="6fa4b-116">このアカウントを Office 365 に同期されます。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="6fa4b-117">次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-117">You will need to:</span></span>
  
- <span data-ttu-id="6fa4b-118">アカウントを作成してアカウントを Active Directory と同期する。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="6fa4b-119">リモート メールボックスを有効にしてプロパティを設定する。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="6fa4b-120">Office 365 のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="6fa4b-121">ビジネス サーバーでは、Skype でデバイスのアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="6fa4b-122">デバイス アカウントを有効にするには、お使いの環境が次の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="6fa4b-123">Office 365 プランに Skype ビジネス online (プラン 2) またはそれ以上にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="6fa4b-124">このプランでは会議機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="6fa4b-125">エンタープライズ VoIP (PSTN テレフォニー) が必要な場合マイクロソフト チームの会議室のテレフォニー サービス プロバイダーを使用する必要があります Skype ビジネス online (プラン 3)。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="6fa4b-126">テナント ユーザーは、Exchange のメールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="6fa4b-127">チームの会議室を Microsoft アカウントが必要ですがオンライン ビジネス (プラン 2) の Skype または Skype ビジネス オンライン (プラン 3) のライセンスが Exchange Online のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="6fa4b-128">チームの会議室を Microsoft アカウントに、Skype ビジネス サーバー ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="6fa4b-129">アカウントを作成して Active Directory と同期する</span><span class="sxs-lookup"><span data-stu-id="6fa4b-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="6fa4b-130">**Active Directory ユーザーとコンピューター**ツールで、フォルダーまたはアカウントを作成するのには、マイクロソフト チーム ルームは、[**新規**作成] をクリックし、] をクリックして**ユーザー**の組織単位を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="6fa4b-p107">前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="6fa4b-p108">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6fa4b-136">Skype マイクロソフト チームの部屋にサーバーをビジネスのための要件は、**パスワードを無期限にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="6fa4b-137">ドメイン ルールによって無期限のパスワードが禁止される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="6fa4b-138">場合は、マイクロソフトのチーム会議室デバイスのアカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="6fa4b-139">アカウントを作成したら、ディレクトリの同期を実行します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="6fa4b-140">完了とは、Microsoft 365 管理センターの [ユーザー] ページに移動しを前の手順で作成したアカウントは、マージ オンラインことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="6fa4b-141">リモート メールボックスを有効にしてプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="6fa4b-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="6fa4b-142">[Exchange 管理シェルを開く](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)か、[リモート PowerShell を使用して Exchange サーバーに接続](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="6fa4b-143">Exchange の PowerShell で次のコマンドを実行することによってアカウント (アカウントのメールボックスを有効に) 用のメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="6fa4b-144">詳細な構文やパラメーターの情報を[有効にするメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="6fa4b-145">Exchange の PowerShell では、会議エクスペリエンスを向上させるために会議室メールボックスに次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="6fa4b-146">AutomateProcessing: 自動承諾 (会議の開催者が人間の介入なしで直接ルーム予約の意思決定を受信: 無料 = 受け入れる; 時間 = 辞退)。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="6fa4b-147">AddOrganizerToSubject: の $false (会議の開催者は会議出席依頼の件名にない追加)。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="6fa4b-148">DeleteComments: $false (会議出席依頼のメッセージ本文に任意のテキストを保持)。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6fa4b-149">DeleteSubject: $false (まま会議出席依頼の件名)</span><span class="sxs-lookup"><span data-stu-id="6fa4b-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6fa4b-150">RemovePrivateProperty: $false (ことを元の会議の会議の開催者から送信されたプライベート フラグの要求に指定されたままになります)。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="6fa4b-151">(AdditionalResponse パラメーターで指定されたテキストは、会議出席依頼に追加されます)。 AddAdditionalResponse: $true</span><span class="sxs-lookup"><span data-stu-id="6fa4b-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="6fa4b-152">AdditionalResponse:「これは、Skype の会議室!」</span><span class="sxs-lookup"><span data-stu-id="6fa4b-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="6fa4b-153">(会議出席依頼に追加する追加のテキストです。)</span><span class="sxs-lookup"><span data-stu-id="6fa4b-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="6fa4b-154">この例では、という名前のプロジェクト-Rigel-01 会議室メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="6fa4b-155">詳細な構文とパラメーター情報は、[一連の CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="6fa4b-156">Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6fa4b-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="6fa4b-157">Azure Active Directory に接続します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="6fa4b-158">詳細については、Active Directory は、 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="6fa4b-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="6fa4b-160">デバイスのアカウントは、有効な Office 365 のライセンスでは、する必要があるか、Exchange および Microsoft のチームは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="6fa4b-161">ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="6fa4b-162">使用することができます。`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="6fa4b-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="6fa4b-163">使用可能な Sku の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="6fa4b-164">使用して、ライセンスを追加する次に、`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="6fa4b-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="6fa4b-165">コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-165">cmdlet.</span></span> <span data-ttu-id="6fa4b-166">この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="6fa4b-167">詳細については、 [Office 365 の PowerShell でのユーザー アカウントにライセンスを割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="6fa4b-168">デバイスのアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-168">Enable the device account</span></span>

<span data-ttu-id="6fa4b-169">ビジネス オンライン PowerShell の Skype を使用すると、オンライン ビジネスのマイクロソフトのチームと Skype の両方のサービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="6fa4b-170">次のように PC からリモートの Windows PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="6fa4b-171">チームの会議室を Microsoft アカウントを有効にするには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-171">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="6fa4b-172">環境内で RegistrarPool パラメーターを使用するのにはどのような値がわからない場合は、このコマンドを使用して既存のユーザーから値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-172">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="6fa4b-173">チームの会議室を Microsoft アカウントにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-173">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="6fa4b-174">テナント管理者としてログイン、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-174">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="6fa4b-175">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-175">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="6fa4b-176">マイクロソフト チームの会議室のアカウント] をクリックし、アカウント情報を編集するのには [ペン] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-176">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="6fa4b-177">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-177">Click **Licenses**.</span></span>
5. <span data-ttu-id="6fa4b-178">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-178">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="6fa4b-179">マイクロソフト チームの会議室でエンタープライズ VoIP を使用する場合は、計画の 3 ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-179">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="6fa4b-180">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-180">Click **Save**.</span></span>

<span data-ttu-id="6fa4b-181">検証では、このアカウントにログインするすべてのクライアントを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-181">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6fa4b-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fa4b-182">See also</span></span>

[<span data-ttu-id="6fa4b-183">マイクロソフト チームの会議室のアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-183">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="6fa4b-184">マイクロソフト チームの会議室のプラン</span><span class="sxs-lookup"><span data-stu-id="6fa4b-184">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="6fa4b-185">マイクロソフト チームの会議室を配置します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-185">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="6fa4b-186">マイクロソフト チームの会議室のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="6fa4b-186">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="6fa4b-187">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="6fa4b-187">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
