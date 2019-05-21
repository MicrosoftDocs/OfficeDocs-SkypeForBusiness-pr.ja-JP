---
title: Skype for Business Server に Skype の接続を展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '概要: skype for Business Server を Skype コンシューマーと接続する方法について説明します。 これは、Skype 接続とも呼ばれます。'
ms.openlocfilehash: 1f03b873299828dedf6c0ffca113d60d277bf65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302832"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a><span data-ttu-id="69eba-104">Skype for Business Server に Skype の接続を展開する</span><span class="sxs-lookup"><span data-stu-id="69eba-104">Deploy Skype Connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="69eba-105">**概要:** Skype for business Server を Skype コンシューマーに接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="69eba-105">**Summary:** Learn how to connect Skype for Business Server with Skype consumer.</span></span> <span data-ttu-id="69eba-106">これは、Skype 接続とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="69eba-106">Also known as Skype connectivity.</span></span>
  
<span data-ttu-id="69eba-107">ここでは、Skype Connectivity の展開について順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="69eba-107">This article walks through deployment for Skype Connectivity.</span></span>
  
## <a name="skype-connectivity-overview-for-it-professionals"></a><span data-ttu-id="69eba-108">Skype Connectivity の概要 (IT 担当者向け)</span><span class="sxs-lookup"><span data-stu-id="69eba-108">Skype Connectivity Overview for IT Professionals</span></span>

<span data-ttu-id="69eba-109">Skype 接続を使うと、skype for Business ユーザーが Skype ユーザーを検索して追加することができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-109">Skype Connectivity provides Skype for Business users with the ability to search for and add Skype users.</span></span> <span data-ttu-id="69eba-110">Skype 接続は skype for Business の機能で、Skype ユーザとのフェデレーションおよびディレクトリ検索を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-110">Skype Connectivity is a feature of Skype for Business that lets you enable federation and directory search with Skype users.</span></span> <span data-ttu-id="69eba-111">Skype の接続を有効にすると、skype for Business ユーザーは skype ユーザを検索して追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="69eba-111">After you enable Skype Connectivity your Skype for Business users will be able to search for and add Skype users.</span></span>
  
## <a name="skype-directory-search"></a><span data-ttu-id="69eba-112">Skype Directory Search</span><span class="sxs-lookup"><span data-stu-id="69eba-112">Skype Directory Search</span></span>

<span data-ttu-id="69eba-p104">Skype Directory Search 機能によって、Skype for Business ユーザーは、Skype の連絡先を検索できます。検索機能により、ユーザーは以下の手段を使用して検索を実行できます。</span><span class="sxs-lookup"><span data-stu-id="69eba-p104">Skype Directory Search functionality provides Skype for Business users with the ability to search for Skype contacts. The search functionality lets users search using the following:</span></span>
  
- <span data-ttu-id="69eba-115">**表示名、"John Doe" の例で検索**すると、多くの結果が返される可能性があるため、探している情報が見つからないことがあります。</span><span class="sxs-lookup"><span data-stu-id="69eba-115">**Search by display name, example "John Doe"** - This could return many results, so you might not find what you are looking for.</span></span>
    
- <span data-ttu-id="69eba-116">**表示名と場所を指定して検索します。たとえば、"John Doe In スペインバルセロナ"** のように指定します。これにより、検索結果を大幅に絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-116">**Search by display name plus location, example "John Doe in Barcelona"** - This will narrow the results of the search down considerably.</span></span>
    
- <span data-ttu-id="69eba-117">**メールで検索して、"johndoe@outlook.com"** のようにします。ほとんどの場合、これは1つの結果を返します。指定したメールと完全に一致するもの。</span><span class="sxs-lookup"><span data-stu-id="69eba-117">**Search by email, example "johndoe@outlook.com"** - This should return one result in most cases; the one that matches the specified email exactly.</span></span> <span data-ttu-id="69eba-118">ただし、同じメールが複数のアカウントに関連付けられている場合は、複数の結果が返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="69eba-118">But if the same email is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="69eba-119">**電話番号で検索します。 "123-123-1234"** のようにします。ほとんどの場合、これは1つの結果を返します。指定した電話と正確に一致するもの。</span><span class="sxs-lookup"><span data-stu-id="69eba-119">**Search by phone number, example "123-123-1234"** - This should return one result in most cases; the one that matches the specified phone exactly.</span></span> <span data-ttu-id="69eba-120">電話番号には国コードを含める必要があります (例: xxx-yyy-zzzz)。</span><span class="sxs-lookup"><span data-stu-id="69eba-120">Phone number must include the country code (i.e. 1-xxx-yyy-zzzz).</span></span> <span data-ttu-id="69eba-121">同じ電話番号が複数のアカウントに関連付けられている場合は、複数の結果が返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="69eba-121">If the same phone number is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="69eba-122">**Skype 名で検索します。 "JohnDoe1456"** のように指定します。完全一致が見つかった場合は、最初の結果として返されます。</span><span class="sxs-lookup"><span data-stu-id="69eba-122">**Search by Skype Name, example "JohnDoe1456"** - If exact match is found, it will be returned as the first result.</span></span> <span data-ttu-id="69eba-123">その他の可能性のある "名前" の一致は、返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-123">Other possible "name" matches may be returned.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="69eba-124">Skype Directory Search では、ポート 443 で IP アドレス 104.40.75.246、23.101.135.34、40.113.86.19 と通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-124">Skype Directory Search must be able to communicate with the following IP addresses on port 443: 104.40.75.246, 23.101.135.34, and 40.113.86.19.</span></span> 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a><span data-ttu-id="69eba-125">Skype Directory Search のサポートされる展開のマトリックス</span><span class="sxs-lookup"><span data-stu-id="69eba-125">Supported deployment matrix for Skype Directory Search</span></span>

<span data-ttu-id="69eba-126">以下の表に、Skype Directory Search のサポートの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="69eba-126">The following table outlines support for Skype Directory Search.</span></span>
  

||<span data-ttu-id="69eba-127">**Skype for Business Server のフロントエンド**</span><span class="sxs-lookup"><span data-stu-id="69eba-127">**Skype for Business Server Front End**</span></span>|<span data-ttu-id="69eba-128">**Lync Server 2013 (またはそれ以降の) フロントエンド**</span><span class="sxs-lookup"><span data-stu-id="69eba-128">**Lync Server 2013 (or older) Front End**</span></span>|<span data-ttu-id="69eba-129">**コメント**</span><span class="sxs-lookup"><span data-stu-id="69eba-129">**Comments**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69eba-130">Skype for Business Server Edge</span><span class="sxs-lookup"><span data-stu-id="69eba-130">Skype for Business Server Edge</span></span>  <br/> |<span data-ttu-id="69eba-131">サポート対象</span><span class="sxs-lookup"><span data-stu-id="69eba-131">Supported</span></span>  <br/> |<span data-ttu-id="69eba-132">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="69eba-132">Not Supported</span></span>  <br/> |<span data-ttu-id="69eba-133">Skype for Business Server と Edge は Skype ディレクトリ検索の前提条件です</span><span class="sxs-lookup"><span data-stu-id="69eba-133">Skype for Business Server and Edge are prerequisites for Skype Directory Search</span></span>  <br/> |
|<span data-ttu-id="69eba-134">Skype for Business Server Edge + Lync Server 2013 Edge が並列で展開されている</span><span class="sxs-lookup"><span data-stu-id="69eba-134">Skype for Business Server Edge + Lync Server 2013 Edge deployed side-by-side</span></span>  <br/> |<span data-ttu-id="69eba-135">サポート対象</span><span class="sxs-lookup"><span data-stu-id="69eba-135">Supported</span></span>  <br/> |<span data-ttu-id="69eba-136">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="69eba-136">Not Supported</span></span>  <br/> |<span data-ttu-id="69eba-p108">Skype Directory Search のトラフィックは Skype for Business Server エッジ サーバーを通過します。フェデレーション トラフィックは、管理者により構成されたエッジを通過します。たとえば、管理者は、Skype Directory Search をサポートしない Lync Server 2013 エッジ サーバーを介してフェデレーション トラフィックを引き続き送信することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="69eba-p108">Skype Directory Search traffic flows through Skype for Business Server Edge servers. Federation traffic goes through edge configured by the administrator. For example, the administrator could choose to continue to send federation traffic through Lync Server 2013 Edge servers which would not support Skype Directory Search.</span></span>  <br/> |
|<span data-ttu-id="69eba-140">Lync Server 2013 (またはそれ以降の) エッジ</span><span class="sxs-lookup"><span data-stu-id="69eba-140">Lync Server 2013 (or older) Edge</span></span>  <br/> |<span data-ttu-id="69eba-141">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="69eba-141">Not Supported</span></span>  <br/> |<span data-ttu-id="69eba-142">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="69eba-142">Not Supported</span></span>  <br/> ||
   
> [!NOTE]
> <span data-ttu-id="69eba-143">Skype for Business Server のフロントエンドで実行されている電話帳サービスは、エッジサーバーの Skype 検索ポート4443の存在によってエッジを検索します。</span><span class="sxs-lookup"><span data-stu-id="69eba-143">Addressbook service running on Skype for Business Server Front End finds the Edge by the existence of the Skype Search port 4443 in the Edge server.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="69eba-144">顧客がオンプレミスの展開に複数のサイトを持っていて、1つの Skype for Business Server Edge サーバー/プールのみを展開している場合、すべてのサイトからのトラフィックの検索は、利用可能な1つのエッジサーバーを経由します。</span><span class="sxs-lookup"><span data-stu-id="69eba-144">In case a customer has multiple sites in their on-premises deployment, and if they have deployed just one Skype for Business Server Edge server/pool, then Search traffic from all sites will go through the single available Edge server.</span></span> <span data-ttu-id="69eba-145">管理者は、展開された Skype for Business Server Edge サーバー/プールに、すべてのサイトのプールがアクセスできることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-145">The administrator needs to make sure the pools from all sites can access the deployed Skype for Business Server Edge server/pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="69eba-146">Skype グラフ サービスは、要求レートが 15 要求/秒を超えた場合、すべてのオンプレミスまたは Office 365 カスタマーからの検索要求を調整します。</span><span class="sxs-lookup"><span data-stu-id="69eba-146">Skype graph service will throttle search requests from any on-premises or Office 365 customer if the request rate exceeds 15 requests / second.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="69eba-147">大規模エンタープライズ オンプレミス カスタマーに対しては、より高い要求レートを許可するために、ドメインを Skype 検索サービスのホワイトリストに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-147">For large enterprise on-premises customers, the domains will need to be whitelisted with the Skype search service to allow higher request rates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="69eba-148">キューに保留中の要求が多すぎると、Skype for Business Server によって着信要求が抑制されます。</span><span class="sxs-lookup"><span data-stu-id="69eba-148">Skype for Business Server will throttle incoming requests, if there are too many pending requests in the queue.</span></span> 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a><span data-ttu-id="69eba-149">Office 365 での Skype for Business Server Online 用の Skype Connectivity の展開</span><span class="sxs-lookup"><span data-stu-id="69eba-149">Deploying Skype Connectivity for Skype for Business Online in Office 365</span></span>

<span data-ttu-id="69eba-p110">Skype Connectivity は、Office 365 の一部である Skype for Business Online の機能でもあります。Office 365 ポータル内の Skype for Business 管理センターから、Skype Connectivity 機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-p110">Skype Connectivity is also a feature of Skype for Business Online, which is part of Office 365. You can enable the Skype Connectivity feature from the Skype for Business Administration Center within the Office 365 portal.</span></span>
  
<span data-ttu-id="69eba-152">Office 365 中堅企業向け、Office 365 Enterprise、Office 365 エデュケーション、office 365 for Government: Office 365 ポータルにサインインして、Skype for Business 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="69eba-152">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Office 365 portal and navigate to the Skype for Business Administration Center.</span></span> <span data-ttu-id="69eba-153">外部通信に移動します。</span><span class="sxs-lookup"><span data-stu-id="69eba-153">Go to External Communications.</span></span> <span data-ttu-id="69eba-154">[パブリック IM サービスプロバイダー] で [有効にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69eba-154">Under Public IM Service Providers, click Enable.</span></span> <span data-ttu-id="69eba-155">個人ユーザの Skype 接続へのアクセスを制御するには、個々のユーザの外部通信設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="69eba-155">If you want to control individual user access to Skype Connectivity, you can do so by editing individual users' External Communications settings.</span></span>
  
<span data-ttu-id="69eba-156">Office 365 Small Business Premium の場合: Office 365 にサインインし、[管理者\>サービスの\>設定] で [インスタントメッセージング、会議、会議] に移動します。</span><span class="sxs-lookup"><span data-stu-id="69eba-156">For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Settings \> Instant messaging, meetings and conferencing.</span></span> <span data-ttu-id="69eba-157">外部通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="69eba-157">Turn on External communications.</span></span> <span data-ttu-id="69eba-158">[外部通信] スイッチは、skype for Business を使用する他の組織との Skype 接続と通信の両方を有効にします。</span><span class="sxs-lookup"><span data-stu-id="69eba-158">The External communications switch turns on both Skype Connectivity and communications with other organizations that use Skype for Business.</span></span>
  
<span data-ttu-id="69eba-159">Skype for Business Online の管理の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69eba-159">For more information about Skype for Business Online administration, see:</span></span>
  
- [<span data-ttu-id="69eba-160">ユーザーが外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="69eba-160">Allow users to contact external Skype for Business users</span></span>](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [<span data-ttu-id="69eba-161">Skype for Business または Skype の外部連絡先に IM できない場合の対応策</span><span class="sxs-lookup"><span data-stu-id="69eba-161">What to try if you can't IM Skype for Business or Skype external contacts</span></span>](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [<span data-ttu-id="69eba-162">Skype for Business で連絡先を追加する</span><span class="sxs-lookup"><span data-stu-id="69eba-162">Add a contact in Skype for Business</span></span>](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [<span data-ttu-id="69eba-163">管理者: 個別のユーザーの Skype for Business の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="69eba-163">Admins: Configure Skype for Business settings for individual users</span></span>](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a><span data-ttu-id="69eba-164">Skype for Business Server 向けの Skype 接続の展開</span><span class="sxs-lookup"><span data-stu-id="69eba-164">Deploying Skype Connectivity for Skype for Business Server</span></span>

<span data-ttu-id="69eba-165">Skype for Business Server は、フェデレーションアクセスアーキテクチャを使用して、Skype との接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="69eba-165">Skype for Business Server uses the federation access architecture to support connectivity with Skype.</span></span> <span data-ttu-id="69eba-166">この接続によって、Skype for Business Server ユーザーは Skype を追加できます。</span><span class="sxs-lookup"><span data-stu-id="69eba-166">This connectivity enables your Skype for Business Server users to add Skype.</span></span> <span data-ttu-id="69eba-167">Skype クライアントは、Skype for Business ユーザをコンタクトリストに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="69eba-167">Skype clients can also add Skype for Business users to their contact list.</span></span> <span data-ttu-id="69eba-168">Skype for Business Server ユーザーは、管理者が設定したポリシーに基づいて、インスタントメッセージを使ってコミュニケーションを行い、互いのプレゼンスを確認して、音声通話とビデオ通話を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-168">Based on policies administratively set in Skype for Business Server users will be able to communicate using instant messaging, see each other's presence, and initiate audio and video calls.</span></span> <span data-ttu-id="69eba-169">Skype 接続は、skype for Business Online の機能でもあり、Office 365 ポータル内の Skype for Business 管理センターから Skype for business Online のお客様に対して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-169">Skype connectivity is also a feature of Skype for Business Online, and can be enabled for Skype for Business Online customers from the Skype for Business Administration Center within the Office 365 portal.</span></span>
  
> [!NOTE]
> <span data-ttu-id="69eba-p114">Skype for Business Server がパブリック インスタント メッセージング接続 (PIC) を使用して Windows Messenger と接続するように既に構成されている場合、展開は、既に Skype Connectivity 用に構成されています。検討が必要と思われるのは、既存の Messenger PIC エントリの名前を Skype などに変更することだけです。</span><span class="sxs-lookup"><span data-stu-id="69eba-p114">If Skype for Business Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> 
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server"></a><span data-ttu-id="69eba-172">Skype for business server のパブリック IM 接続プロビジョニングサイトへのアクセス</span><span class="sxs-lookup"><span data-stu-id="69eba-172">Accessing the Skype for Business Server public IM connectivity provisioning site from Skype for Business Server</span></span>

<span data-ttu-id="69eba-p115">このプロビジョニング プロセスは、完了するまで最長で 30 日かかる可能性がありますが、要求量によっては数日のみで完了することもあります。Microsoft は、このドキュメントの残りの手順を完了する前に、このプロセスを先に開始することをお勧めします。Skype のプロビジョニング プロセスが完了した後、アカウントがアクティブになり、適格なユーザーのパブリック IM 接続が有効になります。</span><span class="sxs-lookup"><span data-stu-id="69eba-p115">This provisioning process can take up to thirty days to complete but may take only a few days depending on the volume of requests. We recommend that you start this process first, prior to completing the remaining steps in this document. After the Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span> 
  
<span data-ttu-id="69eba-176">Skype Connectivity をプロビジョニングするには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="69eba-176">To provision Skype connectivity, you need the following information:</span></span>
  
- <span data-ttu-id="69eba-177">Microsoft 契約番号</span><span class="sxs-lookup"><span data-stu-id="69eba-177">Microsoft Agreement Number</span></span>
    
- <span data-ttu-id="69eba-178">アクセス エッジ サービスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="69eba-178">Access Edge service fully qualified domain name (FQDN)</span></span>
    
- <span data-ttu-id="69eba-179">セッション開始プロトコル (SIP) のドメイン</span><span class="sxs-lookup"><span data-stu-id="69eba-179">Session Initiation Protocol (SIP) domain(s)</span></span>
    
- <span data-ttu-id="69eba-180">追加のアクセス エッジ サービスの FQDN</span><span class="sxs-lookup"><span data-stu-id="69eba-180">Any additional Access Edge service FQDNs</span></span>
    
- <span data-ttu-id="69eba-181">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="69eba-181">Contact information</span></span>
    
<span data-ttu-id="69eba-182">Skype Connectivity のプロビジョニング プロセスを開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="69eba-182">To initiate the provisioning process for Skype Connectivity:</span></span>
  
1. <span data-ttu-id="69eba-183">Microsoft Windows Live ID を使用https://pic.lync.comして、web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="69eba-183">Sign in to the website, https://pic.lync.com, using your Microsoft Windows Live ID.</span></span>
    
2. <span data-ttu-id="69eba-184">Microsoft ライセンスの契約の種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="69eba-184">Select the Microsoft licensing agreement type.</span></span>
    
3. <span data-ttu-id="69eba-185">チェック ボックスをオンにし、Skype for Business Server の製品使用権の内容を読んで同意したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="69eba-185">Select the check box, verifying that you have read and accept the Product Use Rights for Skype for Business Server.</span></span>
    
4. <span data-ttu-id="69eba-186">プロビジョニング要求を開始するためのページで、適切なリンクをクリックしてプロビジョニング要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="69eba-186">On the Initiate a Provisioning Request page, click the appropriate link to initiate a provisioning request:</span></span>
    
5. <span data-ttu-id="69eba-187">プロビジョニング情報を指定するためのページで、アクセス エッジ サービスの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="69eba-187">On the Specify Provisioning Information page, enter the Access Edge service FQDN.</span></span> <span data-ttu-id="69eba-188">たとえば、sip.contoso.com と入力します。</span><span class="sxs-lookup"><span data-stu-id="69eba-188">For example, sip.contoso.com.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69eba-189">2017 年 7 月 1 日以降マイクロソフトは、パブリック インスタント メッセージの接続を機能し続けるために、お客様側でのフェデレーション DNS SRV レコードの展開を追加の必須要件とします。</span><span class="sxs-lookup"><span data-stu-id="69eba-189">After July 1st 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span> 
  
6. <span data-ttu-id="69eba-190">少なくとも 1 つの SIP ドメイン名を入力し、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69eba-190">Enter at least one or more SIP domain names, and then click Add.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="69eba-p117">プロビジョニング プロセスを完了するには、少なくとも 1 つのアクセス エッジ サーバーが必要です。1 つのアクセス エッジ FQDN で複数の SIP ドメインをサポートできますが、複数のアクセス エッジ FQDN で 1 つの SIP ドメインを表現することはできません。SIP ドメインとアクセス エッジ サーバーは、アクティブで、正常に機能し、ネットワーク上で到達可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-p117">At least one Access Edge server is required to complete the provisioning process. While a single Access Edge FQDN can support multiple SIP domains, a single SIP domain cannot be represented by more than one Access Edge FQDN. The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span> 
  
7. <span data-ttu-id="69eba-194">[パブリック IM サービス プロバイダー] の一覧で [Skype] を選び、[次へ] をクリックして連絡先情報を追加し、プロビジョニング要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="69eba-194">In the list of Public IM Service providers, select Skype, and click Next to add contact information, and submit the provisioning request.</span></span>
    
<span data-ttu-id="69eba-195">プロビジョニング要求が送信された後、アカウントをアクティブにして、ユーザーを Skype Connectivity で有効にするには、最長 30 日かかる可能性があります。ただし、キューによっては数日のみで済むこともあります。</span><span class="sxs-lookup"><span data-stu-id="69eba-195">After the provisioning request has been submitted, it can take up to 30 days, but may take only a few days depending on queue, for the account to activate and for users to be enabled for Skype Connectivity.</span></span>
  
### <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="69eba-196">フェデレーションとパブリック IM 接続 (PIC) の有効化</span><span class="sxs-lookup"><span data-stu-id="69eba-196">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="69eba-p118">プロビジョニング要求を送信した後は、Skype Connectivity を構成するために必要な、Skype for Business Server の環境と管理タスクに重点を移すことができます。このセクションでは、管理者は Skype for Business Server を展開し、外部アクセス (エッジ サーバーとも呼ばれます) を構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="69eba-p118">After you have submitted the provisioning request, you can focus on the Skype for Business Server environment and administrative tasks required to configure Skype Connectivity. In this section, we assume that the administrator has deployed Skype for Business Server and configured external access, also known as Edge servers.</span></span> 
  
<span data-ttu-id="69eba-p119">フェデレーションと PIC を有効にするために必要な主な 3 つのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="69eba-p119">There are three primary steps required to enable federation and PIC. These are:</span></span>
  
1. <span data-ttu-id="69eba-201">フェデレーションと PIC を構成する</span><span class="sxs-lookup"><span data-stu-id="69eba-201">Configure Federation and PIC</span></span>
    
2. <span data-ttu-id="69eba-202">フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="69eba-202">Configure at least one policy to support federated user access</span></span>
    
3. <span data-ttu-id="69eba-203">Skype PIC プロバイダー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="69eba-203">Configure the Skype PIC provider setting</span></span>
    
#### <a name="1-configure-federation-and-pic"></a><span data-ttu-id="69eba-204">1. フェデレーションと PIC を構成する</span><span class="sxs-lookup"><span data-stu-id="69eba-204">1. Configure Federation and PIC</span></span>

<span data-ttu-id="69eba-p120">フェデレーションは、Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Skype for Business ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、Skype for Business Server コントロール パネルを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="69eba-p120">Federation is required to enable Skype users to communicate with Skype for Business users in your organization. Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business users to communicate with Skype users. Federation and PIC are configured by using the Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="69eba-208">PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="69eba-208">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="69eba-209">PIC フェデレーションでサポートされているプラットフォームには、Skype for Business Server、Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2 があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-209">The supported platforms for PIC federation include Skype for Business Server, Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="69eba-p122">フェデレーションは、Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Skype for Business ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、次に示すように Skype for Business Server コントロール パネルの [エッジ構成] ダイアログを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="69eba-p122">Federation is required to enable Skype users to communicate with Skype for Business users in your organization. Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business Server users to communicate with Skype users. Federation and PIC are configured by using the Edge configuration dialog of the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![新しいエッジ プールの定義](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> <span data-ttu-id="69eba-214">検索を使用するには、パブリック プロバイダーの設定 (後の手順を参照) で EnableSkypeIdRouting 属性と EnableSkypeDirectorySearch 属性を True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-214">EnableSkypeIdRouting and EnableSkypeDirectorySearch attributes need to be set to true in the public provider settings (see later instructions) for Search to work.</span></span> 
  
<span data-ttu-id="69eba-p123">これで、サーバー上で実行する必要がある管理タスクが完了し、Skype Connectivity を使用するように設定されました。</span><span class="sxs-lookup"><span data-stu-id="69eba-p123">This completes the administrative tasks that must be performed on the server. You are now set up for Skype Connectivity.</span></span>
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="69eba-217">2. フェデレーションされたユーザーアクセスをサポートするように、少なくとも1つのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="69eba-217">2. Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="69eba-218">管理者は Skype for Business Server コントロール パネルを使用して外部ユーザー アクセス ポリシーを 1 つ以上構成し、Skype ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-218">Using the Skype for Business Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Skype for Business Server users.</span></span>
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a><span data-ttu-id="69eba-219">3. Skype PIC プロバイダ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="69eba-219">3. Configure the Skype PIC provider setting</span></span>

<span data-ttu-id="69eba-220">管理者は Skype for Business Server 管理シェルを使用して Skype for Business クライアント ポリシーを構成し、Skype を追加の PIC プロバイダーとして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-220">Using the Skype for Business Server Management Shell, an administrator must configure the Skype for Business client policy to display Skype as an additional PIC provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="69eba-221">パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために、少なくとも1つのポリシー (この手順では、前の手順 2) を構成するまで、組織内の IM または会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="69eba-221">Users of the Public Instant Messaging Connectivity (PIC) service providers can't participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span> 
  
<span data-ttu-id="69eba-222">新規インストールの場合は、図に示すように Skype for Business Server コントロール パネルを使用して Skype パブリック プロバイダーを有効にすることで、Skype Connectivity を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-222">For new installations you can configure Skype Connectivity by enabling a Skype Public Provider using the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![SIP フェデレーション プロバイダー](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> <span data-ttu-id="69eba-224">Skype for Business Server にアップグレードする場合に Skype Connectivity を構成するには、既存の Skype パブリック プロバイダーを削除してから再度追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-224">To configure Skype Connectivity when upgrading to Skype for Business Server you must remove and re-add the existing Skype public provider.</span></span> 
  
<span data-ttu-id="69eba-p124">Skype Connectivity の構成は、PowerShell のみを使用して行うこともできます。PowerShell を使用して Skype Connectivity を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="69eba-p124">Configuring Skype Connectivity can also be done using only PowerShell. To configure Skype Connectivity using PowerShell:</span></span>
  
1. <span data-ttu-id="69eba-227">Skype for Business Server フロントエンド サーバーから、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="69eba-227">From a Skype for Business Server Front End Server, open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="69eba-228">次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="69eba-228">Run the following two commands:</span></span>
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > <span data-ttu-id="69eba-229">環境にまだ PIC プロバイダーがなく、新しい PIC プロバイダーを作成している場合は、Remove-CsPublicProvider コマンドレットを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69eba-229">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the Remove-CsPublicProvider cmdlet.</span></span> 
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    <span data-ttu-id="69eba-230">意味がわかりにくいパラメーターの動作</span><span class="sxs-lookup"><span data-stu-id="69eba-230">What do the less obvious parameters do?</span></span>
    
   - <span data-ttu-id="69eba-231">ProxyFqdn:  (Microsoft により所有/維持管理される) Skype フェデレーション エッジの場所</span><span class="sxs-lookup"><span data-stu-id="69eba-231">ProxyFqdn: location of Skype federation edge (owned/maintained by Microsoft)</span></span>
    
   - <span data-ttu-id="69eba-232">IconURL: Lync &amp; Skype for business クライアントが skype の連絡先を視覚的に識別するために使用するアイコン</span><span class="sxs-lookup"><span data-stu-id="69eba-232">IconURL: icon used by Lync &amp; Skype for Business client to visually identify Skype contacts</span></span>
    
   - <span data-ttu-id="69eba-233">NameDecorationRoutingDomain と NameDecorationExcludedDomainList: setting を設定すると、ユーザーは "msn.com" で、Microsoft 以外のドメインを "装飾" していることを知らなくても、Skype ユーザーの MSAs を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-233">NameDecorationRoutingDomain and NameDecorationExcludedDomainList: setting these allows users to enter Skype users' MSAs without needing to know about "decorating" non-Microsoft domains with "msn.com".</span></span> <span data-ttu-id="69eba-234">これにより、ExcludedDomainList にないすべてのドメインに対して「user (contoso) @msn」と入力する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="69eba-234">This eliminates the need to type "user(contoso.com)@msn.com" for all domains that are NOT in the ExcludedDomainList.</span></span> <span data-ttu-id="69eba-235">ドメインが除外リストに存在しない場合、SfB クライアントは自動的に MSA を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="69eba-235">The SfB client will automatically format the MSA if the domain is NOT in the Excluded list.</span></span> <span data-ttu-id="69eba-236">最も一般的な Microsoft アカウントドメインを除外リストに追加しました。</span><span class="sxs-lookup"><span data-stu-id="69eba-236">We've added the most common Microsoft Account domains to the excluded list.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="69eba-237">変更が行われた場合は、パブリック プロバイダーを削除して新しく追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eba-237">Public Provider must be removed and added new if changes are made.</span></span> <span data-ttu-id="69eba-238">インプレースでの変更は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="69eba-238">No in-place changes are allowed.</span></span> 
  
     > [!NOTE]
     > <span data-ttu-id="69eba-239">Lync Server 2013 CU5 以降&amp; lync デスクトップクライアントに OFFICE 2013 SP1 で追加されました。 lync ユーザーが Skype の連絡先を追加して、Microsoft 以外のドメインを「修飾」することができるようになりました。 NameDecorationRoutingDomain と NameDecorationExcludedDomainListSkype (: user (contoso) @msn の形式) を特定して、ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="69eba-239">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to "decorate" non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="69eba-240">これらの新しい設定では、NameDecorationRoutingDomain (NameDecorationExcludedDomainList のドメインが含まれていない場合は、「Skype コンタクトを追加」ダイアログボックスで、「Skype コンタクトを追加」ダイアログボックスで、「msn.com」に設定する必要があります)。現時点では、msn.com、live.com、Hotmail.com、outlook.com) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="69eba-240">These new settings will allow automatic formatting of the address user's enter in the "Add Skype contact" dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span> 
  
3. <span data-ttu-id="69eba-241">Skype for Business クライアントから、ユーザーは Skype ユーザーを検索および追加することができます。</span><span class="sxs-lookup"><span data-stu-id="69eba-241">From a Skype for Business client users can now search for and add a Skype user.</span></span>
    
## <a name="clients-and-interoperability-matrix"></a><span data-ttu-id="69eba-242">クライアントと相互運用性のマトリックス</span><span class="sxs-lookup"><span data-stu-id="69eba-242">Clients and Interoperability Matrix</span></span>

<span data-ttu-id="69eba-243">次の表に、コンシューマー向け Skype の最新バージョンと Skype for Business の最新バージョンとの相互運用性のステータスを示します。</span><span class="sxs-lookup"><span data-stu-id="69eba-243">The following table outlines the status of interop between the latest version of Skype consumer and the latest version of Skype for Business.</span></span>
  

|<span data-ttu-id="69eba-244">**Skype クライアント**</span><span class="sxs-lookup"><span data-stu-id="69eba-244">**Skype Clients**</span></span>|<span data-ttu-id="69eba-245">**連絡先の追加、IM、プレゼンス、音声、ビデオ通話**</span><span class="sxs-lookup"><span data-stu-id="69eba-245">**Add contacts, IM, presence, audio, and video calling**</span></span>|<span data-ttu-id="69eba-246">**コメント**</span><span class="sxs-lookup"><span data-stu-id="69eba-246">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69eba-247">Skype Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="69eba-247">Skype Windows Desktop</span></span>  <br/> |<span data-ttu-id="69eba-248">7.6 以降、Windows XP 以降</span><span class="sxs-lookup"><span data-stu-id="69eba-248">7.6 or higher, Windows XP and higher</span></span>  <br/> |<span data-ttu-id="69eba-249">**新**機能: windows XP および windows Vista で実行されている windows Skype クライアント用のサポートが追加されました **(最新のクライアントバージョン7.26 以上が必要です)** 。</span><span class="sxs-lookup"><span data-stu-id="69eba-249">**NEW**: Support added for Windows Skype client running on Windows XP, and Windows Vista **(requires latest client version 7.26 or higher)**</span></span> <br/> |
|<span data-ttu-id="69eba-250">Skype Mobile - Android 携帯電話およびタブレット </span><span class="sxs-lookup"><span data-stu-id="69eba-250">Skype Mobile - Android Phone and Tablet</span></span>  <br/> |<span data-ttu-id="69eba-251">6.19 以降、Android OS バージョン 4.0.3 以降を実行</span><span class="sxs-lookup"><span data-stu-id="69eba-251">6.19 or higher, running Android OS version 4.0.3 or higher</span></span>  <br/> |<span data-ttu-id="69eba-252">性能の高くない機種ではビデオ通話がサポートされない場合あり</span><span class="sxs-lookup"><span data-stu-id="69eba-252">Low spec devices may not support video calling</span></span>  <br/> |
|<span data-ttu-id="69eba-253">Skype Mobile-iOS</span><span class="sxs-lookup"><span data-stu-id="69eba-253">Skype Mobile - iOS</span></span>  <br/> |<span data-ttu-id="69eba-254">6.11 以降、IOS 7 以降</span><span class="sxs-lookup"><span data-stu-id="69eba-254">6.11 or higher, on IOS 7 or higher</span></span>  <br/> |<span data-ttu-id="69eba-255">iPhone 4 以前、iPod 第 4 世代以前、iPad 第 1 世代はサポート外</span><span class="sxs-lookup"><span data-stu-id="69eba-255">Not supported are iPhone 4 and earlier, iPod 4th generation and earlier, iPad 1st generation</span></span>  <br/> |
|<span data-ttu-id="69eba-256">Skype Mac</span><span class="sxs-lookup"><span data-stu-id="69eba-256">Skype Mac</span></span>  <br/> |<span data-ttu-id="69eba-257">7.19 以降、Mac OS X 10.9 (Mavericks) 以降</span><span class="sxs-lookup"><span data-stu-id="69eba-257">7.19 or higher, on Mac OS X 10.9 (Mavericks) or higher</span></span>  <br/> |<span data-ttu-id="69eba-258">Mac OS X 10.9 以降</span><span class="sxs-lookup"><span data-stu-id="69eba-258">Requires Mac OSX 10.9 or higher</span></span>  <br/> |
|<span data-ttu-id="69eba-259">Skype Universal Windows アプリ (Windows 10) デスクトップおよびモバイル</span><span class="sxs-lookup"><span data-stu-id="69eba-259">Skype Universal Windows App (Windows 10) Desktop and Mobile</span></span>  <br/> |<span data-ttu-id="69eba-260">Windows 10 (Redstone 1 更新プログラム以降)</span><span class="sxs-lookup"><span data-stu-id="69eba-260">Windows 10 (Redstone 1 update or later)</span></span>  <br/> |<span data-ttu-id="69eba-261">Windows Universal App には 2016 年秋にアップデートが配信され、相互運用性のサポートが追加される予定</span><span class="sxs-lookup"><span data-stu-id="69eba-261">Windows Universal App will receive update in Fall 2016 adding interop support</span></span>  <br/> |
   
<span data-ttu-id="69eba-262">次の表に、Skype for Business の最新バージョンとコンシューマー向け Skype の最新バージョンとの相互運用性のステータスを示します。</span><span class="sxs-lookup"><span data-stu-id="69eba-262">The following table outlines the status of interop between the latest version of Skype for Business and the latest version of Skype consumer.</span></span> 
  
|<span data-ttu-id="69eba-263">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="69eba-263">**Client**</span></span>|<span data-ttu-id="69eba-264">**Skype Directory Search と、連絡先の追加**</span><span class="sxs-lookup"><span data-stu-id="69eba-264">**Skype Directory Search and Add Contacts**</span></span>|<span data-ttu-id="69eba-265">**Skype A/V、IM の相互運用性**</span><span class="sxs-lookup"><span data-stu-id="69eba-265">**Skype A/V, IM interop**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69eba-266">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="69eba-266">Skype for Business</span></span>  <br/> |<span data-ttu-id="69eba-267">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-267">Yes</span></span>  <br/> |<span data-ttu-id="69eba-268">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-268">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-269">Mac 版 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="69eba-269">Skype for Business on Mac</span></span>  <br/> |<span data-ttu-id="69eba-270">追加可能 (検索不可)</span><span class="sxs-lookup"><span data-stu-id="69eba-270">Can add (no search)</span></span>  <br/> |<span data-ttu-id="69eba-271">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-271">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-272">Lync Desktop 2013</span><span class="sxs-lookup"><span data-stu-id="69eba-272">Lync Desktop 2013</span></span>  <br/> |<span data-ttu-id="69eba-273">追加可能 (検索不可)</span><span class="sxs-lookup"><span data-stu-id="69eba-273">Can add (no search)</span></span>  <br/> |<span data-ttu-id="69eba-274">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-274">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-275">Lync Web App - オンラインとオンプレミス</span><span class="sxs-lookup"><span data-stu-id="69eba-275">Lync Web App - online and on-premises</span></span>  <br/> |<span data-ttu-id="69eba-276">N/A</span><span class="sxs-lookup"><span data-stu-id="69eba-276">N/A</span></span>  <br/> |<span data-ttu-id="69eba-277">N/A</span><span class="sxs-lookup"><span data-stu-id="69eba-277">N/A</span></span>  <br/> |
|<span data-ttu-id="69eba-278">Lync Mobile - Windows Phone</span><span class="sxs-lookup"><span data-stu-id="69eba-278">Lync Mobile - Windows Phone</span></span>  <br/> |<span data-ttu-id="69eba-279">準備中</span><span class="sxs-lookup"><span data-stu-id="69eba-279">Coming Soon</span></span>  <br/> |<span data-ttu-id="69eba-280">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-280">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-281">Lync Mobile - Android</span><span class="sxs-lookup"><span data-stu-id="69eba-281">Lync Mobile - Android</span></span>  <br/> |<span data-ttu-id="69eba-282">準備中</span><span class="sxs-lookup"><span data-stu-id="69eba-282">Coming Soon</span></span>  <br/> |<span data-ttu-id="69eba-283">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-283">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-284">Lync Mobile - iOS</span><span class="sxs-lookup"><span data-stu-id="69eba-284">Lync Mobile - iOS</span></span>  <br/> |<span data-ttu-id="69eba-285">準備中</span><span class="sxs-lookup"><span data-stu-id="69eba-285">Coming Soon</span></span>  <br/> |<span data-ttu-id="69eba-286">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-286">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-287">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="69eba-287">Lync Room System</span></span>  <br/> |<span data-ttu-id="69eba-288">準備中</span><span class="sxs-lookup"><span data-stu-id="69eba-288">Coming Soon</span></span>  <br/> |<span data-ttu-id="69eba-289">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-289">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-290">Lync Modern App (Win 8.1)</span><span class="sxs-lookup"><span data-stu-id="69eba-290">Lync Modern App (Win 8.1)</span></span>  <br/> |<span data-ttu-id="69eba-291">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-291">Yes</span></span>  <br/> |<span data-ttu-id="69eba-292">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-292">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-293">Lync Mac 2011</span><span class="sxs-lookup"><span data-stu-id="69eba-293">Lync Mac 2011</span></span>  <br/> |<span data-ttu-id="69eba-294">追加可能 (検索不可)</span><span class="sxs-lookup"><span data-stu-id="69eba-294">Can add (no search)</span></span>  <br/> |<span data-ttu-id="69eba-295">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-295">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-296">Lync Desktop 2010</span><span class="sxs-lookup"><span data-stu-id="69eba-296">Lync Desktop 2010</span></span>  <br/> |<span data-ttu-id="69eba-297">追加可能 (検索不可)</span><span class="sxs-lookup"><span data-stu-id="69eba-297">Can add (no search)</span></span>  <br/> |<span data-ttu-id="69eba-298">はい</span><span class="sxs-lookup"><span data-stu-id="69eba-298">Yes</span></span>  <br/> |
|<span data-ttu-id="69eba-299">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="69eba-299">Lync Phone Edition</span></span>  <br/> |<span data-ttu-id="69eba-300">N/A</span><span class="sxs-lookup"><span data-stu-id="69eba-300">N/A</span></span>  <br/> |<span data-ttu-id="69eba-301">N/A</span><span class="sxs-lookup"><span data-stu-id="69eba-301">N/A</span></span>  <br/> |
|<span data-ttu-id="69eba-302">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="69eba-302">Lync Attendant</span></span>  <br/> |<span data-ttu-id="69eba-303">該当なし</span><span class="sxs-lookup"><span data-stu-id="69eba-303">N/A</span></span>  <br/> |<span data-ttu-id="69eba-304">該当なし</span><span class="sxs-lookup"><span data-stu-id="69eba-304">N/A</span></span>  <br/> |
   

