---
title: 'Lync Server 2013: リバースプロキシサーバーの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd5b57c29a622b7c0f051b00bb0ef30e265743e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="cd7a8-102">Lync Server 2013 用のリバースプロキシサーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="cd7a8-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd7a8-103">_**トピックの最終更新日:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="cd7a8-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="cd7a8-104">Microsoft Lync Server 2013 エッジサーバー展開の場合、外部クライアントがディレクターおよびユーザーのホームプールで Lync Server 2013 Web サービス (Office Communications Server の*Web コンポーネント*と呼ばれます) にアクセスするには、境界ネットワーク内の HTTPS リバースプロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="cd7a8-105">リバース プロキシ経由の外部アクセスが必要な機能には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="cd7a8-106">外部ユーザーが会議の会議コンテンツをダウンロードできるようにする。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="cd7a8-107">外部ユーザーが配布グループを展開できるようにする。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="cd7a8-108">リモート ユーザーがアドレス帳サービスからファイルをダウンロードできるようにする。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="cd7a8-109">Lync Web App クライアントにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="cd7a8-110">[ダイヤルイン会議の設定] Web ページにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="cd7a8-111">外部デバイスからデバイス更新 Web サービスに接続して更新プログラムを入手できるようにする。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="cd7a8-112">モバイルアプリケーションが自動的に検出してインターネットからのモビリティ (Mcx) Url を使用できるようにする。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="cd7a8-113">Lync 2013 クライアント、Lync Windows ストアアプリ、Lync 2013 Mobile クライアントを有効にして、Lync discovery (自動検出) Url を検索し、統合コミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="cd7a8-114">HTTP リバース プロキシは、すべてのプールのすべての Web サービスを公開するように設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="cd7a8-115">Https://ExternalFQDN の発行\* /プールのすべての IIS 仮想ディレクトリを公開します。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="cd7a8-116">組織内の Standard Edition サーバー、フロントエンド プール、またはディレクターやディレクター プールごとに、公開ルールが 1 つずつ必要です。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="cd7a8-117">さらに、簡単な Url を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="cd7a8-118">組織にディレクターまたはディレクタープールがある場合、HTTP リバースプロキシは簡単な Url に対する HTTP/HTTPS 要求をリッスンし、ディレクターまたはディレクタープールの外部 Web サービス仮想ディレクトリにプロキシを送信します。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="cd7a8-119">ディレクターを展開していない場合は、簡易 Url への要求を処理するプールを1つ指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="cd7a8-120">(これがユーザーのホームプールでない場合は、ユーザーのホームプールの Web サービスにリダイレクトされます)。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="cd7a8-121">簡易 Url は専用の web 公開ルールによって処理されることも、ディレクターの web 公開ルールのパブリック名に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="cd7a8-122">外部自動検出サービスの URL も公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="cd7a8-123">リバースプロキシとしてアプリケーション要求ルーティング (IIS ARR) を使用して、Microsoft Forefront Threat Management Gateway 2010、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー 2006 SP1、または Internet Information Server 7.0、7.5 または8.0 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="cd7a8-124">このセクションの詳細な手順では、Forefront Threat Management Gateway 2010 を構成する方法と、ISA Server 2006 を構成する手順をほぼ同一にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="cd7a8-125">IIS のガイダンスも提供されています。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="cd7a8-126">別のリバースプロキシを使用している場合は、その製品のドキュメントを参照し、ここで定義されている要件を他のリバースプロキシの関連付けられている機能にマップします。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cd7a8-127">インターネットインフォメーションサービスアプリケーション要求ルーティング (IIS ARR) は、Lync Server 2010 および Lync Server 2013 のリバースプロキシを実装するための完全にテストおよびサポートされたオプションです。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="cd7a8-128">2012年11月日、Microsoft ceased ライセンス販売の ForeFront Threat Management Gateway 2010、または TMG。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="cd7a8-129">TMG は、完全にサポートされている製品で、サードパーティが販売しているアプライアンスでも引き続き販売できます。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="cd7a8-130">また、サードパーティのハードウェアロードバランサーとファイアウォールの多くはリバースプロキシサポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="cd7a8-131">リバースプロキシ機能を提供するハードウェアロードバランサーとファイアウォールについては、各製品を構成して、Lync Server のリバースプロキシサポートを提供する方法について、ベンダーに確認してください。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="cd7a8-132">また、製品のドキュメントを Microsoft に送信した第三者を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="cd7a8-133">サポートは、サードパーティのソリューションによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="cd7a8-134">ソリューションを提供するためにアクティブなサードパーティを確認するには、「 <A href="http://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync 用のインフラストラクチャ認定</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-134">To see third parties that are active in providing solutions, see <A href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="cd7a8-135">以下のトピックと手順では、展開および構成手順の基礎として Forefront Threat Management Gateway 2010 と IIS ARR を使用しています。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="cd7a8-136">Lync Server 2013 用に web ファーム Fqdn を構成する</span><span class="sxs-lookup"><span data-stu-id="cd7a8-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="cd7a8-137">Lync Server 2013 でネットワークアダプターを構成する</span><span class="sxs-lookup"><span data-stu-id="cd7a8-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="cd7a8-138">Lync Server 2013 でのリバース HTTP プロキシの証明書の要求と構成</span><span class="sxs-lookup"><span data-stu-id="cd7a8-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="cd7a8-139">Lync Server 2013 での単一の内部プールの web 公開ルールの構成</span><span class="sxs-lookup"><span data-stu-id="cd7a8-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="cd7a8-140">Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する</span><span class="sxs-lookup"><span data-stu-id="cd7a8-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="cd7a8-141">Lync Server 2013 でリバースプロキシサーバーの DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="cd7a8-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="cd7a8-142">Lync Server 2013 でリバースプロキシ経由のアクセスを確認する</span><span class="sxs-lookup"><span data-stu-id="cd7a8-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="cd7a8-143">作業を始める前に</span><span class="sxs-lookup"><span data-stu-id="cd7a8-143">Before You Begin</span></span>

<span data-ttu-id="cd7a8-144">Forefront Threat Management Gateway 2010 をリバース プロキシとして正しく展開するには、Forefront Threat Management Gateway 2010 のドキュメントに定義されている前提条件およびハードウェア要件を使用してサーバーを設定および構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="cd7a8-145">続行する前に、「ハードウェアを適切に構成し、Forefront Threat Management Gateway 2010 をサーバーにインストールするには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="cd7a8-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="cd7a8-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="cd7a8-147">Forefront TMG 2010 ハードウェアに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="cd7a8-147">Forefront TMG 2010 hardware recommendations</span></span>](http://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="cd7a8-148">IIS ARR をリバースプロキシとして正常に展開するには、次のトピックを参照してハードウェアおよび前提条件のソフトウェアを構成します。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="cd7a8-149">IIS を Windows Server 2008 または Windows Server 2008 R2 にインストールするには、「 [Windows server 2008 または Windows server 2008 r2 に iis 7](http://go.microsoft.com/fwlink/?linkid=291296)をインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="cd7a8-150">Windows Server 2012 に IIS をインストールするには、「 [Windows server 2012 で iis 8 をインストール](http://go.microsoft.com/fwlink/?linkid=291297)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="cd7a8-151">Windows Server 2012 R2 に IIS をインストールするには、「 [Windows server 2012 r2 に iis 8.5 を](http://go.microsoft.com/fwlink/?linkid=330687)インストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="cd7a8-152">IIS のアプリケーション要求ルーティング拡張機能をダウンロードするには、「[アプリケーション要求ルーティング](http://go.microsoft.com/fwlink/?linkid=291298)V2.0 のダウンロード」に記載されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](http://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="cd7a8-153">ARR をインストールするには、「[アプリケーション要求ルーティングバージョン2のインストール](http://go.microsoft.com/fwlink/?linkid=291299)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](http://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd7a8-154">現在投稿されている命令は、ARR 2.0 に対応しています。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="cd7a8-155">拡張機能のインストールでは、2つのバージョンの間に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="cd7a8-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

