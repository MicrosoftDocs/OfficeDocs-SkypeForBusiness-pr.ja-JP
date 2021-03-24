---
title: Skype for Business Server のモビリティの展開と構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この記事では、モバイル デバイスが Skype for Business Server モビリティ機能を利用できるように、モビリティ サービスを使用する既存の Skype for Business Server インストールを構成する手順について説明します。
ms.openlocfilehash: 2ba0a81350dac6e47f4e909b4cfba256ee90de18
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103863"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="4635f-103">Skype for Business Server のモビリティの展開と構成</span><span class="sxs-lookup"><span data-stu-id="4635f-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="4635f-104">この記事では、モバイル デバイスが Skype for Business Server モビリティ機能を利用できるように、モビリティ サービスを使用する既存の Skype for Business Server インストールを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="4635f-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="4635f-105">「Plan [for Mobility for Skype for Business Server」](../plan-your-deployment/mobility.md) の記事を確認した後、以下の手順に進み、Skype for Business Server 環境に Mobility を展開する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="4635f-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="4635f-106">手順は次のとおりです (この表にアクセス許可の一覧を含めます)。</span><span class="sxs-lookup"><span data-stu-id="4635f-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="4635f-107">**フェーズ**</span><span class="sxs-lookup"><span data-stu-id="4635f-107">**Phase**</span></span>|<span data-ttu-id="4635f-108">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="4635f-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4635f-109">DNS レコードの作成</span><span class="sxs-lookup"><span data-stu-id="4635f-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="4635f-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="4635f-110">Domain Admins</span></span>  <br/> <span data-ttu-id="4635f-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="4635f-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="4635f-112">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="4635f-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="4635f-113">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="4635f-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="4635f-114">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="4635f-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="4635f-115">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="4635f-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="4635f-116">ハイブリッド展開を使用してモビリティの自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="4635f-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="4635f-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="4635f-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="4635f-118">モビリティの展開をテストする</span><span class="sxs-lookup"><span data-stu-id="4635f-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="4635f-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4635f-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="4635f-120">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="4635f-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="4635f-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4635f-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="4635f-122">モビリティ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="4635f-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="4635f-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4635f-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="4635f-124">以下のすべてのセクションには、「計画」トピックを読んだと仮定した手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4635f-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="4635f-125">何かわかりにくい場合は、その情報を自由に確認してください。</span><span class="sxs-lookup"><span data-stu-id="4635f-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="4635f-126">従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4635f-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4635f-127">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4635f-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4635f-128">MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="4635f-129">DNS レコードの作成</span><span class="sxs-lookup"><span data-stu-id="4635f-129">Create DNS records</span></span>
<span data-ttu-id="4635f-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="4635f-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="4635f-131">Skype for Business Server 環境の一部として既にこれらを使用している場合がありますが、自動検出が機能するには、次のレコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="4635f-132">組織のネットワーク内から接続しているモバイル ユーザーをサポートする内部 DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="4635f-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="4635f-133">組織のネットワーク外から接続しているモバイル ユーザーをサポートする外部 (またはパブリック) DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="4635f-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="4635f-134">これらのレコードには、A (ホスト) 名または CNAME レコードのいずれかを指定できます (両方を作成する必要はありません。ここでは、すべての手順を含むだけです)。</span><span class="sxs-lookup"><span data-stu-id="4635f-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="4635f-135">内部 DNS CNAME レコードの作成</span><span class="sxs-lookup"><span data-stu-id="4635f-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="4635f-136">ドメイン管理者グループまたは **DnsAdmins** グループのメンバーであるネットワーク内の **DNS サーバーにログイン** します。</span><span class="sxs-lookup"><span data-stu-id="4635f-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="4635f-137">[**スタート]** ボタン、[管理ツールの選択]  **([** スタート] メニューのオプションではない場合は検索が必要な場合があります **)、[DNS]** をクリックして DNS 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="4635f-138">コンソール ウィンドウの左側のウィンドウで、Skype for Business Server のフロント エンド サーバーがあるドメインに移動し、そこに [前方参照領域] を展開する **必要** があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="4635f-139">少し時間を取って、次の中のどちらを使用しているのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4635f-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="4635f-140">フロントエンド サーバー (Standard または Enterprise) またはフロント エンド プールのホスト A または AAAA レコード。</span><span class="sxs-lookup"><span data-stu-id="4635f-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="4635f-141">ディレクター プールまたはディレクター プールのホスト A または AAAA レコード (展開に必要なオプションの構成)。</span><span class="sxs-lookup"><span data-stu-id="4635f-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="4635f-142">これを確認したら、SIP ドメイン名を右クリックし、メニューから **[新しいエイリアス ] (CNAME)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4635f-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="4635f-143">[エイリアス名 **] テキスト** ボックスに、内部自動検出サービスの URL に「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4635f-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="4635f-144">上記の手順 4 で示した完全修飾ドメイン名 (ターゲット ホストの **FQDN)** で、フロント エンド プール (または単一のフロント エンド サーバー、またはディレクター プールまたはディレクター) の内部 Web サービス FQDN を入力または参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="4635f-145">これが入力された場合は、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4635f-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="4635f-146">Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照領域に新しい自動検出 CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="4635f-147">外部 DNS CNAME レコードの作成</span><span class="sxs-lookup"><span data-stu-id="4635f-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="4635f-148">これらの手順は、使用しているパブリック DNS プロバイダーを特定できないので、一般的ですが、引き続きお手伝いしたいと考えられます。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="4635f-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="4635f-149">この時点で、Skype for Business Server 用の SIP ドメインが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="4635f-150">この SIP **ドメインの前方参照領域** を展開するか、それ以外の場合は開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="4635f-151">少し時間を取って、次の中のどちらを使用しているのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4635f-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="4635f-152">フロントエンド サーバー (Standard または Enterprise) またはフロント エンド プールのホスト A または AAAA レコード。</span><span class="sxs-lookup"><span data-stu-id="4635f-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="4635f-153">ディレクター プールまたはディレクター プールのホスト A または AAAA レコード (展開に必要なオプションの構成)。</span><span class="sxs-lookup"><span data-stu-id="4635f-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="4635f-154">その情報を取得したら、新しいエイリアス (CNAME) を作成するためのオプション **を選択できる必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="4635f-155">これで、エイリアス名を入力できる **必要** があります。外部自動検出サービスの URL については、ここで lyncdiscover を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="4635f-156">次に、ターゲット ホストの FQDN に入力する領域が必要です。これは、上記の手順 3 で示したフロントエンド プール (または単一のフロント エンド サーバー、またはディレクター プールまたはディレクター) の **FQDN** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="4635f-157">ここで保存する必要がある場合や、Skype for Business Server 環境内の各 SIP ドメインの前方参照領域に追加の CNAME レコードを作成する必要がある場合は、これを行う必要がありますが、準備ができたら作業を保存します。</span><span class="sxs-lookup"><span data-stu-id="4635f-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="4635f-158">内部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4635f-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="4635f-159">ドメイン管理者グループまたは **DnsAdmins** グループのメンバーであるネットワーク内の **DNS サーバーにログイン** します。</span><span class="sxs-lookup"><span data-stu-id="4635f-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="4635f-160">[**スタート]** ボタン、[管理ツールの選択]  **([** スタート] メニューのオプションではない場合は検索が必要な場合があります **)、[DNS]** をクリックして DNS 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="4635f-161">コンソール ウィンドウの左側のウィンドウで、Skype for Business Server のフロント エンド サーバーがあるドメインに移動し、そこに [前方参照領域] を展開する **必要** があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="4635f-162">少し時間を取って、次の中のどちらを使用しているのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4635f-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="4635f-163">フロントエンド サーバー (Standard または Enterprise) またはフロント エンド プールのホスト A または AAAA レコード。</span><span class="sxs-lookup"><span data-stu-id="4635f-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="4635f-164">ディレクター プールまたはディレクター プールのホスト A または AAAA レコード (展開に必要なオプションの構成)。</span><span class="sxs-lookup"><span data-stu-id="4635f-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="4635f-165">これを確認したら、SIP ドメイン名を右クリックし、メニューから [新しいホスト (A または **AAAA)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4635f-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="4635f-166">[名前 **] テキスト** ボックスに、ホスト名の lyncdiscoverinternal と入力し、内部自動検出サービスの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4635f-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="4635f-167">**[IP アドレス] テキスト** ボックスに、上記の手順 4 で示したフロントエンド プール (または単一のフロント エンド サーバー、またはディレクター プールまたはディレクター) の内部 Web サービス IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="4635f-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="4635f-168">これが完了したら、[ホストの追加] **をクリック** し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4635f-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="4635f-169">Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照領域に新しい自動検出 A または AAAA レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="4635f-170">これを行うには、必要に応じて手順 6 ~ 8 を何度も繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4635f-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="4635f-171">完了したら、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4635f-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="4635f-172">外部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4635f-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="4635f-173">これらの手順は、使用しているパブリック DNS プロバイダーを特定できないので、一般的ですが、引き続きお手伝いしたいと考えられます。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="4635f-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="4635f-174">この時点で、Skype for Business Server 用の SIP ドメインが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="4635f-175">この SIP **ドメインの前方参照領域** を展開するか、それ以外の場合は開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="4635f-176">少し時間を取って、次の中のどちらを使用しているのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4635f-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="4635f-177">フロントエンド サーバー (Standard または Enterprise) またはフロント エンド プールのホスト A または AAAA レコード。</span><span class="sxs-lookup"><span data-stu-id="4635f-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="4635f-178">ディレクター プールまたはディレクター プールのホスト A または AAAA レコード (展開に必要なオプションの構成)。</span><span class="sxs-lookup"><span data-stu-id="4635f-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="4635f-179">その情報を取得したら、新しいホスト A または AAAA を作成するためのオプション **を選択できる必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="4635f-180">これで、名前を入力 **できる必要があります**。外部自動検出サービスの URL については、ここで lyncdiscover を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="4635f-181">**次に、IP** アドレスに入力する領域が必要です。これは、上記の手順 3 で示したフロントエンド プール (または単一のフロント エンド サーバー、またはディレクター プールまたはディレクター) の IP である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="4635f-182">ここで保存する必要がある場合や、Skype for Business Server 環境の各 SIP ドメインの前方参照領域に追加の A レコードまたは AAAA レコードを作成する必要がある場合は、これを行う必要がありますが、準備ができたら作業を保存します。</span><span class="sxs-lookup"><span data-stu-id="4635f-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="4635f-183">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="4635f-183">Modify certificates</span></span>
<span data-ttu-id="4635f-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="4635f-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="4635f-185">証明書の計画に関する質問がある場合は [、「Plan for Mobility for Skype for Business Server」の記事に記載](../plan-your-deployment/mobility.md) されています。</span><span class="sxs-lookup"><span data-stu-id="4635f-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="4635f-186">その確認が完了したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4635f-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="4635f-187">新しい証明書が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="4635f-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="4635f-188">証明機関 (CA) からの新しい証明書の要求。</span><span class="sxs-lookup"><span data-stu-id="4635f-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="4635f-189">PowerShell を使用して置換を使用してインプレイス証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="4635f-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="4635f-190">Microsoft 管理コンソール (MMC) で証明書スナップインを使用して証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="4635f-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="4635f-191">新しい証明書が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="4635f-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="4635f-192">最初に、どの証明書がインプレイスで、必要なエントリを持っているかどうかを確認し、確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="4635f-193">これを行うには、ローカル管理者であるアカウントを使用して Skype for Business Server にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="4635f-194">また、このアカウントには、発行元証明機関 (CA) に対する権限が必要な場合があります。これらの手順の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="4635f-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="4635f-195">Skype for Business Server 管理シェルを開きます ([スタート] メニューまたはタスク バーにピン留めされていない場合は、検索を使用して検索できます)。</span><span class="sxs-lookup"><span data-stu-id="4635f-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="4635f-196">更新された証明書を追加する前に、割り当てられている証明書を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="4635f-197">コマンドで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4635f-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="4635f-198">手順 3 の情報は、ユーザーに固有の情報です。</span><span class="sxs-lookup"><span data-stu-id="4635f-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="4635f-199">複数の証明書に割り当てられている証明書が 1 つなのか、必要なコンポーネントごとに異なる証明書が割り当てられているのかを確認するには、その証明書を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="4635f-200">**Use パラメーター** は、証明書の使用方法を示し、**拇** 印パラメーターは、証明書が同じ証明書か複数の証明書かを示します。</span><span class="sxs-lookup"><span data-stu-id="4635f-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="4635f-201">[計画] セクションで推奨される SAN エントリがある場合は、適切です。</span><span class="sxs-lookup"><span data-stu-id="4635f-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="4635f-202">存在しない場合は、新しい証明書、または複数の証明書 (構成に応じて) を証明機関から要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="4635f-203">証明機関 (CA) から新しい証明書または証明書を要求する</span><span class="sxs-lookup"><span data-stu-id="4635f-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="4635f-204">自分が持っている SAN エントリを確認した後、(上記の手順で確認した後で) 1 つの証明書を持っているのが分かっています。必要なすべてのエントリを持っている必要はないと学習しました。</span><span class="sxs-lookup"><span data-stu-id="4635f-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="4635f-205">CA に対して新しい証明書要求を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="4635f-206">Skype for Business Server PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="4635f-207">不足している自動検出サービス SAN の場合 (-Ca パラメーターを独自の証明機関パスに置き換える):</span><span class="sxs-lookup"><span data-stu-id="4635f-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="4635f-208">複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4635f-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="4635f-209">代わりに DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="4635f-210">DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="4635f-211">たとえば、次のようになります (-Ca パラメーターを独自の証明機関パスに置き換える)。</span><span class="sxs-lookup"><span data-stu-id="4635f-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="4635f-212">または、自分が持っている SAN エントリを確認した後、必要なすべてのエントリを持っていない複数の証明書が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4635f-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="4635f-213">CA に対して新しい証明書要求を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="4635f-214">Skype for Business Server PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="4635f-215">不足している自動検出サービス SAN の場合 (-Ca パラメーターを独自の証明機関パスに置き換える):</span><span class="sxs-lookup"><span data-stu-id="4635f-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="4635f-216">複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4635f-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="4635f-217">代わりに DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="4635f-218">DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="4635f-219">例は次のようになります (-Ca パラメーターを独自の証明機関パスに置き換える)。</span><span class="sxs-lookup"><span data-stu-id="4635f-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="4635f-220">CA によって新しい証明書が生成されると、それらを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4635f-221">Skype for Business Server 管理シェルを使用して証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="4635f-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="4635f-222">上記の [新しい認定が必要な場合] セクションで見つけた内容に応じて、次のいずれかを実行 **する** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="4635f-223">すべての証明書が 1 つ (拇印が同一) の場合は、次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="4635f-224">異なる証明書がある場合 (拇印はすべて異なります)、代わりに次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4635f-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="4635f-225">Microsoft 管理コンソール (MMC) での証明書の表示</span><span class="sxs-lookup"><span data-stu-id="4635f-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="4635f-226">MMC の証明書スナップインを使用して証明書を確認するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4635f-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="4635f-227">MMC を検索に入力するだけで、アプリケーション オプションとしてポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="4635f-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="4635f-228">証明書スナップインを追加するには、[ファイル] をクリックし、[スナップインの追加 **と削除]** をクリックする必要があります。(またはキーボード ショートカット Ctrl **+ M** も機能します)。</span><span class="sxs-lookup"><span data-stu-id="4635f-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="4635f-229">**左側の** ウィンドウで証明書を選択し、ポップアップ ウィンドウで [ **コンピューター** アカウント] を選択し、[次へ] の順に **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="4635f-230">それでも、ポップアップ ウィンドウでは、確認する必要がある証明書が保存されているコンピューターでこれを行う可能性が高いので、ローカル コンピューターで選択したままにします。そうである場合は、ローカル コンピューターで選択を残します。</span><span class="sxs-lookup"><span data-stu-id="4635f-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="4635f-231">リモート コンピューターで作業している場合は、ラジオ ボタンを [別のコンピューター] に変更し、そのコンピューターの FQDNを入力するか、[参照] ボタンを使用して AD を通じてそのコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="4635f-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="4635f-232">コンピューターを選択した後、準備ができたら [完了]をクリックし **、[OK]** をクリックしてスナップインを MMC に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="4635f-233">MMC **の左側** のウィンドウで [証明書] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="4635f-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="4635f-234">[個人用] **フォルダーも** 展開し、[証明書] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="4635f-235">これにより、このストアに証明書を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="4635f-236">表示する証明書を見つけて右クリックし、[開く] を選択する必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4635f-237">これが何の証明書かを知る方法は?</span><span class="sxs-lookup"><span data-stu-id="4635f-237">How do you know what certificate this is?</span></span> <span data-ttu-id="4635f-238">ファームのすべてに割り当てられた単一の証明書か、Default、Internal Web Services など、さまざまなものに対して複数の証明書を持つ必要があります。その場合は、複数の証明書を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="4635f-239">複数の証明書が同じ拇印を持つ。</span><span class="sxs-lookup"><span data-stu-id="4635f-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="4635f-240">[証明書] ビューにアクセスしたら **、[詳細** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="4635f-241">これにより、[サブジェクト] を選択すると証明書のサブジェクト名が表示され、割り当てられたサブジェクト名と関連付けられたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4635f-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="4635f-242">サブジェクト代替名エントリも確認 **する** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="4635f-243">次の 1 つ以上の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4635f-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="4635f-244">このプールのプール名、またはプールではない場合は単一のサーバー名。</span><span class="sxs-lookup"><span data-stu-id="4635f-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="4635f-245">証明書が割り当てられているサーバー名。</span><span class="sxs-lookup"><span data-stu-id="4635f-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="4635f-246">単純な URL レコード (通常は会議とダイヤルイン)。</span><span class="sxs-lookup"><span data-stu-id="4635f-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="4635f-247">トポロジ ビルダーおよび過剰な Web サービスの選択で行われた選択に基づいて、Web サービスの内部および Web サービスの外部名 (webpool01.contoso.net、webpool01.contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="4635f-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="4635f-248">既に割り当てられている場合は、lyncdiscover。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="4635f-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="4635f-249">lyncdiscoverinternal。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="4635f-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="4635f-250">レコード。</span><span class="sxs-lookup"><span data-stu-id="4635f-250">records.</span></span>
    
     <span data-ttu-id="4635f-251">複数の証明書が割り当てられている場合は、複数の証明書を確認する必要があります (上記のメモを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="4635f-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="4635f-252">したがって、lyncdiscover が見つかった場合。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="4635f-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="4635f-253">lyncdiscoverinternal。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="4635f-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="4635f-254">レコードの場合は、既に構成済みです。</span><span class="sxs-lookup"><span data-stu-id="4635f-254">records, you've got this configured already.</span></span> <span data-ttu-id="4635f-255">MMC を閉じできます。</span><span class="sxs-lookup"><span data-stu-id="4635f-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="4635f-256">割り当てられていない場合は、新しい証明書要求 (上記で説明) を行う必要があります。または、要求後にインストールする必要があります (このため、上記の PowerShell を次に示す方法をお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="4635f-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="4635f-257">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="4635f-257">Configure the reverse proxy</span></span>
<span data-ttu-id="4635f-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="4635f-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="4635f-259">以下の手順は、正確に従う必要があるという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="4635f-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="4635f-260">これは、以前のバージョンの製品では、たとえば、脅威管理ゲートウェイ (TMG) の構成などについて説明し、それを使用しない場合は、そこから独自のバージョンを作成する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="4635f-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="4635f-261">TMG は製品として Microsoft によって提供されなくなりました。それでも構成する必要がある場合は [、Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility)の手順を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility).</span></span> <span data-ttu-id="4635f-262">ただし、以下の情報は、すべてのリバース プロキシに対して特定のウォークスルー 手順を提供する方法がない場合でも、より一般的に役立つ情報を提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="4635f-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="4635f-263">考慮すべき主な点は次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="4635f-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="4635f-264">HTTPS 経由で最初の自動検出要求を実行するつもりですか (推奨)</span><span class="sxs-lookup"><span data-stu-id="4635f-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="4635f-265">Web 発行ルールがある場合は、変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="4635f-266">Web 発行ルールがまだない場合は、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="4635f-267">HTTP で最初の自動検出要求を実行する場合は、そのルールも作成または変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4635f-268">**重要** プロキシのタイム アウト値は、展開によって異なる数値です。</span><span class="sxs-lookup"><span data-stu-id="4635f-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="4635f-269">展開を監視し、クライアントに最適なエクスペリエンスを得る値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="4635f-270">値を 200 に設定できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="4635f-271">環境で Lync モバイル クライアントをサポートしている場合は、Office 365 からのプッシュ通知のタイム アウトを許可する値を 960 に設定する必要があります。これは、タイム アウト値が 900 です。</span><span class="sxs-lookup"><span data-stu-id="4635f-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="4635f-272">値が小さすぎるとクライアントの切断を回避するために、タイム アウト値を大きくする必要がある可能性が非常に高く、プロキシ経由の接続が切断されないが、クライアントが切断された後に長くクリアする場合は、数を減らします。</span><span class="sxs-lookup"><span data-stu-id="4635f-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="4635f-273">環境に対して通常の状態を監視およびベース化する方法は、この値の適切な設定を決定する唯一の正確な方法です。</span><span class="sxs-lookup"><span data-stu-id="4635f-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="4635f-274">外部自動検出 SAN と URL の既存の Web 発行ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="4635f-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="4635f-275">リバース プロキシ インターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="4635f-276">Web 発行ルールを見つけて、[編集] オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブに表示される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="4635f-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="4635f-277">この Web 発行ルールの適用条件を示す領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="4635f-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="4635f-278">受信サイトまたはサイトの要求に対してこのルールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="4635f-279">新しいエントリを **追加** します。</span><span class="sxs-lookup"><span data-stu-id="4635f-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="4635f-280">自動検出サイトの名前を入力し (使用する例は lyncdiscover.contoso.com)、リバース プロキシの形式に応じて **[OK]** または [保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4635f-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="4635f-281">自動検出 SAN エントリを含む新しい証明書がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="4635f-282">リバース プロキシの設定に従って使用するようにインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="4635f-283">構成が完了したら、必ずすべてを保存してください。</span><span class="sxs-lookup"><span data-stu-id="4635f-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="4635f-284">リバース プロキシにテスト機能 **がある** 場合は、その機能を利用して、すべてが正しく動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="4635f-285">ここで、環境にディレクター またはディレクター プールがある場合は、これらの手順を繰り返す必要があります (これは、2 番目のルールがあるという意味です)。</span><span class="sxs-lookup"><span data-stu-id="4635f-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="4635f-286">外部自動検出 URL の Web 発行ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="4635f-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="4635f-287">リバース プロキシ インターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="4635f-288">Web 発行ルールを作成するインターフェイス内の場所を見つけて、[新規] または [作成]オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブにある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="4635f-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="4635f-289">新しい Web 発行ルールを作成するオプションを探しています。</span><span class="sxs-lookup"><span data-stu-id="4635f-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="4635f-290">通常、次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="4635f-291">**名前**: ルールの名前</span><span class="sxs-lookup"><span data-stu-id="4635f-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="4635f-292">**ルールアクション**: この場合、 **許可ルールは** 、リバース プロキシを通過させるルールです。</span><span class="sxs-lookup"><span data-stu-id="4635f-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="4635f-293">選択 **する発行** ルールまたはオプションは、単一 **の Web サイトまたはロード バランサーになります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="4635f-294">これは、外部アクセス用 **の SSL** である必要があります。そのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4635f-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="4635f-295">内部発行のパスを発行し、フロントエンド プールのロード バランサー (またはディレクター プールのロード バランサーの FQDN) に外部 Web サービスの FQDN を入力する必要があります。たとえば、sfb_pool01.contoso.local です。</span><span class="sxs-lookup"><span data-stu-id="4635f-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="4635f-296">発行するパスとして _ と入力する必要がありますが、元のホスト ヘッダー **/\\** \**を _*forward する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="4635f-297">パブリックまたは外部の名前の **詳細または情報の** オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4635f-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="4635f-298">これは、入力できる場所です。</span><span class="sxs-lookup"><span data-stu-id="4635f-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="4635f-299">**要求を受け** 入れるが、ドメイン名用である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="4635f-300">[名前 **] に\*\*\*\*「lyncdiscover」と入力する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="4635f-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="4635f-301"><sipdomain> (これは外部自動検出サービスの URL です)。</span><span class="sxs-lookup"><span data-stu-id="4635f-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="4635f-302">ここで、フロントエンド プールに外部 Web サービス URL のルールを作成する場合は、フロントエンド プールの外部 Web サービスの FQDN を入力する必要があります (たとえば、lyncwebextpool01.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="4635f-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="4635f-303">[パス] オプション **が** 表示され、ここに \* と入力 **/\\** する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-303">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="4635f-304">最新のパブリック証明書を使用して **SSL リスナー** を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-304">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="4635f-305">**認証委任は** [委任なし] **に設定する** 必要がありますが、直接 **クライアント認証を** 許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="4635f-306">ルールは [すべてのユーザー] **に設定する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="4635f-307">これは、このルールを作成し、続行するために必要なすべての情報である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="4635f-308">元のホスト ヘッダーが転送されるの **を確認する** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="4635f-309">Web **サーバー ポート** も設定する必要があります。次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="4635f-310">**要求を HTTP ポートにリダイレクトし** 、ポート番号は **8080 である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="4635f-311">**要求を SSL ポートにリダイレクトし** 、ポート番号は **4443 である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="4635f-312">すべてが構成されている場合は、これらを保存または適用し、ルールをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="4635f-313">ポート 80 の Web 発行ルールを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="4635f-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="4635f-314">リバース プロキシ インターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="4635f-315">Web 発行ルールを作成するインターフェイス内の場所を見つけて、[新規] または [作成]オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブにある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="4635f-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="4635f-316">新しい Web 発行ルールを作成するオプションを探しています。</span><span class="sxs-lookup"><span data-stu-id="4635f-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="4635f-317">通常、次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="4635f-318">**名前**: ルールの名前</span><span class="sxs-lookup"><span data-stu-id="4635f-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="4635f-319">**ルールアクション**: この場合、 **許可ルールは** 、リバース プロキシを通過させるルールです。</span><span class="sxs-lookup"><span data-stu-id="4635f-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="4635f-320">選択 **する発行** ルールまたはオプションは、単一 **の Web サイトまたはロード バランサーになります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="4635f-321">公開された Web サーバーまたはファームに接続するには、セキュリティで保護されていない **接続である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="4635f-322">内部発行のパスを発行し、フロントエンド プールのロード バランサーの VIP アドレスの **FQDN** を入力する必要があります。例は sfb_pool01.contoso.local です。</span><span class="sxs-lookup"><span data-stu-id="4635f-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="4635f-323">発行するパスとして _ と入力する必要がありますが、元のホスト ヘッダー **/\\** \**を _*forward する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="4635f-324">パブリックまたは外部の名前の **詳細または情報の** オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4635f-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="4635f-325">これは、入力できる場所です。</span><span class="sxs-lookup"><span data-stu-id="4635f-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="4635f-326">**要求を受け** 入れるが、ドメイン名用である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="4635f-327">[名前 **] に\*\*\*\*「lyncdiscover」と入力する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="4635f-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="4635f-328"><sipdomain> (これは外部自動検出サービスの URL です)。</span><span class="sxs-lookup"><span data-stu-id="4635f-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="4635f-329">[パス] オプション **が** 表示され、ここに \* と入力 **/\\** する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-329">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="4635f-330">Web リスナーを選択するか、リバース プロキシで作成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="4635f-331">**[認証委任** ] を **[委任** なし] に設定する必要がありますが、直接クライアント認証 **は** 許可されません。</span><span class="sxs-lookup"><span data-stu-id="4635f-331">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="4635f-332">ルールは [すべてのユーザー] **に設定する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="4635f-333">これは、このルールを作成し、続行するために必要なすべての情報である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="4635f-334">Web **サーバー ポート** を設定する必要があります。次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="4635f-335">**要求を HTTP ポートにリダイレクトし** 、ポート番号は **8080 である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="4635f-336">**要求を SSL ポートにリダイレクトし** 、ポート番号は **4443 である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4635f-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="4635f-337">すべてが構成されている場合は、これらを保存または適用し、ルールをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="4635f-338">ハイブリッド展開を使用してモビリティの自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="4635f-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="4635f-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="4635f-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="4635f-340">Skype for Business Server のハイブリッド環境は、オンプレミス環境と O365 環境を組み合わせた環境です。</span><span class="sxs-lookup"><span data-stu-id="4635f-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="4635f-341">Skype for Business Server がハイブリッド環境で動作している場合、自動検出サービスは、これらの環境のどちらかからユーザーを見つけ出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="4635f-342">モバイル クライアントがユーザーの場所を検出するには、自動検出サービスを新しい統一リソース ロケーター (URL) で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="4635f-343">手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4635f-343">The steps are:</span></span>
  
1. <span data-ttu-id="4635f-344">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4635f-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="4635f-345">次のコマンドを実行して、Skype for Business Server 環境の **ProxyFQDN** 属性の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4635f-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="4635f-346">次に、シェル ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4635f-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="4635f-347">[identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4635f-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="4635f-348">モビリティの展開をテストする</span><span class="sxs-lookup"><span data-stu-id="4635f-348">Test your Mobility deployment</span></span>
<span data-ttu-id="4635f-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="4635f-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="4635f-350">Skype for Business Server Mobility Service と Skype for Business Server Autodiscover Service を展開したら、テスト トランザクションを実行して、展開が正しく機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="4635f-351">**Test-CsUcwaConference** を実行して、2 人のユーザーが会議を作成、参加、通信する機能をテストできます。</span><span class="sxs-lookup"><span data-stu-id="4635f-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="4635f-352">このテストを実行するには、2 人のユーザー (実際またはテスト) と完全な資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="4635f-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="4635f-353">このコマンドは、Skype for Business クライアントと Lync Server 2013 クライアントの両方で機能します。</span><span class="sxs-lookup"><span data-stu-id="4635f-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="4635f-354">Skype for Business Server 2015 の Lync Server 2010 クライアントの場合は **、Test-CsMcxP2PIM** を実行してテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="4635f-355">Lync Server 2010 ユーザーは、実際のユーザー、または定義済みのテスト ユーザーである必要があります。パスワード資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="4635f-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="4635f-356">従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4635f-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4635f-357">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4635f-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4635f-358">MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="4635f-359">Skype for Business および Lync 2013 モバイル クライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="4635f-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="4635f-360">**Skype for Business Server** Management Shell と **Ocscore** がインストールされている任意のコンピューターで **、CsAdministrator** 役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4635f-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4635f-361">Skype **for Business Server 管理シェルを起動** します (検索に名前を入力するか、[すべてのプログラム] に移動 **して選択します** )。</span><span class="sxs-lookup"><span data-stu-id="4635f-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="4635f-362">コマンド ラインで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4635f-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="4635f-363">スクリプトで資格情報を設定し、テスト コマンドレットに渡す方法も可能です。</span><span class="sxs-lookup"><span data-stu-id="4635f-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="4635f-364">この例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4635f-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="4635f-365">Lync 2010 モバイル クライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="4635f-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="4635f-366">従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4635f-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4635f-367">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4635f-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4635f-368">MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="4635f-369">**Skype for Business Server** Management Shell と **Ocscore** がインストールされている任意のコンピューターで **、CsAdministrator** 役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4635f-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4635f-370">Skype **for Business Server 管理シェルを起動** します (検索に名前を入力するか、[すべてのプログラム] に移動 **して選択します** )。</span><span class="sxs-lookup"><span data-stu-id="4635f-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="4635f-371">コマンド ラインで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4635f-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="4635f-372">スクリプトで資格情報を設定し、テスト コマンドレットに渡す方法も可能です。</span><span class="sxs-lookup"><span data-stu-id="4635f-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="4635f-373">この例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4635f-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="4635f-374">さらにコマンド手順を確認するには [、Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) と [Test-CsMcxP2PIM を確認できます](/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4635f-374">To review the command procedures further, you can check out [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="4635f-375">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="4635f-375">Configure for push notifications</span></span>
<span data-ttu-id="4635f-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="4635f-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="4635f-377">プッシュ通知は、バッジ、アイコン、またはアラートの形式で、Skype または Lync アプリが非アクティブな場合でもモバイル デバイスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="4635f-378">しかし、プッシュ通知とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="4635f-378">But what are push notifications?</span></span> <span data-ttu-id="4635f-379">これらは、新しい IM の招待や未承諾の IM 招待、または受信したボイスメールに関するイベント 通知です。</span><span class="sxs-lookup"><span data-stu-id="4635f-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="4635f-380">Skype for Business Server Mobility サービスは、これらの通知をクラウドベースの Skype for Business Server プッシュ通知サービスに送信し、Windows Phone ユーザー向け Microsoft プッシュ通知サービス (MSNS) に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="4635f-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="4635f-381">この機能は Lync Server 2013 から変更されませんが、Skype for Business Server を使用している場合は、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="4635f-382">Skype for Business Server エッジ サーバーの場合は、新しいホスティング プロバイダーである Microsoft Skype for Business Online を追加し、組織と Skype for Business Online 間のホスティング プロバイダー フェデレーションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="4635f-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="4635f-383">**Set-CsPushNotificationConfiguration コマンドレットを実行してプッシュ通知を有効** にします。</span><span class="sxs-lookup"><span data-stu-id="4635f-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="4635f-384">既定では、プッシュ通知はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="4635f-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="4635f-385">フェデレーション構成とプッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="4635f-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="4635f-386">プッシュ通知用に Skype for Business エッジ サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="4635f-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="4635f-387">**CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4635f-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4635f-388">Skype **for Business Server 管理シェルを起動します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4635f-389">Skype for Business Server オンライン ホスティング プロバイダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4635f-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="4635f-390">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4635f-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="4635f-391">1 つのホスティング プロバイダーと複数のフェデレーション関係を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="4635f-392">したがって、sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既にセットアップしている場合は、ホスティング プロバイダーの ID が SkypeOnline 以外の場合でも、別のホスティング プロバイダーを追加しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="4635f-393">Skype for Business Online で組織とプッシュ通知サービスの間のホスティング プロバイダー フェデレーションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="4635f-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="4635f-394">コマンド ラインで、次の入力が必要です。</span><span class="sxs-lookup"><span data-stu-id="4635f-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="4635f-395">プッシュ通知を有効にする</span><span class="sxs-lookup"><span data-stu-id="4635f-395">Enable push notifications</span></span>

1. <span data-ttu-id="4635f-396">**CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4635f-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4635f-397">Skype **for Business Server 管理シェルを起動します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4635f-398">プッシュ通知を有効にする:</span><span class="sxs-lookup"><span data-stu-id="4635f-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="4635f-399">フェデレーションを有効にする:</span><span class="sxs-lookup"><span data-stu-id="4635f-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="4635f-400">フェデレーションとプッシュ通知のテスト</span><span class="sxs-lookup"><span data-stu-id="4635f-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="4635f-401">**CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4635f-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4635f-402">Skype **for Business Server 管理シェルを起動します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4635f-403">フェデレーション構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="4635f-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="4635f-404">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4635f-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="4635f-405">プッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="4635f-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="4635f-406">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4635f-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="4635f-407">モビリティ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="4635f-407">Configure Mobility policy</span></span>
<span data-ttu-id="4635f-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="4635f-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="4635f-409">Skype for Business Server を使用して、モビリティ サービスを使用できるユーザー、仕事で通話できるユーザー、ボイス オーバー IP (VoIP)、ビデオ、および VoIP またはビデオに WiFi が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="4635f-410">[仕事による通話] を使用すると、携帯電話の通話を送受信するときに、携帯電話番号の代わりに、モバイル ユーザーが自分の電話番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="4635f-411">回線のもう一方の端のユーザーは、そのモバイル ユーザーの携帯電話番号を表示し、モバイル ユーザーが発信通話料金を回避できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="4635f-412">VoIP とビデオが設定されている場合、ユーザーは VoIP 通話とビデオを受け取って行います。</span><span class="sxs-lookup"><span data-stu-id="4635f-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="4635f-413">WiFi 使用状況の設定によって、ユーザーのモバイル デバイスが携帯電話データ ネットワークを使用して WiFi ネットワークを使用する必要が生じするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4635f-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="4635f-414">モビリティ、仕事による通話、VoIP 機能とビデオ機能はすべて既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4635f-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="4635f-415">VoIP とビデオに WiFi を要求する設定は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4635f-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="4635f-416">管理者は、これをグローバルに、サイト別、またはユーザー別に変更できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="4635f-417">モビリティ機能と仕事を通じて通話を使用するには、次の条件を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4635f-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="4635f-418">Skype for Business Server で有効</span><span class="sxs-lookup"><span data-stu-id="4635f-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="4635f-419">[有効] エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="4635f-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="4635f-420">**EnableMobility** オプションが True に設定されているモビリティ ポリシーが割り当 **て済みです**。</span><span class="sxs-lookup"><span data-stu-id="4635f-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="4635f-421">ユーザーが仕事で通話を使用するには、次の機能も必要です。</span><span class="sxs-lookup"><span data-stu-id="4635f-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="4635f-422">[電話の同時呼び出しを有効にする] オプションが選択されている音声ポリシー **が** 割り当てされました。</span><span class="sxs-lookup"><span data-stu-id="4635f-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="4635f-423">**EnableOutsideVoice** が True に設定されているモビリティ ポリシーが割り当 **て済みです**。</span><span class="sxs-lookup"><span data-stu-id="4635f-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4635f-424">エンタープライズ VoIP が有効になっていないユーザーは、モバイル デバイスを使用して Skype to Skype VoIP 通話を行い、または関連付けられている Voice ポリシーに対して適切なオプションが設定されている場合は、モバイル デバイスで [クリックして参加] リンクを使用して会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="4635f-425">PLANNING に関するトピックの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="4635f-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="4635f-426">グローバル モビリティ ポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="4635f-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="4635f-427">**CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4635f-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4635f-428">Skype **for Business Server 管理シェルを起動します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4635f-429">次のように入力して、Mobility と Call via Work へのアクセスをグローバルにオフにします。</span><span class="sxs-lookup"><span data-stu-id="4635f-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="4635f-430">モビリティへのアクセスをオフにすることなく、仕事で通話をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="4635f-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="4635f-431">ただし、仕事で通話をオフにしない場合は、モビリティをオフに設定できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="4635f-432">詳細については [、「Set-CsMobilityPolicy」を参照してください](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4635f-432">For more info, check out [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="4635f-433">サイト別にモビリティ ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="4635f-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="4635f-434">**CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4635f-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4635f-435">Skype **for Business Server 管理シェルを起動します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4635f-436">サイト レベルのポリシーを作成し、VoIP とビデオをオフにし、[IP オーディオに WiFi を要求する] と [サイト別 IP ビデオに WiFi を要求する] を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4635f-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="4635f-437">種類:</span><span class="sxs-lookup"><span data-stu-id="4635f-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="4635f-438">詳細については [、「New-CsMobilityPolicy」を参照してください](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4635f-438">Learn more at [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="4635f-439">ユーザーによるモビリティ ポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="4635f-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="4635f-440">**CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4635f-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4635f-441">Skype **for Business Server 管理シェルを起動します**。</span><span class="sxs-lookup"><span data-stu-id="4635f-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4635f-442">ユーザー レベルのモビリティ ポリシーを作成し、モビリティとユーザーによる仕事による通話をオフにします。</span><span class="sxs-lookup"><span data-stu-id="4635f-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="4635f-443">種類:</span><span class="sxs-lookup"><span data-stu-id="4635f-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="4635f-444">サンプル データの追加例:</span><span class="sxs-lookup"><span data-stu-id="4635f-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="4635f-445">モビリティへのアクセスをオフにすることなく、仕事で通話をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="4635f-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="4635f-446">ただし、仕事で通話をオフにしない場合は、モビリティをオフに設定できます。</span><span class="sxs-lookup"><span data-stu-id="4635f-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
