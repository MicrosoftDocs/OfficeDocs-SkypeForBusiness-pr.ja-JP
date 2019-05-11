---
title: Skype ビジネス オンラインと Exchange サーバーの間の統合
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: OAuth を構成するオンライン ビジネスの社内の Exchange と Skype との間の認証は、ビジネスおよび Exchange の統合機能の機能のサポート」に記載の Skype を使用できます。
ms.openlocfilehash: c6a3819c9ec6ae0c207307a23f67bf04e4f07ac0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894240"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="9ac3c-103">オンライン ビジネス用の Skype またはマイクロソフトのチームと Exchange Server との統合を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="9ac3c-104">ビジネス オンラインの Exchange サーバーと Skype との間の統合を構成すると、Skype の[機能のサポート](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)」で説明されているビジネスと Exchange の統合の機能が有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="9ac3c-105">2019 を介して Exchange Server 2013 との統合をこのトピックに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9ac3c-106">事前に必要な知識</span><span class="sxs-lookup"><span data-stu-id="9ac3c-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9ac3c-107">このタスクを完了するまでの予想所要時間: 15 分</span><span class="sxs-lookup"><span data-stu-id="9ac3c-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="9ac3c-108">この手順を実行するには、アクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="9ac3c-109">必要なアクセス許可を表示するには、 [Exchange およびシェル インフラストラクチャのアクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=746511)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="9ac3c-110">このトピックの手順に適用されるキーボード ショートカットの詳細については、 [Exchange 管理センターでのキーボード ショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="9ac3c-111">Exchange Server および O365 間の統合を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="9ac3c-112">手順 1: Exchange Server および O365 間 OAuth 認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="9ac3c-113">次の資料の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="9ac3c-114">Exchange および Exchange Online 組織間の OAuth 認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="9ac3c-115">手順 2: Skype のオンライン ビジネスやチームのパートナー アプリケーションの新しいメール ユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="9ac3c-116">この手順は、Exchange サーバー上で行われます。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="9ac3c-117">これによって、メール ユーザーを作成し、適切な管理役割の権限を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="9ac3c-118">このアカウントは、次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="9ac3c-119">Exchange 組織用の検証済みのドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="9ac3c-120">このドメインは、オンプレミスの Exchange アカウントを使用するプライマリ SMTP ドメインとして使用する同じドメインにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="9ac3c-121">このドメインと呼ばれる\<、検証済みのドメイン\>、次の手順にします。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="9ac3c-122">また、 \<DomainControllerFQDN\>ドメイン コント ローラーの FQDN である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="9ac3c-123">このコマンドによって、アドレス一覧で新しいメール ユーザーが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="9ac3c-124">次の 2 つのコマンドでは、この新しいアカウントに UserApplication および ArchiveApplication の管理役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="9ac3c-125">手順 3: を作成し、ビジネスをオンラインまたはチームの Skype のパートナーのアプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="9ac3c-126">新しいパートナー アプリケーションを作成し、先に作成したアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="9ac3c-127">設置型で、Exchange の PowerShell Exchange 組織で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="9ac3c-128">成否を確認する</span><span class="sxs-lookup"><span data-stu-id="9ac3c-128">Verify your success</span></span>

<span data-ttu-id="9ac3c-129">正常に作業している機能のいくつかを確認し、構成が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="9ac3c-130">Outlook の予定表委任 2016 の Exchange Server とメールボックスの 2019 2 チームのユーザーを指定の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="9ac3c-131">モバイル クライアントの会話の履歴は、Outlook の会話履歴フォルダーに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="9ac3c-132">代わりに、トラフィックを見てください。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="9ac3c-133">OAuth のハンド シェークのトラフィックが非常に特徴的な (そして基本認証と同様に表示されない)、特に領域、どこを開始するために次のような発行元のトラフィックを参照してください: @ 00000004-0000-0ff1-ce00-000000000000 (こともありますが、前@ 記号)、渡されるトークンです。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="9ac3c-134">ユーザー名またはパスワード、OAuth のポイントは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="9ac3c-135">ですが、'Office' の発行元が表示されます – ここでは「4」業務と、サブスクリプション レルムの Skype。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="9ac3c-136">場合は必ず正常に OAuth を使用している、確認しておきます内容を予測して、どのようなトラフィックのようになります知っています。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="9ac3c-137">[予想される結果を次のとおりです](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)が、ここでは、ごく標準的な[Microsoft アプリケーションで、OAuth トラフィックの例](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)(読み取り、更新トークンを使用しないが非常に役立ちます)、あり、Fiddler の拡張機能に、OAuth JWT (JSON を表示できるようになります。Web トークン)。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="9ac3c-138">[を設定するには 1 つの例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)を次のとおりですが、このプロセスに着手するときに任意のネットワーク トレース ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9ac3c-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9ac3c-139">Related topics</span></span>

[<span data-ttu-id="9ac3c-140">Exchange および Exchange Online 組織間の OAuth 認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ac3c-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
