---
title: Skype for Business Server のモビリティを展開および構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この記事では、モビリティサービスを使用するように既存の Skype for Business Server のインストールを構成する手順について説明します。これにより、モバイルデバイスで Skype for Business Server のモビリティ機能を利用できるようになります。
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029068"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="4ffd5-103">Skype for Business Server のモビリティを展開および構成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="4ffd5-104">この記事では、モビリティサービスを使用するように既存の Skype for Business Server のインストールを構成する手順について説明します。これにより、モバイルデバイスで Skype for Business Server のモビリティ機能を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="4ffd5-105">Skype for business [server のモビリティの計画](../plan-your-deployment/mobility.md)を確認したら、以下の手順を続行して、モビリティを Skype For business server 環境に展開する準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="4ffd5-106">手順は次のとおりです (この表には、アクセス許可の一覧が含まれています)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="4ffd5-107">**フェーズ**</span><span class="sxs-lookup"><span data-stu-id="4ffd5-107">**Phase**</span></span>|<span data-ttu-id="4ffd5-108">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="4ffd5-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4ffd5-109">DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="4ffd5-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="4ffd5-110">Domain Admins</span></span>  <br/> <span data-ttu-id="4ffd5-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="4ffd5-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="4ffd5-112">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="4ffd5-113">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="4ffd5-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="4ffd5-114">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="4ffd5-115">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="4ffd5-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="4ffd5-116">ハイブリッド展開によるモビリティの自動検出の構成</span><span class="sxs-lookup"><span data-stu-id="4ffd5-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="4ffd5-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="4ffd5-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="4ffd5-118">モビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="4ffd5-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="4ffd5-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4ffd5-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="4ffd5-120">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="4ffd5-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4ffd5-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="4ffd5-122">モビリティポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="4ffd5-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4ffd5-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="4ffd5-124">以降のすべてのセクションには、計画のトピックを読んでいることを前提とする手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="4ffd5-125">混乱が生じた場合は、その情報を自由に確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="4ffd5-126">従来のモバイルクライアントに対する MCX (Mobility Service) のサポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4ffd5-127">現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4ffd5-128">MCX を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="4ffd5-129">DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-129">Create DNS records</span></span>
<span data-ttu-id="4ffd5-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="4ffd5-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="4ffd5-131">これらは、既に Skype for Business Server 環境の一部として用意されている場合がありますが、自動検出を動作させるには、次のレコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="4ffd5-132">組織のネットワーク内から接続しているモバイルユーザーをサポートするための内部 DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="4ffd5-133">組織のネットワーク外から接続しているモバイルユーザーをサポートするための外部 (またはパブリック) DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="4ffd5-134">これらのレコードは、(ホスト) 名または CNAME レコードのいずれかにすることができます (両方の操作を行う必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="4ffd5-135">内部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="4ffd5-136">**Domain Admins**グループまたは**DnsAdmins**グループのメンバーである、ネットワーク内の DNS サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="4ffd5-137">[**スタート**] ボタンをクリックし、[**管理ツール**] を選択します ([スタート] メニューからオプションが表示されていない場合に**検索**する必要がある場合があります)。次に、[ **DNS** ] をクリックして、dns 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="4ffd5-138">コンソールウィンドウの左側のウィンドウで、Skype for Business Server のフロントエンドサーバーのホームとなるドメインに移動し、そこで**前方参照ゾーン**を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="4ffd5-139">すぐに、次のどちらがあるか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="4ffd5-140">フロントエンドサーバー (Standard または Enterprise) またはフロントエンドプールの任意のホスト A または AAAA レコード。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="4ffd5-141">ディレクターまたはディレクタープールの任意のホスト A または AAAA レコード (展開でオプションとして使用できる構成)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="4ffd5-142">この点を確認したら、SIP ドメイン名を右クリックし、メニューから [**新しいエイリアス (CNAME)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="4ffd5-143">[**エイリアス名**] テキストボックスに、内部自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="4ffd5-144">**完全修飾ドメイン名 (ターゲットホストの fqdn**) で、前の手順4で確認したフロントエンドプール (または単一のフロントエンドサーバーまたはディレクタープールまたはディレクター) の内部 WEB サービス fqdn を入力または参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="4ffd5-145">入力した場合は、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="4ffd5-146">Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="4ffd5-147">外部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="4ffd5-148">これらの手順は汎用的なものですが、使用しているパブリック DNS プロバイダーを知ることはできませんが、サポートが必要な場合もあります。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="4ffd5-149">この時点で、Skype for Business Server には SIP ドメインが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="4ffd5-150">この SIP ドメインの**前方参照ゾーン**を展開するか、またはそれを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="4ffd5-151">すぐに、次のどちらがあるか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="4ffd5-152">フロントエンドサーバー (Standard または Enterprise) またはフロントエンドプールの任意のホスト A または AAAA レコード。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="4ffd5-153">ディレクターまたはディレクタープールの任意のホスト A または AAAA レコード (展開でオプションとして使用できる構成)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="4ffd5-154">この情報を取得すると、**新しいエイリアス (CNAME)** を作成するためのオプションを選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="4ffd5-155">これで、**エイリアス名**を入力できるようになります。外部自動検出サービス URL には、lyncdiscover を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="4ffd5-156">次に、**ターゲットホストの fqdn**に入力する領域が存在する必要があります。これは、前述の手順3で確認したフロントエンドプール (または単一のフロントエンドサーバーまたはディレクタープールまたはディレクター) の fqdn である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="4ffd5-157">ここで保存する必要がある場合や、Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンで追加の CNAME レコードを作成する必要がある場合は、この手順を実行する必要がありますが、準備が整ったら、作業を保存します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="4ffd5-158">内部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="4ffd5-159">**Domain Admins**グループまたは**DnsAdmins**グループのメンバーである、ネットワーク内の DNS サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="4ffd5-160">[**スタート**] ボタンをクリックし、[**管理ツール**] を選択します ([スタート] メニューからオプションが表示されていない場合に**検索**する必要がある場合があります)。次に、[ **DNS** ] をクリックして、dns 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="4ffd5-161">コンソールウィンドウの左側のウィンドウで、Skype for Business Server のフロントエンドサーバーのホームとなるドメインに移動し、そこで**前方参照ゾーン**を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="4ffd5-162">すぐに、次のどちらがあるか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="4ffd5-163">フロントエンドサーバー (Standard または Enterprise) またはフロントエンドプールの任意のホスト A または AAAA レコード。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="4ffd5-164">ディレクターまたはディレクタープールの任意のホスト A または AAAA レコード (展開でオプションとして使用できる構成)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="4ffd5-165">この点を確認したら、SIP ドメイン名を右クリックし、メニューから [**新しいホスト (A または AAAA)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="4ffd5-166">[**名前**] ボックスに、内部自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="4ffd5-167">[ **IP アドレス**] テキストボックスに、前の手順4で確認したフロントエンドプール (または単一のフロントエンドサーバーまたはディレクタープールまたはディレクター) の内部 WEB サービス IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="4ffd5-168">完了したら、[**ホストの追加**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="4ffd5-169">Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 A または AAAA レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="4ffd5-170">これを行うには、必要に応じて、手順6-8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="4ffd5-171">完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="4ffd5-172">外部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="4ffd5-173">これらの手順は汎用的なものですが、使用しているパブリック DNS プロバイダーを知ることはできませんが、サポートが必要な場合もあります。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="4ffd5-174">この時点で、Skype for Business Server には SIP ドメインが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="4ffd5-175">この SIP ドメインの**前方参照ゾーン**を展開するか、またはそれを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="4ffd5-176">すぐに、次のどちらがあるか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="4ffd5-177">フロントエンドサーバー (Standard または Enterprise) またはフロントエンドプールの任意のホスト A または AAAA レコード。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="4ffd5-178">ディレクターまたはディレクタープールの任意のホスト A または AAAA レコード (展開でオプションとして使用できる構成)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="4ffd5-179">この情報を取得すると、**新しいホスト a または AAAA**を作成するためのオプションを選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="4ffd5-180">これで、**名前**を入力できるようになります。外部自動検出サービス URL には、lyncdiscover を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="4ffd5-181">次に、 **Ip Addresss**で入力する領域が必要になります。これは、前の手順3で確認したフロントエンドプール (または単一のフロントエンドサーバーまたはディレクタープールまたはディレクター) の IP である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="4ffd5-182">ここで保存する必要がある場合や、Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンで追加の A または AAAA レコードを作成する必要がある場合は、そのようにする必要があります。準備が整ったら、作業を保存します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="4ffd5-183">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-183">Modify certificates</span></span>
<span data-ttu-id="4ffd5-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="4ffd5-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="4ffd5-185">証明書の計画についてご質問がある場合は、「 [Skype for Business Server のモビリティの計画](../plan-your-deployment/mobility.md)」の記事で説明しています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="4ffd5-186">その点を確認したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="4ffd5-187">新しい証明書が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="4ffd5-188">証明機関 (CA) から新しい証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="4ffd5-189">PowerShell を使用して、インプレース証明書を置き換えて更新します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="4ffd5-190">Microsoft 管理コンソール (MMC) の証明書スナップインを使用して証明書を確認する。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="4ffd5-191">新しい証明書が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="4ffd5-192">最初に、どの証明書がインプレースになっているか、また必要なエントリがあるかどうかを確認して確認する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="4ffd5-193">そのためには、ローカル管理者のアカウントを使用して Skype for Business Server にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="4ffd5-194">このアカウントには、これらの手順の一部についても、発行元の証明機関 (CA) に対する権限が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="4ffd5-195">[Skype for Business Server 管理シェル] を開きます ([スタート] メニューまたはタスクバーに固定していない場合は、検索を使用して見つけることができます)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="4ffd5-196">更新された証明書を追加する前に、どの証明書が割り当てられているかを知ることが重要になります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="4ffd5-197">そのため、コマンドで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="4ffd5-198">手順3の情報は、自分にとって一意です。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="4ffd5-199">複数の用途に対して割り当てられた1つの証明書があるかどうか、または必要なさまざまなコンポーネントに対して異なる証明書が割り当てられているかどうかを判断するには、それを調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="4ffd5-200">**Use**パラメーターは、証明書がどのように使用されているかを示し、 **Thumbprint**パラメーターは、すべて同じ証明書、または複数の証明書があるかどうかを通知します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="4ffd5-201">「計画」セクションで推奨されている SAN エントリがある場合は、問題ありません。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="4ffd5-202">それ以外の場合は、新しい証明書、または (構成に応じて) 証明機関からの複数の証明書を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="4ffd5-203">証明機関 (CA) から新しい証明書または証明書を要求する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="4ffd5-204">どの SAN エントリを使用しているかを確認した後、 **1 つの証明書**があること (前述の手順を実行した後)、必要なすべてのエントリがないことがわかりました。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="4ffd5-205">CA に対して新しい証明書の要求を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="4ffd5-206">Skype for Business Server PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="4ffd5-207">不足している自動検出サービス SAN (-Ca パラメーターを独自の証明機関パスに置き換えます):</span><span class="sxs-lookup"><span data-stu-id="4ffd5-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="4ffd5-208">これで、複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="4ffd5-209">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="4ffd5-210">また、DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="4ffd5-211">例としては、次のようになります (-Ca パラメーターを独自の証明機関パスで置き換える)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="4ffd5-212">または、どの SAN エントリを使用しているかを確認した後、必要なエントリがすべて含まれていない**複数の証明書**があることがわかりました。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="4ffd5-213">CA に対して新しい証明書の要求を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="4ffd5-214">Skype for Business Server PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="4ffd5-215">不足している自動検出サービス SAN (-Ca パラメーターを独自の証明機関パスに置き換えます):</span><span class="sxs-lookup"><span data-stu-id="4ffd5-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="4ffd5-216">これで、複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="4ffd5-217">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="4ffd5-218">また、DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="4ffd5-219">例を示します (-Ca パラメーターを独自の証明機関パスで置き換える)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="4ffd5-220">CA によって新しい証明書が生成されたら、それらを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4ffd5-221">Skype for Business Server 管理シェルを使用して証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="4ffd5-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="4ffd5-222">上記の「新しい証明書を必要とする」セクションで見つけた内容に応じて、次の**いずれか**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="4ffd5-223">すべてに対して1つの証明書がある場合 (拇印が同一) の場合は、次のことを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="4ffd5-224">何らかの証明書を取得している場合 (拇印はすべて異なる)、代わりに次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="4ffd5-225">Microsoft 管理コンソール (MMC) での証明書の表示</span><span class="sxs-lookup"><span data-stu-id="4ffd5-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="4ffd5-226">MMC の証明書スナップインを使用して証明書を確認するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="4ffd5-227">検索に MMC と入力するだけで、アプリケーションオプションとしてポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="4ffd5-228">証明書スナップインを追加するには、[**ファイル**] をクリックし、[**スナップインの追加と削除**] (または、キーボードショートカット**Ctrl + M**も動作します) をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="4ffd5-229">**証明書**は左側のウィンドウでオプションとなり、それを選択して**から、** [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="4ffd5-230">ポップアップウィンドウで、表示する必要がある証明書をホームにしているコンピューターでこれを実行する可能性がある場合は、[**ローカルコンピューター** ] を選択したままにします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="4ffd5-231">リモートコンピューターで作業している場合は、ラジオボタンを**別のコンピューター**に変更し、そのコンピューターの FQDN を入力するか、[**参照**] ボタンを使用してそのコンピューターを AD 経由で検索します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="4ffd5-232">コンピューターを選択したら、[準備ができたら、**完了**] をクリックし**てから、** スナップインを MMC に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="4ffd5-233">MMC の左側のウィンドウで、[**証明書**] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="4ffd5-234">[**個人**] フォルダーも展開し、[**証明書**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="4ffd5-235">これにより、このストア内の証明書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="4ffd5-236">表示する証明書を見つけて右クリックし、[**開く**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ffd5-237">このような証明書を確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-237">How do you know what certificate this is?</span></span> <span data-ttu-id="4ffd5-238">これは、ファームのすべてに割り当てられている単一の証明書であるか、または既定の内部 Web サービスなど、さまざまな用途に対して複数の証明書がある場合があります。その場合は、複数の証明書を調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="4ffd5-239">複数の証明書の拇印は同じです。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="4ffd5-240">**証明書**ビューが表示されたら、[**詳細**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="4ffd5-241">これにより、[**件名**] を選択したときに証明書のサブジェクト名が表示され、割り当てられたサブジェクト名と関連付けられたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="4ffd5-242">**サブジェクトの別名**エントリを確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="4ffd5-243">次のうちの1つまたは複数が見つかります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="4ffd5-244">このプールのプール名、またはプールでない場合は単一のサーバー名。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="4ffd5-245">証明書が割り当てられているサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="4ffd5-246">簡単な URL レコード (通常はミーティングとダイヤルイン)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="4ffd5-247">Web サービス内部および Web サービスの外部名 (たとえば、webpool01.contoso.net、webpool01.contoso.com) は、トポロジビルダーおよび優先度のある Web サービスの選択肢に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="4ffd5-248">既に割り当てられている場合は、lyncdiscover。\<microsoft.rtc.management.xds.sipdomain\>および lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>レコード</span><span class="sxs-lookup"><span data-stu-id="4ffd5-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="4ffd5-249">複数の証明書が割り当てられている場合は、複数の証明書をチェックする必要があります (上記の注を確認してください)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="4ffd5-250">そのため、lyncdiscover が見つかった場合。\<microsoft.rtc.management.xds.sipdomain\>および lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>レコードは既に構成されています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="4ffd5-251">MMC を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="4ffd5-252">割り当てられていない場合は、新しい証明書の要求を作成するか (上記の説明に従って)、post 要求をインストールする必要があります (これについては、上記の PowerShell を使用することをお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="4ffd5-253">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-253">Configure the reverse proxy</span></span>
<span data-ttu-id="4ffd5-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="4ffd5-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="4ffd5-255">以下の手順は、厳密に従うことを意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="4ffd5-256">これは、以前のバージョンの製品では、「Threat Management Gateway (TMG) を構成する」を参照していて、それを使用していなかった場合は、そこから独自のバージョンを使用する必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="4ffd5-257">TMG は Microsoft によって製品として提供されなくなりましたが、まだ構成が必要な場合は、「 [Lync Server 2013 の手順](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="4ffd5-258">しかし、次の情報は、リバースプロキシごとに特定のチュートリアル手順を提供できない場合でも、より一般的に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="4ffd5-259">次の2つの主な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="4ffd5-260">HTTPS を使用して最初の自動検出要求を実行しようとしていますか (お勧めします)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="4ffd5-261">Web 公開ルールを持っている場合は、それを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="4ffd5-262">Web 公開ルールをまだ持っていない場合は、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="4ffd5-263">HTTP 経由で最初の自動検出要求を行う場合は、そのルールも作成または変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ffd5-264">**重要**プロキシタイムアウト値は、展開から展開までの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="4ffd5-265">クライアントにとって最適な環境を実現するために、展開を監視し、価値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="4ffd5-266">この値は、少なくとも200に設定できます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="4ffd5-267">ご使用の環境で Lync モバイルクライアントをサポートしている場合は、値を960に設定して、タイムアウト値が900である Office 365 からのプッシュ通知のタイムアウトを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="4ffd5-268">この値が小さすぎると、クライアントの切断を回避するためにタイムアウト値を増やす必要があります。または、クライアントが切断された後に、プロキシ経由の接続が切断されることがなく、長時間になる場合は、数を減らす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="4ffd5-269">この値に対して適切な設定を判断するには、環境に適したものを監視し、基準にすることが唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="4ffd5-270">外部自動検出 SAN および URL の既存の web 公開ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="4ffd5-271">リバースプロキシインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="4ffd5-272">Web 公開ルールを見つけて、[編集] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブ上にある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="4ffd5-273">この web 公開ルールが適用されている場所を示す領域が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="4ffd5-274">サイトの受信サイトまたは要求に対してこのルールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="4ffd5-275">新しいエントリを**追加**します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="4ffd5-276">リバースプロキシの形式に応じて、自動検出サイトの名前 (使用する例は lyncdiscover.contoso.com) を入力し、[ **OK]** または [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="4ffd5-277">自動検出 SAN エントリが含まれている新しい証明書が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="4ffd5-278">これは、リバースプロキシの設定に従って、をインストールして、使用するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="4ffd5-279">構成が完了したら、必ずすべてを保存してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="4ffd5-280">リバースプロキシに**テスト**機能がある場合は、その機能を利用して、すべてが正しく動作することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="4ffd5-281">ご使用の環境にディレクターまたはディレクタープールがある場合は、この手順を繰り返す必要があります (これは、2番目のルールがあることを意味します)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="4ffd5-282">外部自動検出 URL の web 公開ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="4ffd5-283">リバースプロキシインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="4ffd5-284">Web 公開ルールを作成するインターフェイス内の場所を特定して、[**新規**作成] または [**作成**] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブ上にある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="4ffd5-285">新しい web 公開ルールを作成するオプションを探している場合。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="4ffd5-286">通常は、次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="4ffd5-287">**Name**: ルールの名前</span><span class="sxs-lookup"><span data-stu-id="4ffd5-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="4ffd5-288">**ルールの処理**: この例では、**許可**ルールとして、リバースプロキシを介して何かが渡されることができます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="4ffd5-289">選択している**公開**ルールまたはオプションは、**単一の web サイトまたはロードバランサー**です。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="4ffd5-290">外部アクセスには**SSL**を使用する必要があり、そのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="4ffd5-291">**内部発行**用のパスを公開し、フロントエンドプールのロードバランサーに外部 Web サービスの fqdn を入力する必要があります。または、使用している場合は、ディレクタープールのロードバランサーの fqdn を入力します。そのためには、例を sfb_pool01 します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="4ffd5-292">公開するパス\*\* /\*\* として「\*」を入力する必要がありますが、**元のホストヘッダーも転送**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="4ffd5-293">**パブリックまたは外部の名前**の詳細または情報に関するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="4ffd5-294">入力できる場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="4ffd5-295">**要求を受け入れ**ますが、これはドメイン名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="4ffd5-296">**名前**については、「 **lyncdiscover** 」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="4ffd5-297"><sipdomain>(これは外部自動検出サービス URL です)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="4ffd5-298">次に、フロントエンドプールの外部 Web サービス URL のルールを作成している場合は、フロントエンドプールの外部 Web サービスの FQDN (たとえば、lyncwebextpool01.contoso.com) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="4ffd5-299">**パス**オプションが表示されます。ここで、\* を\*\* /\*\* 入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="4ffd5-300">最新のパブリック証明書を使用して、 **SSL リスナー**を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="4ffd5-301">**認証の委任**を [**委任しない**] に設定する必要がありますが、直接クライアント認証を許可する**必要**があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="4ffd5-302">ルールは**すべてのユーザー**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="4ffd5-303">このルールを作成して続行できるようにするために必要な情報をすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="4ffd5-304">**元のホストヘッダー**が転送されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="4ffd5-305">**Web サーバー**のポートも設定する必要があります。次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="4ffd5-306">**要求を HTTP ポートにリダイレクト**し、ポート番号を**8080**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="4ffd5-307">**SSL ポートに要求をリダイレクト**し、ポート番号を**4443**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="4ffd5-308">すべての構成が完了したら、それらを保存または適用し、ルールをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="4ffd5-309">ポート80の web 公開ルールを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="4ffd5-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="4ffd5-310">リバースプロキシインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="4ffd5-311">Web 公開ルールを作成するインターフェイス内の場所を特定して、[**新規**作成] または [**作成**] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブ上にある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="4ffd5-312">新しい web 公開ルールを作成するオプションを探している場合。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="4ffd5-313">通常は、次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="4ffd5-314">**Name**: ルールの名前</span><span class="sxs-lookup"><span data-stu-id="4ffd5-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="4ffd5-315">**ルールの処理**: この例では、**許可**ルールとして、リバースプロキシを介して何かが渡されることができます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="4ffd5-316">選択している**公開**ルールまたはオプションは、**単一の web サイトまたはロードバランサー**です。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="4ffd5-317">公開され**た Web サーバーまたはファームに接続するに**は、セキュリティで保護されていない接続を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="4ffd5-318">**内部発行**用のパスを公開し、フロントエンドプールのロードバランサーの**VIP アドレス**の FQDN を入力する必要がある場合は、例として sfb_pool01 します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="4ffd5-319">公開するパス\*\* /\*\* として「\*」を入力する必要がありますが、**元のホストヘッダーも転送**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="4ffd5-320">**パブリックまたは外部の名前**の詳細または情報に関するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="4ffd5-321">入力できる場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="4ffd5-322">**要求を受け入れ**ますが、これはドメイン名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="4ffd5-323">**名前**については、「 **lyncdiscover** 」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="4ffd5-324"><sipdomain>(これは外部自動検出サービス URL です)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="4ffd5-325">**パス**オプションが表示されます。ここで、\* を\*\* /\*\* 入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="4ffd5-326">Web リスナーを選択するか、リバースプロキシで作成することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="4ffd5-327">**認証の委任**は**委任なし**に設定する必要がありますが、直接の**クライアント認証は許可しないでください**。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="4ffd5-328">ルールは**すべてのユーザー**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="4ffd5-329">このルールを作成して続行できるようにするために必要な情報をすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="4ffd5-330">**Web サーバー**のポートを設定する必要があります。次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="4ffd5-331">**要求を HTTP ポートにリダイレクト**し、ポート番号を**8080**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="4ffd5-332">**SSL ポートに要求をリダイレクト**し、ポート番号を**4443**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="4ffd5-333">すべての構成が完了したら、それらを保存または適用し、ルールをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="4ffd5-334">ハイブリッド展開によるモビリティの自動検出の構成</span><span class="sxs-lookup"><span data-stu-id="4ffd5-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="4ffd5-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="4ffd5-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="4ffd5-336">Skype for Business Server のハイブリッド環境は、オンプレミスの環境と O365 環境を組み合わせた環境です。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="4ffd5-337">ハイブリッド環境で Skype for Business Server を使用している場合、自動検出サービスは、これらの環境のいずれかからユーザーを検索できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="4ffd5-338">モバイルクライアントがユーザーの場所を検出できるようにするには、自動検出サービスを新しい uniform resource locator (URL) を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="4ffd5-339">手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-339">The steps are:</span></span>
  
1. <span data-ttu-id="4ffd5-340">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="4ffd5-341">次を実行して、Skype for Business Server 環境の属性**Proxyfqdn**の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="4ffd5-342">その後もシェルウィンドウで、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="4ffd5-343">[identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="4ffd5-344">モビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="4ffd5-344">Test your Mobility deployment</span></span>
<span data-ttu-id="4ffd5-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="4ffd5-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="4ffd5-346">Skype for Business Server Mobility Service と Skype for Business Server の自動検出サービスを展開したら、テストトランザクションを実行して、展開が正常に動作することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="4ffd5-347">**Test-csucwaconference**を実行すると、2人のユーザーが会議で作成、参加、および通信できるかどうかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="4ffd5-348">このテストを行うには、2人のユーザー (real または test) とその完全な資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="4ffd5-349">このコマンドは、Skype for Business クライアントと Lync Server 2013 クライアントの両方に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="4ffd5-350">Skype for Business Server 2015 の Lync Server 2010 クライアントでは、テストのために**test-csmcxp2pim**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="4ffd5-351">Lync Server 2010 ユーザーは、実際のユーザーまたは事前定義されたテストユーザーである必要があり、パスワード資格情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="4ffd5-352">従来のモバイルクライアントに対する MCX (Mobility Service) のサポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4ffd5-353">現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4ffd5-354">MCX を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="4ffd5-355">Skype for Business および Lync 2013 モバイルクライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="4ffd5-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="4ffd5-356">**Skype For Business Server 管理シェル**および**ocscore**がインストールされている任意のコンピューターで、 **csadministrator**の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4ffd5-357">**Skype For Business Server 管理シェル**を起動します ([検索] で名前を入力するか、[**すべてのプログラム**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="4ffd5-358">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="4ffd5-359">スクリプトで資格情報を設定して、テストコマンドレットに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="4ffd5-360">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="4ffd5-361">Lync 2010 モバイルクライアントのテスト会議</span><span class="sxs-lookup"><span data-stu-id="4ffd5-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="4ffd5-362">従来のモバイルクライアントに対する MCX (Mobility Service) のサポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4ffd5-363">現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4ffd5-364">MCX を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="4ffd5-365">**Skype For Business Server 管理シェル**および**ocscore**がインストールされている任意のコンピューターで、 **csadministrator**の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4ffd5-366">**Skype For Business Server 管理シェル**を起動します ([検索] で名前を入力するか、[**すべてのプログラム**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="4ffd5-367">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="4ffd5-368">スクリプトで資格情報を設定して、テストコマンドレットに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="4ffd5-369">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="4ffd5-370">コマンドプロシージャをさらに詳しく確認するには、 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)および[test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="4ffd5-371">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-371">Configure for push notifications</span></span>
<span data-ttu-id="4ffd5-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="4ffd5-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="4ffd5-373">プッシュ通知は、バッジ、アイコン、または通知の形式で、Skype または Lync アプリが非アクティブな場合でもモバイルデバイスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="4ffd5-374">プッシュ通知とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-374">But what are push notifications?</span></span> <span data-ttu-id="4ffd5-375">これらは、新しいまたは不在着信した IM 出席依頼や受信したボイスメールなどのイベント通知です。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="4ffd5-376">Skype for Business Server Mobility service は、これらの通知をクラウドベースの Skype for business Server プッシュ通知サービスに送信します。これにより、Windows Phone ユーザーの Microsoft プッシュ通知サービス (MSNS) に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="4ffd5-377">この機能は Lync Server 2013 から変更されていませんが、Skype for Business Server を使用している場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="4ffd5-378">Skype for Business Server エッジサーバーの場合は、新しいホスティングプロバイダーである Microsoft Skype for Business Online を追加し、組織と Skype for Business Online の間のホスティングプロバイダーフェデレーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="4ffd5-379">**Set-Cspの設定**コマンドレットを実行して、プッシュ通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="4ffd5-380">既定では、プッシュ通知はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="4ffd5-381">フェデレーション構成とプッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="4ffd5-382">プッシュ通知用に Skype for Business エッジサーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="4ffd5-383">**Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4ffd5-384">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ffd5-385">Skype for Business Server online ホスティングプロバイダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="4ffd5-386">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="4ffd5-387">1つのホスティングプロバイダーとの間に複数のフェデレーション関係を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="4ffd5-388">そのため、sipfed.online.lync.com とのフェデレーション関係を持つホスティングプロバイダーを既にセットアップしている場合は、ホスティングプロバイダーの id が SkypeOnline 以外のものであっても、別のホスティングプロバイダーを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="4ffd5-389">Skype for Business Online の組織とプッシュ通知サービスとの間のホスティングプロバイダーフェデレーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="4ffd5-390">コマンドラインで、次のように入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="4ffd5-391">プッシュ通知を有効にする</span><span class="sxs-lookup"><span data-stu-id="4ffd5-391">Enable push notifications</span></span>

1. <span data-ttu-id="4ffd5-392">**Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4ffd5-393">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ffd5-394">プッシュ通知を有効にする:</span><span class="sxs-lookup"><span data-stu-id="4ffd5-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="4ffd5-395">フェデレーションを有効にする:</span><span class="sxs-lookup"><span data-stu-id="4ffd5-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="4ffd5-396">フェデレーションとプッシュ通知をテストする</span><span class="sxs-lookup"><span data-stu-id="4ffd5-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="4ffd5-397">**Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4ffd5-398">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ffd5-399">フェデレーション構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="4ffd5-400">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="4ffd5-401">プッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="4ffd5-402">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="4ffd5-403">モビリティポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-403">Configure Mobility policy</span></span>
<span data-ttu-id="4ffd5-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="4ffd5-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="4ffd5-405">Skype for Business Server を使用すると、Mobility service を使用できるユーザーを決定したり、勤務先から通話、ボイスオーバー IP (VoIP)、ビデオを使用したり、VoIP またはビデオで Wi-fi が必要かどうかを確認したりできます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="4ffd5-406">[勤務先から通話] を使用すると、モバイルユーザーは電話を発信または受信するときに、携帯電話の番号ではなく勤務先の電話番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="4ffd5-407">回線の他の端部のユーザーには、そのモバイルユーザーの携帯電話番号が表示されないため、モバイルユーザーは発信通話料金を回避できます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="4ffd5-408">VoIP およびビデオが設定されている場合、ユーザーは VoIP 通話とビデオを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="4ffd5-409">WiFi 使用法の設定では、ユーザーのモバイルデバイスで、携帯データネットワーク経由で WiFi ネットワークを使用する必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="4ffd5-410">モビリティ、勤務先から通話、および VoIP およびビデオ機能はすべて、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="4ffd5-411">VoIP およびビデオ用に WiFi を必須にする設定は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="4ffd5-412">管理者は、グローバル、サイト、またはユーザーのいずれかを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="4ffd5-413">モビリティ機能を使用し、勤務先から通話できるようにするには、ユーザーは次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="4ffd5-414">Skype for Business Server に対して有効</span><span class="sxs-lookup"><span data-stu-id="4ffd5-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="4ffd5-415">エンタープライズ Voip を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="4ffd5-416">**EnableMobility**オプションが**True**に設定されているモビリティポリシーが割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="4ffd5-417">ユーザーが [勤務先から通話] を使用できるようにするには、次のものも必要になります。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="4ffd5-418">[**電話の同時呼び出しを有効に**する] オプションがオンになっている音声ポリシーが割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="4ffd5-419">**EnableOutsideVoice**が**True**に設定されているモビリティポリシーが割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ffd5-420">エンタープライズ Voip が有効になっていないユーザーは、モバイルデバイスを使用して、関連付けられている音声ポリシーに該当するオプションが設定されている場合は、自分のモバイルデバイスを使用して Skype for Business VoIP を通話したり、会議に参加したりすることができます。た.</span><span class="sxs-lookup"><span data-stu-id="4ffd5-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="4ffd5-421">詳細については、「計画」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="4ffd5-422">グローバルモビリティポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="4ffd5-423">**Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4ffd5-424">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ffd5-425">次のように入力して、モビリティへのアクセスをグローバルにオンにして、作業をグローバルに呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="4ffd5-426">モビリティへのアクセスをオフにすることなく、勤務先から通話をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="4ffd5-427">しかし、勤務先から通話をオフにしなくても、モビリティをオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="4ffd5-428">詳細については、「 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="4ffd5-429">モビリティポリシーをサイト別に変更する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="4ffd5-430">**Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4ffd5-431">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ffd5-432">サイトレベルのポリシーを作成し、VoIP およびビデオをオフにして、IP オーディオに対して WiFi を必須にし、サイトごとに IP ビデオに WiFi を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="4ffd5-433">種類:</span><span class="sxs-lookup"><span data-stu-id="4ffd5-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="4ffd5-434">詳細については[、「get-csmobilitypolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="4ffd5-435">モビリティポリシーをユーザー別に変更する</span><span class="sxs-lookup"><span data-stu-id="4ffd5-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="4ffd5-436">**Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="4ffd5-437">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ffd5-438">ユーザーレベルのモビリティポリシーを作成し、ユーザーの勤務時間外でモビリティをオフにします。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="4ffd5-439">種類:</span><span class="sxs-lookup"><span data-stu-id="4ffd5-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="4ffd5-440">サンプルデータの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="4ffd5-441">モビリティへのアクセスをオフにすることなく、勤務先から通話をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="4ffd5-442">しかし、勤務先から通話をオフにしなくても、モビリティをオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4ffd5-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

