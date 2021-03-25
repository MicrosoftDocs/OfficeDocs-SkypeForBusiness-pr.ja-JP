---
title: オンプレミスで Exchange を使用し Microsoft Teams Rooms を展開
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: このトピックでは、オンプレミスの Exchange が搭載されたハイブリッド環境に Microsoft Teams Rooms を展開する方法について説明します。
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117355"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="6df70-103">オンプレミスで Exchange を使用し Microsoft Teams Rooms を展開する</span><span class="sxs-lookup"><span data-stu-id="6df70-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="6df70-104">このトピックでは、オンプレミスのExchange およびMicrosoft Teams またはSkype for Business Online を使用したハイブリッド環境で Microsoft Teams Rooms を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6df70-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="6df70-105">組織にサービスが混在していて、オンプレミスとオンラインでホストされているものがある場合、構成は各サービスのホスト場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6df70-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="6df70-106">このトピックでは Exchangeがオンラインでホストする、Microsoft Teams Rooms のハイブリッドな展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="6df70-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="6df70-107">この種類の展開には、さまざまな違いがあるため、すべての手順を詳細に説明することはできません。</span><span class="sxs-lookup"><span data-stu-id="6df70-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="6df70-108">次のプロセスは、多くの構成で機能します。</span><span class="sxs-lookup"><span data-stu-id="6df70-108">The following process will work for many configurations.</span></span> <span data-ttu-id="6df70-109">このプロセスがユーザーのセットアップに適していない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ結果を達成するか、または他の展開オプションをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6df70-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="6df70-110">Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいユーザー アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams Rooms のユーザー アカウントに変換する助けとなります。</span><span class="sxs-lookup"><span data-stu-id="6df70-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="6df70-111">必要な場合は、次の手順に従って、Microsoft Teams Rooms のデバイスが使用するアカウントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6df70-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6df70-112">要件</span><span class="sxs-lookup"><span data-stu-id="6df70-112">Requirements</span></span>

<span data-ttu-id="6df70-113">Microsoft Teams Rooms をオンプレミスの Exchangeで展開する前に、要件を満たしていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="6df70-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="6df70-114">詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6df70-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="6df70-115">オンプレミスの Exchangeを使用してMicrosoft Teams Rooms を展開する場合は、Active Directory の管理ツールを使用してオンプレミス ドメイン アカウントの電子メール アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6df70-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="6df70-116">このアカウントは、Microsoft 365 または Office 365 に同期されます。</span><span class="sxs-lookup"><span data-stu-id="6df70-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="6df70-117">次の操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="6df70-117">You will need to:</span></span>
  
- <span data-ttu-id="6df70-118">アカウントを作成してアカウントを Active Directory と同期する。</span><span class="sxs-lookup"><span data-stu-id="6df70-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="6df70-119">リモート メールボックスを有効にしてプロパティを設定する。</span><span class="sxs-lookup"><span data-stu-id="6df70-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="6df70-120">Microsoft 365 または Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6df70-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="6df70-121">Skype for Business サーバーでデバイス アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="6df70-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="6df70-122">デバイスアカウントを有効にするには、お使いの環境が次の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df70-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="6df70-123">Microsoft 365 または Office 365 プランの Skype for Business Online (プラン 2) 以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df70-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="6df70-124">プランは会議機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df70-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="6df70-125">Microsoft Teams Rooms 向けテレフォニーサービスプロバイダーを使用して、エンタープライズ ボイス(PSTN テレフォニー) が必要な場合は、Skype for Business Online (プラン 3) が必要です。</span><span class="sxs-lookup"><span data-stu-id="6df70-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="6df70-126">Microsoft Teams または Skype for Business Online でルーム アカウントを構成する場合、そのアカウントをルーム アカウントとして有効にする前に、電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df70-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="6df70-127">テナントユーザーには Exchange メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="6df70-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="6df70-128">Microsoft Teams Rooms のアカウントでは、少なくとも Skype for Business Online (プラン 2)またはSkype for Business Online （Plan 3） のライセンスが必要ですが、Exchange Online のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6df70-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="6df70-129">Microsoft Teams Rooms のアカウントに Skype for Business Server のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6df70-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="6df70-130">アカウントを作成し、Active Directory と同期します。</span><span class="sxs-lookup"><span data-stu-id="6df70-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="6df70-131">**Active Directoryユーザーおよびコンピューター** ツールで、フォルダーまたはMicrosoft Teams Rooms のアカウントの作成先となる組織単位を右クリックし、**新規** そして **ユーザー** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6df70-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="6df70-p107">前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6df70-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="6df70-p108">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6df70-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6df70-137">[**パスワードを無期限にする**] を選択すること は、Microsoft Teams Rooms 上で Skype for Business Serverを使用する要件です。 </span><span class="sxs-lookup"><span data-stu-id="6df70-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="6df70-138">有効期限が切れないパスワードは、ドメインのルールで禁止されるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="6df70-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="6df70-139">その場合は、Microsoft Teams Rooms のユーザーアカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df70-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="6df70-140">アカウントを作成したら、ディレクトリの同期を実行します。</span><span class="sxs-lookup"><span data-stu-id="6df70-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="6df70-141">同期が完了したら、Microsoft 365管理センターの [ユーザー] ページに移動し、上記の手順で作成したアカウントがオンラインにマージされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6df70-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="6df70-142">リモートメールボックスを有効にしてプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="6df70-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="6df70-143">[Exchange 管理シェルを開く](/powershell/exchange/exchange-server/open-the-exchange-management-shell) または、[リモート PowerShellを使用して Exchange サーバーに接続し ます](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6df70-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="6df70-144">Exchange PowerShell で次のコマンドを実行して、アカウントのメールボックスを作成します （アカウントのメールボックス有効化）アカウントを有効にします）。</span><span class="sxs-lookup"><span data-stu-id="6df70-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="6df70-145">構文およびパラメーターの詳細については、「[Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df70-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="6df70-146">Exchange Online PowerShell で、会議機能を向上させるために、会議室メールボックスの次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6df70-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="6df70-147">AutomateProcessing: AutoAccept (会議の開催者は、手動での介入なしに部屋予約の決定を受け取ります: free = 同意; busy = 拒否。)</span><span class="sxs-lookup"><span data-stu-id="6df70-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="6df70-148">AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)</span><span class="sxs-lookup"><span data-stu-id="6df70-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="6df70-149">DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)</span><span class="sxs-lookup"><span data-stu-id="6df70-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6df70-150">DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)</span><span class="sxs-lookup"><span data-stu-id="6df70-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6df70-151">RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)</span><span class="sxs-lookup"><span data-stu-id="6df70-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="6df70-152">AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)</span><span class="sxs-lookup"><span data-stu-id="6df70-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="6df70-153">AdditionalResponse: "これは Skype 会議室です。"</span><span class="sxs-lookup"><span data-stu-id="6df70-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="6df70-154">(会議出席依頼に追加するテキスト)。</span><span class="sxs-lookup"><span data-stu-id="6df70-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="6df70-155">この例では、Project-Rigel-01という名前の会議室メールボックスでこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6df70-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="6df70-156">構文とパラメーターの詳細情報については、[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df70-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="6df70-157">Microsoft 365 または Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6df70-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="6df70-158">Azure Active Directoryに接続する</span><span class="sxs-lookup"><span data-stu-id="6df70-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="6df70-159">Active Directory の詳細については、[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df70-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="6df70-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6df70-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="6df70-161">デバイスアカウントには、Microsoft 365 または Office 365 の有効なライセンスが必要です。さもないと Exchange および Microsoft Teams は機能しません。</span><span class="sxs-lookup"><span data-stu-id="6df70-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="6df70-162">ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。</span><span class="sxs-lookup"><span data-stu-id="6df70-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="6df70-163">`Get-MsolAccountSku`を使用して</span><span class="sxs-lookup"><span data-stu-id="6df70-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="6df70-164">使用可能な SKUの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6df70-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="6df70-165">次に、以下の `Set-MsolUserLicense`を使用してライセンスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6df70-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="6df70-166">することができます。</span><span class="sxs-lookup"><span data-stu-id="6df70-166">cmdlet.</span></span> <span data-ttu-id="6df70-167">この例では、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="6df70-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="6df70-168">手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df70-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="6df70-169">デバイスアカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="6df70-169">Enable the device account</span></span>

<span data-ttu-id="6df70-170">Skype for Business Online PowerShell は、Microsoft Teams および Skype for Business Online のサービスの管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6df70-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="6df70-171">PC からリモートの Windows PowerShell セッションを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6df70-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="6df70-172">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6df70-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="6df70-173">最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6df70-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="6df70-174">アカウントの SIP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6df70-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="6df70-175">**オプション。**</span><span class="sxs-lookup"><span data-stu-id="6df70-175">**Optional.**</span></span> <span data-ttu-id="6df70-176">アカウントに電話番号を割り当てる場合は、この時点で操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df70-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="6df70-177">ダイレクト ルーティングの電話番号を割り当てる場合:</span><span class="sxs-lookup"><span data-stu-id="6df70-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="6df70-178">Microsoft 提供の電話番号を割り当てる場合は、通話プラン ライセンスでユーザーをプロビジョニングした後、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6df70-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="6df70-179">Microsoft Teams Rooms を使用するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6df70-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="6df70-180">お使いの環境の RegistrarPool パラメーターに使用する値が定かでない場合は、次のコマンドを実行して既存のユーザーから値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6df70-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="6df70-181">Microsoft Teams Rooms のアカウントにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6df70-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="6df70-182">テナント管理者としてログインし、Microsoft 365 管理センターを開き、Admin アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6df70-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="6df70-183">[ **ユーザーとグループ**] をクリックし [ **ユーザーの追加]、[パスワードのリセット]、およびその他の** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6df70-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="6df70-184">Microsoft Teams Rooms アカウントをクリックし、ペン アイコンをクリックして、アカウント情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="6df70-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="6df70-185">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6df70-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="6df70-186">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6df70-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="6df70-187">Microsoft Teams Rooms でエンタープライズ通話 を使用する場合は、プラン 3 のライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df70-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="6df70-188">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6df70-188">Click **Save**.</span></span>

<span data-ttu-id="6df70-189">検証を行う場合は、通常、どのクライアントを使用してもこのアカウントにログインできます。</span><span class="sxs-lookup"><span data-stu-id="6df70-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6df70-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="6df70-190">Related topics</span></span>

[<span data-ttu-id="6df70-191">Microsoft Teams Rooms のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="6df70-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="6df70-192">Microsoft Teams Rooms を計画する</span><span class="sxs-lookup"><span data-stu-id="6df70-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="6df70-193">Microsoft Teams Rooms をデプロイする</span><span class="sxs-lookup"><span data-stu-id="6df70-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="6df70-194">Microsoft Teams Rooms コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="6df70-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="6df70-195">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="6df70-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)