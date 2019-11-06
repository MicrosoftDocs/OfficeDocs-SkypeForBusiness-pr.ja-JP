---
title: Exchange Online を使用して Microsoft Teams ミーティング を展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: このトピックでは、Microsoft Teams のルームを Exchange Online と共に展開する方法について説明します。
ms.openlocfilehash: 8b4974b2da2fabf3230fc54359b041cebdffcdd9
ms.sourcegitcommit: 2b4fcf2561134b9f1b9a1b49401d97da1286e89d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "37979790"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="31df6-103">Exchange Online を使用して Microsoft Teams ミーティング を展開</span><span class="sxs-lookup"><span data-stu-id="31df6-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="31df6-104">このトピックでは、オンプレミスの Exchange Online と Skype for Business Server を使用して Microsoft Teams ルームを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31df6-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="31df6-105">組織にサービスが混在していて、オンプレミスのホストとオンラインでホストされているものがある場合、構成は各サービスがホストされている場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="31df6-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="31df6-106">このトピックでは、オンラインでホストされている Microsoft Teams ルームのハイブリッド展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="31df6-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="31df6-107">この種類の展開にはさまざまなバリエーションがあるため、すべてについて詳しく説明することはできません。</span><span class="sxs-lookup"><span data-stu-id="31df6-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="31df6-108">次のプロセスは、さまざまな構成で動作します。</span><span class="sxs-lookup"><span data-stu-id="31df6-108">The following process will work for many configurations.</span></span> <span data-ttu-id="31df6-109">このプロセスが適切に設定されていない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ終了結果とその他の展開オプションを実現することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31df6-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="31df6-110">ユーザーアカウントをセットアップする最も簡単な方法は、リモートの Windows PowerShell を使用してアカウントを構成することです。</span><span class="sxs-lookup"><span data-stu-id="31df6-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="31df6-111">Microsoft には、新しいユーザーアカウントを作成するのに役立つスクリプト、または既存のリソースアカウントを、互換性のある Microsoft Teams 室のユーザーアカウントに変換するために使用している既存のリソースアカウントを検証するための SkypeRoomProvisioningScript が用意されてい[ます](https://go.microsoft.com/fwlink/?linkid=870105)。</span><span class="sxs-lookup"><span data-stu-id="31df6-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="31df6-112">必要に応じて、次の手順に従って、Microsoft Teams の会議室のデバイスで使用するアカウントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="31df6-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="31df6-113">要件</span><span class="sxs-lookup"><span data-stu-id="31df6-113">Requirements</span></span>

<span data-ttu-id="31df6-114">Microsoft Teams のルームを Exchange Online に展開する前に、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="31df6-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="31df6-115">詳細については、「 [Microsoft Teams の会議室の要件](requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31df6-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="31df6-116">Microsoft Teams のルームを Exchange Online と共に展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="31df6-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="31df6-117">関連するコマンドレットを実行するために適切な権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31df6-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="31df6-118">このセクションの[Windows PowerShell コマンドレット用 Azure Active Directory モジュール](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)(たとえば、Set-get-msoluser) は、Microsoft Teams 室デバイスのアカウントのセットアップでテストされています。</span><span class="sxs-lookup"><span data-stu-id="31df6-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="31df6-119">ただし、他のコマンドレットは動作する可能性がありますが、この特定のシナリオではテストされていません。</span><span class="sxs-lookup"><span data-stu-id="31df6-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="31df6-120">アカウントを作成して Exchange プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="31df6-120">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="31df6-121">PC でリモート Windows PowerShell セッションを開始し、次の手順に従って Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="31df6-121">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. <span data-ttu-id="31df6-122">セッションを確立したら、新しいメールボックスを作成して、RoomMailboxAccount として有効にするか、既存の会議のメールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="31df6-122">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="31df6-123">これにより、アカウントが Microsoft Teams のルームに認証されるようになります。</span><span class="sxs-lookup"><span data-stu-id="31df6-123">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="31df6-124">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="31df6-124">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="31df6-125">新しいリソースメールボックスを作成する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="31df6-125">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="31df6-126">会議のエクスペリエンスを向上させるには、次のようにして、ユーザーアカウントの Exchange プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31df6-126">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="31df6-127">オンプレミスのドメイン アカウントに電子メール アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="31df6-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="31df6-128">**Active Directory ユーザーとコンピューターの AD**ツールで、Microsoft Teams の会議室のアカウントが作成されるコンテナーまたは組織単位を右クリックし、[**新規**作成] をクリックして、[**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31df6-128">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="31df6-129">前のコマンドレットの表示名 (-Identity) を [**氏名**] ボックスに入力し、[**ユーザーのログオン名**] ボックスにエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="31df6-129">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="31df6-130">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31df6-130">Click **Next**.</span></span>
3. <span data-ttu-id="31df6-p108">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31df6-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="31df6-134">[**パスワードを無期限**にする] を選ぶことは、Microsoft Teams のルームの Skype For business Server の要件です。</span><span class="sxs-lookup"><span data-stu-id="31df6-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="31df6-135">ドメイン ルールによって無期限のパスワードが禁止される場合があります。</span><span class="sxs-lookup"><span data-stu-id="31df6-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="31df6-136">そうである場合は、Microsoft Teams のルームユーザーアカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31df6-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="31df6-137">アカウントを作成するには、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31df6-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="31df6-138">アカウントを作成したら、ディレクトリ同期を実行します。</span><span class="sxs-lookup"><span data-stu-id="31df6-138">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="31df6-139">これは、PowerShell で[MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)を使うことで実現できます。</span><span class="sxs-lookup"><span data-stu-id="31df6-139">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="31df6-140">完了したら、[ユーザー] ページに移動し、前の手順で作成した2つのアカウントがマージされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31df6-140">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="31df6-141">Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="31df6-141">Assign an Office 365 license</span></span>

1. <span data-ttu-id="31df6-142">まず、[Azure AD に接続して、いくつかのアカウント設定を適用します] を選びます。</span><span class="sxs-lookup"><span data-stu-id="31df6-142">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="31df6-143">次のコマンドレットを実行して接続することができます。</span><span class="sxs-lookup"><span data-stu-id="31df6-143">You can run this cmdlet to connect.</span></span> <span data-ttu-id="31df6-144">Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31df6-144">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="31df6-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="31df6-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="31df6-146">Exchange と Skype for Business Server が動作するためには、ユーザーアカウントが有効な Office 365 ライセンスを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="31df6-146">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="31df6-147">ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。</span><span class="sxs-lookup"><span data-stu-id="31df6-147">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="31df6-148">課題は、次の手順で作成します。</span><span class="sxs-lookup"><span data-stu-id="31df6-148">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="31df6-149">次に、`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="31df6-149">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="31df6-150">Office 365 テナントで利用可能な Sku の一覧を取得するには、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31df6-150">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="31df6-151">Sku の一覧が表示されたら、`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="31df6-151">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="31df6-152">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="31df6-152">cmdlet.</span></span> <span data-ttu-id="31df6-153">この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="31df6-153">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="31df6-154">Skype for Business Server を使用してユーザーアカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="31df6-154">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="31df6-155">PC からリモート Windows PowerShell セッションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="31df6-155">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="31df6-156">Skype for Business Server 用の Microsoft Teams ルームアカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="31df6-156">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="31df6-157">環境の RegistrarPool パラメーターに使用する値がわからない場合は、このコマンドを使用して、既存の Skype for Business Server ユーザーから値を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="31df6-157">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="31df6-158">Skype for Business Server のライセンスを Microsoft Teams のルームアカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="31df6-158">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="31df6-159">テナント管理者としてログインし、Office 365 管理ポータルを開いて、[管理者] アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="31df6-159">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="31df6-160">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31df6-160">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="31df6-161">Microsoft Teams のルームアカウントをクリックし、ペンアイコンをクリックしてアカウント情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="31df6-161">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="31df6-162">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31df6-162">Click **Licenses**.</span></span>
5. <span data-ttu-id="31df6-163">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="31df6-163">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="31df6-164">Microsoft Teams のルームでエンタープライズ Voip を使用する場合は、プラン3ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31df6-164">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="31df6-165">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31df6-165">Click **Save**.</span></span>

<span data-ttu-id="31df6-166">検証のために、Skype for Business クライアントを使用して、このアカウントにログインできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31df6-166">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="31df6-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="31df6-167">See also</span></span>

[<span data-ttu-id="31df6-168">Microsoft Teams 室のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="31df6-168">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="31df6-169">Microsoft Teams のルームを計画する</span><span class="sxs-lookup"><span data-stu-id="31df6-169">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="31df6-170">Microsoft Teams ルームの展開</span><span class="sxs-lookup"><span data-stu-id="31df6-170">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="31df6-171">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="31df6-171">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="31df6-172">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="31df6-172">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
