---
title: Skype for Business Online と Exchange server の統合
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: オンプレミスの Exchange と Skype for Business Online の間で OAuth 認証を構成すると、機能のサポートで説明されている Skype for Business と Exchange の統合機能が有効になります。
ms.openlocfilehash: 3c896e8b430276e5bb48bc425425292a382a1021
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244221"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="9234e-103">Skype for Business Online と Exchange Server の間で統合と OAuth を構成する</span><span class="sxs-lookup"><span data-stu-id="9234e-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="9234e-104">Exchange server と Skype for Business Online との統合を構成すると、[機能のサポート](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)で説明されている Skype for Business と Exchange の統合機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="9234e-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="9234e-105">このトピックは、Exchange Server 2013 から2019への統合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9234e-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9234e-106">事前に必要な知識</span><span class="sxs-lookup"><span data-stu-id="9234e-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9234e-107">このタスクを完了するまでの予想所要時間: 15 分</span><span class="sxs-lookup"><span data-stu-id="9234e-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="9234e-108">この手順を実行するには、アクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9234e-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="9234e-109">必要なアクセス許可を確認するには、「 [Exchange とシェルインフラストラクチャのアクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=746511)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9234e-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="9234e-110">このトピックの手順に適用される可能性があるショートカットキーの詳細については、「 [Exchange 管理センターのキーボードショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9234e-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="9234e-111">互換性の詳細については、「 [Skype For business と Office アプリの互換性](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9234e-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="9234e-112">Exchange Server と O365 の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="9234e-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="9234e-113">手順 1: Exchange Server と O365 の間の OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="9234e-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="9234e-114">次の記事の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9234e-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="9234e-115">Exchange と Exchange Online の組織間の OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="9234e-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="9234e-116">手順 2: Skype for Business Online パートナーアプリケーションの新しいメールユーザーアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="9234e-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="9234e-117">この手順は Exchange server で行います。</span><span class="sxs-lookup"><span data-stu-id="9234e-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="9234e-118">これによって、メール ユーザーを作成し、適切な管理役割の権限を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9234e-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="9234e-119">このアカウントは、次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="9234e-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="9234e-120">Exchange 組織の確認済みドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="9234e-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="9234e-121">このドメインは、オンプレミスの Exchange アカウントで使用されるプライマリ SMTP ドメインと同じドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9234e-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="9234e-122">このドメインは、次\<の手順で\> 、確認済みドメインとして参照されます。</span><span class="sxs-lookup"><span data-stu-id="9234e-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="9234e-123">また、ドメイン\<コントローラーの fqdn\>として domainコントローラ fqdn を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9234e-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="9234e-124">このコマンドによって、アドレス一覧で新しいメール ユーザーが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9234e-124">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="9234e-125">次の 2 つのコマンドでは、この新しいアカウントに UserApplication および ArchiveApplication の管理役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9234e-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="9234e-126">手順 3: Skype for Business Online のパートナーアプリケーションを作成して有効にする</span><span class="sxs-lookup"><span data-stu-id="9234e-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="9234e-127">新しいパートナー アプリケーションを作成し、先に作成したアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9234e-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="9234e-128">オンプレミスの Exchange 組織の Exchange PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9234e-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="9234e-129">手順 4: オンプレミスの認証証明書をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="9234e-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="9234e-130">PowerShell スクリプトを実行して、オンプレミスの認証証明書をエクスポートします。これは、次の手順で Skype for Business Online 組織にインポートします。</span><span class="sxs-lookup"><span data-stu-id="9234e-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="9234e-131">次のテキストを、たとえば ExportAuthCert.ps1 という名前の PowerShell スクリプト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="9234e-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

``` Powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

<span data-ttu-id="9234e-132">オンプレミスの Exchange 組織の Exchange PowerShell で、作成した PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="9234e-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="9234e-133">例: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="9234e-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="9234e-134">手順 6: Azure Active Directory ACS にオンプレミス認証証明書をアップロードする</span><span class="sxs-lookup"><span data-stu-id="9234e-134">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="9234e-135">次に、Windows PowerShell を使用して、先の手順でエクスポートしたオンプレミス認証証明書を Azure Active Directory アクセス制御サービス (ACS) にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9234e-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="9234e-136">このためには、Windows PowerShell コマンドレット用の Azure Active Directory モジュールが既にインストールされていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="9234e-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="9234e-137">インストールされていない場合は[https://aka.ms/aadposh](https://aka.ms/aadposh) 、「Azure Active Directory Module For Windows PowerShell をインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9234e-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="9234e-138">Windows PowerShell 用 Azure Active Directory モジュールのインストール後、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="9234e-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="9234e-p107">**Windows PowerShell 用 Azure Active Directory モジュール**のショートカットをクリックして、Azure AD コマンドレットがインストールされた Windows PowerShell ワークスペースを開きます。この手順のすべてのコマンドは、Azure Active Directory コンソール用 Windows PowerShell を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="9234e-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="9234e-141">たとえば、という名前の PowerShell スクリプトファイルに次のテキストを`UploadAuthCert.ps1`保存します。</span><span class="sxs-lookup"><span data-stu-id="9234e-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ``` Powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="9234e-142">先の手順で作成した PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="9234e-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="9234e-143">例えば：`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="9234e-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="9234e-p109">スクリプトの開始後、[資格情報] ダイアログ ボックスが表示されます。Microsoft Online Azure AD 組織のテナント管理者アカウントの資格情報を入力します。スクリプトを実行した後に、Azure AD セッションで Windows PowerShell を開いたままにします。次の手順では、これを使用して PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="9234e-p109">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-7-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="9234e-148">手順 7: 証明書が Skype for Business のサービスプリンシパルにアップロードされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9234e-148">Step 7: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="9234e-149">PowerShell で、Azure Active Directory が開かれ、認証されている場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9234e-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="9234e-150">ReturnKeyValues の入力を求められたら enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9234e-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="9234e-151">Exchange Oauth 証明書の開始日と終了日に一致する、[開始日] と [終了] のキーが表示されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9234e-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="9234e-152">成否を確認する</span><span class="sxs-lookup"><span data-stu-id="9234e-152">Verify your success</span></span>

<span data-ttu-id="9234e-153">機能の一部が正常に動作していることを確認して、構成が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9234e-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="9234e-154">ハイブリッド Exchange Server の構成を使用している組織内の Skype for Business ユーザーが、ボイスメールの応答メッセージを正常に変更できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9234e-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="9234e-155">[モバイルクライアントの会話履歴を確認する] が Outlook の [会話履歴] フォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9234e-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="9234e-156">[EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)を使用して、アーカイブされたチャットメッセージが [削除] フォルダー内のユーザーのオンプレミスのメールボックスに記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9234e-156">Confirm that archived chat messages are deposited in the user's on premise mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="9234e-157">または、トラフィックを確認します。</span><span class="sxs-lookup"><span data-stu-id="9234e-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="9234e-158">OAuth ハンドシェイクのトラフィックは、実際には非常に優れています (基本的な認証とは言えません)。特に、領域については、次のような発行者のトラフィックを表示することになります (例: 00000004-0000-0ff1-ce00-000000000000 @@ sign)。これは、渡されるトークンの中にあります。</span><span class="sxs-lookup"><span data-stu-id="9234e-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="9234e-159">OAuth のポイントであるユーザー名またはパスワードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9234e-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="9234e-160">ただし、"Office" の発行者が表示されます。この例では、「4」が Skype for Business であり、サブスクリプションの領域です。</span><span class="sxs-lookup"><span data-stu-id="9234e-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="9234e-161">OAuth を正常に使用していることを確認したい場合は、想定される内容と、トラフィックの外観を把握してください。</span><span class="sxs-lookup"><span data-stu-id="9234e-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="9234e-162">ここ[](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)では、 [Microsoft アプリケーションでの oauth トラフィックの](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)標準的な例を示します (この例では、更新トークンを使用していませんが、Fiddler の拡張機能を使って oauth JWT (JSON) を表示することができます)。Web Token)。</span><span class="sxs-lookup"><span data-stu-id="9234e-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="9234e-163">次に[1 つを設定する例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)を示しますが、この処理を実行する任意のネットワークトレースツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9234e-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9234e-164">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9234e-164">Related topics</span></span>

[<span data-ttu-id="9234e-165">Exchange と Exchange Online の組織間の OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="9234e-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
