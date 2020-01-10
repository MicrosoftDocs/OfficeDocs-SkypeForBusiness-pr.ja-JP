---
title: Skype for Business Server のモビリティの展開と構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この記事では、モバイルデバイスで Skype for business Server のモバイル機能を利用できるように、既存の Skype for Business Server のインストールを設定する手順について説明します。
ms.openlocfilehash: 3e39c354fd77d7ac36e3a4c36ed7e36e1d8ffbbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002867"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="a939b-103">Skype for Business Server のモビリティの展開と構成</span><span class="sxs-lookup"><span data-stu-id="a939b-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="a939b-104">この記事では、モバイルデバイスで Skype for business Server のモバイル機能を利用できるように、既存の Skype for Business Server のインストールを設定する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a939b-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="a939b-105">[Skype For Business server のモバイルプランの計画](../plan-your-deployment/mobility.md)を確認した後、次の手順に従って Skype For business server 環境にモビリティを展開する準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="a939b-106">手順は次のとおりです (この表には許可一覧も含めます)。</span><span class="sxs-lookup"><span data-stu-id="a939b-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="a939b-107">**段階**</span><span class="sxs-lookup"><span data-stu-id="a939b-107">**Phase**</span></span>|<span data-ttu-id="a939b-108">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="a939b-108">**Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a939b-109">
            「[DNS レコードの作成](deploy-and-configure-mobility.md#CreateDNSRec)」</span><span class="sxs-lookup"><span data-stu-id="a939b-109">[Create DNS records](deploy-and-configure-mobility.md#CreateDNSRec)</span></span> <br/> |<span data-ttu-id="a939b-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="a939b-110">Domain Admins</span></span>  <br/> <span data-ttu-id="a939b-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="a939b-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="a939b-112">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="a939b-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="a939b-113">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="a939b-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="a939b-114">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="a939b-115">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="a939b-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="a939b-116">ハイブリッド展開でのモビリティの自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="a939b-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="a939b-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="a939b-118">モビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="a939b-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="a939b-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a939b-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="a939b-120">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="a939b-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a939b-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="a939b-122">モビリティ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="a939b-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a939b-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="a939b-p102">次のすべてのセクションには、計画トピックを読んでいることが前提となる手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a939b-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="a939b-126">Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a939b-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a939b-127">現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="a939b-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a939b-128">MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="a939b-129">DNS レコードの作成</span><span class="sxs-lookup"><span data-stu-id="a939b-129">Create DNS records</span></span>
<span data-ttu-id="a939b-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="a939b-130"></span></span>

<span data-ttu-id="a939b-131">すでに Skype for Business Server 環境に含まれている場合もありますが、自動検出機能を使用するには、次のレコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="a939b-132">組織のネットワーク内から接続するモバイル ユーザーをサポートするための内部 DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="a939b-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="a939b-133">組織のネットワーク外から接続するモバイル ユーザーをサポートするための外部 (またはパブリック) DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="a939b-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="a939b-134">これらのレコードは、A (ホスト) 名または CNAME のどちらかにできます (両方作成する必要はなく、すべての手順がここに含まれています)。</span><span class="sxs-lookup"><span data-stu-id="a939b-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="a939b-135">内部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="a939b-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="a939b-136">**Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="a939b-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="a939b-137">[**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="a939b-138">コンソールウィンドウの左側のウィンドウで、Skype for Business Server のフロントエンドサーバーのホームになっているドメインに移動して、そこにある [**前方参照**] を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="a939b-139">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="a939b-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a939b-140">いずれかのホスト A または AAAA レコード (標準またはエンタープライズ) またはフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="a939b-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a939b-141">ディレクターまたはディレクタープールのすべての host A レコードまたは AAAA レコード (展開に含まれているオプションの構成)。</span><span class="sxs-lookup"><span data-stu-id="a939b-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="a939b-142">判別できたら SIP ドメイン名を右クリックしてから、[**新しいエイリアス (CNAME)**] をメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="a939b-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="a939b-143">[**エイリアス名**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="a939b-144">**完全修飾ドメイン名 (ターゲットホスト用の fqdn**) で、上記の手順4で確認した、フロントエンドプール (または単一のフロントエンドサーバー、またはディレクタープールまたはディレクター) 用の内部 WEB サービス fqdn を入力または参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="a939b-145">入力したら、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a939b-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="a939b-146">Skype for Business Server 環境でサポートされている各 SIP ドメイン用の、前方参照ゾーンに新しい自動検出 CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="a939b-147">外部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="a939b-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="a939b-148">ご利用のパブリック DNS プロバイダーが分かりませんので、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="a939b-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="a939b-149">現時点では、Skype for Business Server 用に SIP ドメインが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="a939b-150">この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="a939b-151">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="a939b-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a939b-152">いずれかのホスト A または AAAA レコード (標準またはエンタープライズ) またはフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="a939b-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a939b-153">ディレクターまたはディレクタープールのすべての host A レコードまたは AAAA レコード (展開に含まれているオプションの構成)。</span><span class="sxs-lookup"><span data-stu-id="a939b-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="a939b-154">その情報が得られたら、[**新しいエイリアス (CNAME)**] の作成オプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="a939b-155">[**エイリアス名**] を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="a939b-156">次に、**ターゲットホストの fqdn**に入力する領域が必要です。上記の手順3で確認した、フロントエンドプール (または単一のフロントエンドサーバー、またはディレクタープールまたはディレクター) の fqdn を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="a939b-157">Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンで追加の CNAME レコードを作成する必要がある場合は、ここで保存しておく必要があります。ただし、準備ができたら、作業内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="a939b-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="a939b-158">内部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="a939b-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="a939b-159">**Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="a939b-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="a939b-160">[**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="a939b-161">コンソールウィンドウの左側のウィンドウで、Skype for Business Server のフロントエンドサーバーのホームになっているドメインに移動して、そこにある [**前方参照**] を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="a939b-162">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="a939b-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a939b-163">いずれかのホスト A または AAAA レコード (標準またはエンタープライズ) またはフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="a939b-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a939b-164">ディレクターまたはディレクタープールのすべての host A レコードまたは AAAA レコード (展開に含まれているオプションの構成)。</span><span class="sxs-lookup"><span data-stu-id="a939b-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="a939b-165">判別できたら SIP ドメイン名を右クリックしてから、[**新しいホスト (A または AAAA)**] をメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="a939b-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="a939b-166">[**名前**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="a939b-167">[ **IP アドレス**] ボックスに、上記の手順4で確認した、フロントエンドプール (または単一のフロントエンドサーバー、またはディレクタープールまたはディレクター) の内部 WEB サービス IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="a939b-168">入力したら [**ホストの追加**] をクリックしてから [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a939b-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="a939b-169">Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 A レコードまたは AAAA レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="a939b-170">これを行うには手順 6 - 8 を必要な回数繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a939b-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="a939b-171">終了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a939b-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="a939b-172">外部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="a939b-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="a939b-173">ご利用のパブリック DNS プロバイダーがわからないため、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="a939b-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="a939b-174">現時点では、Skype for Business Server 用に SIP ドメインが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="a939b-175">この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="a939b-176">次のどちらがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="a939b-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a939b-177">いずれかのホスト A または AAAA レコード (標準またはエンタープライズ) またはフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="a939b-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a939b-178">ディレクターまたはディレクタープールのすべての host A レコードまたは AAAA レコード (展開に含まれているオプションの構成)。</span><span class="sxs-lookup"><span data-stu-id="a939b-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="a939b-179">その情報が得られたら、[**新しいホスト A または AAAA**] の作成オプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="a939b-180">**エイリアス名**を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="a939b-181">次に、 **Ip Addresss**に入力する領域が必要です。これは、上記の手順3で確認した、フロントエンドプール (または単一のフロントエンドサーバー、またはディレクタープールまたはディレクター) の ip アドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="a939b-182">ここに保存しなければならない場合があります。または、Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンで追加の A レコードまたは AAAA レコードを作成する必要がある場合は、この操作を行う必要があります。準備ができたら、作業内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="a939b-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="a939b-183">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="a939b-183">Modify certificates</span></span>
<span data-ttu-id="a939b-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a939b-184"></span></span>

<span data-ttu-id="a939b-185">証明書の計画について質問がある場合は、「 [Skype For Business Server のモバイル機能の計画](../plan-your-deployment/mobility.md)」の記事で説明しています。</span><span class="sxs-lookup"><span data-stu-id="a939b-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="a939b-186">それを読んだ後で、以下の点を説明します。</span><span class="sxs-lookup"><span data-stu-id="a939b-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="a939b-187">新しい証明書が必要か。</span><span class="sxs-lookup"><span data-stu-id="a939b-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="a939b-188">認証局 (CA) に新しい証明書を申請する。</span><span class="sxs-lookup"><span data-stu-id="a939b-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="a939b-189">PowerShell を使用して、使用中の証明書をアップグレードする。</span><span class="sxs-lookup"><span data-stu-id="a939b-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="a939b-190">Microsoft 管理コンソール (MMC) の証明書スナップインを使用して証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="a939b-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="a939b-191">新しい証明書が必要か。</span><span class="sxs-lookup"><span data-stu-id="a939b-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="a939b-192">まず使用中の証明書の内容を確認して、必要とするエントリーの有無を調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="a939b-193">そのためには、ローカル管理者のアカウントで Skype for Business サーバーにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="a939b-194">このアカウントには、手順中のいくつかで認証局 (CA) の発行権限も必要とされます。</span><span class="sxs-lookup"><span data-stu-id="a939b-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="a939b-195">Skype for Business Server 管理シェルを開きます ([スタート] メニューまたはタスクバーに固定されていない場合は、[検索] を使用して見つけることができます)。</span><span class="sxs-lookup"><span data-stu-id="a939b-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="a939b-p110">更新された証明書の追加を行う前に、すでに付与されている証明書の内容を知っておくことが重要となります。コマンドで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="a939b-p111">手順 3 で得られた情報は固有の内容です。内容を吟味して、複数のことに対して単一の証明書が付与されているのか、それとも証明書を必要とする別々のコンポーネントに別の証明書が付与されているのか判断します。**Use** パラメーターを使用すれば、証明書がどのように使われているかが分かり、**Thumbprint** パラメーターを使用すれば、証明書が同一か別々かが分かります。</span><span class="sxs-lookup"><span data-stu-id="a939b-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="a939b-p112">計画セクションで推奨されている SAN エントリーがあれば、申し分ありません。ない場合は、新規の証明書を 1 つ または複数の証明書を認証局に申請する必要があります (構成に依存します)。</span><span class="sxs-lookup"><span data-stu-id="a939b-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="a939b-203">認証局 (CA) に新しい証明書を申請する。</span><span class="sxs-lookup"><span data-stu-id="a939b-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="a939b-204">使用している SAN エントリを確認したら、 **1 つの証明書**(上記の手順に従って) があることを確認し、必要なエントリがすべて含まれていないことを確認しました。</span><span class="sxs-lookup"><span data-stu-id="a939b-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="a939b-205">新しい証明書の要求を CA に対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="a939b-206">Skype for Business Server PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="a939b-207">欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="a939b-208">複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a939b-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="a939b-209">代わりに DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="a939b-210">DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="a939b-211">一例として次のようになります (-Ca パラメーターを自分の認証局パスで置き換える)。</span><span class="sxs-lookup"><span data-stu-id="a939b-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="a939b-212">または、使用している SAN エントリが何であるかを確認した後、必要なエントリがすべて含まれていない**複数の証明書**があることがわかりました。</span><span class="sxs-lookup"><span data-stu-id="a939b-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="a939b-213">新しい証明書の要求を CA に対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="a939b-214">Skype for Business Server PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="a939b-215">欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="a939b-216">複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a939b-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="a939b-217">代わりに DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="a939b-218">DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="a939b-219">次のような例になります (-Ca パラメーターを自分の認証局パスで置き換える)。</span><span class="sxs-lookup"><span data-stu-id="a939b-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="a939b-220">CA により新しい証明書が作成されたら、それを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a939b-221">Skype for Business Server 管理シェルを使用して証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a939b-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="a939b-222">「新しい証明書が必要か」のセクションで判明した内容に応じて、次のうちの**いずれか 1 つ**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="a939b-223">すべてに対して単一の証明書しかない (どの thumbprint も同じ) 場合、これを実行します。</span><span class="sxs-lookup"><span data-stu-id="a939b-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="a939b-224">別々の証明書が付与されている (thumbprint が異なる) 場合、代わりにこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="a939b-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="a939b-225">Microsoft 管理コンソール (MMC)</span><span class="sxs-lookup"><span data-stu-id="a939b-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="a939b-p117">MMC の証明書スナップインを使用して、証明書を調べるオプションを利用します。検索に MMC と入力すれば、アプリケーション オプションのようにポップアップします。</span><span class="sxs-lookup"><span data-stu-id="a939b-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="a939b-p118">証明書スナップインを追加するには、「**ファイル**] をクリックしてから [**スナップインの追加と削除...**] をクリックします (またはキーボード ショートカット **Ctrl+M** を利用してもよい)。 **証明書** が左側のウィンドウにオプションとして表示されるので、それを選択してから、ポップアップ ウィンドウで [**コンピュータ アカウント**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a939b-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="a939b-230">まだポップアップ ウィンドウの中で、おそらく調べたい証明書が所属しているコンピュータ上で作業を行っているはずなので、そうであれば選択されている [**ローカル コンピュータ**] のままにします。</span><span class="sxs-lookup"><span data-stu-id="a939b-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="a939b-231">リモート マシンで作業を行っている場合は、ラジオ ボタンを [**別のコンピュータ**] に切り替え、そのコンピュータの QFDN を入力するか、[**参照**] ボタンを使用して AD 内でそのコンピュータを探します。</span><span class="sxs-lookup"><span data-stu-id="a939b-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="a939b-232">コンピューターを選択した後は、準備ができたら [**完了**] をクリックし、[ **OK]** をクリックしてスナップインを MMC に追加します。</span><span class="sxs-lookup"><span data-stu-id="a939b-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="a939b-233">MMC の左側のウィンドウで [**証明書**] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a939b-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="a939b-234">[**個人**] フォルダーも展開して、[**証明書**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a939b-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="a939b-235">これでこのストアにある証明書を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="a939b-236">表示したい証明書の場所を探すには、証明書を右クリックし、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a939b-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a939b-237">これはどのような証明書を知っていますか?</span><span class="sxs-lookup"><span data-stu-id="a939b-237">How do you know what certificate this is?</span></span> <span data-ttu-id="a939b-238">1つの証明書がファームのすべてに割り当てられているか、既定の Web サービスなどのさまざまな証明書がある場合は、複数の証明書を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="a939b-239">複数の証明書の拇印は同じになります。</span><span class="sxs-lookup"><span data-stu-id="a939b-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="a939b-p122">**証明書** ビューが表示されたら、[**詳細**] を選択します。そこで [**サブジェクト**] を選択すると、証明書のサブジェクト名が表示され、付与されたサブジェクト名と関連プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a939b-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="a939b-p123">**サブジェクトの別名**エントリーも確認する必要があります。次のうちの 1 つまたは複数が見つかります。</span><span class="sxs-lookup"><span data-stu-id="a939b-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="a939b-244">このプールのプール名、または1つのサーバー名 (プールではない場合)。</span><span class="sxs-lookup"><span data-stu-id="a939b-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="a939b-245">証明書が割り当てられるサーバーの名前</span><span class="sxs-lookup"><span data-stu-id="a939b-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="a939b-246">簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)</span><span class="sxs-lookup"><span data-stu-id="a939b-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="a939b-247">Web サービスの内部および Web サービス外部名 (webpool01.contoso.net、webpool01.contoso.com など) は、トポロジビルダーでの選択肢と、[Web サービスの変更] オプションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a939b-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="a939b-248">既に割り当てられている場合は、lyncdiscover です。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコード。</span><span class="sxs-lookup"><span data-stu-id="a939b-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="a939b-249">割り当てられている証明書が 2つ以上の場合は、それらを確認する必要があります (上記の注記を参照)。</span><span class="sxs-lookup"><span data-stu-id="a939b-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="a939b-250">Lyncdiscover を見つけた場合は、\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコードは、既に設定されています。</span><span class="sxs-lookup"><span data-stu-id="a939b-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="a939b-251">MMC を終了します。</span><span class="sxs-lookup"><span data-stu-id="a939b-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="a939b-252">これらが割り当てられていない場合は、新しい証明書を申請するか (上記で概説)、これらをポストリクエストでインストールする必要があります (次の PowerShell を推奨)。</span><span class="sxs-lookup"><span data-stu-id="a939b-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="a939b-253">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-253">Configure the reverse proxy</span></span>
<span data-ttu-id="a939b-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="a939b-254"></span></span>

<span data-ttu-id="a939b-p125">次の手順は、そのとおりに実行するように意図されたものではありません。と言うのは、製品の前のバージョンで、たとえば Threat Management Gateway (TMG) の構成について順を追って手順を説明しました。これを使用していないのであれば、自分のバージョンではそこから仕上げる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="a939b-257">TMG は、Microsoft によって製品として提供されていないため、まだ構成が必要な場合は、「 [Lync Server 2013 の手順](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a939b-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="a939b-258">ただし、次の情報は、各リバースプロキシ用の特定のチュートリアル手順を提供する方法がない場合でも、より一般的に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="a939b-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="a939b-259">検討すべき重要な事柄が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="a939b-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="a939b-260">最初の自動検出申請を HTTPS で行いますか (それを推奨しています)。</span><span class="sxs-lookup"><span data-stu-id="a939b-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="a939b-261">Web 公開ルールがある場合、それを変更する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="a939b-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="a939b-262">まだ Web 公開ルールがないのであれば、それを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="a939b-263">最初の自動検出申請を HTTPS で行うのであれば、規則の作成や変更も必要となります。</span><span class="sxs-lookup"><span data-stu-id="a939b-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a939b-264">**重要**プロキシのタイムアウト値は、展開から展開までのさまざまな数値です。</span><span class="sxs-lookup"><span data-stu-id="a939b-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="a939b-265">クライアントに最適なエクスペリエンスを実現するには、展開を監視して、値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="a939b-266">この値は、200に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="a939b-267">環境で Lync モバイルクライアントをサポートしている場合は、値を960に設定して、タイムアウト値が900である Office 365 からプッシュ通知のタイムアウトを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="a939b-268">この値が低すぎる場合はクライアントの切断を回避するためにタイムアウト値を増やす必要があります。または、クライアントの接続が切断された後に、プロキシ経由の接続が切断されない場合は、その数を少なくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="a939b-269">環境に応じた通常の監視とベースラインの設定は、この値の適切な設定を判断する唯一の唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="a939b-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="a939b-270">外部自動検出 SAN および URL の既存の Web 公開ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="a939b-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="a939b-271">リバースプロキシインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a939b-272">Web 公開ルールを見つけて、[編集] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブにある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="a939b-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="a939b-273">この web 公開ルールが適用される場所を示す領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="a939b-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="a939b-274">着信サイトやサイトへのリクエストに関するこのルールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="a939b-275">新しいエントリーを**追加**します。</span><span class="sxs-lookup"><span data-stu-id="a939b-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="a939b-276">[自動検出サイト] の名前 (使用する例は lyncdiscover.contoso.com) を入力し、リバースプロキシの形式に応じて [ **OK]** または [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a939b-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="a939b-277">自動検出 SAN エントリーのある新しい証明書が付与されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="a939b-278">これは、リバースプロキシの設定に従ってインストールし、使用できるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="a939b-279">構成が完了したら、必ずすべてを保存してください。</span><span class="sxs-lookup"><span data-stu-id="a939b-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="a939b-280">リバースプロキシに**テスト**機能がある場合は、その機能を利用して、すべてが正しく動作することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a939b-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="a939b-281">これで、使用している環境にディレクターまたはディレクタープールがある場合は、次の手順を繰り返すことが必要になることがあります (これは、2つ目のルールがあることを意味します)。</span><span class="sxs-lookup"><span data-stu-id="a939b-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="a939b-282">外部の自動検出 URL 用の web 公開ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="a939b-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="a939b-283">リバースプロキシインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a939b-284">Web 公開ルールを作成するインターフェイス内の場所を特定し、[**新規**作成] または [**作成**] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブに表示される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="a939b-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="a939b-285">新しい Web 公開ルールを作成するためのオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="a939b-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="a939b-286">一般的に次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="a939b-287">**名前**: 規則の名前</span><span class="sxs-lookup"><span data-stu-id="a939b-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="a939b-288">**ルールアクション**: この例では、**許可**ルールであり、逆プロキシを通じて何らかの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="a939b-289">選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。</span><span class="sxs-lookup"><span data-stu-id="a939b-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="a939b-290">外部アクセス用に **SSL** にする必要があるため、そのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a939b-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="a939b-291">**内部公開**用のパスを公開し、フロントエンドプールのロードバランサーに外部 Web サービスの fqdn を入力する必要があります。または、所有している場合は、ディレクタープールのロードバランサーの fqdn (存在する場合は、ディレクタープールのロードバランサーの fqdn) を sfb_pool01 使用します。</span><span class="sxs-lookup"><span data-stu-id="a939b-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="a939b-292">公開するパス\*\* /\*\* として「\*」と入力しますが、**元のホストヘッダーも転送**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="a939b-p131">**パブリック名または外部名**の詳細や情報のオプションがあります。ここに</span><span class="sxs-lookup"><span data-stu-id="a939b-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="a939b-295">**Accept requests** と入力できますが、これはドメイン名用です。</span><span class="sxs-lookup"><span data-stu-id="a939b-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="a939b-296">**名前**には **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="a939b-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="a939b-297"><sipdomain>(外部自動検出サービス URL)。</span><span class="sxs-lookup"><span data-stu-id="a939b-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="a939b-298">ここで、フロントエンドプールで外部 Web サービスの URL のルールを作成する場合は、外部 Web サービスの FQDN を、フロントエンドプールに入力する必要があります (たとえば、lyncwebextpool01.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a939b-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="a939b-299">[ **Path** ] オプションが表示されます。ここに「 \*\* / \*\*\*」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="a939b-300">最新のユーザー アカウントで **SSL リスナー**を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="a939b-301">**認証の委任**を [**委任できません。** クライアントの直接認証を\*\*\*\* 許可します] に設定します。</span><span class="sxs-lookup"><span data-stu-id="a939b-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="a939b-302">ルールが**全ユーザー**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a939b-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="a939b-303">これがこのルールを作成して、手順を進めるために必要なすべての情報です。</span><span class="sxs-lookup"><span data-stu-id="a939b-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="a939b-304">**元のホスト ヘッダー**が転送されたか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="a939b-305">**Web サーバー**のポートも設定する必要があります。次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="a939b-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="a939b-306">
            [\*\*HTTP ポートに要求をリダイレクトする\**] を選択し、ポート番号を  **8080** にします。</span><span class="sxs-lookup"><span data-stu-id="a939b-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="a939b-307">
            [\*\*SSL ポートに要求をリダイレクトする\**] を選択し、ポート番号を  **4443** にします。</span><span class="sxs-lookup"><span data-stu-id="a939b-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="a939b-308">すべての構成が終了したら、構成内容を保存または適用してからルールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="a939b-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="a939b-309">ポート 80 の Web 公開ルールを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="a939b-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="a939b-310">リバースプロキシインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a939b-311">Web 公開ルールを作成するインターフェイス内の場所を特定し、[**新規**作成] または [**作成**] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブに表示される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="a939b-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="a939b-312">新しい Web 公開ルールを作成するためのオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="a939b-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="a939b-313">一般的に次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="a939b-314">**名前**: 規則の名前</span><span class="sxs-lookup"><span data-stu-id="a939b-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="a939b-315">**ルールアクション**: この例では、**許可**ルールであり、逆プロキシを通じて何らかの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="a939b-316">選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。</span><span class="sxs-lookup"><span data-stu-id="a939b-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="a939b-317">これは [**公開された Web サーバーまたはサーバー ファームへの接続に、セキュリティで保護されていない接続を使用する**] にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="a939b-318">**内部公開**用のパスを公開し、フロントエンドプールのロードバランサーの**VIP アドレス**の FQDN を入力する必要がある場合は、sfb_pool01 例として「.local」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="a939b-319">公開するパス\*\* /\*\* として「\*」と入力しますが、**元のホストヘッダーも転送**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="a939b-p134">**パブリック名または外部名**の詳細や情報のオプションがあります。ここに</span><span class="sxs-lookup"><span data-stu-id="a939b-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="a939b-322">**Accept requests** と入力できますが、これはドメイン名用です。</span><span class="sxs-lookup"><span data-stu-id="a939b-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="a939b-323">**名前**には **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="a939b-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="a939b-324"><sipdomain>(外部自動検出サービス URL)。</span><span class="sxs-lookup"><span data-stu-id="a939b-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="a939b-325">[ **Path** ] オプションが表示されます。ここに「 \*\* / \*\*\*」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="a939b-326">Web リスナーを選ぶか、リバースプロキシで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="a939b-327">**認証の委任**を [**委任できません。** クライアントの直接認証を\*\*\*\* 許可します] に設定します。</span><span class="sxs-lookup"><span data-stu-id="a939b-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="a939b-328">ルールが**全ユーザー**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a939b-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="a939b-329">これがこのルールを作成して、手順を進めるために必要なすべての情報です。</span><span class="sxs-lookup"><span data-stu-id="a939b-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="a939b-330">**Web サーバー**のポートを設定する必要があります。次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="a939b-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="a939b-331">
            [\*\*HTTP ポートに要求をリダイレクトする\**] を選択し、ポート番号を  **8080** にします。</span><span class="sxs-lookup"><span data-stu-id="a939b-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="a939b-332">
            [\*\*SSL ポートに要求をリダイレクトする\**] を選択し、ポート番号を  **4443** にします。</span><span class="sxs-lookup"><span data-stu-id="a939b-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="a939b-333">すべての構成が終了したら、構成内容を保存または適用してからルールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="a939b-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="a939b-334">ハイブリッド展開でのモビリティの自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="a939b-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="a939b-335"></span></span>

<span data-ttu-id="a939b-336">Skype for Business Server のハイブリッド環境は、オンプレミスと O365 の環境を組み合わせた環境です。</span><span class="sxs-lookup"><span data-stu-id="a939b-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="a939b-337">ハイブリッド環境で Skype for Business Server を使用している場合、自動検出サービスでは、これらの環境のいずれかからユーザーを検索できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="a939b-p137">モバイル クライアントがユーザーの場所を検出できるようにするには、自動検出サービスを新しい URL で構成する必要があります。手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a939b-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="a939b-340">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a939b-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="a939b-341">Skype for Business Server 環境の属性**Proxyfqdn**の値を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a939b-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="a939b-342">それからシェル ウィンドウ内で以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="a939b-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="a939b-343">[identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a939b-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="a939b-344">モビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="a939b-344">Test your Mobility deployment</span></span>
<span data-ttu-id="a939b-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="a939b-345"></span></span>

<span data-ttu-id="a939b-346">Skype for Business Server Mobility Service と Skype for Business Server 自動検出サービスを展開したら、テストトランザクションを実行して、展開が正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a939b-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="a939b-347">**Test-CsUcwaConference** を実行して、会議における 2 人のユーザーの作成、参加、および通信能力をテストできます。</span><span class="sxs-lookup"><span data-stu-id="a939b-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="a939b-348">ユーザー (実際のユーザーまたはテスト ユーザー) 2人とテストを行うための完全な資格情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="a939b-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="a939b-349">このコマンドは、Skype for Business クライアントと Lync Server 2013 クライアントの両方に対応しています。</span><span class="sxs-lookup"><span data-stu-id="a939b-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="a939b-350">Skype for Business Server 2015 上の Lync Server 2010 クライアントの場合、テストのために**CsMcxP2PIM**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="a939b-351">Lync Server 2010 ユーザーは、実際のユーザー、または事前定義されたテストユーザーである必要があります。また、パスワード資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="a939b-352">Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a939b-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a939b-353">現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="a939b-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a939b-354">MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="a939b-355">Skype for Business and Lync 2013 モバイル クライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="a939b-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="a939b-356">**Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターで、 **csadministrator**ロールのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="a939b-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a939b-357">**Skype For Business Server 管理シェル**を起動します ([検索] に名前を入力するか、[**すべてのプログラム**] に移動して選択します)。</span><span class="sxs-lookup"><span data-stu-id="a939b-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="a939b-358">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="a939b-p141">スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a939b-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="a939b-361">Lync 2010 モバイル クライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="a939b-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="a939b-362">Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a939b-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a939b-363">現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="a939b-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a939b-364">MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="a939b-365">**Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターで、 **csadministrator**ロールのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="a939b-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a939b-366">**Skype For Business Server 管理シェル**を起動します ([検索] に名前を入力するか、[**すべてのプログラム**] に移動して選択します)。</span><span class="sxs-lookup"><span data-stu-id="a939b-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="a939b-367">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="a939b-p143">スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a939b-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="a939b-370">コマンド プロシージャについて詳細を調べるには、「[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)」および「 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a939b-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="a939b-371">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-371">Configure for push notifications</span></span>
<span data-ttu-id="a939b-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="a939b-372"></span></span>

<span data-ttu-id="a939b-373">プッシュ通知は、Skype または Lync アプリが非アクティブであっても、バッジ、アイコン、または警告の形式で送信できます。</span><span class="sxs-lookup"><span data-stu-id="a939b-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="a939b-374">プッシュ通知とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="a939b-374">But what are push notifications?</span></span> <span data-ttu-id="a939b-375">これはユーザーに、新規または不在着信の IM 招待状、受信したボイス メールなどのイベントを通知するものです。</span><span class="sxs-lookup"><span data-stu-id="a939b-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="a939b-376">Skype for Business Server Mobility service は、これらの通知をクラウドベースの Skype for Business Server プッシュ通知サービスに送信します。これにより、Windows Phone ユーザー用の Microsoft プッシュ通知サービス (MSNS) に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a939b-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="a939b-377">この機能は Lync Server 2013 から変更されませんが、Skype for Business Server をお持ちの場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a939b-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="a939b-378">Skype for Business Server Edge Server の場合は、新しいホスティングプロバイダーである Microsoft Skype for Business Online を追加し、組織と Skype for Business Online の間でホスティングプロバイダーフェデレーションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="a939b-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="a939b-p145">プッシュ通知を有効にするには、 **Set-CsPushNotificationConfiguration** コマンドレットを実行する必要があります。既定では、プッシュ通知は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a939b-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="a939b-381">フェデレーション構成とプッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="a939b-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="a939b-382">Skype for Business エッジ サーバーのプッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="a939b-383">**Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a939b-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a939b-384">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="a939b-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a939b-385">Skype for Business Server online ホスティングプロバイダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a939b-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="a939b-386">例:</span><span class="sxs-lookup"><span data-stu-id="a939b-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="a939b-p146">単一のホスティング プロバイダーに対して複数のフェデレーション関係を持つことはできません。そのため sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既に設定している場合は、ホスティング プロバイダーの ID が SkypeOnline 以外のものであっても、別のホスティング プロバイダーを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="a939b-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="a939b-389">組織と Skype for Business Online のプッシュ通知サービスとの間のホスティングプロバイダーフェデレーションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="a939b-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="a939b-390">コマンド ラインで次ぎように入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="a939b-391">プッシュ通知を有効にする</span><span class="sxs-lookup"><span data-stu-id="a939b-391">Enable push notifications</span></span>

1. <span data-ttu-id="a939b-392">**Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a939b-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a939b-393">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="a939b-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a939b-394">プッシュ通知を有効にする:</span><span class="sxs-lookup"><span data-stu-id="a939b-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="a939b-395">フェデレーションを有効にする:</span><span class="sxs-lookup"><span data-stu-id="a939b-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="a939b-396">フェデレーションとプッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="a939b-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="a939b-397">**Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a939b-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a939b-398">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="a939b-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a939b-399">フェデレーションの構成をテストする</span><span class="sxs-lookup"><span data-stu-id="a939b-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="a939b-400">例:</span><span class="sxs-lookup"><span data-stu-id="a939b-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="a939b-401">プッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="a939b-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="a939b-402">例:</span><span class="sxs-lookup"><span data-stu-id="a939b-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="a939b-403">モビリティ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a939b-403">Configure Mobility policy</span></span>
<span data-ttu-id="a939b-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="a939b-404"></span></span>

<span data-ttu-id="a939b-405">Skype for Business Server を使用すると、モビリティサービスを使うことができるユーザー、勤務先の電話での通話、ボイスオーバー IP (VoIP)、ビデオのほか、VoIP またはビデオに WiFi が必要かどうかを特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a939b-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="a939b-406">[勤務先から通話] 機能では、モバイル ユーザーが携帯電話の番号ではなく、勤務先の電話番号を使用して携帯電話で通話を発信および着信できます。</span><span class="sxs-lookup"><span data-stu-id="a939b-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="a939b-407">この機能により、相手に発信者の携帯電話番号が表示されるのを防ぎ、発信の電話料金を回避できます。</span><span class="sxs-lookup"><span data-stu-id="a939b-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="a939b-408">VoIP およびビデオを設定すると、VoIP 通話の発信と着信やビデオの利用ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="a939b-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="a939b-409">また、WiFi の使用法の設定では、携帯電話会社の回線経由での WiFi ネットワークの使用をユーザーのデバイスで必須にするかどうかを決められます。</span><span class="sxs-lookup"><span data-stu-id="a939b-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="a939b-410">モバイル機能、勤務先からの通話、VoIP およびビデオ機能は、すべて既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a939b-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="a939b-411">VoIP およびビデオで WiFi を必須にする設定は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a939b-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="a939b-412">管理者は、グローバルに、サイト別に、またはユーザー別にこれらの機能を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a939b-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="a939b-413">モバイル機能を使用し、勤務先から通話を発信できるようにするには、次のことが必要です。</span><span class="sxs-lookup"><span data-stu-id="a939b-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="a939b-414">Skype for Business Server に対応</span><span class="sxs-lookup"><span data-stu-id="a939b-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="a939b-415">エンタープライズ VoIP が有効。</span><span class="sxs-lookup"><span data-stu-id="a939b-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="a939b-416">**EnableMobility**オプションが**True**に設定されたモビリティポリシーが割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="a939b-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="a939b-417">[勤務先から通話] を使用するには、ユーザーが次の前提条件も満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a939b-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="a939b-418">[\*\*電話の同時呼び出しを有効にする \*\*] オプションを選択した音声ポリシーが割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="a939b-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="a939b-419">**EnableOutsideVoice**が**True**に設定されたモビリティポリシーを割り当てました。</span><span class="sxs-lookup"><span data-stu-id="a939b-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a939b-p150">エンタープライズ VoIP が有効になっていないユーザーは、関連付けられている音声ポリシーのオプション設定が適切であれば、モバイル デバイスで [クリックして参加] リンクを使用すれば、モバイル デバイスから Skype 間の VoIP 通話や会議参加会議ができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="a939b-422">グローバル モビリティ ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="a939b-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="a939b-423">**Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a939b-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a939b-424">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="a939b-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a939b-425">次のように入力することにより、機動性へのアクセスをオフにして、世界中で通話を発信します</span><span class="sxs-lookup"><span data-stu-id="a939b-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="a939b-426">「モビリティーへのアクセスをオフにする」をオフにすると、勤務先から通話をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="a939b-427">ただし、勤務先からの通話をオフにすることなく、モバイル機能をオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a939b-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="a939b-428">詳しくは、「 [Set-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a939b-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="a939b-429">サイトごとのモバイル機能ポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="a939b-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="a939b-430">**Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a939b-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a939b-431">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="a939b-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a939b-p152">サイト レベルのポリシーを作成し、VoIP とビデオを無効にして、IP オーディオと IP ビデオに対して WiFi を必須にする機能をサイト別に有効にします。次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="a939b-434">詳細については、「 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a939b-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="a939b-435">ユーザーによるモビリティポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="a939b-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="a939b-436">**Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a939b-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a939b-437">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="a939b-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a939b-438">ユーザーレベルのモバイル処理ポリシーを作成し、機動性をオフにして、ユーザーによる勤務先から通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="a939b-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="a939b-439">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a939b-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="a939b-440">サンプル データ付き詳細例:</span><span class="sxs-lookup"><span data-stu-id="a939b-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="a939b-441">「モビリティーへのアクセスをオフにする」をオフにすると、勤務先から通話をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a939b-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="a939b-442">ただし、勤務先からの通話をオフにすることなく、モバイル機能をオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a939b-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

