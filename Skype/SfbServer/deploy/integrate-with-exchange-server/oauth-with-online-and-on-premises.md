---
title: Skype for Business Online と Exchange server の統合
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: オンプレミスの Exchange と Skype for Business Online の間で OAuth 認証を構成すると、機能のサポートで説明されている Skype for Business と Exchange の統合機能が有効になります。
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278127"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="f2544-103">Skype for Business Online または Microsoft Teams と Exchange Server との統合を構成する</span><span class="sxs-lookup"><span data-stu-id="f2544-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="f2544-104">Exchange server と Skype for Business Online との統合を構成すると、[機能のサポート](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)で説明されている Skype for Business と Exchange の統合機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2544-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="f2544-105">このトピックは、Exchange Server 2013 から2019への統合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2544-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f2544-106">事前に必要な知識</span><span class="sxs-lookup"><span data-stu-id="f2544-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f2544-107">このタスクを完了するまでの予想所要時間: 15 分</span><span class="sxs-lookup"><span data-stu-id="f2544-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="f2544-108">この手順を実行するには、アクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2544-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="f2544-109">必要なアクセス許可を確認するには、「 [Exchange とシェルインフラストラクチャのアクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=746511)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2544-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="f2544-110">このトピックの手順に適用される可能性があるショートカットキーの詳細については、「 [Exchange 管理センターのキーボードショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2544-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="f2544-111">Exchange Server と O365 の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="f2544-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="f2544-112">手順 1: Exchange Server と O365 の間の OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="f2544-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="f2544-113">次の記事の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f2544-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="f2544-114">Exchange と Exchange Online の組織間の OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="f2544-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="f2544-115">手順 2: Skype for Business Online または Teams パートナーアプリケーションの新しいメールユーザーアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="f2544-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="f2544-116">この手順は Exchange server で行います。</span><span class="sxs-lookup"><span data-stu-id="f2544-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="f2544-117">これによって、メール ユーザーを作成し、適切な管理役割の権限を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f2544-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="f2544-118">このアカウントは、次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="f2544-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="f2544-119">Exchange 組織の確認済みドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2544-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="f2544-120">このドメインは、オンプレミスの Exchange アカウントで使用されるプライマリ SMTP ドメインと同じドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2544-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="f2544-121">このドメインは、次\<の手順で\> 、確認済みドメインとして参照されます。</span><span class="sxs-lookup"><span data-stu-id="f2544-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="f2544-122">また、ドメイン\<コントローラーの fqdn\>として domainコントローラ fqdn を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2544-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="f2544-123">このコマンドによって、アドレス一覧で新しいメール ユーザーが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="f2544-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="f2544-124">次の 2 つのコマンドでは、この新しいアカウントに UserApplication および ArchiveApplication の管理役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f2544-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="f2544-125">手順 3: Skype for Business Online または Teams のパートナーアプリケーションを作成して有効にする</span><span class="sxs-lookup"><span data-stu-id="f2544-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="f2544-126">新しいパートナー アプリケーションを作成し、先に作成したアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2544-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="f2544-127">オンプレミスの Exchange 組織の Exchange PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2544-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="f2544-128">成否を確認する</span><span class="sxs-lookup"><span data-stu-id="f2544-128">Verify your success</span></span>

<span data-ttu-id="f2544-129">機能の一部が正常に動作していることを確認して、構成が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2544-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="f2544-130">Outlook の予定表の委任の確認 Exchange Server 2016 または2019メールボックスを使用している2つの Teams ユーザーの間で動作します。</span><span class="sxs-lookup"><span data-stu-id="f2544-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="f2544-131">[モバイルクライアントの会話履歴を確認する] が Outlook の [会話履歴] フォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2544-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="f2544-132">または、トラフィックを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2544-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="f2544-133">OAuth ハンドシェイクのトラフィックは、実際には非常に優れています (基本的な認証とは言えません)。特に、領域については、次のような発行者のトラフィックを表示することになります (例: 00000004-0000-0ff1-ce00-000000000000 @@ sign)。これは、渡されるトークンの中にあります。</span><span class="sxs-lookup"><span data-stu-id="f2544-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="f2544-134">OAuth のポイントであるユーザー名またはパスワードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f2544-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="f2544-135">ただし、"Office" の発行者が表示されます。この例では、「4」が Skype for Business であり、サブスクリプションの領域です。</span><span class="sxs-lookup"><span data-stu-id="f2544-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="f2544-136">OAuth を正常に使用していることを確認したい場合は、想定される内容と、トラフィックの外観を把握してください。</span><span class="sxs-lookup"><span data-stu-id="f2544-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="f2544-137">ここ[](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)では、 [Microsoft アプリケーションでの oauth トラフィックの](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)標準的な例を示します (この例では、更新トークンを使用していませんが、Fiddler の拡張機能を使って oauth JWT (JSON) を表示することができます)。Web Token)。</span><span class="sxs-lookup"><span data-stu-id="f2544-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="f2544-138">次に[1 つを設定する例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)を示しますが、この処理を実行する任意のネットワークトレースツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2544-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2544-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f2544-139">Related topics</span></span>

[<span data-ttu-id="f2544-140">Exchange と Exchange Online の組織間の OAuth 認証を構成する</span><span class="sxs-lookup"><span data-stu-id="f2544-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
