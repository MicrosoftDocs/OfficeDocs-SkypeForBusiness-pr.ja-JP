---
title: オンライン Exchange とマイクロソフトのチームの会議室を配置します。
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
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Exchange オンラインでマイクロソフト チームの会議室を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 09a9cf6ed01ea4b523e6f790d30a586e92b5c4f5
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012885"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="243c4-103">オンライン Exchange とマイクロソフトのチームの会議室を配置します。</span><span class="sxs-lookup"><span data-stu-id="243c4-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="243c4-104">マイクロソフト チーム会議室と、Exchange オンライン Skype ビジネス サーバー設置型の展開方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="243c4-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="243c4-105">設置型およびいくつかのホストがオンラインでホストされているいくつかのさまざまなサービスがある場合は、各サービスがホストされているによって、構成が決まります。</span><span class="sxs-lookup"><span data-stu-id="243c4-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="243c4-106">このトピックでは、オンラインでホストされている Exchange と Microsoft チームの会議室のハイブリッド展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="243c4-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="243c4-107">この種類の展開で非常に多くのさまざまなバリエーションがあるため、それらのすべての詳細な説明を提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="243c4-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="243c4-108">以下、処理の多くの構成です。</span><span class="sxs-lookup"><span data-stu-id="243c4-108">The following process will work for many configurations.</span></span> <span data-ttu-id="243c4-109">プロセスが、設定の適切でない場合は、ここでは、およびその他の展開オプションが記載されているように、同じ結果を達成するために Windows PowerShell を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="243c4-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="243c4-110">ユーザー アカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。</span><span class="sxs-lookup"><span data-stu-id="243c4-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="243c4-111">マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または互換性のある Microsoft チームの会議室のユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="243c4-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="243c4-112">場合は、マイクロソフト チームの会議室デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="243c4-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="243c4-113">要件</span><span class="sxs-lookup"><span data-stu-id="243c4-113">Requirements</span></span>

<span data-ttu-id="243c4-114">Exchange オンラインでマイクロソフト チームの会議室を展開する前に、要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="243c4-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="243c4-115">詳細については、[マイクロソフト チームの会議室の要件](../../plan-your-deployment/clients-and-devices/requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="243c4-115">For more information, see [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="243c4-116">Exchange オンラインでマイクロソフト チームの会議室を配置するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="243c4-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="243c4-117">関連するコマンドレットを実行するために適切な権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="243c4-117">Be sure you have the right permissions to run the associated cmdlets.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="243c4-118">アカウントを作成して Exchange プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="243c4-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="243c4-119">PC 上でリモートの Windows PowerShell セッションを開始し、Exchange Online への接続を次のようにします。</span><span class="sxs-lookup"><span data-stu-id="243c4-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="243c4-120">セッションを確立するには後、するが新しいメールボックスを作成して、RoomMailboxAccount、として有効にか既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="243c4-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="243c4-121">これにより、マイクロソフトのチームの会議室に認証するためにアカウントが許可されます。</span><span class="sxs-lookup"><span data-stu-id="243c4-121">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="243c4-122">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="243c4-122">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="243c4-123">: 新しいリソース メールボックスを作成する場合</span><span class="sxs-lookup"><span data-stu-id="243c4-123">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="243c4-124">会議エクスペリエンスを向上させるため、次のようにユーザー アカウントに Exchange のプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="243c4-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="243c4-125">Azure AD に接続して、アカウント設定をいくつか適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="243c4-125">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="243c4-126">次のコマンドレットを実行して接続することができます。</span><span class="sxs-lookup"><span data-stu-id="243c4-126">You can run this cmdlet to connect.</span></span>

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="243c4-127">オンプレミスのドメイン アカウントに電子メール アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="243c4-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="243c4-128">**Active Directory ユーザーとコンピューターの AD**ツールで、フォルダーまたはアカウントを作成するのには、マイクロソフト チーム ルームは、[**新規**作成] をクリックし、] をクリックして**ユーザー**の組織単位を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="243c4-128">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="243c4-p107">前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243c4-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
3. <span data-ttu-id="243c4-p108">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="243c4-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="243c4-134">Skype マイクロソフト チームの部屋にサーバーをビジネスのための要件は、**パスワードを無期限にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="243c4-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="243c4-135">ドメイン ルールによって無期限のパスワードが禁止される場合があります。</span><span class="sxs-lookup"><span data-stu-id="243c4-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="243c4-136">その場合は、マイクロソフト チームの会議室のユーザー アカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="243c4-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="243c4-137">アカウントを作成するには、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243c4-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="243c4-p110">アカウントを作成したら、ディレクトリの同期を実行します。それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="243c4-p110">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="243c4-140">Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="243c4-140">Assign an Office 365 license</span></span>

1. <span data-ttu-id="243c4-141">ユーザー アカウントは、Exchange と Skype のビジネス サーバーが動作することを確認するのには有効な Office 365 ライセンスを所有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="243c4-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="243c4-142">ライセンスがあれば、利用場所を割り当てるユーザー アカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定です。</span><span class="sxs-lookup"><span data-stu-id="243c4-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
2. <span data-ttu-id="243c4-143">次を使用して、`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="243c4-143">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="243c4-144">Office 365 テナントの使用可能な Sku の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="243c4-144">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
3. <span data-ttu-id="243c4-145">ライセンスを使用してを追加するには、Sku を一覧表示すると、`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="243c4-145">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="243c4-146">コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="243c4-146">cmdlet.</span></span> <span data-ttu-id="243c4-147">この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="243c4-147">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="243c4-148">ビジネス サーバーの Skype でのユーザー アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="243c4-148">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="243c4-149">次のように PC からリモートの Windows PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="243c4-149">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="243c4-150">ビジネスのサーバーでは、Skype のマイクロソフト チームの会議室のアカウントを有効にするには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="243c4-150">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="243c4-151">ビジネス サーバーのユーザーがこのコマンドを使用して既存の Skype から値を取得するには、環境内の RegistrarPool パラメーターを使用するのにはどのような値がわからない場合</span><span class="sxs-lookup"><span data-stu-id="243c4-151">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="243c4-152">チームの会議室を Microsoft アカウントに、Skype ビジネス サーバー ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="243c4-152">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="243c4-153">テナント管理者としてログイン、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。</span><span class="sxs-lookup"><span data-stu-id="243c4-153">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="243c4-154">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243c4-154">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="243c4-155">マイクロソフト チームの会議室のアカウント] をクリックし、アカウント情報を編集するのには [ペン] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="243c4-155">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="243c4-156">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243c4-156">Click **Licenses**.</span></span>
5. <span data-ttu-id="243c4-157">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="243c4-157">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="243c4-158">マイクロソフト チームの会議室でエンタープライズ VoIP を使用する場合は、計画の 3 ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="243c4-158">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="243c4-159">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243c4-159">Click **Save**.</span></span>

<span data-ttu-id="243c4-160">検証、ビジネス クライアント用の Skype を使用してこのアカウントにログインできるように。</span><span class="sxs-lookup"><span data-stu-id="243c4-160">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="243c4-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="243c4-161">See also</span></span>

[<span data-ttu-id="243c4-162">マイクロソフト チームの会議室のアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="243c4-162">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="243c4-163">マイクロソフト チームの会議室のプラン</span><span class="sxs-lookup"><span data-stu-id="243c4-163">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="243c4-164">マイクロソフト チームの会議室を配置します。</span><span class="sxs-lookup"><span data-stu-id="243c4-164">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="243c4-165">マイクロソフト チームの会議室のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="243c4-165">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="243c4-166">マイクロソフト チームの会議室を管理します。</span><span class="sxs-lookup"><span data-stu-id="243c4-166">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
