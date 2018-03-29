---
title: Skype for Business Server 2015 のモビリティの展開および構成
ms.author: heidip
author: microsoftheidi
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この資料でを Skype ビジネス サーバー移動機能を利用できるモバイル デバイスをできるように、モバイル サービスを使用するビジネス サーバー 2015 のインストールに既存の Skype を構成する手順を説明します。
ms.openlocfilehash: c23974477ec815fca9c0cd3d78ac7acc0b81912e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server-2015"></a><span data-ttu-id="6e210-103">Skype for Business Server 2015 のモビリティの展開および構成</span><span class="sxs-lookup"><span data-stu-id="6e210-103">Deploy and Configure Mobility for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6e210-104">この資料でを Skype ビジネス サーバー移動機能を利用できるモバイル デバイスをできるように、モバイル サービスを使用するビジネス サーバー 2015 のインストールに既存の Skype を構成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="6e210-104">This article will walk you through the steps to configure an existing Skype for Business Server 2015 installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="6e210-105">[ビジネス サーバー 2015 の Skype のモビリティの計画](../plan-your-deployment/mobility.md)の資料を確認し、する必要がありますサーバー 2015 のビジネス環境について、Skype にモビリティを展開する次の手順を続行する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="6e210-105">Having reviewed the [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server 2015 environment.</span></span> <span data-ttu-id="6e210-106">手順は次のとおりです (この表には許可一覧も含めます)。</span><span class="sxs-lookup"><span data-stu-id="6e210-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="6e210-107">**フェーズ**</span><span class="sxs-lookup"><span data-stu-id="6e210-107">**Phase**</span></span>|<span data-ttu-id="6e210-108">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="6e210-108">**Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6e210-109">
            「[DNS レコードの作成](deploy-and-configure-mobility.md#CreateDNSRec)」</span><span class="sxs-lookup"><span data-stu-id="6e210-109">[Create DNS records](deploy-and-configure-mobility.md#CreateDNSRec)</span></span> <br/> |<span data-ttu-id="6e210-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="6e210-110">Domain Admins</span></span>  <br/> <span data-ttu-id="6e210-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="6e210-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="6e210-112">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="6e210-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="6e210-113">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="6e210-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="6e210-114">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="6e210-115">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="6e210-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="6e210-116">ハイブリッド展開でのモビリティの自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="6e210-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="6e210-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="6e210-118">モビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="6e210-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="6e210-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6e210-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="6e210-120">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="6e210-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6e210-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="6e210-122">モビリティ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="6e210-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6e210-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="6e210-p102">次のすべてのセクションには、計画トピックを読んでいることが前提となる手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e210-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="6e210-126">DNS レコードの作成</span><span class="sxs-lookup"><span data-stu-id="6e210-126">Create DNS records</span></span>
<span data-ttu-id="6e210-127"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="6e210-127"></span></span>

<span data-ttu-id="6e210-128">ビジネス サーバー環境で、Skype の一部としてこれらを既に必要がありますが、操作する自動検出のための次のレコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-128">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="6e210-129">組織のネットワーク内から接続するモバイル ユーザーをサポートするための内部 DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="6e210-129">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="6e210-130">組織のネットワーク外から接続するモバイル ユーザーをサポートするための外部 (またはパブリック) DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="6e210-130">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="6e210-131">これらのレコードは、A (ホスト) 名または CNAME のどちらかにできます (両方作成する必要はなく、すべての手順がここに含まれています)。</span><span class="sxs-lookup"><span data-stu-id="6e210-131">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="6e210-132">内部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="6e210-132">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="6e210-133">**Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="6e210-133">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="6e210-134">[**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-134">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="6e210-135">コンソール ウィンドウの左側のペインでは、ドメインに移動する必要がありますのビジネス サーバーのフロント エンド サーバーでは、Skype をホームし、が**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="6e210-135">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="6e210-136">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="6e210-136">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="6e210-137">(標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。</span><span class="sxs-lookup"><span data-stu-id="6e210-137">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="6e210-138">任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6e210-138">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="6e210-139">判別できたら SIP ドメイン名を右クリックしてから、[**新しいエイリアス (CNAME)**] をメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="6e210-139">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="6e210-140">[**エイリアス名**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6e210-140">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="6e210-141">**完全修飾ドメイン名 (ターゲットのホストに対して FQDN を**をフロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上記の手順 4 で特定の内部の Web サービスの FQDN を入力または参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-141">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="6e210-142">入力したら、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e210-142">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="6e210-143">ビジネス サーバー環境に、Skype でサポートされている各 SIP ドメインの前方参照ゾーンに新しい自動検出の CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-143">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="6e210-144">外部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="6e210-144">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="6e210-145">ご利用のパブリック DNS プロバイダーが分かりませんので、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="6e210-145">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="6e210-146">この時点では、SIP ドメインは既に存在してある Skype のビジネス サーバー 2015 の。</span><span class="sxs-lookup"><span data-stu-id="6e210-146">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="6e210-147">この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-147">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="6e210-148">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="6e210-148">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="6e210-149">(標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。</span><span class="sxs-lookup"><span data-stu-id="6e210-149">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="6e210-150">任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6e210-150">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="6e210-151">その情報が得られたら、[**新しいエイリアス (CNAME)**] の作成オプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="6e210-151">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="6e210-152">[**エイリアス名**] を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-152">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="6e210-153">次に**ターゲット ・ ホストの FQDN**を入力する領域が存在する必要があります、これは、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上記の手順 3 で特定の FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-153">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="6e210-154">ここでは、保存する必要があります。 またはビジネス サーバー環境に、Skype では、各 SIP ドメインの前方参照ゾーンに追加の CNAME レコードを作成する場合は、する必要がありますが、あなたが準備ができて、作業内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="6e210-154">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="6e210-155">内部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="6e210-155">Create an internal DNS A record</span></span>

1. <span data-ttu-id="6e210-156">**Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="6e210-156">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="6e210-157">[**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-157">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="6e210-158">コンソール ウィンドウの左側のペインでは、ドメインに移動する必要がありますのビジネス サーバーのフロント エンド サーバーでは、Skype をホームし、が**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="6e210-158">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="6e210-159">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="6e210-159">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="6e210-160">(標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。</span><span class="sxs-lookup"><span data-stu-id="6e210-160">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="6e210-161">任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6e210-161">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="6e210-162">判別できたら SIP ドメイン名を右クリックしてから、[**新しいホスト (A または AAAA)**] をメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="6e210-162">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="6e210-163">[**名前**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6e210-163">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="6e210-164">[ **IP アドレス**] ボックスで、上記の手順 4 では、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、内部の Web サービスの IP アドレスの種類が識別されます。</span><span class="sxs-lookup"><span data-stu-id="6e210-164">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="6e210-165">入力したら [**ホストの追加**] をクリックしてから [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e210-165">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="6e210-166">ビジネス サーバー環境に、Skype でサポートされている各 SIP ドメインの前方参照ゾーンで新しいの自動検出の A または AAAA レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-166">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="6e210-167">これを行うには手順 6 - 8 を必要な回数繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6e210-167">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="6e210-168">終了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e210-168">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="6e210-169">外部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="6e210-169">Create an external DNS A record</span></span>

1. <span data-ttu-id="6e210-170">ご利用のパブリック DNS プロバイダーがわからないため、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="6e210-170">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="6e210-171">この時点では、SIP ドメインは既に存在してある Skype のビジネス サーバー 2015 の。</span><span class="sxs-lookup"><span data-stu-id="6e210-171">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="6e210-172">この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-172">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="6e210-173">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="6e210-173">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="6e210-174">(標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。</span><span class="sxs-lookup"><span data-stu-id="6e210-174">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="6e210-175">任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6e210-175">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="6e210-176">その情報が得られたら、[**新しいホスト A または AAAA**] の作成オプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="6e210-176">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="6e210-177">**エイリアス名**を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-177">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="6e210-178">次の**IP アドレス**を入力する領域が存在する必要があります、これは、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上の手順 3 で特定の ip アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-178">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="6e210-179">ここでは、保存する必要があります。 または追加作成する必要がある場合 A または AAAA レコード各 SIP ドメインの前方参照ゾーンで、Skype をビジネスのサーバー環境のを行う必要がありますが、1 回の準備が整ったら、作業を保存します。</span><span class="sxs-lookup"><span data-stu-id="6e210-179">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="6e210-180">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="6e210-180">Modify certificates</span></span>
<span data-ttu-id="6e210-181"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="6e210-181"></span></span>

<span data-ttu-id="6e210-182">証明書に関する計画についての疑問があれば、私たちを記述する[ビジネス サーバー 2015 の Skype のモビリティの計画](../plan-your-deployment/mobility.md)の記事で。</span><span class="sxs-lookup"><span data-stu-id="6e210-182">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="6e210-183">それを読んだ後で、以下の点を説明します。</span><span class="sxs-lookup"><span data-stu-id="6e210-183">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="6e210-184">新しい証明書が必要か。</span><span class="sxs-lookup"><span data-stu-id="6e210-184">Do I need new certificates?</span></span>
    
- <span data-ttu-id="6e210-185">認証局 (CA) に新しい証明書を申請する。</span><span class="sxs-lookup"><span data-stu-id="6e210-185">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="6e210-186">PowerShell を使用して、使用中の証明書をアップグレードする。</span><span class="sxs-lookup"><span data-stu-id="6e210-186">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="6e210-187">Microsoft 管理コンソール (MMC) で証明書スナップインを使用して証明書を確認しています。</span><span class="sxs-lookup"><span data-stu-id="6e210-187">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="6e210-188">新しい証明書が必要か。</span><span class="sxs-lookup"><span data-stu-id="6e210-188">Do I need new certificates?</span></span>

1. <span data-ttu-id="6e210-189">まず使用中の証明書の内容を確認して、必要とするエントリーの有無を調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-189">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="6e210-190">ビジネス サーバー 2015 のサーバーのローカル管理者アカウントでは、Skype にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-190">To do that, you'll need to log into your Skype for Business Server 2015 server with an account that's a local Administrator.</span></span> <span data-ttu-id="6e210-191">このアカウントには、手順中のいくつかで認証局 (CA) の発行権限も必要とされます。</span><span class="sxs-lookup"><span data-stu-id="6e210-191">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="6e210-192">ビジネス サーバー管理シェルには (場合は、[スタート] メニューまたはタスク バーに固定されていることがあるないことを検索する検索を使用できます)、Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-192">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="6e210-p109">更新された証明書の追加を行う前に、すでに付与されている証明書の内容を知っておくことが重要となります。コマンドで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6e210-p109">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="6e210-p110">手順 3 で得られた情報は固有の内容です。内容を吟味して、複数のことに対して単一の証明書が付与されているのか、それとも証明書を必要とする別々のコンポーネントに別の証明書が付与されているのか判断します。**Use** パラメーターを使用すれば、証明書がどのように使われているかが分かり、**Thumbprint** パラメーターを使用すれば、証明書が同一か別々かが分かります。</span><span class="sxs-lookup"><span data-stu-id="6e210-p110">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="6e210-p111">計画セクションで推奨されている SAN エントリーがあれば、申し分ありません。ない場合は、新規の証明書を 1 つ または複数の証明書を認証局に申請する必要があります (構成に依存します)。</span><span class="sxs-lookup"><span data-stu-id="6e210-p111">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="6e210-200">認証局 (CA) に新しい証明書を申請する。</span><span class="sxs-lookup"><span data-stu-id="6e210-200">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="6e210-201">あるどのような SAN エントリを参照するを確認して後、知っている (確認後上記の手順を使用して)、**単一の証明書**があるし、する必要があるすべてのエントリがないと説明しました。</span><span class="sxs-lookup"><span data-stu-id="6e210-201">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="6e210-202">新しい証明書要求を CA になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-202">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="6e210-203">ビジネス サーバー PowerShell の Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-203">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="6e210-204">欠落した自動検出サービス SAN (-Ca パラメーターを自分の認証局パスで置き換える) を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-204">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="6e210-p113">複数の SIP ドメインがある場合は、AllSipDomain パラメーターを上記の例のように使用することはできません。代わりに DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。一例として次のようになります (-Ca パラメーターを自分の認証局パスで置き換える)。</span><span class="sxs-lookup"><span data-stu-id="6e210-p113">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="6e210-209">または、必要なすべてのエントリがない**複数の証明書**があるが見つかりましたが、どのような SAN エントリを参照するを確認して後、。</span><span class="sxs-lookup"><span data-stu-id="6e210-209">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="6e210-210">新しい証明書要求を CA になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-210">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="6e210-211">ビジネス サーバー PowerShell の Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-211">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="6e210-212">欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-212">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="6e210-p115">複数の SIP ドメインがある場合は、AllSipDomain パラメーターを上記の例のように使用することはできません。代わりに DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。次のような例になります (-Ca パラメーターを自分の認証局パスで置き換える)。</span><span class="sxs-lookup"><span data-stu-id="6e210-p115">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="6e210-217">CA により新しい証明書が作成されたら、それを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-217">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6e210-218">Skype for Business Server 管理シェルを使用して証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="6e210-218">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="6e210-219">「新しい証明書が必要か」のセクションで判明した内容に応じて、次のうちの**いずれか 1 つ**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-219">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="6e210-220">すべてに対して単一の証明書しかない (どの thumbprint も同じ) 場合、これを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e210-220">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="6e210-221">別々の証明書が付与されている (thumbprint が異なる) 場合、代わりにこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e210-221">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="6e210-222">Microsoft 管理コンソール (MMC)</span><span class="sxs-lookup"><span data-stu-id="6e210-222">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="6e210-p116">MMC の証明書スナップインを使用して、証明書を調べるオプションを利用します。検索に MMC と入力すれば、アプリケーション オプションのようにポップアップします。</span><span class="sxs-lookup"><span data-stu-id="6e210-p116">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="6e210-p117">証明書スナップインを追加するには、「**ファイル**] をクリックしてから [**スナップインの追加と削除...**] をクリックします (またはキーボード ショートカット **Ctrl+M** を利用してもよい)。 **証明書** が左側のウィンドウにオプションとして表示されるので、それを選択してから、ポップアップ ウィンドウで [**コンピュータ アカウント**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e210-p117">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="6e210-227">まだポップアップ ウィンドウの中で、おそらく調べたい証明書が所属しているコンピュータ上で作業を行っているはずなので、そうであれば選択されている [**ローカル コンピュータ**] のままにします。</span><span class="sxs-lookup"><span data-stu-id="6e210-227">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="6e210-228">リモート マシンで作業を行っている場合は、ラジオ ボタンを [**別のコンピュータ**] に切り替え、そのコンピュータの QFDN を入力するか、[**参照**] ボタンを使用して AD 内でそのコンピュータを探します。</span><span class="sxs-lookup"><span data-stu-id="6e210-228">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="6e210-229">コンピューターを選択すると、準備ができたら、[**終了**して [ **ok]** MMC にスナップインを追加する] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-229">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="6e210-230">MMC の左側のペインで [**証明書**] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="6e210-230">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="6e210-231">[**個人**] フォルダーも展開して、[**証明書**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e210-231">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="6e210-232">これでこのストアにある証明書を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="6e210-232">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="6e210-233">表示したい証明書の場所を探すには、証明書を右クリックし、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e210-233">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e210-234">知るには、どのような証明書ですか。</span><span class="sxs-lookup"><span data-stu-id="6e210-234">How do you know what certificate this is?</span></span> <span data-ttu-id="6e210-235">いずれか、単一の証明書をファームのすべてのものに割り当てられている必要があります別など、既定値、内部の Web サービスなどの複数の証明書がある場合があります、場合に複数の証明書を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-235">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="6e210-236">複数の証明書は、同じ拇印があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-236">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="6e210-p121">**証明書** ビューが表示されたら、[**詳細**] を選択します。そこで [**サブジェクト**] を選択すると、証明書のサブジェクト名が表示され、付与されたサブジェクト名と関連プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e210-p121">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="6e210-p122">**サブジェクトの別名**エントリーも確認する必要があります。次のうちの 1 つまたは複数が見つかります。</span><span class="sxs-lookup"><span data-stu-id="6e210-p122">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="6e210-241">このプールは、プールの名前またはこの場合は、単一のサーバー名は、プールにはありません。</span><span class="sxs-lookup"><span data-stu-id="6e210-241">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="6e210-242">証明書が割り当てられるサーバーの名前</span><span class="sxs-lookup"><span data-stu-id="6e210-242">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="6e210-243">簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)</span><span class="sxs-lookup"><span data-stu-id="6e210-243">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="6e210-244">Web サービスの内部、および Web サービス外部の名前 (たとえば、webpool01.contoso.net、webpool01.contoso.com)、選択した内容に基づいてトポロジ ビルダーと Web サービスの選択を無効にします。</span><span class="sxs-lookup"><span data-stu-id="6e210-244">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="6e210-245">既に割り当てられている場合、lyncdiscover。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコード。</span><span class="sxs-lookup"><span data-stu-id="6e210-245">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="6e210-246">割り当てられている証明書が 2つ以上の場合は、それらを確認する必要があります (上記の注記を参照)。</span><span class="sxs-lookup"><span data-stu-id="6e210-246">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="6e210-247">したがってには、lyncdiscover を検索する場合。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコードを既に手に既に構成されているこの。</span><span class="sxs-lookup"><span data-stu-id="6e210-247">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="6e210-248">MMC を終了します。</span><span class="sxs-lookup"><span data-stu-id="6e210-248">You can close the MMC.</span></span>
    
9. <span data-ttu-id="6e210-249">これらが割り当てられていない場合は、新しい証明書を申請するか (上記で概説)、これらをポストリクエストでインストールする必要があります (次の PowerShell を推奨)。</span><span class="sxs-lookup"><span data-stu-id="6e210-249">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="6e210-250">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-250">Configure the reverse proxy</span></span>
<span data-ttu-id="6e210-251"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="6e210-251"></span></span>

<span data-ttu-id="6e210-p124">次の手順は、そのとおりに実行するように意図されたものではありません。と言うのは、製品の前のバージョンで、たとえば Threat Management Gateway (TMG) の構成について順を追って手順を説明しました。これを使用していないのであれば、自分のバージョンではそこから仕上げる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-p124">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="6e210-254">TMG が不要になった製品として Microsoft によって提供されると、 [Lync Server 2013 の手順](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)を表示できる場合はそれを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-254">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="6e210-255">次の情報はのすべてのリバース プロキシが特定のチュートリアルの手順を提供できる方法がない場合でもより一般的には役に立つを目的としています。</span><span class="sxs-lookup"><span data-stu-id="6e210-255">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="6e210-256">検討すべき重要な事柄が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="6e210-256">We have two main things to consider:</span></span>
  
- <span data-ttu-id="6e210-257">最初の自動検出申請を HTTPS で行いますか (それを推奨しています)。</span><span class="sxs-lookup"><span data-stu-id="6e210-257">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="6e210-258">Web 公開ルールがある場合、それを変更する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="6e210-258">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="6e210-259">まだ Web 公開ルールがないのであれば、それを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-259">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="6e210-260">最初の自動検出申請を HTTPS で行うのであれば、規則の作成や変更も必要となります。</span><span class="sxs-lookup"><span data-stu-id="6e210-260">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6e210-261">**重要です**プロキシ タイムアウト値は、配置から配置に変化する番号です。</span><span class="sxs-lookup"><span data-stu-id="6e210-261">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="6e210-262">展開の監視では、クライアントの値を変更してください。</span><span class="sxs-lookup"><span data-stu-id="6e210-262">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="6e210-263">値を 200 程度に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6e210-263">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="6e210-264">環境内で Lync モバイル クライアントをサポートしている場合は、900 のタイムアウト値を持つ、Office 365 からプッシュ通知のタイムアウトを許可する 960 に値を設定してください。</span><span class="sxs-lookup"><span data-stu-id="6e210-264">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="6e210-265">クライアントを避けるためにタイムアウト値を大きく必要がある可能性があります切断の値が低すぎる、または数を減らす場合は、プロキシ経由での接続が切断されないが、クライアントが切断された後に時間をオフにします。</span><span class="sxs-lookup"><span data-stu-id="6e210-265">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="6e210-266">監視、ベースラインの設定、環境の一般的なはこの値を適切に設定を判断するだけの正確な方法です。</span><span class="sxs-lookup"><span data-stu-id="6e210-266">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="6e210-267">外部自動検出 SAN および URL の既存の Web 公開ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="6e210-267">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="6e210-268">リバース プロキシのインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-268">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="6e210-269">Web 公開ルールを見つけ、(メニューまたは、リバース プロキシの構成] タブをできない場合があります) の編集] オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-269">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="6e210-270">領域は、この web 公開ルールの適用することを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-270">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="6e210-271">着信サイトやサイトへのリクエストに関するこのルールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-271">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="6e210-272">新しいエントリーを**追加**します。</span><span class="sxs-lookup"><span data-stu-id="6e210-272">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="6e210-273">(使用例では lyncdiscover.contoso.com)、自動検出サイトの名前を入力し、リバース プロキシの形式に応じて、[ **OK** ] または [**保存**するには、します。</span><span class="sxs-lookup"><span data-stu-id="6e210-273">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="6e210-274">自動検出 SAN エントリーのある新しい証明書が付与されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-274">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="6e210-275">インストールして、リバース プロキシの設定によって使用できるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-275">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="6e210-276">構成が完了したら、必ずすべてを保存してください。</span><span class="sxs-lookup"><span data-stu-id="6e210-276">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="6e210-277">**テスト**機能、リバース プロキシの場合は、クリックしてくださいすべてことを確認するのには、それを使用して正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="6e210-277">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="6e210-278">ディレクターまたはディレクターがある場合、同じ手順をする必要がありますようになりましたが、環境内のプール (つまり、2 番目のルールがある場合)。</span><span class="sxs-lookup"><span data-stu-id="6e210-278">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="6e210-279">自動検出 URL を外部の web 公開ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e210-279">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="6e210-280">リバース プロキシのインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-280">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="6e210-281">場所インターフェイスで、web 公開ルールを作成して (ある可能性がありますメニューの [または] タブで、リバース プロキシの構成によって)、または [**新規****作成**] オプションを選択するを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-281">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="6e210-282">新しい Web 公開ルールを作成するためのオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="6e210-282">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="6e210-283">一般的に次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-283">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="6e210-284">**名前**: 規則の名前</span><span class="sxs-lookup"><span data-stu-id="6e210-284">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="6e210-285">**ルールの処理**:**許可**ルールはここでは、できるようにする、リバース プロキシを通過するものです。</span><span class="sxs-lookup"><span data-stu-id="6e210-285">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="6e210-286">選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。</span><span class="sxs-lookup"><span data-stu-id="6e210-286">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="6e210-287">外部アクセス用に **SSL** にする必要があるため、そのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e210-287">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="6e210-288">**内部発行**のパスを発行し、フロント エンド プールのロード バランサー (またはいずれかの操作をした場合に、ディレクター プールのロード バランサーの FQDN) を外部の Web サービスの FQDN を入力する必要があります。 しようとしている、例として sfb_ があります。pool01.contoso.local。</span><span class="sxs-lookup"><span data-stu-id="6e210-288">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="6e210-289">入力する必要があります**/**、公開へのパスですが、**元のホスト ヘッダーを転送**する必要もします。</span><span class="sxs-lookup"><span data-stu-id="6e210-289">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="6e210-p130">**パブリック名または外部名**の詳細や情報のオプションがあります。ここに</span><span class="sxs-lookup"><span data-stu-id="6e210-p130">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="6e210-292">**Accept requests** と入力できますが、これはドメイン名用です。</span><span class="sxs-lookup"><span data-stu-id="6e210-292">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="6e210-293">**名前**には **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="6e210-293">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="6e210-294"><sipdomain>これは、外部の自動検出サービスの URL)。</span><span class="sxs-lookup"><span data-stu-id="6e210-294"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="6e210-295">ここで、フロント エンド プールの外部 Web サービスの URL のルールを作成する場合は、フロント エンド プール (たとえば、lyncwebextpool01.contoso.com) では、外部の Web サービスの FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-295">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="6e210-296">[**パス**] オプションがあり、入力する必要があります**/**はここです。</span><span class="sxs-lookup"><span data-stu-id="6e210-296">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="6e210-297">最新のユーザー アカウントで **SSL リスナー**を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-297">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="6e210-298">**認証の委任**を [**委任できません。**クライアントの直接認証を****許可します] に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e210-298">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="6e210-299">ルールが**全ユーザー**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6e210-299">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="6e210-300">これがこのルールを作成して、手順を進めるために必要なすべての情報です。</span><span class="sxs-lookup"><span data-stu-id="6e210-300">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="6e210-301">**元のホスト ヘッダー**が転送されたか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-301">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="6e210-302">**Web サーバー**のポートも設定する必要があります。次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="6e210-302">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="6e210-303">
            [**HTTP ポートに要求をリダイレクトする**] を選択し、ポート番号を  **8080** にします。</span><span class="sxs-lookup"><span data-stu-id="6e210-303">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="6e210-304">
            [**SSL ポートに要求をリダイレクトする**] を選択し、ポート番号を  **4443** にします。</span><span class="sxs-lookup"><span data-stu-id="6e210-304">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="6e210-305">すべての構成が終了したら、構成内容を保存または適用してからルールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="6e210-305">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="6e210-306">ポート 80 の Web 公開ルールを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="6e210-306">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="6e210-307">リバース プロキシのインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-307">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="6e210-308">場所インターフェイスで、web 公開ルールを作成して (ある可能性がありますメニューの [または] タブで、リバース プロキシの構成によって)、または [**新規****作成**] オプションを選択するを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-308">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="6e210-309">新しい Web 公開ルールを作成するためのオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="6e210-309">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="6e210-310">一般的に次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-310">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="6e210-311">**名前**: 規則の名前</span><span class="sxs-lookup"><span data-stu-id="6e210-311">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="6e210-312">**ルールの処理**:**許可**ルールはここでは、できるようにする、リバース プロキシを通過するものです。</span><span class="sxs-lookup"><span data-stu-id="6e210-312">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="6e210-313">選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。</span><span class="sxs-lookup"><span data-stu-id="6e210-313">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="6e210-314">これは [**公開された Web サーバーまたはサーバー ファームへの接続に、セキュリティで保護されていない接続を使用する**] にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-314">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="6e210-315">**内部発行**のパスを発行し、フロント エンド プールのロード バランサーの**VIP アドレス**の FQDN を入力する必要がありますしようとしている、例として sfb_pool01.contoso.local があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-315">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="6e210-316">入力する必要があります**/**、公開へのパスですが、**元のホスト ヘッダーを転送**する必要もします。</span><span class="sxs-lookup"><span data-stu-id="6e210-316">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="6e210-p133">**パブリック名または外部名**の詳細や情報のオプションがあります。ここに</span><span class="sxs-lookup"><span data-stu-id="6e210-p133">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="6e210-319">**Accept requests** と入力できますが、これはドメイン名用です。</span><span class="sxs-lookup"><span data-stu-id="6e210-319">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="6e210-320">**名前**には **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="6e210-320">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="6e210-321"><sipdomain>これは、外部の自動検出サービスの URL)。</span><span class="sxs-lookup"><span data-stu-id="6e210-321"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="6e210-322">[**パス**] オプションがあり、入力する必要があります**/**はここです。</span><span class="sxs-lookup"><span data-stu-id="6e210-322">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="6e210-323">Web リスナーを選択するか、リバース プロキシを作成するを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-323">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="6e210-324">**認証の委任**を [**委任できません。**クライアントの直接認証を****許可します] に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e210-324">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="6e210-325">ルールが**全ユーザー**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6e210-325">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="6e210-326">これがこのルールを作成して、手順を進めるために必要なすべての情報です。</span><span class="sxs-lookup"><span data-stu-id="6e210-326">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="6e210-327">**Web サーバー**のポートを設定する必要があります。次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="6e210-327">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="6e210-328">
            [**HTTP ポートに要求をリダイレクトする**] を選択し、ポート番号を  **8080** にします。</span><span class="sxs-lookup"><span data-stu-id="6e210-328">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="6e210-329">
            [**SSL ポートに要求をリダイレクトする**] を選択し、ポート番号を  **4443** にします。</span><span class="sxs-lookup"><span data-stu-id="6e210-329">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="6e210-330">すべての構成が終了したら、構成内容を保存または適用してからルールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="6e210-330">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="6e210-331">ハイブリッド展開でのモビリティの自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-331">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="6e210-332"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="6e210-332"></span></span>

<span data-ttu-id="6e210-333">ビジネス サーバー 2015 の Skype のハイブリッド環境は、設置を組み合わせた環境および O365 環境です。</span><span class="sxs-lookup"><span data-stu-id="6e210-333">Hybrid environments in Skype for Business Server 2015 are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="6e210-334">ハイブリッド環境で作業しているビジネス サーバーの Skype すると、自動検出サービスをユーザーがこれらの環境のいずれかの方法を見つけることができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-334">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="6e210-p136">モバイル クライアントがユーザーの場所を検出できるようにするには、自動検出サービスを新しい URL で構成する必要があります。手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e210-p136">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="6e210-337">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e210-337">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="6e210-338">ビジネス サーバー環境に、Skype の**ProxyFQDN**属性の値を取得するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e210-338">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
  ```
  Get-CsHostingProvider
  ```

3. <span data-ttu-id="6e210-339">それからシェル ウィンドウ内で以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e210-339">Then, still in the shell window, run:</span></span>
    
  ```
  Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
  ```

    <span data-ttu-id="6e210-340">[identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6e210-340">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="6e210-341">モビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="6e210-341">Test your Mobility deployment</span></span>
<span data-ttu-id="6e210-342"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="6e210-342"></span></span>

<span data-ttu-id="6e210-343">ビジネス サーバーの自動検出サービスのビジネス サーバー移動のサービスは、Skype の Skype を展開して、確認作業の配置の右に、テスト トランザクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e210-343">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="6e210-344">**Test-CsUcwaConference** を実行して、会議における 2 人のユーザーの作成、参加、および通信能力をテストできます。</span><span class="sxs-lookup"><span data-stu-id="6e210-344">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="6e210-345">ユーザー (実際のユーザーまたはテスト ユーザー) 2人とテストを行うための完全な資格情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6e210-345">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="6e210-346">Lync Server 2013 クライアントだけでなく、ビジネス クライアントの両方 Skype のこのコマンドが動作します。</span><span class="sxs-lookup"><span data-stu-id="6e210-346">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="6e210-347">Lync Server 2010 クライアントでは、テストに**テスト CsMcxP2PIM**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-347">For Lync Server 2010 clients, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="6e210-348">Lync Server 2010 ユーザーがする必要が実際のユーザーまたはユーザーの定義済みのテスト、およびパスワード資格情報を必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-348">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="6e210-349">Skype for Business and Lync 2013 モバイル クライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="6e210-349">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="6e210-350">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされている任意のコンピューター上の**CsAdministrator**ロールのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6e210-350">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e210-351">**ビジネス サーバー管理シェルの Skype** (可能性があります検索に名前を入力または**すべてのプログラム**に移動して選択) を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e210-351">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="6e210-352">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6e210-352">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="6e210-p139">スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e210-p139">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="6e210-355">Lync 2010 モバイル クライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="6e210-355">Test conferencing for Lync 2010 mobile clients</span></span>

1. <span data-ttu-id="6e210-356">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされている任意のコンピューター上の**CsAdministrator**ロールのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6e210-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e210-357">**ビジネス サーバー管理シェルの Skype** (可能性があります検索に名前を入力または**すべてのプログラム**に移動して選択) を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e210-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="6e210-358">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6e210-358">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="6e210-p140">スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e210-p140">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
  ```
  $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
  $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
  $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
  $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
  Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
  ```

<span data-ttu-id="6e210-361">コマンドの手順を確認するのにはさらに、ことができますおよびチェック アウトする[テスト CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) [テスト CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6e210-361">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="6e210-362">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-362">Configure for push notifications</span></span>
<span data-ttu-id="6e210-363"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="6e210-363"></span></span>

<span data-ttu-id="6e210-364">プッシュ通知は、Skype または Lync アプリが非アクティブであっても、バッジ、アイコン、または警告の形式で送信できます。</span><span class="sxs-lookup"><span data-stu-id="6e210-364">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="6e210-365">ところでプッシュ通知とはどのようなものでしょうか。</span><span class="sxs-lookup"><span data-stu-id="6e210-365">But what are pusn notifications?</span></span> <span data-ttu-id="6e210-366">これはユーザーに、新規または不在着信の IM 招待状、受信したボイス メールなどのイベントを通知するものです。</span><span class="sxs-lookup"><span data-stu-id="6e210-366">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="6e210-367">ビジネス サーバー 2015 モビリティ サービスの Skype では、ビジネス サーバー プッシュ通知サービスは、送信通知マイクロソフト プッシュ通知サービス (MSN) に Windows Phone ユーザーのクラウド ベースの Skype にこれらの通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="6e210-367">The Skype for Business Server 2015 Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="6e210-368">この機能は、Lync Server 2013 から変更されたが、ビジネス サーバーは、Skype があれば、以下を実行するでしょう。</span><span class="sxs-lookup"><span data-stu-id="6e210-368">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="6e210-369">ビジネス 2015 エッジ サーバーの Skype では、新しいホスティング プロバイダーのビジネス オンラインでは、Microsoft の Skype を追加し、設定し、オンライン ビジネスの組織と Skype のプロバイダーのフェデレーションをホストしています。</span><span class="sxs-lookup"><span data-stu-id="6e210-369">For a Skype for Business Server 2015 Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="6e210-p142">プッシュ通知を有効にするには、 **Set-CsPushNotificationConfiguration** コマンドレットを実行する必要があります。既定では、プッシュ通知は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6e210-p142">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="6e210-372">フェデレーション構成とプッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="6e210-372">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="6e210-373">Skype for Business エッジ サーバーのプッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-373">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="6e210-374">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="6e210-374">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e210-375">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e210-375">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e210-376">ビジネス サーバー オンラインのホスティング プロバイダーに、Skype を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e210-376">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="6e210-377">例:</span><span class="sxs-lookup"><span data-stu-id="6e210-377">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="6e210-p143">単一のホスティング プロバイダーに対して複数のフェデレーション関係を持つことはできません。そのため sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既に設定している場合は、ホスティング プロバイダーの ID が SkypeOnline 以外のものであっても、別のホスティング プロバイダーを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="6e210-p143">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="6e210-380">ホスティング プロバイダー フェデレーションの組織と Skype でプッシュ通知サービスとの間のオンライン ビジネスを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e210-380">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="6e210-381">コマンド ラインで次ぎように入力します。</span><span class="sxs-lookup"><span data-stu-id="6e210-381">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="6e210-382">プッシュ通知を有効にする</span><span class="sxs-lookup"><span data-stu-id="6e210-382">Enable push notifications</span></span>

1. <span data-ttu-id="6e210-383">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="6e210-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e210-384">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e210-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e210-385">プッシュ通知を有効にする:</span><span class="sxs-lookup"><span data-stu-id="6e210-385">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="6e210-386">フェデレーションを有効にする:</span><span class="sxs-lookup"><span data-stu-id="6e210-386">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="6e210-387">フェデレーションとプッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="6e210-387">Test federation and push notifications</span></span>

1. <span data-ttu-id="6e210-388">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="6e210-388">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e210-389">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e210-389">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e210-390">フェデレーションの構成をテストする</span><span class="sxs-lookup"><span data-stu-id="6e210-390">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="6e210-391">例:</span><span class="sxs-lookup"><span data-stu-id="6e210-391">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="6e210-392">プッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="6e210-392">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="6e210-393">例:</span><span class="sxs-lookup"><span data-stu-id="6e210-393">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="6e210-394">モビリティ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6e210-394">Configure Mobility policy</span></span>
<span data-ttu-id="6e210-395"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="6e210-395"></span></span>

<span data-ttu-id="6e210-396">機能がある場合、モバイル サービスを使用できるユーザーを決定するのには、ビジネス サーバー 2015 の Skype でを使用して通話作業、ボイス オーバー IP (VoIP)、またはビデオ、WiFi が VoIP またはビデオのために必要になるかどうかも。</span><span class="sxs-lookup"><span data-stu-id="6e210-396">You have the ability with Skype for Business Server 2015 to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="6e210-397">[勤務先から通話] 機能では、モバイル ユーザーが携帯電話の番号ではなく、勤務先の電話番号を使用して携帯電話で通話を発信および着信できます。</span><span class="sxs-lookup"><span data-stu-id="6e210-397">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="6e210-398">この機能により、相手に発信者の携帯電話番号が表示されるのを防ぎ、発信の電話料金を回避できます。</span><span class="sxs-lookup"><span data-stu-id="6e210-398">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="6e210-399">VoIP およびビデオを設定すると、VoIP 通話の発信と着信やビデオの利用ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="6e210-399">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="6e210-400">また、WiFi の使用法の設定では、携帯電話会社の回線経由での WiFi ネットワークの使用をユーザーのデバイスで必須にするかどうかを決められます。</span><span class="sxs-lookup"><span data-stu-id="6e210-400">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="6e210-401">移動作業を使用して呼び出し、VoIP、ビデオ機能は、すべて既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e210-401">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="6e210-402">VoIP およびビデオで WiFi を必須にする設定は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6e210-402">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="6e210-403">管理者は、グローバルに、サイト別に、またはユーザー別にこれらの機能を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6e210-403">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="6e210-404">モビリティ機能や呼び出しを使用することができるユーザーは、作業を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-404">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="6e210-405">ビジネス サーバー 2015 の Skype を有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6e210-405">Enabled for Skype for Business Server 2015</span></span>
    
- <span data-ttu-id="6e210-406">エンタープライズ VoIP が有効。</span><span class="sxs-lookup"><span data-stu-id="6e210-406">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="6e210-407">**EnableMobility**オプションが**True**に設定されているモビリティ ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6e210-407">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="6e210-408">[勤務先から通話] を使用するには、ユーザーが次の前提条件も満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e210-408">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="6e210-409">[**電話の同時呼び出しを有効にする **] オプションを選択した音声ポリシーが割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="6e210-409">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="6e210-410">**True**に設定する**EnableOutsideVoice**を持つモビリティ ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6e210-410">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6e210-p147">エンタープライズ VoIP が有効になっていないユーザーは、関連付けられている音声ポリシーのオプション設定が適切であれば、モバイル デバイスで [クリックして参加] リンクを使用すれば、モバイル デバイスから Skype 間の VoIP 通話や会議参加会議ができます。</span><span class="sxs-lookup"><span data-stu-id="6e210-p147">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="6e210-413">グローバル モビリティ ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="6e210-413">Modify global Mobility policy</span></span>

1. <span data-ttu-id="6e210-414">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="6e210-414">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e210-415">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e210-415">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e210-416">オフに移動し、作業を使用して呼び出しへのアクセスをグローバルに入力しています。</span><span class="sxs-lookup"><span data-stu-id="6e210-416">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="6e210-417">モビリティへのアクセスを無効にすることがなく作業を使用して呼び出しを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="6e210-417">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="6e210-418">することはできませんを無効に移動も作業を使用して呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6e210-418">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="6e210-419">詳細については、[一連の CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e210-419">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="6e210-420">サイトでのモビリティ ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="6e210-420">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="6e210-421">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="6e210-421">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e210-422">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e210-422">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e210-p149">サイト レベルのポリシーを作成し、VoIP とビデオを無効にして、IP オーディオと IP ビデオに対して WiFi を必須にする機能をサイト別に有効にします。次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6e210-p149">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="6e210-425">[新規 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="6e210-425">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="6e210-426">ユーザーがモビリティ ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="6e210-426">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="6e210-427">**ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。</span><span class="sxs-lookup"><span data-stu-id="6e210-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e210-428">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e210-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e210-429">モビリティ ・ レベル ・ ポリシーにユーザーを作成し、モビリティ、および呼び出しを無効にユーザーの作業を使用しています。</span><span class="sxs-lookup"><span data-stu-id="6e210-429">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="6e210-430">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6e210-430">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="6e210-431">サンプル データ付き詳細例:</span><span class="sxs-lookup"><span data-stu-id="6e210-431">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="6e210-432">モビリティへのアクセスを無効にすることがなく作業を使用して呼び出しを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="6e210-432">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="6e210-433">することはできませんを無効に移動も作業を使用して呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6e210-433">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

