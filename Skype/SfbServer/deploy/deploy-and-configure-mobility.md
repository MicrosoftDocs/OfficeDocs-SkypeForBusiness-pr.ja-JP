---
title: 展開し、Skype のビジネスのサーバーの移動を構成します。
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この資料でを Skype ビジネス サーバー移動機能を利用できるモバイル デバイスをできるように、モバイル サービスを使用するビジネスのサーバーのインストールに既存の Skype を構成する手順を説明します。
ms.openlocfilehash: e1799459d2e7723298aa7fdda17f89a9041efd15
ms.sourcegitcommit: e93b12f5ebaad1140d7df798b5e0647197b9213d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2018
ms.locfileid: "26649716"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="e52ca-103">展開し、Skype のビジネスのサーバーの移動を構成します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="e52ca-104">この資料でを Skype ビジネス サーバー移動機能を利用できるモバイル デバイスをできるように、モバイル サービスを使用するビジネスのサーバーのインストールに既存の Skype を構成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="e52ca-105">[Skype ビジネス サーバーの移動の計画](../plan-your-deployment/mobility.md)の資料を確認し、する必要がありますビジネス サーバー環境で、Skype にモビリティを展開する次の手順を続行する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e52ca-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="e52ca-106">手順は次のとおりです (この表には許可一覧も含めます)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="e52ca-107">**段階**</span><span class="sxs-lookup"><span data-stu-id="e52ca-107">**Phase**</span></span>|<span data-ttu-id="e52ca-108">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="e52ca-108">**Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e52ca-109">
            「[DNS レコードの作成](deploy-and-configure-mobility.md#CreateDNSRec)」</span><span class="sxs-lookup"><span data-stu-id="e52ca-109">[Create DNS records](deploy-and-configure-mobility.md#CreateDNSRec)</span></span> <br/> |<span data-ttu-id="e52ca-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="e52ca-110">Domain Admins</span></span>  <br/> <span data-ttu-id="e52ca-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="e52ca-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="e52ca-112">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="e52ca-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="e52ca-113">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="e52ca-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="e52ca-114">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="e52ca-115">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="e52ca-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="e52ca-116">ハイブリッド展開でのモビリティの自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="e52ca-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="e52ca-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="e52ca-118">モビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="e52ca-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="e52ca-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e52ca-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="e52ca-120">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="e52ca-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e52ca-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="e52ca-122">モビリティ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="e52ca-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e52ca-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="e52ca-p102">次のすべてのセクションには、計画トピックを読んでいることが前提となる手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="e52ca-126">従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e52ca-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e52ca-127">ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e52ca-128">MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="e52ca-129">DNS レコードの作成</span><span class="sxs-lookup"><span data-stu-id="e52ca-129">Create DNS records</span></span>
<span data-ttu-id="e52ca-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="e52ca-130"></span></span>

<span data-ttu-id="e52ca-131">ビジネス サーバー環境で、Skype の一部としてこれらを既に必要がありますが、操作する自動検出のための次のレコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="e52ca-132">組織のネットワーク内から接続するモバイル ユーザーをサポートするための内部 DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="e52ca-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="e52ca-133">組織のネットワーク外から接続するモバイル ユーザーをサポートするための外部 (またはパブリック) DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="e52ca-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="e52ca-134">これらのレコードは、A (ホスト) 名または CNAME のどちらかにできます (両方作成する必要はなく、すべての手順がここに含まれています)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="e52ca-135">内部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="e52ca-136">**Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="e52ca-137">[**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="e52ca-138">コンソール ウィンドウの左側のペインでは、ドメインに移動する必要がありますのビジネス サーバーのフロント エンド サーバーでは、Skype をホームし、が**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="e52ca-139">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="e52ca-140">(標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。</span><span class="sxs-lookup"><span data-stu-id="e52ca-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="e52ca-141">任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="e52ca-142">判別できたら SIP ドメイン名を右クリックしてから、[**新しいエイリアス (CNAME)**] をメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="e52ca-143">[**エイリアス名**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="e52ca-144">**完全修飾ドメイン名 (ターゲットのホストに対して FQDN を**をフロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上記の手順 4 で特定の内部の Web サービスの FQDN を入力または参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="e52ca-145">入力したら、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="e52ca-146">ビジネス サーバー環境に、Skype でサポートされている各 SIP ドメインの前方参照ゾーンに新しい自動検出の CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="e52ca-147">外部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="e52ca-148">ご利用のパブリック DNS プロバイダーが分かりませんので、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="e52ca-149">この時点では、SIP ドメインは既に存在してある Skype のビジネス サーバーの。</span><span class="sxs-lookup"><span data-stu-id="e52ca-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="e52ca-150">この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="e52ca-151">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="e52ca-152">(標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。</span><span class="sxs-lookup"><span data-stu-id="e52ca-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="e52ca-153">任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="e52ca-154">その情報が得られたら、[**新しいエイリアス (CNAME)**] の作成オプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="e52ca-155">[**エイリアス名**] を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="e52ca-156">次に**ターゲット ・ ホストの FQDN**を入力する領域が存在する必要があります、これは、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上記の手順 3 で特定の FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="e52ca-157">ここでは、保存する必要があります。 またはビジネス サーバー環境に、Skype では、各 SIP ドメインの前方参照ゾーンに追加の CNAME レコードを作成する場合は、する必要がありますが、あなたが準備ができて、作業内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="e52ca-158">内部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="e52ca-159">**Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="e52ca-160">[**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="e52ca-161">コンソール ウィンドウの左側のペインでは、ドメインに移動する必要がありますのビジネス サーバーのフロント エンド サーバーでは、Skype をホームし、が**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="e52ca-162">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="e52ca-163">(標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。</span><span class="sxs-lookup"><span data-stu-id="e52ca-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="e52ca-164">任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="e52ca-165">判別できたら SIP ドメイン名を右クリックしてから、[**新しいホスト (A または AAAA)**] をメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="e52ca-166">[**名前**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="e52ca-167">[ **IP アドレス**] ボックスで、上記の手順 4 では、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、内部の Web サービスの IP アドレスの種類が識別されます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="e52ca-168">入力したら [**ホストの追加**] をクリックしてから [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="e52ca-169">ビジネス サーバー環境に、Skype でサポートされている各 SIP ドメインの前方参照ゾーンで新しいの自動検出の A または AAAA レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="e52ca-170">これを行うには手順 6 - 8 を必要な回数繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="e52ca-171">終了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="e52ca-172">外部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="e52ca-173">ご利用のパブリック DNS プロバイダーがわからないため、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="e52ca-174">この時点では、SIP ドメインは既に存在してある Skype のビジネス サーバーの。</span><span class="sxs-lookup"><span data-stu-id="e52ca-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="e52ca-175">この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="e52ca-176">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="e52ca-177">(標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。</span><span class="sxs-lookup"><span data-stu-id="e52ca-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="e52ca-178">任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="e52ca-179">その情報が得られたら、[**新しいホスト A または AAAA**] の作成オプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="e52ca-180">**エイリアス名**を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="e52ca-181">次の**IP アドレス**を入力する領域が存在する必要があります、これは、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上の手順 3 で特定の ip アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="e52ca-182">ここでは、保存する必要があります。 または追加作成する必要がある場合 A または AAAA レコード各 SIP ドメインの前方参照ゾーンで、Skype をビジネスのサーバー環境のを行う必要がありますが、1 回の準備が整ったら、作業を保存します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="e52ca-183">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="e52ca-183">Modify certificates</span></span>
<span data-ttu-id="e52ca-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="e52ca-184"></span></span>

<span data-ttu-id="e52ca-185">証明書に関する計画についての疑問があれば、私たちしたを資料に記載されて、 [Skype のビジネス サーバーの移動を計画](../plan-your-deployment/mobility.md)します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="e52ca-186">それを読んだ後で、以下の点を説明します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="e52ca-187">新しい証明書が必要か。</span><span class="sxs-lookup"><span data-stu-id="e52ca-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="e52ca-188">認証局 (CA) に新しい証明書を申請する。</span><span class="sxs-lookup"><span data-stu-id="e52ca-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="e52ca-189">PowerShell を使用して、使用中の証明書をアップグレードする。</span><span class="sxs-lookup"><span data-stu-id="e52ca-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="e52ca-190">Microsoft 管理コンソール (MMC) で証明書スナップインを使用して証明書を確認しています。</span><span class="sxs-lookup"><span data-stu-id="e52ca-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="e52ca-191">新しい証明書が必要か。</span><span class="sxs-lookup"><span data-stu-id="e52ca-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="e52ca-192">まず使用中の証明書の内容を確認して、必要とするエントリーの有無を調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="e52ca-193">ローカル管理者であるアカウントを使用してビジネス サーバー、Skype にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="e52ca-194">このアカウントには、手順中のいくつかで認証局 (CA) の発行権限も必要とされます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="e52ca-195">ビジネス サーバー管理シェルには (場合は、[スタート] メニューまたはタスク バーに固定されていることがあるないことを検索する検索を使用できます)、Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="e52ca-p110">更新された証明書の追加を行う前に、すでに付与されている証明書の内容を知っておくことが重要となります。コマンドで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="e52ca-p111">手順 3 で得られた情報は固有の内容です。内容を吟味して、複数のことに対して単一の証明書が付与されているのか、それとも証明書を必要とする別々のコンポーネントに別の証明書が付与されているのか判断します。**Use** パラメーターを使用すれば、証明書がどのように使われているかが分かり、**Thumbprint** パラメーターを使用すれば、証明書が同一か別々かが分かります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="e52ca-p112">計画セクションで推奨されている SAN エントリーがあれば、申し分ありません。ない場合は、新規の証明書を 1 つ または複数の証明書を認証局に申請する必要があります (構成に依存します)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="e52ca-203">認証局 (CA) に新しい証明書を申請する。</span><span class="sxs-lookup"><span data-stu-id="e52ca-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="e52ca-204">あるどのような SAN エントリを参照するを確認して後、知っている (確認後上記の手順を使用して)、**単一の証明書**があるし、する必要があるすべてのエントリがないと説明しました。</span><span class="sxs-lookup"><span data-stu-id="e52ca-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="e52ca-205">新しい証明書要求を CA になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="e52ca-206">ビジネス サーバー PowerShell の Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="e52ca-207">欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="e52ca-208">ここで、複数の SIP ドメインがあれば、上記の例に示すように AllSipDomain パラメーターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e52ca-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="e52ca-209">代わりに DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="e52ca-210">DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="e52ca-211">一例として次のようになります (-Ca パラメーターを自分の認証局パスで置き換える)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="e52ca-212">または、必要なすべてのエントリがない**複数の証明書**があるが見つかりましたが、どのような SAN エントリを参照するを確認して後、。</span><span class="sxs-lookup"><span data-stu-id="e52ca-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="e52ca-213">新しい証明書要求を CA になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="e52ca-214">ビジネス サーバー PowerShell の Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="e52ca-215">欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="e52ca-216">ここで、複数の SIP ドメインがあれば、上記の例に示すように AllSipDomain パラメーターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e52ca-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="e52ca-217">代わりに DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="e52ca-218">DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="e52ca-219">次のような例になります (-Ca パラメーターを自分の認証局パスで置き換える)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="e52ca-220">CA により新しい証明書が作成されたら、それを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e52ca-221">Skype for Business Server 管理シェルを使用して証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="e52ca-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="e52ca-222">「新しい証明書が必要か」のセクションで判明した内容に応じて、次のうちの**いずれか 1 つ**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="e52ca-223">すべてに対して単一の証明書しかない (どの thumbprint も同じ) 場合、これを実行します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="e52ca-224">別々の証明書が付与されている (thumbprint が異なる) 場合、代わりにこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="e52ca-225">Microsoft 管理コンソール (MMC)</span><span class="sxs-lookup"><span data-stu-id="e52ca-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="e52ca-p117">MMC の証明書スナップインを使用して、証明書を調べるオプションを利用します。検索に MMC と入力すれば、アプリケーション オプションのようにポップアップします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="e52ca-p118">証明書スナップインを追加するには、「**ファイル**] をクリックしてから [**スナップインの追加と削除...**] をクリックします (またはキーボード ショートカット **Ctrl+M** を利用してもよい)。 **証明書** が左側のウィンドウにオプションとして表示されるので、それを選択してから、ポップアップ ウィンドウで [**コンピュータ アカウント**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="e52ca-230">まだポップアップ ウィンドウの中で、おそらく調べたい証明書が所属しているコンピュータ上で作業を行っているはずなので、そうであれば選択されている [**ローカル コンピュータ**] のままにします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="e52ca-231">リモート マシンで作業を行っている場合は、ラジオ ボタンを [**別のコンピュータ**] に切り替え、そのコンピュータの QFDN を入力するか、[**参照**] ボタンを使用して AD 内でそのコンピュータを探します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="e52ca-232">コンピューターを選択すると、準備ができたら、[**終了**して [ **ok]** MMC にスナップインを追加する] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="e52ca-233">MMC の左側のペインで [**証明書**] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="e52ca-234">[**個人**] フォルダーも展開して、[**証明書**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="e52ca-235">これでこのストアにある証明書を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="e52ca-236">表示したい証明書の場所を探すには、証明書を右クリックし、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e52ca-237">知るには、どのような証明書ですか。</span><span class="sxs-lookup"><span data-stu-id="e52ca-237">How do you know what certificate this is?</span></span> <span data-ttu-id="e52ca-238">いずれか、単一の証明書をファームのすべてのものに割り当てられている必要があります別など、既定値、内部の Web サービスなどの複数の証明書がある場合があります、場合に複数の証明書を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="e52ca-239">複数の証明書は、同じ拇印があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="e52ca-p122">**証明書** ビューが表示されたら、[**詳細**] を選択します。そこで [**サブジェクト**] を選択すると、証明書のサブジェクト名が表示され、付与されたサブジェクト名と関連プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="e52ca-p123">**サブジェクトの別名**エントリーも確認する必要があります。次のうちの 1 つまたは複数が見つかります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="e52ca-244">このプールは、プールの名前またはこの場合は、単一のサーバー名は、プールにはありません。</span><span class="sxs-lookup"><span data-stu-id="e52ca-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="e52ca-245">証明書が割り当てられるサーバーの名前</span><span class="sxs-lookup"><span data-stu-id="e52ca-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="e52ca-246">簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)</span><span class="sxs-lookup"><span data-stu-id="e52ca-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="e52ca-247">Web サービスの内部、および Web サービス外部の名前 (たとえば、webpool01.contoso.net、webpool01.contoso.com)、選択した内容に基づいてトポロジ ビルダーと Web サービスの選択を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="e52ca-248">既に割り当てられている場合、lyncdiscover。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコード。</span><span class="sxs-lookup"><span data-stu-id="e52ca-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="e52ca-249">割り当てられている証明書が 2つ以上の場合は、それらを確認する必要があります (上記の注記を参照)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="e52ca-250">したがってには、lyncdiscover を検索する場合。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコードを既に手に既に構成されているこの。</span><span class="sxs-lookup"><span data-stu-id="e52ca-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="e52ca-251">MMC を終了します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="e52ca-252">これらが割り当てられていない場合は、新しい証明書を申請するか (上記で概説)、これらをポストリクエストでインストールする必要があります (次の PowerShell を推奨)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="e52ca-253">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-253">Configure the reverse proxy</span></span>
<span data-ttu-id="e52ca-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="e52ca-254"></span></span>

<span data-ttu-id="e52ca-p125">次の手順は、そのとおりに実行するように意図されたものではありません。と言うのは、製品の前のバージョンで、たとえば Threat Management Gateway (TMG) の構成について順を追って手順を説明しました。これを使用していないのであれば、自分のバージョンではそこから仕上げる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="e52ca-257">TMG は Microsoft からはもはや製品として提供されておらず、その構成を行う必要があれば、「[Lync Server 2013 手順](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)」を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="e52ca-258">次の情報はのすべてのリバース プロキシが特定のチュートリアルの手順を提供できる方法がない場合でもより一般的には役に立つを目的としています。</span><span class="sxs-lookup"><span data-stu-id="e52ca-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="e52ca-259">検討すべき重要な事柄が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="e52ca-260">最初の自動検出申請を HTTPS で行いますか (それを推奨しています)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="e52ca-261">Web 公開ルールがある場合、それを変更する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="e52ca-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="e52ca-262">まだ Web 公開ルールがないのであれば、それを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="e52ca-263">最初の自動検出申請を HTTPS で行うのであれば、規則の作成や変更も必要となります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e52ca-264">**重要です**プロキシ タイムアウト値は、配置から配置に変化する番号です。</span><span class="sxs-lookup"><span data-stu-id="e52ca-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="e52ca-265">展開の監視では、クライアントの値を変更してください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="e52ca-266">値を 200 程度に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="e52ca-267">環境内で Lync モバイル クライアントをサポートしている場合は、900 のタイムアウト値を持つ、Office 365 からプッシュ通知のタイムアウトを許可する 960 に値を設定してください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="e52ca-268">クライアントを避けるためにタイムアウト値を大きく必要がある可能性があります切断の値が低すぎる、または数を減らす場合は、プロキシ経由での接続が切断されないが、クライアントが切断された後に時間をオフにします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="e52ca-269">監視、ベースラインの設定、環境の一般的なはこの値を適切に設定を判断するだけの正確な方法です。</span><span class="sxs-lookup"><span data-stu-id="e52ca-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="e52ca-270">外部自動検出 SAN および URL の既存の Web 公開ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="e52ca-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="e52ca-271">リバース プロキシのインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="e52ca-272">Web 公開ルールを見つけ、(メニューまたは、リバース プロキシの構成] タブをできない場合があります) の編集] オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="e52ca-273">領域は、この web 公開ルールの適用することを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="e52ca-274">着信サイトやサイトへのリクエストに関するこのルールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="e52ca-275">新しいエントリーを**追加**します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="e52ca-276">(使用例では lyncdiscover.contoso.com)、自動検出サイトの名前を入力し、リバース プロキシの形式に応じて、[ **OK** ] または [**保存**するには、します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="e52ca-277">自動検出 SAN エントリーのある新しい証明書が付与されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="e52ca-278">インストールして、リバース プロキシの設定によって使用できるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="e52ca-279">構成が完了したら、必ずすべてを保存してください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="e52ca-280">**テスト**機能、リバース プロキシの場合は、クリックしてくださいすべてことを確認するのには、それを使用して正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="e52ca-281">ディレクターまたはディレクターがある場合、同じ手順をする必要がありますようになりましたが、環境内のプール (つまり、2 番目のルールがある場合)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="e52ca-282">自動検出 URL を外部の web 公開ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="e52ca-283">リバース プロキシのインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="e52ca-284">場所インターフェイスで、web 公開ルールを作成して (ある可能性がありますメニューの [または] タブで、リバース プロキシの構成によって)、または [**新規\*\*\*\*作成**] オプションを選択するを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="e52ca-285">新しい Web 公開ルールを作成するためのオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="e52ca-286">一般的に次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="e52ca-287">**名前**: 規則の名前</span><span class="sxs-lookup"><span data-stu-id="e52ca-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="e52ca-288">**ルールの処理**:**許可**ルールはここでは、できるようにする、リバース プロキシを通過するものです。</span><span class="sxs-lookup"><span data-stu-id="e52ca-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="e52ca-289">選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="e52ca-290">外部アクセス用に **SSL** にする必要があるため、そのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="e52ca-291">**内部発行**のパスを発行し、フロント エンド プールのロード バランサー (またはいずれかの操作をした場合に、ディレクター プールのロード バランサーの FQDN) を外部の Web サービスの FQDN を入力する必要があります。 しようとしている、例として sfb_ があります。pool01.contoso.local。</span><span class="sxs-lookup"><span data-stu-id="e52ca-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="e52ca-292">入力する必要があります**/\*\*\*、公開へのパスですが、**元のホスト ヘッダーを転送\*\*する必要もします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="e52ca-p131">**パブリック名または外部名**の詳細や情報のオプションがあります。ここに</span><span class="sxs-lookup"><span data-stu-id="e52ca-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="e52ca-295">**Accept requests** と入力できますが、これはドメイン名用です。</span><span class="sxs-lookup"><span data-stu-id="e52ca-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="e52ca-296">**名前**には **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="e52ca-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="e52ca-297"><sipdomain>これは、外部の自動検出サービスの URL)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="e52ca-298">ここで、フロント エンド プールの外部 Web サービスの URL のルールを作成する場合は、フロント エンド プール (たとえば、lyncwebextpool01.contoso.com) では、外部の Web サービスの FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="e52ca-299">[**パス**] オプションがあり、入力する必要があります**/**\* ここでは。</span><span class="sxs-lookup"><span data-stu-id="e52ca-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="e52ca-300">最新のユーザー アカウントで **SSL リスナー**を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="e52ca-301">**認証の委任**を [**委任できません。** クライアントの直接認証を\*\*\*\* 許可します] に設定します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="e52ca-302">ルールが**全ユーザー**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="e52ca-303">これがこのルールを作成して、手順を進めるために必要なすべての情報です。</span><span class="sxs-lookup"><span data-stu-id="e52ca-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="e52ca-304">**元のホスト ヘッダー**が転送されたか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="e52ca-305">**Web サーバー**のポートも設定する必要があります。次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="e52ca-306">
            [\*\*HTTP ポートに要求をリダイレクトする\**] を選択し、ポート番号を  **8080** にします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="e52ca-307">
            [\*\*SSL ポートに要求をリダイレクトする\**] を選択し、ポート番号を  **4443** にします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="e52ca-308">すべての構成が終了したら、構成内容を保存または適用してからルールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="e52ca-309">ポート 80 の Web 公開ルールを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="e52ca-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="e52ca-310">リバース プロキシのインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="e52ca-311">場所インターフェイスで、web 公開ルールを作成して (ある可能性がありますメニューの [または] タブで、リバース プロキシの構成によって)、または [**新規\*\*\*\*作成**] オプションを選択するを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="e52ca-312">新しい Web 公開ルールを作成するためのオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="e52ca-313">一般的に次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="e52ca-314">**名前**: 規則の名前</span><span class="sxs-lookup"><span data-stu-id="e52ca-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="e52ca-315">**ルールの処理**:**許可**ルールはここでは、できるようにする、リバース プロキシを通過するものです。</span><span class="sxs-lookup"><span data-stu-id="e52ca-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="e52ca-316">選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="e52ca-317">これは [**公開された Web サーバーまたはサーバー ファームへの接続に、セキュリティで保護されていない接続を使用する**] にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="e52ca-318">**内部発行**のパスを発行し、フロント エンド プールのロード バランサーの**VIP アドレス**の FQDN を入力する必要がありますしようとしている、例として sfb_pool01.contoso.local があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="e52ca-319">入力する必要があります**/\*\*\*、公開へのパスですが、**元のホスト ヘッダーを転送\*\*する必要もします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="e52ca-p134">**パブリック名または外部名**の詳細や情報のオプションがあります。ここに</span><span class="sxs-lookup"><span data-stu-id="e52ca-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="e52ca-322">**Accept requests** と入力できますが、これはドメイン名用です。</span><span class="sxs-lookup"><span data-stu-id="e52ca-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="e52ca-323">**名前**には **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="e52ca-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="e52ca-324"><sipdomain>これは、外部の自動検出サービスの URL)。</span><span class="sxs-lookup"><span data-stu-id="e52ca-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="e52ca-325">[**パス**] オプションがあり、入力する必要があります**/**\* ここでは。</span><span class="sxs-lookup"><span data-stu-id="e52ca-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="e52ca-326">Web リスナーを選択するか、リバース プロキシを作成するを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="e52ca-327">**認証の委任**を [**委任できません。** クライアントの直接認証を\*\*\*\* 許可します] に設定します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="e52ca-328">ルールが**全ユーザー**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="e52ca-329">これがこのルールを作成して、手順を進めるために必要なすべての情報です。</span><span class="sxs-lookup"><span data-stu-id="e52ca-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="e52ca-330">**Web サーバー**のポートを設定する必要があります。次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="e52ca-331">
            [\*\*HTTP ポートに要求をリダイレクトする\**] を選択し、ポート番号を  **8080** にします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="e52ca-332">
            [\*\*SSL ポートに要求をリダイレクトする\**] を選択し、ポート番号を  **4443** にします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="e52ca-333">すべての構成が終了したら、構成内容を保存または適用してからルールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="e52ca-334">ハイブリッド展開でのモビリティの自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="e52ca-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="e52ca-335"></span></span>

<span data-ttu-id="e52ca-336">Skype ビジネス サーバー用のハイブリッド環境は、設置を組み合わせた環境および O365 環境です。</span><span class="sxs-lookup"><span data-stu-id="e52ca-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="e52ca-337">ハイブリッド環境で作業しているビジネス サーバーの Skype すると、自動検出サービスをユーザーがこれらの環境のいずれかの方法を見つけることができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="e52ca-p137">モバイル クライアントがユーザーの場所を検出できるようにするには、自動検出サービスを新しい URL で構成する必要があります。手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="e52ca-340">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="e52ca-341">ビジネス サーバー環境に、Skype の**ProxyFQDN**属性の値を取得するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="e52ca-342">それからシェル ウィンドウ内で以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="e52ca-343">[identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="e52ca-344">モビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="e52ca-344">Test your Mobility deployment</span></span>
<span data-ttu-id="e52ca-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="e52ca-345"></span></span>

<span data-ttu-id="e52ca-346">ビジネス サーバーの自動検出サービスのビジネス サーバー移動のサービスは、Skype の Skype を展開して、確認作業の配置の右に、テスト トランザクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="e52ca-347">**Test-CsUcwaConference** を実行して、会議における 2 人のユーザーの作成、参加、および通信能力をテストできます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="e52ca-348">ユーザー (実際のユーザーまたはテスト ユーザー) 2人とテストを行うための完全な資格情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="e52ca-349">Lync Server 2013 クライアントだけでなく、ビジネス クライアントの両方 Skype のこのコマンドが動作します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="e52ca-350">ビジネス サーバー 2015 の Skype の Lync Server 2010 クライアントは、テストに**テスト CsMcxP2PIM**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="e52ca-351">Lync Server 2010 ユーザーがする必要が実際のユーザーまたはユーザーの定義済みのテスト、およびパスワード資格情報を必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="e52ca-352">従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e52ca-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e52ca-353">ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e52ca-354">MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="e52ca-355">Skype for Business and Lync 2013 モバイル クライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="e52ca-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="e52ca-356">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされている任意のコンピューター上の**CsAdministrator**ロールのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e52ca-357">**ビジネス サーバー管理シェルの Skype** (可能性があります検索に名前を入力または**すべてのプログラム**に移動して選択) を起動します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="e52ca-358">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="e52ca-p141">スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="e52ca-361">Lync 2010 モバイル クライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="e52ca-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="e52ca-362">従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e52ca-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e52ca-363">ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e52ca-364">MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="e52ca-365">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされている任意のコンピューター上の**CsAdministrator**ロールのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e52ca-366">**ビジネス サーバー管理シェルの Skype** (可能性があります検索に名前を入力または**すべてのプログラム**に移動して選択) を起動します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="e52ca-367">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="e52ca-p143">スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="e52ca-370">コマンド プロシージャについて詳細を調べるには、「[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)」および「 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="e52ca-371">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-371">Configure for push notifications</span></span>
<span data-ttu-id="e52ca-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="e52ca-372"></span></span>

<span data-ttu-id="e52ca-373">プッシュ通知は、Skype または Lync アプリが非アクティブであっても、バッジ、アイコン、または警告の形式で送信できます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="e52ca-374">ところでプッシュ通知とはどのようなものでしょうか。</span><span class="sxs-lookup"><span data-stu-id="e52ca-374">But what are pusn notifications?</span></span> <span data-ttu-id="e52ca-375">これはユーザーに、新規または不在着信の IM 招待状、受信したボイス メールなどのイベントを通知するものです。</span><span class="sxs-lookup"><span data-stu-id="e52ca-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="e52ca-376">業務でサーバーの移動サービスの Skype は、ビジネス サーバー プッシュ通知サービスは、送信通知マイクロソフト プッシュ通知サービス (MSN) に Windows Phone ユーザーのクラウド ベースの Skype にこれらの通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="e52ca-377">この機能は、Lync Server 2013 から変更されたが、ビジネス サーバーは、Skype があれば、以下を実行するでしょう。</span><span class="sxs-lookup"><span data-stu-id="e52ca-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="e52ca-378">ビジネス エッジ サーバーの Skype では、新しいホスティング プロバイダーのビジネス オンラインでは、Microsoft の Skype を追加し、設定し、オンライン ビジネスの組織と Skype のプロバイダーのフェデレーションをホストしています。</span><span class="sxs-lookup"><span data-stu-id="e52ca-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="e52ca-p145">プッシュ通知を有効にするには、 **Set-CsPushNotificationConfiguration** コマンドレットを実行する必要があります。既定では、プッシュ通知は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="e52ca-381">フェデレーション構成とプッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="e52ca-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="e52ca-382">Skype for Business エッジ サーバーのプッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="e52ca-383">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e52ca-384">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e52ca-385">ビジネス サーバー オンラインのホスティング プロバイダーに、Skype を追加します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="e52ca-386">例:</span><span class="sxs-lookup"><span data-stu-id="e52ca-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="e52ca-p146">単一のホスティング プロバイダーに対して複数のフェデレーション関係を持つことはできません。そのため sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既に設定している場合は、ホスティング プロバイダーの ID が SkypeOnline 以外のものであっても、別のホスティング プロバイダーを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="e52ca-389">ホスティング プロバイダー フェデレーションの組織と Skype でプッシュ通知サービスとの間のオンライン ビジネスを設定します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="e52ca-390">コマンド ラインで次ぎように入力します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="e52ca-391">プッシュ通知を有効にする</span><span class="sxs-lookup"><span data-stu-id="e52ca-391">Enable push notifications</span></span>

1. <span data-ttu-id="e52ca-392">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e52ca-393">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e52ca-394">プッシュ通知を有効にする:</span><span class="sxs-lookup"><span data-stu-id="e52ca-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="e52ca-395">フェデレーションを有効にする:</span><span class="sxs-lookup"><span data-stu-id="e52ca-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="e52ca-396">フェデレーションとプッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="e52ca-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="e52ca-397">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e52ca-398">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e52ca-399">フェデレーションの構成をテストする</span><span class="sxs-lookup"><span data-stu-id="e52ca-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="e52ca-400">例:</span><span class="sxs-lookup"><span data-stu-id="e52ca-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="e52ca-401">プッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="e52ca-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="e52ca-402">例:</span><span class="sxs-lookup"><span data-stu-id="e52ca-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="e52ca-403">モビリティ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="e52ca-403">Configure Mobility policy</span></span>
<span data-ttu-id="e52ca-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="e52ca-404"></span></span>

<span data-ttu-id="e52ca-405">機能がある場合、モバイル サービスを使用できるユーザーを決定するビジネス サーバーの Skype でを使用して通話作業、ボイス オーバー IP (VoIP)、またはビデオ、WiFi が VoIP またはビデオのために必要になるかどうかも。</span><span class="sxs-lookup"><span data-stu-id="e52ca-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="e52ca-406">[勤務先から通話] 機能では、モバイル ユーザーが携帯電話の番号ではなく、勤務先の電話番号を使用して携帯電話で通話を発信および着信できます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="e52ca-407">この機能により、相手に発信者の携帯電話番号が表示されるのを防ぎ、発信の電話料金を回避できます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="e52ca-408">VoIP およびビデオを設定すると、VoIP 通話の発信と着信やビデオの利用ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="e52ca-409">また、WiFi の使用法の設定では、携帯電話会社の回線経由での WiFi ネットワークの使用をユーザーのデバイスで必須にするかどうかを決められます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="e52ca-410">移動作業を使用して呼び出し、VoIP、ビデオ機能は、すべて既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="e52ca-411">VoIP およびビデオで WiFi を必須にする設定は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e52ca-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="e52ca-412">管理者は、グローバルに、サイト別に、またはユーザー別にこれらの機能を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="e52ca-413">モビリティ機能や呼び出しを使用することができるユーザーは、作業を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="e52ca-414">Skype のビジネス サーバー対応</span><span class="sxs-lookup"><span data-stu-id="e52ca-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="e52ca-415">エンタープライズ VoIP が有効。</span><span class="sxs-lookup"><span data-stu-id="e52ca-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="e52ca-416">**EnableMobility**オプションが**True**に設定されているモビリティ ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="e52ca-417">[勤務先から通話] を使用するには、ユーザーが次の前提条件も満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e52ca-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="e52ca-418">[\*\*電話の同時呼び出しを有効にする \*\*] オプションを選択した音声ポリシーが割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="e52ca-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="e52ca-419">**True**に設定する**EnableOutsideVoice**を持つモビリティ ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e52ca-p150">エンタープライズ VoIP が有効になっていないユーザーは、関連付けられている音声ポリシーのオプション設定が適切であれば、モバイル デバイスで [クリックして参加] リンクを使用すれば、モバイル デバイスから Skype 間の VoIP 通話や会議参加会議ができます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="e52ca-422">グローバル モビリティ ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="e52ca-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="e52ca-423">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e52ca-424">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e52ca-425">オフに移動し、作業を使用して呼び出しへのアクセスをグローバルに入力しています。</span><span class="sxs-lookup"><span data-stu-id="e52ca-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="e52ca-426">モビリティへのアクセスを無効にすることがなく作業を使用して呼び出しを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="e52ca-427">することはできませんを無効に移動も作業を使用して呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="e52ca-428">詳細については、[一連の CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="e52ca-429">サイトでのモビリティ ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="e52ca-430">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e52ca-431">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e52ca-p152">サイト レベルのポリシーを作成し、VoIP とビデオを無効にして、IP オーディオと IP ビデオに対して WiFi を必須にする機能をサイト別に有効にします。次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="e52ca-434">詳細については、「 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e52ca-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="e52ca-435">ユーザーがモビリティ ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="e52ca-436">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e52ca-437">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e52ca-438">モビリティ ・ レベル ・ ポリシーにユーザーを作成し、モビリティ、および呼び出しを無効にユーザーの作業を使用しています。</span><span class="sxs-lookup"><span data-stu-id="e52ca-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="e52ca-439">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e52ca-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="e52ca-440">サンプル データ付き詳細例:</span><span class="sxs-lookup"><span data-stu-id="e52ca-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="e52ca-441">モビリティへのアクセスを無効にすることがなく作業を使用して呼び出しを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e52ca-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="e52ca-442">することはできませんを無効に移動も作業を使用して呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e52ca-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

