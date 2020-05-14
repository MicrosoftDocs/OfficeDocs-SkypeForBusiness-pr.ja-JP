---
title: Skype for Business Server でのエッジサーバーのシステム要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: '概要: Skype for Business Server のエッジサーバーのシステム要件について説明します。'
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221027"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="41088-103">Skype for Business Server でのエッジサーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="41088-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="41088-104">**概要:** Skype for Business Server のエッジサーバーのシステム要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="41088-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="41088-105">Skype for Business Server エッジサーバーの展開については、次のように、環境構造の計画だけでなく、環境内のサーバーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="41088-106">トポロジ、DNS、証明書、およびその他のインフラストラクチャの問題の詳細については、「環境要件」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41088-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="41088-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="41088-107">Components</span></span>

<span data-ttu-id="41088-108">エッジサーバー環境について説明するときには、境界ネットワークに展開されているコンポーネント (ワークグループ内、または Skype for Business Server ドメイン構造の外部にあるドメインのいずれかであることを言う) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="41088-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="41088-109">この点を念頭に置いて、エッジを正常に展開するために考慮する必要があるコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="41088-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="41088-110">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="41088-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="41088-111">リバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="41088-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="41088-112">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="41088-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="41088-113">[ディレクター](system-requirements.md#Directors) (これらはオプションであり、含まれている場合は内部ネットワーク上に配置されます)</span><span class="sxs-lookup"><span data-stu-id="41088-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="41088-114">[ロードバランサー](system-requirements.md#LoadBalancers) (DNS 負荷分散またはハードウェアロードバランサー (hlb) を使用できますが、単一エッジサーバーの場合はこれは必要ありません)</span><span class="sxs-lookup"><span data-stu-id="41088-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="41088-115">以下の各セクションについて詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="41088-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="41088-116">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="41088-116">Edge Servers</span></span>
<span data-ttu-id="41088-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="41088-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="41088-118">これらは、境界環境に展開された Skype for Business サーバーです。</span><span class="sxs-lookup"><span data-stu-id="41088-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="41088-119">これらの役割は、内部の Skype for Business Server 展開で提供されるサービスについて、外部ユーザーへのネットワークトラフィックを送受信することです。</span><span class="sxs-lookup"><span data-stu-id="41088-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="41088-120">この操作を正常に行うには、各エッジサーバーが次のように実行されます。</span><span class="sxs-lookup"><span data-stu-id="41088-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="41088-121">**アクセスエッジサービス**: 発信および受信のセッション開始プロトコル (SIP) トラフィックに対して、1つの信頼できる接続ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="41088-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="41088-122">**Web 会議エッジサービス**: 外部ユーザーが、内部の Skype For business Server 環境でホストされている会議に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="41088-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="41088-123">音声ビデオ**エッジサービス**: 外部ユーザーがオーディオ、ビデオ、アプリケーション共有、およびファイル転送を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="41088-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="41088-124">**Xmpp プロキシサービス**: 構成済みの Xmpp フェデレーションパートナーとの間で、拡張可能な messaging およびプレゼンスプロトコル (xmpp) メッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="41088-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="41088-125">許可された外部ユーザーは、内部の Skype for Business Server 展開に接続するためにエッジサーバーを使用することができますが、それ以外の場合は、どのユーザーにも内部ネットワークへのアクセスを提供しません。</span><span class="sxs-lookup"><span data-stu-id="41088-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41088-126">エッジサーバーは、有効な Skype for Business クライアントおよびその他のエッジサーバー (フェデレーションのシナリオ) への接続を提供するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="41088-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="41088-127">他のエンドポイントクライアントまたはサーバーの種類から接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="41088-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="41088-128">XMPP ゲートウェイサーバーは、構成された XMPP パートナーとの接続を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="41088-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="41088-129">しかし、それでも動作するのはクライアントとフェデレーションの種類だけです。</span><span class="sxs-lookup"><span data-stu-id="41088-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="41088-130">XMPP ゲートウェイおよびプロキシは、Skype for business Server 2015 で利用できますが、Skype for business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="41088-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="41088-131">詳細については、「 [XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41088-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="41088-132">リバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="41088-132">Reverse proxies</span></span>
<span data-ttu-id="41088-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="41088-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="41088-134">リバースプロキシ (RP) サーバーには Skype for Business Server の役割はありませんが、エッジサーバーの展開に不可欠なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="41088-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="41088-135">リバースプロキシを使用すると、外部ユーザーは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="41088-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="41088-136">簡易 Url を使用して会議またはダイヤルイン会議に接続します。</span><span class="sxs-lookup"><span data-stu-id="41088-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="41088-137">会議コンテンツをダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="41088-137">download meeting content.</span></span>
    
- <span data-ttu-id="41088-138">[配布グループ] を展開します。</span><span class="sxs-lookup"><span data-stu-id="41088-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="41088-139">クライアント証明書ベースの認証用のユーザーベースの証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="41088-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="41088-140">アドレス帳サーバーからファイルをダウンロードするか、アドレス帳 Web クエリサービスにクエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="41088-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="41088-141">クライアントおよびデバイスソフトウェアの更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="41088-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="41088-142">モバイルデバイスの場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="41088-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="41088-143">これにより、モビリティサービスを提供するフロントエンドサーバーを自動的に検出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="41088-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="41088-144">Microsoft 365 または Office 365 からモバイルデバイスへのプッシュ通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="41088-144">it enables push notifications from Microsoft 365 or Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="41088-145">現在のリバースプロキシの推奨事項については、「Skype for business[のテレフォニーインフラストラクチャ](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41088-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="41088-146">そのため、リバースプロキシは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="41088-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="41088-147">パブリック証明書を介して環境に導入されたトランスポート層セキュリティ (TLS) を使用して、次のような公開外部 Web サービスに接続できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="41088-148">ディレクターまたはディレクター プール</span><span class="sxs-lookup"><span data-stu-id="41088-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="41088-149">フロントエンドサーバーまたはフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="41088-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="41088-150">は、暗号化用の証明書を使用して内部 Web サイトを公開するか、必要に応じて暗号化されていない方法で公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="41088-151">完全修飾ドメイン名 (FQDN) を使用して、内部でホストされている web サイトを外部に公開できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="41088-152">ホストされている web サイトのすべてのコンテンツを発行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="41088-153">既定では、 **/\\** ほとんどの web サーバーによって認識される \* ディレクティブを使用して、"web サーバー上のすべてのコンテンツを公開" という意味を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="41088-153">By default, you can use the **/\\**\* directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="41088-154">また、ディレクティブ (たとえば、\* */Uwca/* \* \*) を変更することもでき \\ ます。これは、"仮想ディレクトリの下にあるすべてのコンテンツを公開する" という意味です。</span><span class="sxs-lookup"><span data-stu-id="41088-154">You can also modify the directive—for example, \*\*/Uwca/\\*\*\*, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="41088-155">発行された web サイトのコンテンツを要求するクライアントとの TLS 接続を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="41088-156">サブジェクトの別名 (SAN) エントリを含む証明書を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="41088-157">外部 web サービスの FQDN が解決されるリスナーまたはインターフェイスへの証明書のバインドを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="41088-158">リスナー構成は、インターフェイスに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="41088-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="41088-159">多くのリスナーは、1つのインターフェイスで構成できます。</span><span class="sxs-lookup"><span data-stu-id="41088-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="41088-160">ホストヘッダー処理の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="41088-161">多くの場合、要求元のクライアントによって送信される元のホストヘッダーは、リバースプロキシによって変更されるのではなく、透過的に渡される必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="41088-162">外部で定義された1つのポート (たとえば、tcp 443) から別の定義済みポート (たとえば、TCP 4443) への TLS トラフィックのブリッジを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="41088-163">リバースプロキシは、受信時にパケットの暗号化を解除し、送信時にパケットを再度暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="41088-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="41088-164">1つのポート (たとえば、tcp 80) から別のポート (たとえば、TCP 8080) への暗号化されていない TCP トラフィックのブリッジを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="41088-165">NTLM 認証、認証なし、パススルー認証の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="41088-166">リバースプロキシがこの一覧に記載されているすべてのニーズに対応できる場合は、この記事のリンクにある推奨事項にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="41088-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="41088-167">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="41088-167">Firewalls</span></span>
<span data-ttu-id="41088-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="41088-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="41088-169">エッジの展開は、外部ファイアウォールの背後に配置する必要がありますが、エッジ環境と内部環境の間には、2つのファイアウォール、1つの外部、内部の1つを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41088-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="41088-170">シナリオに記載されているすべてのドキュメントは、2つのファイアウォールを備えています。</span><span class="sxs-lookup"><span data-stu-id="41088-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="41088-171">2つのファイアウォールを使用することをお勧めします。これにより、ネットワークエッジ間の厳密なルーティングが行われ、内部ネットワークのファイアウォール保護が2倍になります。</span><span class="sxs-lookup"><span data-stu-id="41088-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="41088-172">レ</span><span class="sxs-lookup"><span data-stu-id="41088-172">Directors</span></span>
<span data-ttu-id="41088-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="41088-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="41088-174">これはオプションの役割です。</span><span class="sxs-lookup"><span data-stu-id="41088-174">This is an optional role.</span></span> <span data-ttu-id="41088-175">1台のサーバー、またはディレクターの役割を実行しているサーバーのプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="41088-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="41088-176">これは、内部の Skype for Business Server 環境で見つかった役割です。</span><span class="sxs-lookup"><span data-stu-id="41088-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="41088-177">ディレクターは、Skype for Business Server の内部サーバーを宛先とするエッジサーバーからの受信 SIP トラフィックを受信する、内部の次ホップサーバーです。</span><span class="sxs-lookup"><span data-stu-id="41088-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="41088-178">受信要求を事前認証し、ユーザーのホームプールまたはサーバーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="41088-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="41088-179">この事前認証により、未識別のユーザーアカウント要求を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="41088-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="41088-180">このような問題があるのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="41088-180">Why does that matter?</span></span> <span data-ttu-id="41088-181">ディレクターの重要な機能は、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックから、Standard Edition サーバーとフロントエンドサーバーまたはフロントエンドプールを保護することです。</span><span class="sxs-lookup"><span data-stu-id="41088-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="41088-182">ネットワークに無効な外部トラフィックが殺到している場合、トラフィックはディレクターで停止します。</span><span class="sxs-lookup"><span data-stu-id="41088-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="41088-183">ロードバランサー</span><span class="sxs-lookup"><span data-stu-id="41088-183">Load Balancers</span></span>
<span data-ttu-id="41088-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="41088-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="41088-185">Skype for Business Server 拡張統合エッジトポロジは、新しい展開で DNS 負荷分散のために最適化されており、これをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41088-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="41088-186">高可用性が必要な場合は、1つの特定の状況でハードウェアロードバランサーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41088-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="41088-187">Exchange 2013**より前**の exchange um を使用するリモートユーザー用の exchange um。</span><span class="sxs-lookup"><span data-stu-id="41088-187">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="41088-188">ロードバランサーを混在させることはできないことに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="41088-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="41088-189">Skype for Business Server 環境では、すべてのインターフェイスで DNS または HLB のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="41088-190">Skype for Business Server では、Direct server return (DSR) NAT はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="41088-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="41088-191">音声ビデオエッジサービスを実行するエッジサーバーエッジサーバーに対するハードウェアロードバランサーの要件</span><span class="sxs-lookup"><span data-stu-id="41088-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="41088-192">音声ビデオエッジサービスを実行しているエッジサーバーについては、次の要件があります。</span><span class="sxs-lookup"><span data-stu-id="41088-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="41088-193">内部および外部の両方のポートに対して TCP ネーグル処理がをオフにします 443 (ネーグル処理がは、複数の小さなパケットを1つの大きなパケットに結合して、より効率的に転送するプロセスです)。</span><span class="sxs-lookup"><span data-stu-id="41088-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="41088-194">外部ポート範囲 5万 ~ 59999 の TCP ネーグル処理がをオフにします。</span><span class="sxs-lookup"><span data-stu-id="41088-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="41088-195">内部または外部のファイアウォールで NAT を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="41088-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="41088-196">エッジの内部インターフェイスは、エッジサーバーの外部インターフェイスとは別のネットワークに配置し、それらの間のルーティングを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="41088-197">音声ビデオエッジサービスを実行しているすべてのエッジサーバーの外部インターフェイスでは、公開されたルーティング可能な IP アドレスを使用し、エッジの外部 IP アドレスで NAT またはポート変換を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="41088-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="41088-198">HLB の要件</span><span class="sxs-lookup"><span data-stu-id="41088-198">HLB requirements</span></span>

<span data-ttu-id="41088-199">Skype for Business Server には、多くの cookie ベースのアフィニティ要件はありません。</span><span class="sxs-lookup"><span data-stu-id="41088-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="41088-200">そのため、cookie ベースの永続性を使用する必要はありません (これが Skype for Business Server 2015 固有**の場合)** 、Skype For business server 環境で Lync Server 2010 フロントエンドサーバーまたはフロントエンドプールを使用する予定です。</span><span class="sxs-lookup"><span data-stu-id="41088-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="41088-201">Lync Server 2010 に推奨される構成方法では、cookie ベースのアフィニティが必要になります。</span><span class="sxs-lookup"><span data-stu-id="41088-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41088-202">HLB に対して cookie ベースのアフィニティを有効にする場合は、環境で必要でない場合でも、そのような問題はありません。</span><span class="sxs-lookup"><span data-stu-id="41088-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="41088-203">環境で cookie ベースのアフィニティが**必要ない場合**は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="41088-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="41088-204">ポート443のリバースプロキシ公開ルールで、[**フォワードホストヘッダー** ] を [ **True**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="41088-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="41088-205">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="41088-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="41088-206">Cookie**ベースのアフィニティを必要と**する展開の場合:</span><span class="sxs-lookup"><span data-stu-id="41088-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="41088-207">ポート443のリバースプロキシ公開ルールで、[**フォワードホストヘッダー** ] を [ **True**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="41088-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="41088-208">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="41088-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="41088-209">ハードウェアロードバランサーの cookie は、httpOnly とマークさ**れていてはなりません**。</span><span class="sxs-lookup"><span data-stu-id="41088-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="41088-210">ハードウェアロードバランサーの cookie に有効期限を設定することは**できません**。</span><span class="sxs-lookup"><span data-stu-id="41088-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="41088-211">ハードウェアロードバランサーの cookie は、 **MS-WSMAN**という名前にする**必要があり**ます (これは、Web サービスが期待する値で、変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="41088-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="41088-212">ハードウェアロードバランサー cookie は、同じ TCP 接続に対する以前の HTTP 応答が cookie を受け取ったかどうかにかかわらず、受信 HTTP 要求が cookie を持たないすべての HTTP 応答で設定**する必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="41088-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="41088-213">ハードウェアロードバランサーが、TCP 接続ごとに1回だけ cookie 挿入を最適化する場合は、その最適化を使用**しないでください**。</span><span class="sxs-lookup"><span data-stu-id="41088-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="41088-214">通常、HLB 構成では、ソースアフィニティと20分の TCP セッションの有効期間を使用します。これは、Skype for Business Server およびそのクライアントには適しています。これは、クライアントの使用状況やアプリケーションの相互作用によってセッション状態が維持されるためです。</span><span class="sxs-lookup"><span data-stu-id="41088-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="41088-215">モバイルデバイスを展開している場合、HLB は TCP セッション内の個々の要求を負荷分散できる必要があります (実際には、ターゲット IP アドレスに基づいて個々の要求を負荷分散できる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="41088-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="41088-216">F5 HLBs には、OneConnect という機能があります。</span><span class="sxs-lookup"><span data-stu-id="41088-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="41088-217">これにより、TCP 接続内の各要求が個別に負荷分散されるようになります。</span><span class="sxs-lookup"><span data-stu-id="41088-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="41088-218">モバイルデバイスを展開している場合は、HLB ベンダーが同じ機能をサポートしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="41088-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="41088-219">最新の iOS モバイルアプリでは、TLS バージョン1.2 が必要です。</span><span class="sxs-lookup"><span data-stu-id="41088-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="41088-220">詳細については、「F5」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41088-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="41088-221">(オプション) ディレクターおよび (必須) フロントエンドプール Web サービスの HLB 要件を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="41088-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="41088-222">内部 Web サービスの Vip で、HLB の Source_addr 常設 (内部ポート 80, 443) を設定します。</span><span class="sxs-lookup"><span data-stu-id="41088-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="41088-223">Skype for Business Server の場合、Source_addr 常設は、セッション状態を維持するために、1つの IP アドレスからの複数の接続が常に1つのサーバーに送信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="41088-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="41088-224">TCP アイドルタイムアウト (1800 秒) を使用します。</span><span class="sxs-lookup"><span data-stu-id="41088-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="41088-225">リバースプロキシと次ホッププールの HLB の間のファイアウォールで、リバースプロキシから HLB に https: 4443 トラフィックを許可するためのルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="41088-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="41088-226">ポート80、443、4443をリッスンするように HLB を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="41088-227">HLB アフィニティ要件の概要</span><span class="sxs-lookup"><span data-stu-id="41088-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="41088-228">**クライアント/ユーザーの場所**</span><span class="sxs-lookup"><span data-stu-id="41088-228">**Client/user location**</span></span>|<span data-ttu-id="41088-229">**外部 Web サービスの FQDN のアフィニティ要件**</span><span class="sxs-lookup"><span data-stu-id="41088-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="41088-230">**内部 web サービスの各アフィニティの要件**</span><span class="sxs-lookup"><span data-stu-id="41088-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41088-231">Skype for Business Web App (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="41088-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="41088-232">モバイルデバイス (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="41088-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="41088-233">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="41088-233">No affinity</span></span>  <br/> |<span data-ttu-id="41088-234">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="41088-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="41088-235">Skype for Business Web App (外部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="41088-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="41088-236">モバイルデバイス (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="41088-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="41088-237">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="41088-237">No affinity</span></span>  <br/> |<span data-ttu-id="41088-238">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="41088-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="41088-239">Skype for Business Web App (内部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="41088-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="41088-240">モバイル デバイス (展開しない)</span><span class="sxs-lookup"><span data-stu-id="41088-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="41088-241">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="41088-241">No affinity</span></span>  <br/> |<span data-ttu-id="41088-242">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="41088-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="41088-243">HLBs ポートの監視</span><span class="sxs-lookup"><span data-stu-id="41088-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="41088-244">ハードウェアまたは通信障害によって特定のサービスがいつ使用できなくなるかを判断するには、ハードウェアロードバランサーに対してポート監視を定義します。</span><span class="sxs-lookup"><span data-stu-id="41088-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="41088-245">たとえば、フロントエンドサーバーまたはフロントエンドプールに障害が発生したためにフロントエンドサーバーサービス (RTCSRV) が停止した場合、HLB の監視でも Web サービス上のトラフィックの受信を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="41088-246">Hlb にポート監視を実装して、HLB 外部インターフェイスの次のものを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41088-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="41088-247">**仮想 IP/ポート**</span><span class="sxs-lookup"><span data-stu-id="41088-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="41088-248">**ノード ポート**</span><span class="sxs-lookup"><span data-stu-id="41088-248">**Node Port**</span></span>|<span data-ttu-id="41088-249">**ノード コンピューター/モニター**</span><span class="sxs-lookup"><span data-stu-id="41088-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="41088-250">**保存プロファイル**</span><span class="sxs-lookup"><span data-stu-id="41088-250">**Persistence Profile**</span></span>|<span data-ttu-id="41088-251">**メモ**</span><span class="sxs-lookup"><span data-stu-id="41088-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41088-252">\<プール \> web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="41088-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="41088-253">443</span><span class="sxs-lookup"><span data-stu-id="41088-253">443</span></span>  <br/> |<span data-ttu-id="41088-254">4443</span><span class="sxs-lookup"><span data-stu-id="41088-254">4443</span></span>  <br/> |<span data-ttu-id="41088-255">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="41088-255">Front End</span></span>  <br/> <span data-ttu-id="41088-256">5061</span><span class="sxs-lookup"><span data-stu-id="41088-256">5061</span></span>  <br/> |<span data-ttu-id="41088-257">なし</span><span class="sxs-lookup"><span data-stu-id="41088-257">None</span></span>  <br/> |<span data-ttu-id="41088-258">HTTPS</span><span class="sxs-lookup"><span data-stu-id="41088-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="41088-259">\<プール \> web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="41088-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="41088-260">80</span><span class="sxs-lookup"><span data-stu-id="41088-260">80</span></span>  <br/> |<span data-ttu-id="41088-261">8080</span><span class="sxs-lookup"><span data-stu-id="41088-261">8080</span></span>  <br/> |<span data-ttu-id="41088-262">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="41088-262">Front End</span></span>  <br/> <span data-ttu-id="41088-263">5061</span><span class="sxs-lookup"><span data-stu-id="41088-263">5061</span></span>  <br/> |<span data-ttu-id="41088-264">なし</span><span class="sxs-lookup"><span data-stu-id="41088-264">None</span></span>  <br/> |<span data-ttu-id="41088-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="41088-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="41088-266">ハードウェア要件およびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="41088-266">Hardware and software requirements</span></span>

<span data-ttu-id="41088-267">ここでは、「Skype for business [server 2015 のサーバーの](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)全体的な要件」および「 [Skype for business server 2019 のドキュメントのシステム要件](../../../SfBServer2019/plan/system-requirements.md)」に記載されているエッジサーバーのハードウェア要件とソフトウェア要件について説明してきました。</span><span class="sxs-lookup"><span data-stu-id="41088-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="41088-268">併置</span><span class="sxs-lookup"><span data-stu-id="41088-268">Collocation</span></span>

<span data-ttu-id="41088-269">[Skype For Business server のドキュメントに関するトポロジの基本](../../plan-your-deployment/topology-basics/topology-basics.md)については、「エッジサーバーの併置」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41088-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

