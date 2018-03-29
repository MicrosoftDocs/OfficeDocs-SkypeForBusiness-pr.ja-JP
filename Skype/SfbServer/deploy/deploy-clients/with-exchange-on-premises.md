---
title: 'Skype Room Systems バージョン 2 と Exchange On-Premises を展開する (ハイブリッド) '
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: 社内の Exchange とのハイブリッド環境で Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a><span data-ttu-id="491af-103">Skype Room Systems バージョン 2 と Exchange On-Premises を展開する (ハイブリッド) </span><span class="sxs-lookup"><span data-stu-id="491af-103">Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)</span></span>
 
<span data-ttu-id="491af-104">社内の Exchange とのハイブリッド環境で Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="491af-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises.</span></span>
  
<span data-ttu-id="491af-105">設置型およびいくつかのホストがオンラインでホストされているいくつかのさまざまなサービスがある場合は、各サービスがホストされているによって、構成が決まります。</span><span class="sxs-lookup"><span data-stu-id="491af-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="491af-106">このトピックでは、社内設置型でホストされている Exchange と Skype ルーム システム v2 のハイブリッド展開を説明します。</span><span class="sxs-lookup"><span data-stu-id="491af-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="491af-107">この種類の展開で非常に多くのさまざまなバリエーションがあるため、それらのすべての詳細な説明を提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="491af-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="491af-108">以下、処理の多くの構成です。</span><span class="sxs-lookup"><span data-stu-id="491af-108">The following process will work for many configurations.</span></span> <span data-ttu-id="491af-109">プロセスが、設定の適切でない場合は、ここでは、およびその他の展開オプションが記載されているように、同じ結果を達成するために Windows PowerShell を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="491af-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="491af-110">提供されている Windows PowerShell スクリプトを使用して、Skype ルーム システム v2 のセットアップを確認します。</span><span class="sxs-lookup"><span data-stu-id="491af-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="491af-111">(詳しくは、アカウントの確認スクリプトを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="491af-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="491af-112">Skype Room Systems バージョン 2 と Exchange On-Premises を展開する</span><span class="sxs-lookup"><span data-stu-id="491af-112">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="491af-113">社内の Exchange と Skype ルーム システム v2 を展開する前に、要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="491af-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="491af-114">詳細については、 [Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="491af-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="491af-115">社内の Exchange と Skype ルーム システム v2 を展開する場合、オンプレミス ドメイン アカウントの電子メール アドレスを追加するのには Active Directory 管理ツールを使用するは。</span><span class="sxs-lookup"><span data-stu-id="491af-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="491af-116">このアカウントを Office 365 に同期されます。</span><span class="sxs-lookup"><span data-stu-id="491af-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="491af-117">次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-117">You will need to:</span></span>
  
- <span data-ttu-id="491af-118">アカウントを作成してアカウントを Active Directory と同期する。</span><span class="sxs-lookup"><span data-stu-id="491af-118">Create an account and synchronize the account with Active Directory.</span></span>
    
- <span data-ttu-id="491af-119">リモート メールボックスを有効にしてプロパティを設定する。</span><span class="sxs-lookup"><span data-stu-id="491af-119">Enable the remote mailbox and set properties.</span></span>
    
- <span data-ttu-id="491af-120">Office 365 のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="491af-120">Assign an Office 365 license.</span></span>
    
- <span data-ttu-id="491af-121">ビジネス サーバーでは、Skype でデバイスのアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="491af-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="491af-122">デバイス アカウントを有効にするには、お使いの環境が次の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>
    
  - <span data-ttu-id="491af-123">Office 365 プランに Skype ビジネス online (プラン 2) またはそれ以上にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="491af-124">このプランでは会議機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-124">The plan needs to support conferencing capability.</span></span>
    
  - <span data-ttu-id="491af-125">エンタープライズ VoIP (PSTN テレフォニー) が必要な場合 Skype ルーム システム v2 のテレフォニー サービス プロバイダーを使用する必要があります Skype ビジネス online (プラン 3)。</span><span class="sxs-lookup"><span data-stu-id="491af-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
  - <span data-ttu-id="491af-126">テナント ユーザーは、Exchange のメールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="491af-126">Your tenant users must have Exchange mailboxes.</span></span>
    
  - <span data-ttu-id="491af-127">Skype ルーム システム v2 アカウントが必要ですがビジネス オンライン (プラン 2) の Skype または Skype ビジネス オンライン (プラン 3) のライセンスが、Exchange のオンライン ・ ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="491af-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
- <span data-ttu-id="491af-128">Skype ルーム システム v2 アカウントに、Skype ビジネス サーバー ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="491af-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="491af-129">アカウントを作成して Active Directory と同期する</span><span class="sxs-lookup"><span data-stu-id="491af-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="491af-130">**Active Directory ユーザーとコンピューターの AD**ツールで、フォルダーまたは Skype ルーム システムは、v2 のアカウントを作成するには [**新規**作成] をクリックし、**ユーザー**] をクリックし、組織の単位を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="491af-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>
    
2. <span data-ttu-id="491af-p106">前のコマンドレットで得た表示名を [**フル ネーム**] ボックスに入力し、エイリアスを [**ユーザー ログオン名**] ボックスに入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="491af-p106">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
    
3. <span data-ttu-id="491af-p107">このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="491af-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="491af-136">**パスワードを無期限にする**を選択することは、Skype ルーム システム v2 に Skype ビジネス サーバーのための必要条件です。</span><span class="sxs-lookup"><span data-stu-id="491af-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="491af-137">ドメイン ルールによって無期限のパスワードが禁止される場合があります。</span><span class="sxs-lookup"><span data-stu-id="491af-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="491af-138">その場合は、Skype ルーム システム v2 デバイスのアカウントごとに例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="491af-139">アカウントを作成したら、ディレクトリの同期を実行します。</span><span class="sxs-lookup"><span data-stu-id="491af-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="491af-140">それが完了すると、Office 365 の管理センターで [ユーザー] ページに移動しを前の手順で作成したアカウントは、マージ オンラインことを確認します。</span><span class="sxs-lookup"><span data-stu-id="491af-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="491af-141">リモート メールボックスを有効にしてプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="491af-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="491af-142">管理者権限を持つ、オンプレミスの Exchange 管理シェルを開いて、リモートのメールボックスを有効にし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="491af-142">Enable the remote mailbox by opening your on-premises Exchange management shell with administrator permissions and run the following command:</span></span>
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. <span data-ttu-id="491af-143">リモートの Windows PowerShell セッションを開始し、Microsoft Exchange に接続します。</span><span class="sxs-lookup"><span data-stu-id="491af-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span></span> <span data-ttu-id="491af-144">Office 365 のテナントには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="491af-144">From your Office 365 tenant, run the following commands:</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. <span data-ttu-id="491af-145">会議エクスペリエンスを高めるためには、デバイスのアカウントに Exchange のプロパティを次のように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-145">To improve the meeting experience, you'll need to set the Exchange properties on the device account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    <span data-ttu-id="491af-146">プロパティの詳細については、Exchange のプロパティを参照してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-146">For more information about which properties you need to set, see Exchange properties.</span></span>
    
4. <span data-ttu-id="491af-147">Azure AD に接続して、アカウント設定をいくつか適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-147">You will need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="491af-148">次のコマンドを実行して接続することができます。</span><span class="sxs-lookup"><span data-stu-id="491af-148">You can run this command to connect:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a><span data-ttu-id="491af-149">Office 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="491af-149">Assign an Office 365 license</span></span>

1. <span data-ttu-id="491af-150">デバイスのアカウントは、Exchange と Skype のビジネス サーバーが動作することを確認するのには有効な Office 365 ライセンスを所有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="491af-151">ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。</span><span class="sxs-lookup"><span data-stu-id="491af-151">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="491af-152">次に、Get MsolAccountSku を使用して、Office 365 テナントの使用可能な Sku の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="491af-152">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="491af-p113">SKU のリストを取得したら、Set-MsolUserLicense コマンドレットを使用してライセンスを追加することができます。この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="491af-p113">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="491af-155">Skype for Business でデバイス アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="491af-155">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="491af-156">次のように PC からリモートの Windows PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="491af-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="491af-157">ビジネスのサーバーでは、Skype の Skype ルーム システム v2 アカウントを有効にするには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="491af-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="491af-158">ビジネス サーバーのユーザーがこのコマンドを使用して既存の Skype から値を取得するには、環境内の RegistrarPool パラメーターを使用するのにはどのような値がわからない場合</span><span class="sxs-lookup"><span data-stu-id="491af-158">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="491af-159">Skype for Business のライセンスを Skype Room Systems バージョン 2 アカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="491af-159">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="491af-160">テナント管理者としてログイン、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。</span><span class="sxs-lookup"><span data-stu-id="491af-160">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="491af-161">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="491af-161">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="491af-162">Skype ルーム システム v2 のアカウント] をクリックし、アカウント情報を編集するのには [ペン] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="491af-162">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="491af-163">[**ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="491af-163">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="491af-164">ライセンスとエンタープライズ VoIP の要件に応じて、[**ライセンスの割り当て**] で [Skype for Business (プラン 2)] または [
Skype for Business (プラン 3)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="491af-164">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="491af-165">Skype ルーム システム v2 でエンタープライズ VoIP を使用する場合は、計画の 3 ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="491af-165">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="491af-166">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="491af-166">Click **Save**.</span></span>
    
<span data-ttu-id="491af-167">検証、ビジネス クライアント用の Skype を使用してこのアカウントにログインできるように。</span><span class="sxs-lookup"><span data-stu-id="491af-167">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="491af-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="491af-168">See also</span></span>

#### 

[<span data-ttu-id="491af-169">Skype ルームの計画システム v2</span><span class="sxs-lookup"><span data-stu-id="491af-169">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="491af-170">Skype の部屋を配置するシステム v2</span><span class="sxs-lookup"><span data-stu-id="491af-170">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="491af-171">Skype ルーム システム v2 のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="491af-171">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="491af-172">Skype ルームの管理システム v2</span><span class="sxs-lookup"><span data-stu-id="491af-172">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

