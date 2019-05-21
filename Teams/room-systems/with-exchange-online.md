---
title: Exchange Online を使用して Microsoft Teams ミーティング を展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: このトピックでは、Microsoft Teams のルームを Exchange Online と共に展開する方法について説明します。
ms.openlocfilehash: e90767c6209fdb13eb7a4c6d0794865aa88e65c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288429"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="99eaf-103">Exchange Online を使用して Microsoft Teams ミーティング を展開</span><span class="sxs-lookup"><span data-stu-id="99eaf-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="99eaf-104">このトピックでは、オンプレミスの Exchange Online と Skype for Business Server を使用して Microsoft Teams ルームを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="99eaf-105">組織にサービスが混在していて、オンプレミスのホストとオンラインでホストされているものがある場合、構成は各サービスがホストされている場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="99eaf-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="99eaf-106">このトピックでは、オンラインでホストされている Microsoft Teams ルームのハイブリッド展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="99eaf-107">この種類の展開にはさまざまなバリエーションがあるため、すべてについて詳しく説明することはできません。</span><span class="sxs-lookup"><span data-stu-id="99eaf-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="99eaf-108">次のプロセスは、さまざまな構成で動作します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-108">The following process will work for many configurations.</span></span> <span data-ttu-id="99eaf-109">このプロセスが適切に設定されていない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ終了結果とその他の展開オプションを実現することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99eaf-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="99eaf-110">ユーザーアカウントをセットアップする最も簡単な方法は、リモートの Windows PowerShell を使用してアカウントを構成することです。</span><span class="sxs-lookup"><span data-stu-id="99eaf-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="99eaf-111">Microsoft には、新しいユーザーアカウントを作成するのに役立つスクリプト、または既存のリソースアカウントを、互換性のある Microsoft Teams 室のユーザーアカウントに変換するために使用している既存のリソースアカウントを検証するための SkypeRoomProvisioningScript が用意されてい[ます](https://go.microsoft.com/fwlink/?linkid=870105)。</span><span class="sxs-lookup"><span data-stu-id="99eaf-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="99eaf-112">必要に応じて、次の手順に従って、Microsoft Teams の会議室のデバイスで使用するアカウントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="99eaf-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="99eaf-113">要件</span><span class="sxs-lookup"><span data-stu-id="99eaf-113">Requirements</span></span>

<span data-ttu-id="99eaf-114">Microsoft Teams のルームを Exchange Online に展開する前に、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="99eaf-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="99eaf-115">詳細については、「 [Microsoft Teams の会議室の要件](requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99eaf-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="99eaf-116">Microsoft Teams のルームを Exchange Online と共に展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="99eaf-117">関連するコマンドレットを実行するために適切な権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-117">Be sure you have the right permissions to run the associated cmdlets.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="99eaf-118">アカウントを作成して Exchange プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="99eaf-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="99eaf-119">PC でリモート Windows PowerShell セッションを開始し、次の手順に従って Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="99eaf-120">セッションを確立したら、新しいメールボックスを作成して、RoomMailboxAccount として有効にするか、既存の会議のメールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="99eaf-121">これにより、アカウントが Microsoft Teams のルームに認証されるようになります。</span><span class="sxs-lookup"><span data-stu-id="99eaf-121">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="99eaf-122">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="99eaf-122">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="99eaf-123">新しいリソースメールボックスを作成する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="99eaf-123">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="99eaf-124">会議のエクスペリエンスを向上させるには、次のようにして、ユーザーアカウントの Exchange プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99eaf-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="99eaf-125">オンプレミスのドメイン アカウントに電子メール アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="99eaf-125">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="99eaf-126">**Active Directory ユーザーとコンピューターの AD**ツールで、Microsoft Teams の会議室のアカウントが作成されるコンテナーまたは組織単位を右クリックし、[**新規**作成] をクリックして、[**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99eaf-126">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="99eaf-127">前のコマンドレットの表示名 (-Identity) を [**氏名**] ボックスに入力し、[**ユーザーのログオン名**] ボックスにエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-127">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="99eaf-128">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99eaf-128">Click **Next**.</span></span>
3. <span data-ttu-id="99eaf-p107">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99eaf-132">[**パスワードを無期限**にする] を選ぶことは、Microsoft Teams のルームの Skype For business Server の要件です。</span><span class="sxs-lookup"><span data-stu-id="99eaf-132">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="99eaf-133">ドメイン ルールによって無期限のパスワードが禁止される場合があります。</span><span class="sxs-lookup"><span data-stu-id="99eaf-133">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="99eaf-134">そうである場合は、Microsoft Teams のルームユーザーアカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99eaf-134">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="99eaf-135">アカウントを作成するには、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99eaf-135">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="99eaf-p109">アカウントを作成したら、ディレクトリの同期を実行します。それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-p109">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="99eaf-138">Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="99eaf-138">Assign an Office 365 license</span></span>

1. <span data-ttu-id="99eaf-139">まず、[Azure AD に接続して、いくつかのアカウント設定を適用します] を選びます。</span><span class="sxs-lookup"><span data-stu-id="99eaf-139">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="99eaf-140">次のコマンドレットを実行して接続することができます。</span><span class="sxs-lookup"><span data-stu-id="99eaf-140">You can run this cmdlet to connect.</span></span> <span data-ttu-id="99eaf-141">Active Directory の詳細については、「 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99eaf-141">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="99eaf-142">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="99eaf-142">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="99eaf-143">Exchange と Skype for Business Server が動作するためには、ユーザーアカウントが有効な Office 365 ライセンスを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="99eaf-143">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="99eaf-144">ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントで利用できるライセンス Sku が決定されます。</span><span class="sxs-lookup"><span data-stu-id="99eaf-144">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="99eaf-145">課題は、次の手順で作成します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-145">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="99eaf-146">次に、`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="99eaf-146">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="99eaf-147">Office 365 テナントで利用可能な Sku の一覧を取得するには、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99eaf-147">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="99eaf-148">Sku の一覧が表示されたら、`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="99eaf-148">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="99eaf-149">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="99eaf-149">cmdlet.</span></span> <span data-ttu-id="99eaf-150">この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="99eaf-150">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="99eaf-151">Skype for Business Server を使用してユーザーアカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="99eaf-151">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="99eaf-152">PC からリモート Windows PowerShell セッションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-152">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="99eaf-153">Skype for Business Server 用の Microsoft Teams ルームアカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-153">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="99eaf-154">環境の RegistrarPool パラメーターに使用する値がわからない場合は、このコマンドを使用して、既存の Skype for Business Server ユーザーから値を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="99eaf-154">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="99eaf-155">Skype for Business Server のライセンスを Microsoft Teams のルームアカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="99eaf-155">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="99eaf-156">テナント管理者としてログインし、Office 365 管理ポータルを開いて、[管理者] アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="99eaf-156">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="99eaf-157">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99eaf-157">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="99eaf-158">Microsoft Teams のルームアカウントをクリックし、ペンアイコンをクリックしてアカウント情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-158">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="99eaf-159">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99eaf-159">Click **Licenses**.</span></span>
5. <span data-ttu-id="99eaf-160">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99eaf-160">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="99eaf-161">Microsoft Teams のルームでエンタープライズ Voip を使用する場合は、プラン3ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99eaf-161">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="99eaf-162">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99eaf-162">Click **Save**.</span></span>

<span data-ttu-id="99eaf-163">検証のために、Skype for Business クライアントを使用して、このアカウントにログインできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99eaf-163">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99eaf-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="99eaf-164">See also</span></span>

[<span data-ttu-id="99eaf-165">Microsoft Teams 室のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="99eaf-165">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="99eaf-166">Microsoft Teams のルームを計画する</span><span class="sxs-lookup"><span data-stu-id="99eaf-166">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="99eaf-167">Microsoft Teams ルームの展開</span><span class="sxs-lookup"><span data-stu-id="99eaf-167">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="99eaf-168">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="99eaf-168">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="99eaf-169">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="99eaf-169">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
