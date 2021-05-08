---
title: Exchange Online を使用して Microsoft Teams Rooms を展開
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
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: このトピックでは、Exchange OnlineとSkype for Business Serverオンプレミス を使用して Microsoft Teams Rooms を展開する方法について説明します。
ms.openlocfilehash: 5e3446349be8aaef666c02c73370758027736181
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117345"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="4ebf5-103">Exchange Online を使用して Microsoft Teams Rooms を展開</span><span class="sxs-lookup"><span data-stu-id="4ebf5-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="4ebf5-104">このトピックでは、Exchange OnlineとSkype for Business Serverオンプレミス を使用して Microsoft Teams Rooms を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="4ebf5-105">組織にサービスが混在していて、オンプレミスとオンラインでホストされているものがある場合、構成は各サービスのホスト場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="4ebf5-106">このトピックでは Exchangeがオンラインでホストする、Microsoft Teams Rooms のハイブリッドな展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="4ebf5-107">この種類の展開には、さまざまな違いがあるため、すべての手順を詳細に説明することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="4ebf5-108">次のプロセスは、多くの構成で機能します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-108">The following process will work for many configurations.</span></span> <span data-ttu-id="4ebf5-109">このプロセスがユーザーのセットアップに適していない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ結果を達成するか、または他の展開オプションをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="4ebf5-110">ユーザー アカウントをセットアップする最も簡単な方法は、リモート Windows PowerShell を使用して構成することです。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="4ebf5-111">Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいユーザー アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams Rooms のユーザー アカウントに変換する助けとなります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="4ebf5-112">必要な場合は、次の手順に従って、Microsoft Teams Rooms のデバイスが使用するアカウントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="4ebf5-113">要件</span><span class="sxs-lookup"><span data-stu-id="4ebf5-113">Requirements</span></span>

<span data-ttu-id="4ebf5-114">Microsoft Teams Rooms を Exchange Onlineで展開する前に、要件を満たしていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="4ebf5-115">詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="4ebf5-116">Exchange Online を使用して Microsoft Teams Rooms を展開するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="4ebf5-117">関連するコマンドレットを実行する適切なアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="4ebf5-118">このセクションで説明されている [「Windows PowerShell コマンドレット用の Azure Active Directory モジュール](/powershell/azure/active-directory/overview?view=azureadps-1.0)」 (たとえば  Set-MsolUser)  は、Microsoft Teams Rooms デバイスのアカウントを設定するためにテストされました。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="4ebf5-119">他のコマンドレットでも機能することがありますが、この特定のシナリオではテストされていません。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="4ebf5-120">Active Directory フェデレーションサービス (AD FS) を展開した場合は、次の手順を実行する前に、ユーザーアカウントを管理されているユーザーに変換し、この手順を実行した後にユーザーをフェデレーションユーザーに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="4ebf5-121">アカウントを作成して、Exchange のプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="4ebf5-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="4ebf5-122">PC でリモートの Windows PowerShell セッションを開始し、次のように Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="4ebf5-123">セッションを確立したら、新しいメールボックスを作成して、それを RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="4ebf5-124">これにより、アカウントは、Microsoft Teams Roomsに認証されます。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="4ebf5-125">既存のリソースメールボックスを変更する場合：</span><span class="sxs-lookup"><span data-stu-id="4ebf5-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="4ebf5-126">新しいリソース メールボックスを作成している場合:</span><span class="sxs-lookup"><span data-stu-id="4ebf5-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="4ebf5-127">会議のエクスペリエンスを改善するには、ユーザー アカウントで、次のように Exchangeプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="4ebf5-128">オンプレミスのドメインアカウントのメールアドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="4ebf5-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="4ebf5-129">**Active Directory UsersおよびComputers AD** ツールで、コンテナーまたMicrosoft Teams Rooms のアカウントの作成先となる組織単位を右クリックし、**新規** そして **ユーザー** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="4ebf5-130">前のコマンドレット(Set-MailboxまたはNew-Mailbox)の表示名 (- Identity )を **フルネーム** ボックスに入力し、次にアリアスを **ユーザーログイン名** ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="4ebf5-131">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-131">Click **Next**.</span></span>
3. <span data-ttu-id="4ebf5-p108">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ebf5-135">[**パスワードを無期限にする**] を選択すること は、Microsoft Teams Rooms 上で Skype for Business Serverを使用する要件です。 </span><span class="sxs-lookup"><span data-stu-id="4ebf5-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="4ebf5-136">有効期限が切れないパスワードは、ドメインのルールで禁止されるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="4ebf5-137">その場合は、Microsoft Teams Rooms のユーザーアカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="4ebf5-138">[ **完了**] をクリックしてアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="4ebf5-139">アカウントを作成したら、ディレクトリの同期を実行します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="4ebf5-140">これを行うには、PowerShell で[Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="4ebf5-141">それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="4ebf5-142">Microsoft 365 または Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4ebf5-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="4ebf5-143">最初にAzure AD に接続して、アカウント設定をいくつか適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="4ebf5-144">このコマンドレットを実行して接続できます。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="4ebf5-145">Active Directory の詳細については、[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="4ebf5-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="4ebf5-147">ユーザーアカウントは、Exchange と Skype for Business Serverが正常に機能するように、有効な Microsoft 365 または Office 365 ライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="4ebf5-148">ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4ebf5-149">課題は次の手順で行います。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="4ebf5-150">次に、`Get-MsolAccountSku`を使用します。 </span><span class="sxs-lookup"><span data-stu-id="4ebf5-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="4ebf5-151">Microsoft 365 または Office 365の 組織で使用でき SKU の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="4ebf5-152">SKUの一覧が表示された場合は、`Set-MsolUserLicense`を使用してライセンスを追加できます</span><span class="sxs-lookup"><span data-stu-id="4ebf5-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="4ebf5-153">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="4ebf5-153">cmdlet.</span></span> <span data-ttu-id="4ebf5-154">この例では、表示される SKU コードは$strLicenseです (たとえば、contoso: STANDARDPACK )。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="4ebf5-155">Skype for Business Server でユーザー アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="4ebf5-155">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="4ebf5-156">PC からリモートの Windows PowerShell セッションを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="4ebf5-157">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-157">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="4ebf5-158">最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-158">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="4ebf5-159">Skype for Business Serverに対して Microsoft Teams Rooms を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-159">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="4ebf5-160">お使いの環境のRegistrarPool パラメーターに使用する値が定かでない場合は、次のコマンドを実行して既存のSkype for Business Serverユーザーから値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-160">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="4ebf5-161">Microsoft Teams Rooms のアカウントに Skype for Business Server のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4ebf5-161">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="4ebf5-162">テナント管理者としてログインし、Microsoft 365 管理センターを開き、Admin アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-162">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="4ebf5-163">[ **ユーザーとグループ**] をクリックし [ **ユーザーの追加]、[パスワードのリセット]、およびその他の** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-163">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="4ebf5-164">Microsoft Teams Rooms アカウントをクリックし、ペン アイコンをクリックして、アカウント情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-164">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="4ebf5-165">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-165">Click **Licenses**.</span></span>
5. <span data-ttu-id="4ebf5-166">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-166">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="4ebf5-167">Microsoft Teams Rooms でエンタープライズ通話 を使用する場合は、プラン 3 のライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-167">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="4ebf5-168">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-168">Click **Save**.</span></span>

<span data-ttu-id="4ebf5-169">検証を行う場合は、通常、どの Skype for Businessクライアントを使用してもこのアカウントにログインできます。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-169">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="4ebf5-170">電話会議、または電話システム、通話プランが含まれる Skype for Business プラン 2で、E1、E3、E4、E5 SKU を現在お使いの場合、これらは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-170">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="4ebf5-171">現在のライセンスの有効期限が切れている場合は、[Teams ミーティングルームのライセンスアップデート](rooms-licensing.md)の説明にあるように、簡単なライセンスモデルへの移行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-171">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ebf5-172">Skype for Business プラン 2 を使用している場合、[Skype for Business のみ] のモードで Microsoft Teams Rooms をご利用いただけます。つまり、すべての会議が Skype for Business の会議になります。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-172">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="4ebf5-173">Microsoft Teams ミーティングの会議室を使用できるようにするため、ミーティング ルーム ライセンスのご購入をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4ebf5-173">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4ebf5-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ebf5-174">Related topics</span></span>

[<span data-ttu-id="4ebf5-175">Microsoft Teams Rooms のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="4ebf5-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="4ebf5-176">Microsoft Teams Rooms を計画する</span><span class="sxs-lookup"><span data-stu-id="4ebf5-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="4ebf5-177">Microsoft Teams Rooms をデプロイする</span><span class="sxs-lookup"><span data-stu-id="4ebf5-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="4ebf5-178">Microsoft Teams Rooms コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="4ebf5-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="4ebf5-179">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="4ebf5-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)