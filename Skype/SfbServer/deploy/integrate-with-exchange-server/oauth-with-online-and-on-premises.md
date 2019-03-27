---
title: オンプレミスの Exchange と Skype for Business Online 間での OAuth の構成
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: OAuth を構成するオンライン ビジネスの社内の Exchange と Skype との間の認証は、ビジネスおよび Exchange の統合機能の機能のサポート」に記載の Skype を使用できます。
ms.openlocfilehash: 6fbf6944ec1b7518311d8d7a0bd75ef3249a0142
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876578"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a><span data-ttu-id="d50d1-103">オンプレミスの Exchange と Skype for Business Online 間での OAuth の構成</span><span class="sxs-lookup"><span data-stu-id="d50d1-103">Configure OAuth between Skype for Business Online and Exchange on premises</span></span>

<span data-ttu-id="d50d1-104">OAuth を構成するオンライン ビジネスの社内の Exchange と Skype との間の認証は、Skype の[機能のサポート](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)」で説明されているビジネスと Exchange の統合の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d50d1-104">Configuring OAuth authentication between Exchange on premises and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="d50d1-105">2016 の Exchange Server および Exchange Server 2013 に、このトピックに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d50d1-105">This topic applies to Exchange Server 2016 and Exchange Server 2013.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d50d1-106">事前に必要な知識</span><span class="sxs-lookup"><span data-stu-id="d50d1-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d50d1-107">このタスクを完了するまでの予想所要時間: 15 分</span><span class="sxs-lookup"><span data-stu-id="d50d1-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="d50d1-108">この手順を実行するには、アクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d50d1-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="d50d1-109">必要なアクセス許可を表示するには、 [Exchange およびシェル インフラストラクチャのアクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=746511)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d50d1-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="d50d1-110">このトピックの手順に適用されるキーボード ショートカットの詳細については、 [Exchange 管理センターでのキーボード ショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d50d1-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a><span data-ttu-id="d50d1-111">オンプレミスの Exchange と Skype for Business 組織の間で OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="d50d1-111">Configure OAuth authentication between your on-premises Exchange and Skype for Business organizations</span></span>

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a><span data-ttu-id="d50d1-112">手順 1:  Skype for Business Online 組織の承認サーバー オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="d50d1-112">Step 1: Create an authorization server object for your Skype for Business Online organization</span></span>

<span data-ttu-id="d50d1-113">オンライン ビジネスの組織は、Skype の検証済みのドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-113">Specify a verified domain for your Skype for Business Online organization.</span></span> <span data-ttu-id="d50d1-114">このドメインは、クラウド ベースのアカウントに使用したプライマリ SIP ドメインと同じドメインであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d50d1-114">This domain should be the same domain used as the primary SIP domain used for the cloud-based accounts.</span></span> <span data-ttu-id="d50d1-115">このドメインと呼ばれる\<、検証済みのドメイン\>、次の手順にします。</span><span class="sxs-lookup"><span data-stu-id="d50d1-115">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>

<span data-ttu-id="d50d1-116">設置型で、Exchange 管理シェル (Exchange の PowerShell) Exchange 組織で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-116">Run the following command in the Exchange Management Shell (the Exchange PowerShell) in your on-premises Exchange organization.</span></span>

```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1"
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a><span data-ttu-id="d50d1-117">手順 2:  Skype for Business Online 組織に対してパートナー アプリケーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="d50d1-117">Step 2: Enable the partner application for your Skype for Business Online organization</span></span>

<span data-ttu-id="d50d1-118">設置型で、Exchange の PowerShell Exchange 組織で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-118">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="d50d1-119">手順 3: Skype for Business Online のパートナー アプリケーションの新しいメール ユーザー アカウントを作成する </span><span class="sxs-lookup"><span data-stu-id="d50d1-119">Step 3: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="d50d1-p103">この手順は、オンプレミスで実行します。これによって、メール ユーザーを作成し、適切な管理役割の権限を割り当てます。このアカウントは、次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-p103">This step is done on-premises. It will create a mail user and assign it the appropriate management role rights. This account will then be used in the next step.</span></span>

<span data-ttu-id="d50d1-123">Exchange 組織用の検証済みのドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-123">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="d50d1-124">このドメインは、オンプレミスの Exchange アカウントを使用するプライマリ SMTP ドメインとして使用する同じドメインにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d50d1-124">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="d50d1-125">このドメインと呼ばれる\<、検証済みのドメイン\>、次の手順にします。</span><span class="sxs-lookup"><span data-stu-id="d50d1-125">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="d50d1-126">また、 \<DomainControllerFQDN\>ドメイン コント ローラーの FQDN である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d50d1-126">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="d50d1-127">このコマンドによって、アドレス一覧で新しいメール ユーザーが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="d50d1-127">This command will hide the new mail user from address lists.</span></span>

```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="d50d1-128">次の 2 つのコマンドでは、この新しいアカウントに UserApplication および ArchiveApplication の管理役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d50d1-128">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="d50d1-129">手順 4: Skype for Business Online のパートナー アプリケーションを作成して有効にする</span><span class="sxs-lookup"><span data-stu-id="d50d1-129">Step 4: Create and enable a Partner Application for Skype for Business Online</span></span>

<span data-ttu-id="d50d1-130">新しいパートナー アプリケーションを作成し、先に作成したアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-130">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="d50d1-131">設置型で、Exchange の PowerShell Exchange 組織で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-131">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="d50d1-132">手順 5: オンプレミスの認証証明書をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d50d1-132">Step 5: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="d50d1-133">設置承認証明書をエクスポート、インポート、次の手順でオンライン ビジネスの組織は、Skype をする PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-133">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="d50d1-134">次のテキストを、たとえば ExportAuthCert.ps1 という名前の PowerShell スクリプト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-134">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```
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

<span data-ttu-id="d50d1-135">Exchange、オンプレミスの Exchange 組織内の PowerShell では、作成した PowerShell のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-135">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="d50d1-136">例:.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="d50d1-136">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="d50d1-137">手順 6: Azure Active Directory ACS にオンプレミス認証証明書をアップロードする</span><span class="sxs-lookup"><span data-stu-id="d50d1-137">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="d50d1-138">次に、Windows PowerShell を使用して、先の手順でエクスポートしたオンプレミス認証証明書を Azure Active Directory アクセス制御サービス (ACS) にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d50d1-138">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="d50d1-139">このためには、Windows PowerShell コマンドレット用の Azure Active Directory モジュールが既にインストールされていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d50d1-139">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="d50d1-140">インストールされていない場合に、 [https://aka.ms/aadposh](https://aka.ms/aadposh) 、Azure Active Directory モジュールを Windows PowerShell をインストールするのには。</span><span class="sxs-lookup"><span data-stu-id="d50d1-140">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="d50d1-141">Windows PowerShell 用 Azure Active Directory モジュールのインストール後、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-141">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="d50d1-p108">**Windows PowerShell 用 Azure Active Directory モジュール**のショートカットをクリックして、Azure AD コマンドレットがインストールされた Windows PowerShell ワークスペースを開きます。この手順のすべてのコマンドは、Azure Active Directory コンソール用 Windows PowerShell を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-p108">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="d50d1-144">たとえば、PowerShell スクリプト ファイルに次のテキストを保存`UploadAuthCert.ps1`。</span><span class="sxs-lookup"><span data-stu-id="d50d1-144">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```
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

3. <span data-ttu-id="d50d1-145">先の手順で作成した PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-145">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="d50d1-146">例えば：`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="d50d1-146">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="d50d1-p110">スクリプトの開始後、[資格情報] ダイアログ ボックスが表示されます。Microsoft Online Azure AD 組織のテナント管理者アカウントの資格情報を入力します。スクリプトを実行した後に、Azure AD セッションで Windows PowerShell を開いたままにします。次の手順では、これを使用して PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-p110">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a><span data-ttu-id="d50d1-151">手順 7: SMTP ドメインに対するホスト名の機関を登録する</span><span class="sxs-lookup"><span data-stu-id="d50d1-151">Step 7: Register the hostname authorities for the SMTP domain</span></span>

<span data-ttu-id="d50d1-152">Exchange 組織用の検証済みのドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-152">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="d50d1-153">このドメインは、オンプレミスの Exchange アカウントを使用するプライマリ SMTP ドメインとして使用する同じドメインにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d50d1-153">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="d50d1-154">このドメインと呼ばれる\<、検証済みのドメイン\>、次の手順にします。</span><span class="sxs-lookup"><span data-stu-id="d50d1-154">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="d50d1-155">次のスクリプトを正常に実行するには、先のセクションの手順 4 で説明したように、Azure Active Directory 用 Windows PowerShell を Microsoft Online Azure AD テナントに接続することが必要です。</span><span class="sxs-lookup"><span data-stu-id="d50d1-155">Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.</span></span>

1. <span data-ttu-id="d50d1-156">次のテキストを、たとえば RegisterEndpoints.ps1 という名前の PowerShell スクリプト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-156">Save the following text to a PowerShell script file named, for example, RegisterEndpoints.ps1.</span></span> <span data-ttu-id="d50d1-157">この例では、contoso.com のすべてのエンドポイントを登録するためにワイルドカードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d50d1-157">This example uses a wildcard to register all endpoints for contoso.com.</span></span> <span data-ttu-id="d50d1-158">交換<your Verified Domain>では、オンプレミスの Exchange サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="d50d1-158">Replace <your Verified Domain> with a the FQDN for your on-premises Exchange server.</span></span>

   ```
   $externalAuthority="*.<your Verified Domain>"
   $ServiceName = "00000002-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName;
   $spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority);
   $p.ServicePrincipalNames.Add($spn);
   Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames;
   ```

2. <span data-ttu-id="d50d1-159">Azure Active Directory 用 Windows PowerShell で、先の手順で作成した Windows PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-159">In Windows PowerShell for Azure Active Directory, run the Windows PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="d50d1-160">例えば：`.\RegisterEndpoints.ps1`</span><span class="sxs-lookup"><span data-stu-id="d50d1-160">For example: `.\RegisterEndpoints.ps1`</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="d50d1-161">成否を確認する</span><span class="sxs-lookup"><span data-stu-id="d50d1-161">Verify your success</span></span>

<span data-ttu-id="d50d1-162">Outlook の [会話履歴] フォルダーにモバイル クライアントの会話履歴が表示されるかなど、いくつかの機能が正常に動作するかどうかを調べ、OAuth 構成が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-162">Verify that the OAuth configuration is correct by verifying some of the features are working successfully, such as having conversation history for mobile clients visible in the Outlook Conversation History folder.</span></span>

1. <span data-ttu-id="d50d1-163">Windows Phone または iOS デバイスのモバイル アプリケーションのビジネス用の Skype を起動し、Exchange 2016 またはオンプレミスのメールボックスを Exchange 2013 を使用してオンライン ビジネスのユーザーは、Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d50d1-163">Start the Skype for Business mobile app on your Windows Phone or iOS device and sign in as a Skype for Business Online user with an Exchange 2016 or Exchange 2013 on-premises mailbox.</span></span>

2. <span data-ttu-id="d50d1-164">オンライン ビジネスのユーザーに別の Skype のインスタント メッセージ会話があります。</span><span class="sxs-lookup"><span data-stu-id="d50d1-164">Have an instant messaging conversation with another Skype for Business Online user.</span></span>

3. <span data-ttu-id="d50d1-165">[IM 会話] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d50d1-165">Close the IM conversation window.</span></span>

4. <span data-ttu-id="d50d1-166">このユーザーに対して Outlook を起動し、Outlook の [会話履歴] フォルダーに会話が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-166">Start Outlook for this user and verify that the conversation is visible in the Outlook Conversation history folder.</span></span>

<span data-ttu-id="d50d1-167">代わりに、トラフィックを見てください。</span><span class="sxs-lookup"><span data-stu-id="d50d1-167">Alternately, look at your traffic.</span></span> <span data-ttu-id="d50d1-168">OAuth のハンド シェークのトラフィックが非常に特徴的な (そして基本認証と同様に表示されない)、特に領域、どこを開始するために次のような発行元のトラフィックを参照してください: @ 00000004-0000-0ff1-ce00-000000000000 (こともありますが、前@ 記号)、渡されるトークンです。</span><span class="sxs-lookup"><span data-stu-id="d50d1-168">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="d50d1-169">ユーザー名またはパスワード、OAuth のポイントは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d50d1-169">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="d50d1-170">ですが、'Office' の発行元が表示されます – ここでは「4」業務と、サブスクリプション レルムの Skype。</span><span class="sxs-lookup"><span data-stu-id="d50d1-170">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="d50d1-171">場合は必ず正常に OAuth を使用している、確認しておきます内容を予測して、どのようなトラフィックのようになります知っています。</span><span class="sxs-lookup"><span data-stu-id="d50d1-171">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="d50d1-172">[予想される結果を次のとおりです](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)が、ここでは、ごく標準的な[Microsoft アプリケーションで、OAuth トラフィックの例](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)(読み取り、更新トークンを使用しないが非常に役立ちます)、あり、Fiddler の拡張機能に、OAuth JWT (JSON を表示できるようになります。Web トークン)。</span><span class="sxs-lookup"><span data-stu-id="d50d1-172">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="d50d1-173">[を設定するには 1 つの例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)を次のとおりですが、このプロセスに着手するときに任意のネットワーク トレース ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d50d1-173">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d50d1-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="d50d1-174">Related topics</span></span>

[<span data-ttu-id="d50d1-175">Exchange および Exchange Online 組織間の OAuth 認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="d50d1-175">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
