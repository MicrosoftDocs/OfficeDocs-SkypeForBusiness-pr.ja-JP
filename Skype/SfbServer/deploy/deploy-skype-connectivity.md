---
title: Skype for Business Server 2015 での Skype 接続の展開
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '概要: は、Skype をビジネス サーバー 2015 の Skype のコンシューマーに接続する方法を説明します。 これは、Skype 接続とも呼ばれます。'
ms.openlocfilehash: 4d81d2529435d250957c775d954a33a562bed1e9
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569167"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server-2015"></a><span data-ttu-id="68232-104">Skype for Business Server 2015 での Skype 接続の展開</span><span class="sxs-lookup"><span data-stu-id="68232-104">Deploy Skype Connectivity in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="68232-p102">**概要:** Skype for Business Server 2015 と、Skype コンシューマー向け製品を接続する方法について説明します。これは、Skype 接続とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="68232-p102">**Summary:** Learn how to connect Skype for Business Server 2015 with Skype consumer. Also known as Skype connectivity.</span></span>
  
<span data-ttu-id="68232-107">ここでは、Skype Connectivity の展開について順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="68232-107">This article walks through deployment for Skype Connectivity.</span></span>
  
## <a name="skype-connectivity-overview-for-it-professionals"></a><span data-ttu-id="68232-108">Skype Connectivity の概要 (IT 担当者向け)</span><span class="sxs-lookup"><span data-stu-id="68232-108">Skype Connectivity Overview for IT Professionals</span></span>

<span data-ttu-id="68232-109">Skype 接続では、検索し、Skype ユーザーを追加する機能により、ビジネス ユーザー向け Skype を提供します。</span><span class="sxs-lookup"><span data-stu-id="68232-109">Skype Connectivity provides Skype for Business users with the ability to search for and add Skype users.</span></span> <span data-ttu-id="68232-110">Skype の接続は、Skype ユーザーとフェデレーションおよびディレクトリの検索を有効にすることができるビジネスの Skype の機能です。</span><span class="sxs-lookup"><span data-stu-id="68232-110">Skype Connectivity is a feature of Skype for Business that lets you enable federation and directory search with Skype users.</span></span> <span data-ttu-id="68232-111">Skype の接続を有効にした後、ビジネス ユーザー向けに、Skype は検索し、Skype ユーザーを追加することになります。</span><span class="sxs-lookup"><span data-stu-id="68232-111">After you enable Skype Connectivity your Skype for Business users will be able to search for and add Skype users.</span></span>
  
## <a name="skype-directory-search"></a><span data-ttu-id="68232-112">Skype Directory Search</span><span class="sxs-lookup"><span data-stu-id="68232-112">Skype Directory Search</span></span>

<span data-ttu-id="68232-p104">Skype Directory Search 機能によって、Skype for Business ユーザーは、Skype の連絡先を検索できます。検索機能により、ユーザーは以下の手段を使用して検索を実行できます。</span><span class="sxs-lookup"><span data-stu-id="68232-p104">Skype Directory Search functionality provides Skype for Business users with the ability to search for Skype contacts. The search functionality lets users search using the following:</span></span>
  
- <span data-ttu-id="68232-115">**"John Doe"の例の表示名で検索**を探しているものが見つからなかったため、多くの結果を返すこの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68232-115">**Search by display name, example "John Doe"** - This could return many results, so you might not find what you are looking for.</span></span>
    
- <span data-ttu-id="68232-116">**表示名と場所、「John Doe のバルセロナ」の使用例での検索**- これは絞り検索の結果かなり。</span><span class="sxs-lookup"><span data-stu-id="68232-116">**Search by display name plus location, example "John Doe in Barcelona"** - This will narrow the results of the search down considerably.</span></span>
    
- <span data-ttu-id="68232-117">**例"johndoe@outlook.com"、電子メールでの検索**- これはほとんどの場合で 1 つの結果を返す必要があります指定された電子メールを正確に一致するものです。</span><span class="sxs-lookup"><span data-stu-id="68232-117">**Search by email, example "johndoe@outlook.com"** - This should return one result in most cases; the one that matches the specified email exactly.</span></span> <span data-ttu-id="68232-118">同じメールが複数のアカウントに関連付けられている場合は、複数の結果が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="68232-118">But if the same email is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="68232-119">**例「123-123-1234」の電話番号で検索**- これはほとんどの場合で 1 つの結果を返す必要があります指定された電話を正確に一致するものです。</span><span class="sxs-lookup"><span data-stu-id="68232-119">**Search by phone number, example "123-123-1234"** - This should return one result in most cases; the one that matches the specified phone exactly.</span></span> <span data-ttu-id="68232-120">電話番号は、国コード (つまり 1-xxx、yyy-zzzz) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-120">Phone number must include the country code (i.e. 1-xxx-yyy-zzzz).</span></span> <span data-ttu-id="68232-121">同じ電話番号が複数のアカウントに関連付けられている場合は、複数の結果が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="68232-121">If the same phone number is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="68232-122">**Skype 名を「JohnDoe1456」の使用例で検索**の正確な一致が見つかった場合、それが結果として返される、最初。</span><span class="sxs-lookup"><span data-stu-id="68232-122">**Search by Skype Name, example "JohnDoe1456"** - If exact match is found, it will be returned as the first result.</span></span> <span data-ttu-id="68232-123">他の"name"の一致候補が返されます。</span><span class="sxs-lookup"><span data-stu-id="68232-123">Other possible "name" matches may be returned.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68232-124">Skype Directory Search では、ポート 443 で IP アドレス 104.40.75.246、23.101.135.34、40.113.86.19 と通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-124">Skype Directory Search must be able to communicate with the following IP addresses on port 443: 104.40.75.246, 23.101.135.34, and 40.113.86.19.</span></span> 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a><span data-ttu-id="68232-125">Skype Directory Search のサポートされる展開のマトリックス</span><span class="sxs-lookup"><span data-stu-id="68232-125">Supported deployment matrix for Skype Directory Search</span></span>

<span data-ttu-id="68232-126">以下の表に、Skype Directory Search のサポートの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="68232-126">The following table outlines support for Skype Directory Search.</span></span>
  

||<span data-ttu-id="68232-127">**ビジネス 2015 のサーバーのフロント エンドの Skype**</span><span class="sxs-lookup"><span data-stu-id="68232-127">**Skype for Business Server 2015 Front End**</span></span>|<span data-ttu-id="68232-128">**Lync Server 2013 (または古い) フロント エンド**</span><span class="sxs-lookup"><span data-stu-id="68232-128">**Lync Server 2013 (or older) Front End**</span></span>|<span data-ttu-id="68232-129">**コメント**</span><span class="sxs-lookup"><span data-stu-id="68232-129">**Comments**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="68232-130">Skype for Business Server 2015 エッジ</span><span class="sxs-lookup"><span data-stu-id="68232-130">Skype for Business Server 2015 Edge</span></span>  <br/> |<span data-ttu-id="68232-131">サポート対象</span><span class="sxs-lookup"><span data-stu-id="68232-131">Supported</span></span>  <br/> |<span data-ttu-id="68232-132">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="68232-132">Not Supported</span></span>  <br/> |<span data-ttu-id="68232-133">Skype for Business Server 2015 およびエッジは Skype Directory Search に必須</span><span class="sxs-lookup"><span data-stu-id="68232-133">Skype for Business Server 2015 and Edge are prerequisites for Skype Directory Search</span></span>  <br/> |
|<span data-ttu-id="68232-134">サイド バイ サイドで展開されている Skype for Business Server 2015 エッジ + Lync Server 2013 エッジ</span><span class="sxs-lookup"><span data-stu-id="68232-134">Skype for Business Server 2015 Edge + Lync Server 2013 Edge deployed side-by-side</span></span>  <br/> |<span data-ttu-id="68232-135">サポート対象</span><span class="sxs-lookup"><span data-stu-id="68232-135">Supported</span></span>  <br/> |<span data-ttu-id="68232-136">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="68232-136">Not Supported</span></span>  <br/> |<span data-ttu-id="68232-p108">Skype Directory Search のトラフィックは Skype for Business Server エッジ サーバーを通過します。フェデレーション トラフィックは、管理者により構成されたエッジを通過します。たとえば、管理者は、Skype Directory Search をサポートしない Lync Server 2013 エッジ サーバーを介してフェデレーション トラフィックを引き続き送信することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="68232-p108">Skype Directory Search traffic flows through Skype for Business Server Edge servers. Federation traffic goes through edge configured by the administrator. For example, the administrator could choose to continue to send federation traffic through Lync Server 2013 Edge servers which would not support Skype Directory Search.</span></span>  <br/> |
|<span data-ttu-id="68232-140">Lync Server 2013 (またはそれ以降の) エッジ</span><span class="sxs-lookup"><span data-stu-id="68232-140">Lync Server 2013 (or older) Edge</span></span>  <br/> |<span data-ttu-id="68232-141">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="68232-141">Not Supported</span></span>  <br/> |<span data-ttu-id="68232-142">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="68232-142">Not Supported</span></span>  <br/> ||
   
> [!NOTE]
> <span data-ttu-id="68232-143">Skype for Business Server 2015 フロントエンドで実行されているアドレス帳サービスは、2015 エッジ サーバーの Skype 検索ポート 4443 の存在により、2015 エッジを検出します。</span><span class="sxs-lookup"><span data-stu-id="68232-143">Addressbook service running on Skype for Business Server 2015 Front End finds the 2015 Edge by the existence of the Skype Search port 4443 in the 2015 Edge server.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68232-p109">オンプレミス展開に複数のサイトがあるカスタマーの場合、Skype for Business Server 2015 エッジ サーバー/プールを 1 つだけ展開していると、すべてのサイトから着信する検索トラフィックは、利用できる単一のエッジ サーバーを通過します。管理者は、すべてのサイトのプールが、展開済みの Skype for Business Server 2015 エッジ サーバー/プールにアクセスできることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-p109">In case a customer has multiple sites in their on-premises deployment, and if they have deployed just one Skype for Business Server 2015 Edge server/pool, then Search traffic from all sites will go through the single available Edge server. The administrator needs to make sure the pools from all sites can access the deployed Skype for Business Server 2015 Edge server/pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68232-146">Skype グラフ サービスは、要求レートが 15 要求/秒を超えた場合、すべてのオンプレミスまたは Office 365 カスタマーからの検索要求を調整します。</span><span class="sxs-lookup"><span data-stu-id="68232-146">Skype graph service will throttle search requests from any on-premises or Office 365 customer if the request rate exceeds 15 requests / second.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68232-147">大規模エンタープライズ オンプレミス カスタマーに対しては、より高い要求レートを許可するために、ドメインを Skype 検索サービスのホワイトリストに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-147">For large enterprise on-premises customers, the domains will need to be whitelisted with the Skype search service to allow higher request rates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68232-148">キューに保留中である要求の数が多すぎる場合、Skype for Business Server 2015 は、着信要求を調整します。</span><span class="sxs-lookup"><span data-stu-id="68232-148">Skype for Business Server 2015 will throttle incoming requests, if there are too many pending requests in the queue.</span></span> 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a><span data-ttu-id="68232-149">Office 365 での Skype for Business Server Online 用の Skype Connectivity の展開</span><span class="sxs-lookup"><span data-stu-id="68232-149">Deploying Skype Connectivity for Skype for Business Online in Office 365</span></span>

<span data-ttu-id="68232-p110">Skype Connectivity は、Office 365 の一部である Skype for Business Online の機能でもあります。Office 365 ポータル内の Skype for Business 管理センターから、Skype Connectivity 機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="68232-p110">Skype Connectivity is also a feature of Skype for Business Online, which is part of Office 365. You can enable the Skype Connectivity feature from the Skype for Business Administration Center within the Office 365 portal.</span></span>
  
<span data-ttu-id="68232-152">Office 365 の中規模ビジネス、Office 365 のエンタープライズ、Office 365 の教育、および政府の Office 365 の: office 365 ポータルにサインインし、ビジネス管理センターの Skype に移動します。</span><span class="sxs-lookup"><span data-stu-id="68232-152">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Office 365 portal and navigate to the Skype for Business Administration Center.</span></span> <span data-ttu-id="68232-153">外部との連絡に移動します。</span><span class="sxs-lookup"><span data-stu-id="68232-153">Go to External Communications.</span></span> <span data-ttu-id="68232-154">パブリック IM サービス プロバイダーでは、[有効] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68232-154">Under Public IM Service Providers, click Enable.</span></span> <span data-ttu-id="68232-155">Skype 接続する個々 のユーザーのアクセスを制御する場合は、これを行う個々 のユーザーの外部通信の設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="68232-155">If you want to control individual user access to Skype Connectivity, you can do so by editing individual users' External Communications settings.</span></span>
  
<span data-ttu-id="68232-156">小規模のビジネス プレミアム: Office 365 用には、Office 365 にサインインし、管理者には、\>サービスの設定\>インスタント メッセージング、会議および会議。</span><span class="sxs-lookup"><span data-stu-id="68232-156">For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Settings \> Instant messaging, meetings and conferencing.</span></span> <span data-ttu-id="68232-157">外部との連絡を入れます。</span><span class="sxs-lookup"><span data-stu-id="68232-157">Turn on External communications.</span></span> <span data-ttu-id="68232-158">外部との連絡のスイッチは、Skype の接続性とビジネスの Skype を使用する他の組織との通信の両方オンにします。</span><span class="sxs-lookup"><span data-stu-id="68232-158">The External communications switch turns on both Skype Connectivity and communications with other organizations that use Skype for Business.</span></span>
  
<span data-ttu-id="68232-159">Skype for Business Online の管理の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68232-159">For more information about Skype for Business Online administration, see:</span></span>
  
- [<span data-ttu-id="68232-160">外部の Skype のビジネスまたは Skype の連絡先と通信ビジネスのオンライン ユーザーの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="68232-160">Let Skype for Business Online users communicate with external Skype for Business or Skype contacts</span></span>](https://support.office.com/en-us/article/Let-Skype-for-Business-Online-users-communicate-with-external-Lync-or-Skype-contacts-b414873a-0059-4cd5-aea1-e5d0857dbc94?ui=en-US&amp;rs=en-US&amp;ad=US )
    
- <span data-ttu-id="68232-161">[[中小企業] 組織の外部と通信ビジネスのオンライン ユーザーの Skype を使用します。](https://support.office.com/en-US/article/Let-Lync-Online-users-communicate-outside-your-organization-Small-Business-7F488F09-F004-4DB5-AEC5-01C262AA3D34)</span><span class="sxs-lookup"><span data-stu-id="68232-161">[Let Skype for Business Online users communicate outside your organization [Small Business]](https://support.office.com/en-US/article/Let-Lync-Online-users-communicate-outside-your-organization-Small-Business-7F488F09-F004-4DB5-AEC5-01C262AA3D34)</span></span>
    
- [<span data-ttu-id="68232-162">ビジネスまたは Skype の外部の連絡先の IM の Skype することはできないときにどのような</span><span class="sxs-lookup"><span data-stu-id="68232-162">What to try if you can't IM Skype for Business or Skype external contacts</span></span>](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [<span data-ttu-id="68232-163">ビジネス用の Skype を使用して、外部の連絡先に接続するには</span><span class="sxs-lookup"><span data-stu-id="68232-163">Use Skype for Business to connect with external contacts</span></span>](https://support.office.com/en-US/article/Use-Lync-to-connect-with-external-contacts-E6DA21CE-FFB8-4AF3-A171-871CA245BC30)
    
- [<span data-ttu-id="68232-164">ビジネス用の Skype の連絡先を追加します。</span><span class="sxs-lookup"><span data-stu-id="68232-164">Add a contact in Skype for Business</span></span>](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
    
- [<span data-ttu-id="68232-165">個々 のユーザー用の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="68232-165">Configure settings for individual users</span></span>](https://support.office.com/en-US/article/Configure-settings-for-individual-users-77B26EAC-8228-4161-BA9F-733B187BD836)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server-2015"></a><span data-ttu-id="68232-166">Skype for Business Server 2015 用の Skype Connectivity の展開</span><span class="sxs-lookup"><span data-stu-id="68232-166">Deploying Skype Connectivity for Skype for Business Server 2015</span></span>

<span data-ttu-id="68232-167">ビジネス サーバー 2015 の Skype は、Skype との接続をサポートするためにフェデレーション アクセス アーキテクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="68232-167">Skype for Business Server 2015 uses the federation access architecture to support connectivity with Skype.</span></span> <span data-ttu-id="68232-168">この接続では、Skype は、Skype を追加するのにはビジネスのサーバーのユーザーが有効にします。</span><span class="sxs-lookup"><span data-stu-id="68232-168">This connectivity enables your Skype for Business Server users to add Skype.</span></span> <span data-ttu-id="68232-169">Skype クライアントは Skype を連絡先リストにビジネス ・ ユーザーの追加もできます。</span><span class="sxs-lookup"><span data-stu-id="68232-169">Skype clients can also add Skype for Business users to their contact list.</span></span> <span data-ttu-id="68232-170">ビジネス サーバーのユーザーがインスタント メッセージングを使用して通信できるの Skype で管理者によって設定されたポリシーに基づき、互いの存在を参照してくださいし、音声通話とビデオ通話を開始します。</span><span class="sxs-lookup"><span data-stu-id="68232-170">Based on policies administratively set in Skype for Business Server users will be able to communicate using instant messaging, see each other's presence, and initiate audio and video calls.</span></span> <span data-ttu-id="68232-171">Skype の接続も、有効にできる Skype、Skype からのオンライン ビジネスのお客様のビジネス管理センターの Office 365 ポータル内のビジネス オンラインでは、Skype の機能です。</span><span class="sxs-lookup"><span data-stu-id="68232-171">Skype connectivity is also a feature of Skype for Business Online, and can be enabled for Skype for Business Online customers from the Skype for Business Administration Center within the Office 365 portal.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68232-p114">Skype for Business Server がパブリック インスタント メッセージング接続 (PIC) を使用して Windows Messenger と接続するように既に構成されている場合、展開は、既に Skype Connectivity 用に構成されています。検討が必要と思われるのは、既存の Messenger PIC エントリの名前を Skype などに変更することだけです。</span><span class="sxs-lookup"><span data-stu-id="68232-p114">If Skype for Business Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> 
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server-2015"></a><span data-ttu-id="68232-174">Skype for Business Server 2015 から Skype for Business Server のパブリック IM 接続プロビジョニング サイトへのアクセス</span><span class="sxs-lookup"><span data-stu-id="68232-174">Accessing the Skype for Business Server public IM connectivity provisioning site from Skype for Business Server 2015</span></span>

<span data-ttu-id="68232-p115">このプロビジョニング プロセスは、完了するまで最長で 30 日かかる可能性がありますが、要求量によっては数日のみで完了することもあります。Microsoft は、このドキュメントの残りの手順を完了する前に、このプロセスを先に開始することをお勧めします。Skype のプロビジョニング プロセスが完了した後、アカウントがアクティブになり、適格なユーザーのパブリック IM 接続が有効になります。</span><span class="sxs-lookup"><span data-stu-id="68232-p115">This provisioning process can take up to thirty days to complete but may take only a few days depending on the volume of requests. We recommend that you start this process first, prior to completing the remaining steps in this document. After the Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span> 
  
<span data-ttu-id="68232-178">Skype Connectivity をプロビジョニングするには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="68232-178">To provision Skype connectivity, you need the following information:</span></span>
  
- <span data-ttu-id="68232-179">Microsoft 契約番号</span><span class="sxs-lookup"><span data-stu-id="68232-179">Microsoft Agreement Number</span></span>
    
- <span data-ttu-id="68232-180">アクセス エッジ サービスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="68232-180">Access Edge service fully qualified domain name (FQDN)</span></span>
    
- <span data-ttu-id="68232-181">セッション開始プロトコル (SIP) のドメイン</span><span class="sxs-lookup"><span data-stu-id="68232-181">Session Initiation Protocol (SIP) domain(s)</span></span>
    
- <span data-ttu-id="68232-182">追加のアクセス エッジ サービスの FQDN</span><span class="sxs-lookup"><span data-stu-id="68232-182">Any additional Access Edge service FQDNs</span></span>
    
- <span data-ttu-id="68232-183">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="68232-183">Contact information</span></span>
    
<span data-ttu-id="68232-184">Skype Connectivity のプロビジョニング プロセスを開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="68232-184">To initiate the provisioning process for Skype Connectivity:</span></span>
  
1. <span data-ttu-id="68232-185">Web サイトにサインインするのにhttps://pic.lync.comを Microsoft Windows Live ID を使用して</span><span class="sxs-lookup"><span data-stu-id="68232-185">Sign in to the website, https://pic.lync.com, using your Microsoft Windows Live ID.</span></span>
    
2. <span data-ttu-id="68232-186">Microsoft ライセンスの契約の種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="68232-186">Select the Microsoft licensing agreement type.</span></span>
    
3. <span data-ttu-id="68232-187">チェック ボックスをオンにし、Skype for Business Server の製品使用権の内容を読んで同意したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="68232-187">Select the check box, verifying that you have read and accept the Product Use Rights for Skype for Business Server.</span></span>
    
4. <span data-ttu-id="68232-188">プロビジョニング要求を開始するためのページで、適切なリンクをクリックしてプロビジョニング要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="68232-188">On the Initiate a Provisioning Request page, click the appropriate link to initiate a provisioning request:</span></span>
    
5. <span data-ttu-id="68232-189">プロビジョニング情報を指定するためのページで、アクセス エッジ サービスの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="68232-189">On the Specify Provisioning Information page, enter the Access Edge service FQDN.</span></span> <span data-ttu-id="68232-190">たとえば、sip.contoso.com と入力します。</span><span class="sxs-lookup"><span data-stu-id="68232-190">For example, sip.contoso.com.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="68232-191">2017 年 7 月 1 日以降マイクロソフトは、パブリック インスタント メッセージの接続を機能し続けるために、お客様側でのフェデレーション DNS SRV レコードの展開を追加の必須要件とします。</span><span class="sxs-lookup"><span data-stu-id="68232-191">After July 1st 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span> 
  
6. <span data-ttu-id="68232-192">少なくとも 1 つの SIP ドメイン名を入力し、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68232-192">Enter at least one or more SIP domain names, and then click Add.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68232-p117">プロビジョニング プロセスを完了するには、少なくとも 1 つのアクセス エッジ サーバーが必要です。1 つのアクセス エッジ FQDN で複数の SIP ドメインをサポートできますが、複数のアクセス エッジ FQDN で 1 つの SIP ドメインを表現することはできません。SIP ドメインとアクセス エッジ サーバーは、アクティブで、正常に機能し、ネットワーク上で到達可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-p117">At least one Access Edge server is required to complete the provisioning process. While a single Access Edge FQDN can support multiple SIP domains, a single SIP domain cannot be represented by more than one Access Edge FQDN. The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span> 
  
7. <span data-ttu-id="68232-196">[パブリック IM サービス プロバイダー] の一覧で [Skype] を選び、[次へ] をクリックして連絡先情報を追加し、プロビジョニング要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="68232-196">In the list of Public IM Service providers, select Skype, and click Next to add contact information, and submit the provisioning request.</span></span>
    
<span data-ttu-id="68232-197">プロビジョニング要求が送信された後、アカウントをアクティブにして、ユーザーを Skype Connectivity で有効にするには、最長 30 日かかる可能性があります。ただし、キューによっては数日のみで済むこともあります。</span><span class="sxs-lookup"><span data-stu-id="68232-197">After the provisioning request has been submitted, it can take up to 30 days, but may take only a few days depending on queue, for the account to activate and for users to be enabled for Skype Connectivity.</span></span>
  
### <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="68232-198">フェデレーションとパブリック IM 接続 (PIC) の有効化</span><span class="sxs-lookup"><span data-stu-id="68232-198">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="68232-p118">プロビジョニング要求を送信した後は、Skype Connectivity を構成するために必要な、Skype for Business Server の環境と管理タスクに重点を移すことができます。このセクションでは、管理者は Skype for Business Server を展開し、外部アクセス (エッジ サーバーとも呼ばれます) を構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="68232-p118">After you have submitted the provisioning request, you can focus on the Skype for Business Server environment and administrative tasks required to configure Skype Connectivity. In this section, we assume that the administrator has deployed Skype for Business Server and configured external access, also known as Edge servers.</span></span> 
  
<span data-ttu-id="68232-p119">フェデレーションと PIC を有効にするために必要な主な 3 つのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="68232-p119">There are three primary steps required to enable federation and PIC. These are:</span></span>
  
1. <span data-ttu-id="68232-203">フェデレーションと PIC を構成する</span><span class="sxs-lookup"><span data-stu-id="68232-203">Configure Federation and PIC</span></span>
    
2. <span data-ttu-id="68232-204">フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="68232-204">Configure at least one policy to support federated user access</span></span>
    
3. <span data-ttu-id="68232-205">Skype PIC プロバイダー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="68232-205">Configure the Skype PIC provider setting</span></span>
    
#### <a name="1-configure-federation-and-pic"></a><span data-ttu-id="68232-206">1. フェデレーションと PIC を構成する</span><span class="sxs-lookup"><span data-stu-id="68232-206">1. Configure Federation and PIC</span></span>

<span data-ttu-id="68232-p120">フェデレーションは、Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Skype for Business ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、Skype for Business Server コントロール パネルを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="68232-p120">Federation is required to enable Skype users to communicate with Skype for Business users in your organization. Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business users to communicate with Skype users. Federation and PIC are configured by using the Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68232-p121">PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。PIC フェデレーションがサポートされるプラットフォームとしては、Skype for Business Server 2015、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。</span><span class="sxs-lookup"><span data-stu-id="68232-p121">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007. The supported platforms for PIC federation include Skype for Business Server 2015, Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="68232-p122">フェデレーションは、Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Skype for Business ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、次に示すように Skype for Business Server コントロール パネルの [エッジ構成] ダイアログを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="68232-p122">Federation is required to enable Skype users to communicate with Skype for Business users in your organization. Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business Server users to communicate with Skype users. Federation and PIC are configured by using the Edge configuration dialog of the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![新しいエッジ プールの定義](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> <span data-ttu-id="68232-216">検索を使用するには、パブリック プロバイダーの設定 (後の手順を参照) で EnableSkypeIdRouting 属性と EnableSkypeDirectorySearch 属性を True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-216">EnableSkypeIdRouting and EnableSkypeDirectorySearch attributes need to be set to true in the public provider settings (see later instructions) for Search to work.</span></span> 
  
<span data-ttu-id="68232-p123">これで、サーバー上で実行する必要がある管理タスクが完了し、Skype Connectivity を使用するように設定されました。</span><span class="sxs-lookup"><span data-stu-id="68232-p123">This completes the administrative tasks that must be performed on the server. You are now set up for Skype Connectivity.</span></span>
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="68232-219">2. フェデレーション ユーザー アクセスをサポートするために少なくとも 1 つのポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="68232-219">2. Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="68232-220">管理者は Skype for Business Server コントロール パネルを使用して外部ユーザー アクセス ポリシーを 1 つ以上構成し、Skype ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-220">Using the Skype for Business Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Skype for Business Server users.</span></span>
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a><span data-ttu-id="68232-221">3. 設定 Skype PIC プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="68232-221">3. Configure the Skype PIC provider setting</span></span>

<span data-ttu-id="68232-222">管理者は Skype for Business Server 管理シェルを使用して Skype for Business クライアント ポリシーを構成し、Skype を追加の PIC プロバイダーとして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-222">Using the Skype for Business Server Management Shell, an administrator must configure the Skype for Business client policy to display Skype as an additional PIC provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68232-223">パブリック インスタント メッセージング接続 (PIC) サービス プロバイダーのユーザーは、パブリック IM 接続をサポートするためにも少なくとも 1 つのポリシー (この手順で前の手順 2) を構成するまで、IM または組織内の会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="68232-223">Users of the Public Instant Messaging Connectivity (PIC) service providers can't participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span> 
  
<span data-ttu-id="68232-224">新規インストールの場合は、図に示すように Skype for Business Server コントロール パネルを使用して Skype パブリック プロバイダーを有効にすることで、Skype Connectivity を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="68232-224">For new installations you can configure Skype Connectivity by enabling a Skype Public Provider using the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![SIP フェデレーション プロバイダー](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> <span data-ttu-id="68232-226">Skype for Business Server にアップグレードする場合に Skype Connectivity を構成するには、既存の Skype パブリック プロバイダーを削除してから再度追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-226">To configure Skype Connectivity when upgrading to Skype for Business Server you must remove and re-add the existing Skype public provider.</span></span> 
  
<span data-ttu-id="68232-p124">Skype Connectivity の構成は、PowerShell のみを使用して行うこともできます。PowerShell を使用して Skype Connectivity を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="68232-p124">Configuring Skype Connectivity can also be done using only PowerShell. To configure Skype Connectivity using PowerShell:</span></span>
  
1. <span data-ttu-id="68232-229">Skype for Business Server フロントエンド サーバーから、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="68232-229">From a Skype for Business Server Front End Server, open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="68232-230">次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="68232-230">Run the following two commands:</span></span>
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > <span data-ttu-id="68232-231">環境にまだ PIC プロバイダーがなく、新しい PIC プロバイダーを作成している場合は、Remove-CsPublicProvider コマンドレットを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="68232-231">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the Remove-CsPublicProvider cmdlet.</span></span> 
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    <span data-ttu-id="68232-232">意味がわかりにくいパラメーターの動作</span><span class="sxs-lookup"><span data-stu-id="68232-232">What do the less obvious parameters do?</span></span>
    
  - <span data-ttu-id="68232-233">ProxyFqdn:  (Microsoft により所有/維持管理される) Skype フェデレーション エッジの場所</span><span class="sxs-lookup"><span data-stu-id="68232-233">ProxyFqdn: location of Skype federation edge (owned/maintained by Microsoft)</span></span>
    
  - <span data-ttu-id="68232-234">IconURL: アイコンが Lync で使用される&amp;Skype 連絡先を視覚的に識別するビジネスの Skype</span><span class="sxs-lookup"><span data-stu-id="68232-234">IconURL: icon used by Lync &amp; Skype for Business client to visually identify Skype contacts</span></span>
    
  - <span data-ttu-id="68232-235">NameDecorationRoutingDomain および NameDecorationExcludedDomainList:「msn.com」でマイクロソフト以外のドメインを「装飾」について理解することがなく Skype ユーザーの MSAs を入力するユーザーは、これらの設定。</span><span class="sxs-lookup"><span data-stu-id="68232-235">NameDecorationRoutingDomain and NameDecorationExcludedDomainList: setting these allows users to enter Skype users' MSAs without needing to know about "decorating" non-Microsoft domains with "msn.com".</span></span> <span data-ttu-id="68232-236">ExcludedDomainList ではないすべてのドメインの"ユーザー (contoso.com) @msn.com"を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-236">This eliminates the need to type "user(contoso.com)@msn.com" for all domains that are NOT in the ExcludedDomainList.</span></span> <span data-ttu-id="68232-237">ドメインが除外リストに存在しない場合、SfB クライアントは自動的に MSA を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="68232-237">The SfB client will automatically format the MSA if the domain is NOT in the Excluded list.</span></span> <span data-ttu-id="68232-238">最も一般的な Microsoft アカウント ドメインから除外する一覧に追加しました。</span><span class="sxs-lookup"><span data-stu-id="68232-238">We've added the most common Microsoft Account domains to the excluded list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68232-239">変更が行われた場合は、パブリック プロバイダーを削除して新しく追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68232-239">Public Provider must be removed and added new if changes are made.</span></span> <span data-ttu-id="68232-240">インプレースでの変更は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="68232-240">No in-place changes are allowed.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="68232-241">Lync Server 2013 CU5 に追加&amp;Office 2013 の SP1 では、NameDecorationRoutingDomain および NameDecorationExcludedDomainList でデスクトップの Lync クライアントは、Skype 連絡先を追加するに必要な Lync ユーザーを「修飾」するマイクロソフト以外のドメイン状況を改善識別し、Skype にルーティング (の形式: user(contoso.com)@msn.com)。</span><span class="sxs-lookup"><span data-stu-id="68232-241">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to "decorate" non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="68232-242">これらの新しい設定とアドレスのユーザーの自動書式設定の入力"Skype の連絡先の追加] ダイアログ ボックスで (これは、msn.com に設定する必要があります)、NameDecorationRoutingDomain と NameDecorationExcludedDomainList (内のドメインが含まれていない場合、します。現在サポートできます msn.com、live.com、Hotmail.com、outlook.com)。</span><span class="sxs-lookup"><span data-stu-id="68232-242">These new settings will allow automatic formatting of the address user's enter in the "Add Skype contact" dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span> 
  
3. <span data-ttu-id="68232-243">Skype for Business クライアントから、ユーザーは Skype ユーザーを検索および追加することができます。</span><span class="sxs-lookup"><span data-stu-id="68232-243">From a Skype for Business client users can now search for and add a Skype user.</span></span>
    
## <a name="clients-and-interoperability-matrix"></a><span data-ttu-id="68232-244">クライアントと相互運用性のマトリックス</span><span class="sxs-lookup"><span data-stu-id="68232-244">Clients and Interoperability Matrix</span></span>

<span data-ttu-id="68232-245">次の表に、コンシューマー向け Skype の最新バージョンと Skype for Business の最新バージョンとの相互運用性のステータスを示します。</span><span class="sxs-lookup"><span data-stu-id="68232-245">The following table outlines the status of interop between the latest version of Skype consumer and the latest version of Skype for Business.</span></span>
  

|<span data-ttu-id="68232-246">**Skype クライアント**</span><span class="sxs-lookup"><span data-stu-id="68232-246">**Skype Clients**</span></span>|<span data-ttu-id="68232-247">**取引先担当者、IM、プレゼンス、オーディオ、およびビデオ通話を追加します。**</span><span class="sxs-lookup"><span data-stu-id="68232-247">**Add contacts, IM, presence, audio, and video calling**</span></span>|<span data-ttu-id="68232-248">**コメント**</span><span class="sxs-lookup"><span data-stu-id="68232-248">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="68232-249">Skype Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="68232-249">Skype Windows Desktop</span></span>  <br/> |<span data-ttu-id="68232-250">7.6 以降、Windows XP 以降</span><span class="sxs-lookup"><span data-stu-id="68232-250">7.6 or higher, Windows XP and higher</span></span>  <br/> |<span data-ttu-id="68232-251">**新規**: Windows XP および Windows Vista で実行されている Windows の Skype クライアントのサポートが追加 * * (7.26 またはそれ以降の最新のクライアント バージョンが必要です) * *</span><span class="sxs-lookup"><span data-stu-id="68232-251">**NEW**: Support added for Windows Skype client running on Windows XP, and Windows Vista ** (requires latest client version 7.26 or higher)**</span></span> <br/> |
|<span data-ttu-id="68232-252">Skype Mobile - Android 携帯電話およびタブレット </span><span class="sxs-lookup"><span data-stu-id="68232-252">Skype Mobile - Android Phone and Tablet</span></span>  <br/> |<span data-ttu-id="68232-253">6.19 以降、Android OS バージョン 4.0.3 以降を実行</span><span class="sxs-lookup"><span data-stu-id="68232-253">6.19 or higher, running Android OS version 4.0.3 or higher</span></span>  <br/> |<span data-ttu-id="68232-254">性能の高くない機種ではビデオ通話がサポートされない場合あり</span><span class="sxs-lookup"><span data-stu-id="68232-254">Low spec devices may not support video calling</span></span>  <br/> |
|<span data-ttu-id="68232-255">Skype 携帯 - iOS</span><span class="sxs-lookup"><span data-stu-id="68232-255">Skype Mobile - iOS</span></span>  <br/> |<span data-ttu-id="68232-256">6.11 以降、IOS 7 以降</span><span class="sxs-lookup"><span data-stu-id="68232-256">6.11 or higher, on IOS 7 or higher</span></span>  <br/> |<span data-ttu-id="68232-257">iPhone 4 以前、iPod 第 4 世代以前、iPad 第 1 世代はサポート外</span><span class="sxs-lookup"><span data-stu-id="68232-257">Not supported are iPhone 4 and earlier, iPod 4th generation and earlier, iPad 1st generation</span></span>  <br/> |
|<span data-ttu-id="68232-258">Skype Mac</span><span class="sxs-lookup"><span data-stu-id="68232-258">Skype Mac</span></span>  <br/> |<span data-ttu-id="68232-259">7.19 以降、Mac OS X 10.9 (Mavericks) 以降</span><span class="sxs-lookup"><span data-stu-id="68232-259">7.19 or higher, on Mac OS X 10.9 (Mavericks) or higher</span></span>  <br/> |<span data-ttu-id="68232-260">Mac OS X 10.9 以降</span><span class="sxs-lookup"><span data-stu-id="68232-260">Requires Mac OSX 10.9 or higher</span></span>  <br/> |
|<span data-ttu-id="68232-261">Skype Universal Windows アプリ (Windows 10) デスクトップおよびモバイル</span><span class="sxs-lookup"><span data-stu-id="68232-261">Skype Universal Windows App (Windows 10) Desktop and Mobile</span></span>  <br/> |<span data-ttu-id="68232-262">Windows 10 (Redstone 1 更新プログラム以降)</span><span class="sxs-lookup"><span data-stu-id="68232-262">Windows 10 (Redstone 1 update or later)</span></span>  <br/> |<span data-ttu-id="68232-263">Windows Universal App には 2016 年秋にアップデートが配信され、相互運用性のサポートが追加される予定</span><span class="sxs-lookup"><span data-stu-id="68232-263">Windows Universal App will receive update in Fall 2016 adding interop support</span></span>  <br/> |
   
<span data-ttu-id="68232-264">次の表に、Skype for Business の最新バージョンとコンシューマー向け Skype の最新バージョンとの相互運用性のステータスを示します。</span><span class="sxs-lookup"><span data-stu-id="68232-264">The following table outlines the status of interop between the latest version of Skype for Business and the latest version of Skype consumer.</span></span> 
  
|<span data-ttu-id="68232-265">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="68232-265">**Client**</span></span>|<span data-ttu-id="68232-266">**Skype ディレクトリを検索し、連絡先を追加します。**</span><span class="sxs-lookup"><span data-stu-id="68232-266">**Skype Directory Search and Add Contacts**</span></span>|<span data-ttu-id="68232-267">**Skype の A/V、IM の相互運用機能**</span><span class="sxs-lookup"><span data-stu-id="68232-267">**Skype A/V, IM interop**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="68232-268">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="68232-268">Skype for Business 2015</span></span>  <br/> |<span data-ttu-id="68232-269">はい</span><span class="sxs-lookup"><span data-stu-id="68232-269">Yes</span></span>  <br/> |<span data-ttu-id="68232-270">あり</span><span class="sxs-lookup"><span data-stu-id="68232-270">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-271">Mac 用 Skype For Business</span><span class="sxs-lookup"><span data-stu-id="68232-271">Skype for Business on Mac</span></span>  <br/> |<span data-ttu-id="68232-272">追加可能 (検索不可)</span><span class="sxs-lookup"><span data-stu-id="68232-272">Can add (no search)</span></span>  <br/> |<span data-ttu-id="68232-273">はい</span><span class="sxs-lookup"><span data-stu-id="68232-273">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-274">Lync Desktop 2013</span><span class="sxs-lookup"><span data-stu-id="68232-274">Lync Desktop 2013</span></span>  <br/> |<span data-ttu-id="68232-275">追加可能 (検索不可)</span><span class="sxs-lookup"><span data-stu-id="68232-275">Can add (no search)</span></span>  <br/> |<span data-ttu-id="68232-276">はい</span><span class="sxs-lookup"><span data-stu-id="68232-276">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-277">Lync Web App - オンラインとオンプレミス</span><span class="sxs-lookup"><span data-stu-id="68232-277">Lync Web App - online and on-premises</span></span>  <br/> |<span data-ttu-id="68232-278">該当なし</span><span class="sxs-lookup"><span data-stu-id="68232-278">N/A</span></span>  <br/> |<span data-ttu-id="68232-279">該当なし</span><span class="sxs-lookup"><span data-stu-id="68232-279">N/A</span></span>  <br/> |
|<span data-ttu-id="68232-280">Lync Mobile - Windows Phone</span><span class="sxs-lookup"><span data-stu-id="68232-280">Lync Mobile - Windows Phone</span></span>  <br/> |<span data-ttu-id="68232-281">準備中</span><span class="sxs-lookup"><span data-stu-id="68232-281">Coming Soon</span></span>  <br/> |<span data-ttu-id="68232-282">はい</span><span class="sxs-lookup"><span data-stu-id="68232-282">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-283">Lync Mobile - Android</span><span class="sxs-lookup"><span data-stu-id="68232-283">Lync Mobile - Android</span></span>  <br/> |<span data-ttu-id="68232-284">準備中</span><span class="sxs-lookup"><span data-stu-id="68232-284">Coming Soon</span></span>  <br/> |<span data-ttu-id="68232-285">はい</span><span class="sxs-lookup"><span data-stu-id="68232-285">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-286">Lync Mobile - iOS</span><span class="sxs-lookup"><span data-stu-id="68232-286">Lync Mobile - iOS</span></span>  <br/> |<span data-ttu-id="68232-287">準備中</span><span class="sxs-lookup"><span data-stu-id="68232-287">Coming Soon</span></span>  <br/> |<span data-ttu-id="68232-288">はい</span><span class="sxs-lookup"><span data-stu-id="68232-288">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-289">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="68232-289">Lync Room System</span></span>  <br/> |<span data-ttu-id="68232-290">準備中</span><span class="sxs-lookup"><span data-stu-id="68232-290">Coming Soon</span></span>  <br/> |<span data-ttu-id="68232-291">はい</span><span class="sxs-lookup"><span data-stu-id="68232-291">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-292">Lync Modern App (Win 8.1)</span><span class="sxs-lookup"><span data-stu-id="68232-292">Lync Modern App (Win 8.1)</span></span>  <br/> |<span data-ttu-id="68232-293">はい</span><span class="sxs-lookup"><span data-stu-id="68232-293">Yes</span></span>  <br/> |<span data-ttu-id="68232-294">はい</span><span class="sxs-lookup"><span data-stu-id="68232-294">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-295">Lync Mac 2011</span><span class="sxs-lookup"><span data-stu-id="68232-295">Lync Mac 2011</span></span>  <br/> |<span data-ttu-id="68232-296">追加可能 (検索不可)</span><span class="sxs-lookup"><span data-stu-id="68232-296">Can add (no search)</span></span>  <br/> |<span data-ttu-id="68232-297">はい</span><span class="sxs-lookup"><span data-stu-id="68232-297">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-298">Lync Desktop 2010</span><span class="sxs-lookup"><span data-stu-id="68232-298">Lync Desktop 2010</span></span>  <br/> |<span data-ttu-id="68232-299">追加可能 (検索不可)</span><span class="sxs-lookup"><span data-stu-id="68232-299">Can add (no search)</span></span>  <br/> |<span data-ttu-id="68232-300">はい</span><span class="sxs-lookup"><span data-stu-id="68232-300">Yes</span></span>  <br/> |
|<span data-ttu-id="68232-301">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="68232-301">Lync Phone Edition</span></span>  <br/> |<span data-ttu-id="68232-302">該当なし</span><span class="sxs-lookup"><span data-stu-id="68232-302">N/A</span></span>  <br/> |<span data-ttu-id="68232-303">該当なし</span><span class="sxs-lookup"><span data-stu-id="68232-303">N/A</span></span>  <br/> |
|<span data-ttu-id="68232-304">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="68232-304">Lync Attendant</span></span>  <br/> |<span data-ttu-id="68232-305">該当なし</span><span class="sxs-lookup"><span data-stu-id="68232-305">N/A</span></span>  <br/> |<span data-ttu-id="68232-306">該当なし</span><span class="sxs-lookup"><span data-stu-id="68232-306">N/A</span></span>  <br/> |
   

