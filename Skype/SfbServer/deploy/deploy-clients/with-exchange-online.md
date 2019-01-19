---
title: Skype Room Systems バージョン 2 と Exchange Online を展開する
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Exchange オンラインで Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 0581834666476f2635785a48b189396c9240ac8f
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729387"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="1c5ca-103">Skype Room Systems バージョン 2 と Exchange Online を展開する</span><span class="sxs-lookup"><span data-stu-id="1c5ca-103">Deploy Skype Room Systems v2 with Exchange Online</span></span> 
 
<span data-ttu-id="1c5ca-104">ビジネス サーバー設置型の Exchange Online と Skype の Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="1c5ca-105">設置型およびいくつかのホストがオンラインでホストされているいくつかのさまざまなサービスがある場合は、各サービスがホストされているによって、構成が決まります。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="1c5ca-106">このトピックでは、オンラインでホストされている Exchange と Skype ルーム システム v2 のハイブリッド展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="1c5ca-107">この種類の展開で非常に多くのさまざまなバリエーションがあるため、それらのすべての詳細な説明を提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="1c5ca-108">以下、処理の多くの構成です。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-108">The following process will work for many configurations.</span></span> <span data-ttu-id="1c5ca-109">プロセスが、設定の適切でない場合は、ここでは、およびその他の展開オプションが記載されているように、同じ結果を達成するために Windows PowerShell を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> 

<span data-ttu-id="1c5ca-110">ユーザー アカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="1c5ca-111">マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または Skype ルーム システム v2 の互換性のあるユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="1c5ca-112">場合は、Skype ルーム システム v2 デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-112">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="1c5ca-113">Skype Room Systems バージョン 2 と Exchange Online を展開する</span><span class="sxs-lookup"><span data-stu-id="1c5ca-113">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="1c5ca-114">Exchange オンラインで Skype ルーム システム v2 を展開する前に、要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-114">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="1c5ca-115">詳細については、「[Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-115">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="1c5ca-116">Exchange オンラインで Skype ルーム システム v2 を展開するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-116">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="1c5ca-117">関連するコマンドレットを実行するために適切な権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="1c5ca-118">アカウントを作成して Exchange プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="1c5ca-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="1c5ca-119">PC 上でリモートの Windows PowerShell セッションを開始し、Exchange Online への接続を次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="1c5ca-120">セッションを確立するには後、するが新しいメールボックスを作成して、RoomMailboxAccount、として有効にか既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="1c5ca-121">これにより、Skype ルーム システム v2 を認証するためにアカウントが許可されます。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-121">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="1c5ca-122">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="1c5ca-122">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="1c5ca-123">: 新しいリソース メールボックスを作成する場合</span><span class="sxs-lookup"><span data-stu-id="1c5ca-123">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="1c5ca-124">会議エクスペリエンスを向上させるため、次のようにユーザー アカウントに Exchange のプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. <span data-ttu-id="1c5ca-125">Azure AD に接続して、アカウント設定をいくつか適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-125">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="1c5ca-126">次のコマンドレットを実行して接続することができます。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-126">You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="1c5ca-127">オンプレミスのドメイン アカウントに電子メール アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="1c5ca-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="1c5ca-128">**Active Directory ユーザーとコンピューターの AD**ツールで、フォルダーまたは Skype ルーム システムは、v2 のアカウントを作成するには [**新規**作成] をクリックし、**ユーザー**] をクリックし、組織の単位を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-128">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>
    
2. <span data-ttu-id="1c5ca-p107">前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>


3. <span data-ttu-id="1c5ca-p108">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c5ca-134">**パスワードを無期限にする**を選択することは、Skype ルーム システム v2 に Skype ビジネス サーバーのための必要条件です。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="1c5ca-135">ドメイン ルールによって無期限のパスワードが禁止される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="1c5ca-136">その場合は、Skype ルーム システム v2 のユーザー アカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-136">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
4. <span data-ttu-id="1c5ca-137">アカウントを作成するには、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-137">Click **Finish** to create the account.</span></span>
    
5. <span data-ttu-id="1c5ca-p110">アカウントを作成したら、ディレクトリの同期を実行します。それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-p110">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="1c5ca-140">Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1c5ca-140">Assign an Office 365 license</span></span>

1. <span data-ttu-id="1c5ca-141">ユーザー アカウントは、Exchange と Skype のビジネス サーバーが動作することを確認するのには有効な Office 365 ライセンスを所有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="1c5ca-142">ライセンスがあれば、利用場所を割り当てるユーザー アカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定です。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="1c5ca-143">次に、Get MsolAccountSku を使用して、Office 365 テナントの使用可能な Sku の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-143">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="1c5ca-p112">SKU のリストを取得したら、Set-MsolUserLicense コマンドレットを使用してライセンスを追加することができます。この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-p112">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="1c5ca-146">ビジネス サーバーの Skype でのユーザー アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-146">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="1c5ca-147">次のように PC からリモートの Windows PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-147">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="1c5ca-148">ビジネスのサーバーでは、Skype の Skype ルーム システム v2 アカウントを有効にするには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-148">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="1c5ca-149">ビジネス サーバーのユーザーがこのコマンドを使用して既存の Skype から値を取得するには、環境内の RegistrarPool パラメーターを使用するのにはどのような値がわからない場合</span><span class="sxs-lookup"><span data-stu-id="1c5ca-149">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="1c5ca-150">ビジネス サーバー ライセンス、Skype アカウントに割り当てる、Skype ルーム システム v2</span><span class="sxs-lookup"><span data-stu-id="1c5ca-150">Assign a Skype for Business Server license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="1c5ca-151">テナント管理者としてログイン、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-151">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="1c5ca-152">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-152">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="1c5ca-153">Skype ルーム システム v2 のアカウント] をクリックし、アカウント情報を編集するのには [ペン] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-153">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="1c5ca-154">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-154">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="1c5ca-155">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-155">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="1c5ca-156">Skype ルーム システム v2 でエンタープライズ VoIP を使用する場合は、計画の 3 ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-156">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="1c5ca-157">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-157">Click **Save**.</span></span>
    
<span data-ttu-id="1c5ca-158">検証、ビジネス クライアント用の Skype を使用してこのアカウントにログインできるように。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-158">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c5ca-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c5ca-159">See also</span></span>

[<span data-ttu-id="1c5ca-160">Skype ルーム システム v2 用のアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c5ca-160">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="1c5ca-161">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="1c5ca-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="1c5ca-162">Skype Room System バージョン 2 を展開する</span><span class="sxs-lookup"><span data-stu-id="1c5ca-162">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="1c5ca-163">Skype Room Systems バージョン 2 コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="1c5ca-163">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="1c5ca-164">Skype Room Systems バージョン 2 を管理する</span><span class="sxs-lookup"><span data-stu-id="1c5ca-164">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

