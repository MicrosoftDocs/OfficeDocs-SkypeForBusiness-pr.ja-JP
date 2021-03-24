---
title: Skype for Business Online と Exchange サーバーの統合
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: オンプレミスの Exchange と Skype for Business Online の間で OAuth 認証を構成すると、「機能のサポート」で説明されている Skype for Business 機能と Exchange 統合機能が有効です。
ms.openlocfilehash: 342362926ad0af169acd6c9af4715008425e71c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109713"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="af143-103">Skype for Business Online と Skype の間の統合と OAuth を構成Exchange Server</span><span class="sxs-lookup"><span data-stu-id="af143-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="af143-104">Exchange サーバーと Skype for Business Online の統合を構成すると、「機能のサポート」で説明されている Skype for Business 機能と Exchange 統合機能 [が有効になります](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="af143-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="af143-105">このトピックは、2013 Exchange Server 2019 との統合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="af143-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="af143-106">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="af143-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="af143-107">このタスクの予想所要時間:15 分</span><span class="sxs-lookup"><span data-stu-id="af143-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="af143-108">この手順を実行する際は、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="af143-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="af143-109">必要なアクセス許可を確認するには、「Exchange インフラストラクチャとシェル インフラストラクチャのアクセス許可 [」トピックを参照](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) してください。</span><span class="sxs-lookup"><span data-stu-id="af143-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) topic.</span></span>

- <span data-ttu-id="af143-110">このトピックの手順で使用可能なキーボード ショートカットについては、「[Exchange 管理センターのキーボード ショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af143-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="af143-111">互換性の詳細については [、「Skype for Business とアプリとの互換性」をOfficeしてください](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)。</span><span class="sxs-lookup"><span data-stu-id="af143-111">For information about compatibility, see [Skype for Business compatibility with Office apps](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="af143-112">O365 と Exchange Serverの統合を構成する</span><span class="sxs-lookup"><span data-stu-id="af143-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="af143-113">手順 1: OAuth 認証を O365 Exchange Server構成する</span><span class="sxs-lookup"><span data-stu-id="af143-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="af143-114">次の記事の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af143-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="af143-115">Exchange と Exchange Online 組織の間の OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="af143-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="af143-116">手順 2: Skype for Business Online パートナー アプリケーション用の新しいメール ユーザー アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="af143-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="af143-117">この手順は、Exchange サーバーで行います。</span><span class="sxs-lookup"><span data-stu-id="af143-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="af143-118">メール ユーザーを作成し、適切な管理役割権限を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="af143-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="af143-119">このアカウントは、次の手順で使用されます。</span><span class="sxs-lookup"><span data-stu-id="af143-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="af143-120">Exchange 組織の検証済みドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="af143-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="af143-121">このドメインは、オンプレミスの Exchange アカウントで使用されるプライマリ SMTP ドメインと同じドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="af143-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="af143-122">このドメインは、次の \<your Verified Domain\> 手順で参照されます。</span><span class="sxs-lookup"><span data-stu-id="af143-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="af143-123">また、ドメイン \<DomainControllerFQDN\> コントローラーの FQDN である必要があります。</span><span class="sxs-lookup"><span data-stu-id="af143-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="af143-124">このコマンドは、新しいメール ユーザーをアドレス一覧から非表示にします。</span><span class="sxs-lookup"><span data-stu-id="af143-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="af143-125">次の 2 つのコマンドは、UserApplication および ArchiveApplication 管理役割をこの新しいアカウントに割り当てる予定です。</span><span class="sxs-lookup"><span data-stu-id="af143-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="af143-126">手順 3: Skype for Business Online のパートナー アプリケーションを作成して有効にする</span><span class="sxs-lookup"><span data-stu-id="af143-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="af143-127">新しいパートナー アプリケーションを作成し、作成したアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="af143-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="af143-128">社内 Exchange 組織の Exchange PowerShell で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af143-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="af143-129">手順 4: オンプレミス認証証明書をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="af143-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="af143-130">PowerShell スクリプトを実行して、次の手順で Skype for Business Online 組織にインポートするオンプレミス認証証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="af143-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="af143-131">次のテキストを、たとえば ExportAuthCert.ps1 という名前の PowerShell スクリプト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="af143-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```powershell
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

<span data-ttu-id="af143-132">オンプレミスの Exchange 組織の Exchange PowerShell で、作成した PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="af143-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="af143-133">たとえば、次の.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="af143-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="af143-134">手順 5: オンプレミスの承認証明書を Azure Active Directory ACS にアップロードする</span><span class="sxs-lookup"><span data-stu-id="af143-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="af143-135">次に、Windows PowerShellを使用して、前の手順でエクスポートしたオンプレミス認証証明書を Azure Active Directory Access Control Services (ACS) にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="af143-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="af143-136">これを行うには、Azure Active Directory Module for Windows PowerShellがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="af143-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="af143-137">インストールされていない場合、[https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) に移動して、Windows PowerShell の Azure Active Directory モジュール をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="af143-137">If it's not installed, go to [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="af143-138">Windows PowerShell の Azure Active Directory モジュール のインストール後、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af143-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="af143-p107">**[Windows PowerShell 用 Azure Active Directory モジュール]** ショートカットをクリックして、Azure AD コマンドレットがインストールされた Windows PowerShell ワークスペースを開きます。この手順のすべてのコマンドは、Azure Active Directory コンソール用の Windows PowerShell を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="af143-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="af143-141">次のテキストを、たとえばという名前の PowerShell スクリプト ファイルに保存します  `UploadAuthCert.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="af143-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```powershell
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

3. <span data-ttu-id="af143-142">直前の手順で作成した PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="af143-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="af143-143">例:  `.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="af143-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="af143-144">スクリプトを起動した後に、[資格情報] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af143-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="af143-145">Microsoft Online Azure 組織のテナント管理者アカウントの資格情報ADします。</span><span class="sxs-lookup"><span data-stu-id="af143-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="af143-146">スクリプトの実行後、Azure AD 用 Windows PowerShell セッションを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="af143-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="af143-147">これは、次のステップで PowerShell スクリプトを実行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="af143-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="af143-148">手順 6: 証明書が Skype for Business Service プリンシパルにアップロードされたのを確認する</span><span class="sxs-lookup"><span data-stu-id="af143-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="af143-149">Azure Active Directory で開いて認証された PowerShell で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af143-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="af143-150">ReturnKeyValues の入力を求めるメッセージが表示されたら、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="af143-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="af143-151">Exchange Oauth 証明書の開始日と終了日に一致する開始日と終了データが一覧表示されているキーが表示されるのを確認する</span><span class="sxs-lookup"><span data-stu-id="af143-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="af143-152">成功を確認する</span><span class="sxs-lookup"><span data-stu-id="af143-152">Verify your success</span></span>

<span data-ttu-id="af143-153">一部の機能が正常に動作していることを確認して、構成が正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="af143-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="af143-154">ハイブリッド ボイスメール構成を持つ組織のクラウド ボイスメール サービスを使用する Skype for Business ユーザー Exchange Serverボイスメール案内応答を正常に変更できます。</span><span class="sxs-lookup"><span data-stu-id="af143-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="af143-155">モバイル クライアントの会話履歴が Outlook の会話履歴フォルダーに表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="af143-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="af143-156">アーカイブされたチャット メッセージが [、EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor)を使用して Purges フォルダー内のユーザーのオンプレミス メールボックスに保存されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="af143-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).</span></span>

<span data-ttu-id="af143-157">または、トラフィックを確認します。</span><span class="sxs-lookup"><span data-stu-id="af143-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="af143-158">OAuth ハンドシェイクのトラフィックは、実際には特徴的です (基本認証とは見なしません)、特に領域の周りでは、次のような発行者トラフィックが表示されます。000000004-00000-0ff1-ce000-000000000@ (@記号の前に / がある場合があります)、渡されるトークンで。</span><span class="sxs-lookup"><span data-stu-id="af143-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="af143-159">OAuth のポイントであるユーザー名やパスワードは表示できません。</span><span class="sxs-lookup"><span data-stu-id="af143-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="af143-160">ただし、'Office' 発行者が表示されます 。この場合、'4' は Skype for Business であり、サブスクリプションの領域です。</span><span class="sxs-lookup"><span data-stu-id="af143-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="af143-161">OAuth が正常に使用されたことを確認する場合は、何を期待し、トラフィックの外観を知る必要があるかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="af143-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="af143-162">[ここでは、Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)アプリケーションの OAuth トラフィックの標準的な例を示します (更新トークンは使用しませんが、実際に読むのに役立ちます)、OAuth JWT (JSON Web トークン) を確認できる Fiddler 拡張機能があります。 [](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)</span><span class="sxs-lookup"><span data-stu-id="af143-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="af143-163">セットアップの例 [を次](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)に示しますが、このプロセスを実行するには、任意のネットワーク トレース ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af143-163">Here's an [example of setting one up](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af143-164">関連トピック</span><span class="sxs-lookup"><span data-stu-id="af143-164">Related topics</span></span>

[<span data-ttu-id="af143-165">Exchange と Exchange Online 組織の間の OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="af143-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)