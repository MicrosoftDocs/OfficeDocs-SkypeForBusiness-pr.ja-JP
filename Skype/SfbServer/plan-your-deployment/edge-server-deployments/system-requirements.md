---
title: Skype for Business Server のエッジ サーバーのシステム要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server のエッジ サーバーのシステム要件について説明します。'
ms.openlocfilehash: d5003a265a53c3603892133077a961f54c974401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112743"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="554e4-103">Skype for Business Server のエッジ サーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="554e4-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="554e4-104">**概要:** Skype for Business Server のエッジ サーバーのシステム要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="554e4-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="554e4-105">Skype for Business Server Edge Server の展開に関しては、環境自体にあるサーバーまたはサーバーに対して行う必要があるだけでなく、環境構造を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="554e4-106">トポロジ、DNS、証明書、その他のインフラストラクチャに関する懸念事項の詳細については、環境要件のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="554e4-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="554e4-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="554e4-107">Components</span></span>

<span data-ttu-id="554e4-108">エッジ サーバー環境について説明する場合、大部分は境界ネットワークに展開されているコンポーネントを参照しています (つまり、ワークグループまたは Skype for Business Server ドメイン構造の外部にあるドメインです)。</span><span class="sxs-lookup"><span data-stu-id="554e4-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="554e4-109">これらのコンポーネントは、Edge を正常に展開するために注意する必要があるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="554e4-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="554e4-110">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="554e4-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="554e4-111">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="554e4-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="554e4-112">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="554e4-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="554e4-113">[ディレクター](system-requirements.md#Directors) (これらはオプションで、含まれている場合は内部ネットワークに保存されます)</span><span class="sxs-lookup"><span data-stu-id="554e4-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="554e4-114">[ロード バランサー](system-requirements.md#LoadBalancers) (DNS 負荷分散またはハードウェア ロード バランサー (HLB) を使用できますが、1 つのエッジ サーバーの場合、これは必要ない)</span><span class="sxs-lookup"><span data-stu-id="554e4-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="554e4-115">以下の各詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="554e4-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="554e4-116">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="554e4-116">Edge Servers</span></span>
<span data-ttu-id="554e4-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="554e4-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="554e4-118">これらは、境界環境に展開されている Skype for Business サーバーです。</span><span class="sxs-lookup"><span data-stu-id="554e4-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="554e4-119">その役割は、内部 Skype for Business Server 展開によって提供されるサービスの外部ユーザーに対してネットワーク トラフィックを送受信する役割です。</span><span class="sxs-lookup"><span data-stu-id="554e4-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="554e4-120">これを正常に行うには、各エッジ サーバーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="554e4-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="554e4-121">**Access Edge Service**: 送信セッション開始プロトコル (SIP) トラフィックと受信セッション開始プロトコル (SIP) トラフィックの両方に 1 つの信頼できる接続ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="554e4-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="554e4-122">**Web 会議エッジ サービス**: 外部ユーザーが、内部の Skype for Business Server 環境でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="554e4-123">**音声ビデオ エッジ サービス**: 音声、ビデオ、アプリケーション共有、およびファイル転送を外部ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="554e4-124">**XMPP プロキシ サービス**: 構成済みの XMPP フェデレーション パートナーとの間で、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) メッセージを受け入れて送信します。</span><span class="sxs-lookup"><span data-stu-id="554e4-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="554e4-125">承認された外部ユーザーは、エッジ サーバーを使用して内部 Skype for Business Server 展開に接続できますが、それ以外の場合は、内部ネットワークへのその他のアクセス権を誰にも提供しません。</span><span class="sxs-lookup"><span data-stu-id="554e4-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="554e4-126">エッジ サーバーは、有効な Skype for Business クライアントおよび他のエッジ サーバー (フェデレーション シナリオ) の接続を提供するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="554e4-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="554e4-127">他のエンド ポイント クライアントまたはサーバーの種類から接続できません。</span><span class="sxs-lookup"><span data-stu-id="554e4-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="554e4-128">XMPP ゲートウェイ サーバーは、構成済みの XMPP パートナーとの接続を許可できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="554e4-129">しかし、繰り返しますが、これらは動作する唯一のクライアントとフェデレーションの種類です。</span><span class="sxs-lookup"><span data-stu-id="554e4-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="554e4-130">XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="554e4-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="554e4-131">詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="554e4-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="554e4-132">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="554e4-132">Reverse proxies</span></span>
<span data-ttu-id="554e4-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="554e4-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="554e4-134">リバース プロキシ (RP) サーバーには Skype for Business Server の役割は含めませんが、エッジ サーバー展開の重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="554e4-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="554e4-135">リバース プロキシを使用すると、外部ユーザーは次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="554e4-136">簡単な URL を使用して会議やダイヤルイン会議に接続できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="554e4-137">会議コンテンツをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="554e4-137">download meeting content.</span></span>
    
- <span data-ttu-id="554e4-138">配布グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="554e4-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="554e4-139">クライアント証明書ベース認証のユーザー ベースの証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="554e4-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="554e4-140">アドレス帳サーバーからファイルをダウンロードするか、アドレス帳 Web クエリ サービスにクエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="554e4-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="554e4-141">クライアントおよびデバイス ソフトウェアの更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="554e4-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="554e4-142">モバイル デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="554e4-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="554e4-143">これにより、モビリティ サービスを提供するフロントエンド サーバーを自動的に検出できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="554e4-144">Microsoft 365 または 365 からモバイル Officeプッシュ通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="554e4-144">it enables push notifications from Microsoft 365 or Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="554e4-145">現在のリバース プロキシの推奨事項は、[Skype for Business のテレフォニー [インフラストラクチャ] ページで確認](../../../SfbPartnerCertification/certification/infra-gateways.md) できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md) page.</span></span> <span data-ttu-id="554e4-146">そのため、リバース プロキシは次の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="554e4-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="554e4-147">パブリック証明書を介して環境に導入されたトランスポート層セキュリティ (TLS) を使用して、次の公開された外部 Web サービスに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="554e4-148">ディレクターまたはディレクター プール</span><span class="sxs-lookup"><span data-stu-id="554e4-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="554e4-149">フロントエンド サーバーまたはフロントエンド プール</span><span class="sxs-lookup"><span data-stu-id="554e4-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="554e4-150">必要に応じて、暗号化用の証明書を使用して内部 Web サイトを公開したり、暗号化されていない手段で公開したりできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="554e4-151">完全修飾ドメイン名 (FQDN) を使用して内部ホスト型 Web サイトを外部に公開できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="554e4-152">ホストされる Web サイトのすべてのコンテンツを公開できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="554e4-153">既定では、ほとんどの Web サーバーで認識される _ ディレクティブを使用して、「すべてのコンテンツを Web サーバーに公開する」という **/\\** 意味で使用できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-153">By default, you can use the **/\\** _ directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="554e4-154">また、ディレクティブ (_\*/Uwca/ \*\*\*など) を変更できます。これは「仮想ディレクトリ Ucwa の下のすべてのコンテンツを発行する」を \\ 意味します。</span><span class="sxs-lookup"><span data-stu-id="554e4-154">You can also modify the directive—for example, _\*/Uwca/\\*\*\*, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="554e4-155">公開された Web サイトからコンテンツを要求するクライアントとの TLS 接続を必要とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="554e4-156">サブジェクトの代替名 (SAN) エントリを持つ証明書を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="554e4-157">外部 Web サービス FQDN が解決するリスナーまたはインターフェイスへの証明書のバインドを許可できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="554e4-158">リスナーの構成は、インターフェイスの方が望ましいです。</span><span class="sxs-lookup"><span data-stu-id="554e4-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="554e4-159">多くのリスナーは、1 つのインターフェイスで構成できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="554e4-160">ホスト ヘッダー処理の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="554e4-161">多くの場合、要求元のクライアントによって送信される元のホスト ヘッダーは、リバース プロキシによって変更されるのではなく、透過的に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="554e4-162">1 つの外部定義ポート (TCP 443 など) から別の定義ポート (TCP 4443 など) への TLS トラフィックのブリッジを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="554e4-163">リバース プロキシは、受信時にパケットを復号化し、送信時にパケットを再暗号化する場合があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="554e4-164">あるポート (TCP 80 など) から別のポート (TCP 8080 など) への暗号化されていない TCP トラフィックのブリッジを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="554e4-165">NTLM 認証、認証なし、パススルー認証の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="554e4-166">リバース プロキシでこの一覧のすべてのニーズに対応できる場合は、行くのが良い必要がありますが、上記のリンクにある推奨事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="554e4-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="554e4-167">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="554e4-167">Firewalls</span></span>
<span data-ttu-id="554e4-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="554e4-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="554e4-169">エッジ展開を外部ファイアウォールの背後に配置する必要がありますが、エッジ環境と内部環境の間に 2 つのファイアウォール、1 つの外部ファイアウォール、1 つの内部ファイアウォールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="554e4-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="554e4-170">シナリオのすべてのドキュメントには、2 つのファイアウォールがあります。</span><span class="sxs-lookup"><span data-stu-id="554e4-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="554e4-171">2 つのファイアウォールは、あるネットワーク エッジから別のネットワーク エッジへの厳密なルーティングを保証し、内部ネットワークのファイアウォール保護を倍増するためにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="554e4-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="554e4-172">ディレクター</span><span class="sxs-lookup"><span data-stu-id="554e4-172">Directors</span></span>
<span data-ttu-id="554e4-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="554e4-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="554e4-174">これはオプションの役割です。</span><span class="sxs-lookup"><span data-stu-id="554e4-174">This is an optional role.</span></span> <span data-ttu-id="554e4-175">これは、単一のサーバーまたはディレクターの役割を実行するサーバーのプールです。</span><span class="sxs-lookup"><span data-stu-id="554e4-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="554e4-176">これは、内部の Skype for Business Server 環境で見つかった役割です。</span><span class="sxs-lookup"><span data-stu-id="554e4-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="554e4-177">ディレクターは、Skype for Business Server 内部サーバー宛てのエッジ サーバーから受信 SIP トラフィックを受信する内部ネクスト ホップ サーバーです。</span><span class="sxs-lookup"><span data-stu-id="554e4-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="554e4-178">受信要求を事前認証し、ユーザーのホーム プールまたはサーバーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="554e4-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="554e4-179">この事前認証を使用すると、未確認のユーザー アカウント要求を削除できます。</span><span class="sxs-lookup"><span data-stu-id="554e4-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="554e4-180">なぜそれが重要なのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="554e4-180">Why does that matter?</span></span> <span data-ttu-id="554e4-181">ディレクターにとって重要な機能は、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックから Standard Edition サーバーとフロントエンド サーバーまたはフロントエンド プールを保護する機能です。</span><span class="sxs-lookup"><span data-stu-id="554e4-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="554e4-182">ネットワークに無効な外部トラフィックが殺到した場合、トラフィックはディレクターで停止します。</span><span class="sxs-lookup"><span data-stu-id="554e4-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="554e4-183">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="554e4-183">Load Balancers</span></span>
<span data-ttu-id="554e4-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="554e4-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="554e4-185">Skype for Business Server の拡張統合エッジ トポロジは、新しい展開の DNS 負荷分散用に最適化され、これをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="554e4-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="554e4-186">高可用性が必要な場合は、特定の状況に応じてハードウェア ロード バランサーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="554e4-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="554e4-187">Exchange 2013 より前の Exchange **UM** を使用するリモート ユーザーの Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="554e4-187">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="554e4-188">ロード バランサーを混在できない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="554e4-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="554e4-189">Skype for Business Server 環境では、すべてのインターフェイスで DNS または HLB を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="554e4-190">Skype for Business Server では、ダイレクト サーバーリターン (DSR) NAT はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="554e4-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="554e4-191">A/V Edge サービスを実行するエッジ サーバーエッジ サーバーのハードウェア ロード バランサー要件</span><span class="sxs-lookup"><span data-stu-id="554e4-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="554e4-192">A/V Edge サービスを実行しているエッジ サーバーの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="554e4-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="554e4-193">内部ポートと外部ポート 443 の両方で TCP ナグリングをオフにします (ナグリングは、複数の小さなパケットを 1 つの大きなパケットに結合して、より効率的な送信を行うプロセスです)。</span><span class="sxs-lookup"><span data-stu-id="554e4-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="554e4-194">外部ポート範囲 50000 ~ 59999 の TCP ナグリングをオフにします。</span><span class="sxs-lookup"><span data-stu-id="554e4-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="554e4-195">内部ファイアウォールまたは外部ファイアウォールで NAT を使用しない。</span><span class="sxs-lookup"><span data-stu-id="554e4-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="554e4-196">エッジ内部インターフェイスは、エッジ サーバーの外部インターフェイスとは異なるネットワーク上に必要であり、その間のルーティングを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="554e4-197">A/V Edge サービスを実行しているエッジ サーバーの外部インターフェイスでは、パブリックに送信可能な IP アドレスを使用し、エッジ外部 IP アドレスに NAT またはポート変換を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="554e4-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="554e4-198">HLB の要件</span><span class="sxs-lookup"><span data-stu-id="554e4-198">HLB requirements</span></span>

<span data-ttu-id="554e4-199">Skype for Business Server には、Cookie ベースのアフィニティ要件が多く存在しません。</span><span class="sxs-lookup"><span data-stu-id="554e4-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="554e4-200">そのため、Skype for Business Server 環境で Lync Server 2010 フロントエンド サーバーまたはフロント エンド プールを使用する場合を超え、Cookie ベースの永続性を使用する必要はありません **(これは** Skype for Business Server 2015 固有の場合)。</span><span class="sxs-lookup"><span data-stu-id="554e4-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="554e4-201">Lync Server 2010 に推奨される構成方法では、Cookie ベースのアフィニティが必要になります。</span><span class="sxs-lookup"><span data-stu-id="554e4-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="554e4-202">HLB に対して Cookie ベースのアフィニティを有効にした場合、環境に必要ない場合でも問題はありません。</span><span class="sxs-lookup"><span data-stu-id="554e4-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="554e4-203">環境で Cookie **ベースの** アフィニティが必要ない場合は、次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="554e4-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="554e4-204">ポート 443 のリバース プロキシ発行ルールで、[ホスト ヘッダーの転送] を True **に\*\*\*\*設定します**。</span><span class="sxs-lookup"><span data-stu-id="554e4-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="554e4-205">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="554e4-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="554e4-206">Cookie ベースのアフィニティ **が** 必要な展開の場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="554e4-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="554e4-207">ポート 443 のリバース プロキシ発行ルールで、[ホスト ヘッダーの転送] を True **に\*\*\*\*設定します**。</span><span class="sxs-lookup"><span data-stu-id="554e4-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="554e4-208">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="554e4-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="554e4-209">ハードウェア ロード バランサー Cookie **に** httpOnly のマークを付けなさる必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="554e4-210">ハードウェア ロード バランサー Cookie **に有効期限** が設定されていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="554e4-211">ハードウェア ロード バランサー **Cookie** には **MS-WSMAN** という名前を付けます (これは、Web サービスが期待する値であり、変更できません)。</span><span class="sxs-lookup"><span data-stu-id="554e4-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="554e4-212">同じ TCP接続の以前の HTTP 応答が Cookie を取得したかどうかに関係なく、受信 HTTP 要求に Cookie が含めなかった HTTP 応答ごとに、ハードウェア ロード バランサー Cookie を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="554e4-213">ハードウェア ロード バランサーが Cookie 挿入を TCP 接続ごとに 1 回だけ最適化する場合は、その最適化 **を使用** する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="554e4-214">HLB 構成では、ソース アフィニティと 20 分間の TCP セッションの有効期間を使用するのが一般的です。これは、クライアントの使用状況やアプリケーションの操作によってセッション状態が維持されるので、Skype for Business Server とそのクライアントでは問題ありません。</span><span class="sxs-lookup"><span data-stu-id="554e4-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="554e4-215">モバイル デバイスを展開する場合、HLB は TCP セッション内で個々の要求を負荷分散できる必要があります (実際には、ターゲット IP アドレスに基づいて個々の要求を負荷分散できる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="554e4-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="554e4-216">F5 HLB には OneConnect という機能があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="554e4-217">これにより、TCP 接続内の各要求が個別に負荷分散されます。</span><span class="sxs-lookup"><span data-stu-id="554e4-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="554e4-218">モバイル デバイスを展開する場合は、HLB ベンダーが同じ機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="554e4-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="554e4-219">最新の iOS モバイル アプリでは、TLS バージョン 1.2 が必要です。</span><span class="sxs-lookup"><span data-stu-id="554e4-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="554e4-220">詳細を知る必要がある場合は、F5 はこのための特定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="554e4-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="554e4-221">(省略可能) ディレクターおよび (必須) フロントエンド プール Web サービスの HLB 要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="554e4-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="554e4-222">内部 Web サービスの VIP については、HLB Source_addr永続性 (内部ポート 80,443) を設定します。</span><span class="sxs-lookup"><span data-stu-id="554e4-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="554e4-223">Skype for Business Server の場合、Source_addrは、セッション状態を維持するために、1 つの IP アドレスから送信される複数の接続が常に 1 つのサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="554e4-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="554e4-224">1800 秒の TCP アイドル タイムアウトを使用します。</span><span class="sxs-lookup"><span data-stu-id="554e4-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="554e4-225">リバース プロキシとネクスト ホップ プールの HLB の間のファイアウォールで、リバース プロキシから HLB への https: ポート 4443 のトラフィックを許可するルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="554e4-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="554e4-226">HLB は、ポート 80、443、および 4443 でリッスンするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="554e4-227">HLB アフィニティ要件の概要</span><span class="sxs-lookup"><span data-stu-id="554e4-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="554e4-228">**クライアント/ユーザーの場所**</span><span class="sxs-lookup"><span data-stu-id="554e4-228">**Client/user location**</span></span>|<span data-ttu-id="554e4-229">**外部 Web サービスの FQDN のアフィニティ要件**</span><span class="sxs-lookup"><span data-stu-id="554e4-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="554e4-230">**内部 Web サービス FQSN アフィニティ要件**</span><span class="sxs-lookup"><span data-stu-id="554e4-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="554e4-231">Skype for Business Web App (内部ユーザーと外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="554e4-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="554e4-232">モバイル デバイス (内部ユーザーと外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="554e4-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="554e4-233">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="554e4-233">No affinity</span></span>  <br/> |<span data-ttu-id="554e4-234">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="554e4-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="554e4-235">Skype for Business Web App (外部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="554e4-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="554e4-236">モバイル デバイス (内部ユーザーと外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="554e4-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="554e4-237">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="554e4-237">No affinity</span></span>  <br/> |<span data-ttu-id="554e4-238">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="554e4-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="554e4-239">Skype for Business Web App (内部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="554e4-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="554e4-240">モバイル デバイス (展開しない)</span><span class="sxs-lookup"><span data-stu-id="554e4-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="554e4-241">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="554e4-241">No affinity</span></span>  <br/> |<span data-ttu-id="554e4-242">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="554e4-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="554e4-243">HLB のポート監視</span><span class="sxs-lookup"><span data-stu-id="554e4-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="554e4-244">ハードウェア ロード バランサーでポート監視を定義して、ハードウェアまたは通信の障害により、特定のサービスが利用できなくなったかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="554e4-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="554e4-245">たとえば、フロント エンド サーバー またはフロント エンド プールに障害が発生してフロント エンド サーバー サービス (RTCSRV) が停止した場合、HLB 監視によって Web サービス上のトラフィックの受信も停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="554e4-246">HLB の外部インターフェイスに対して次の監視を行う場合は、HLB でポート監視を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="554e4-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="554e4-247">**仮想 IP/ポート**</span><span class="sxs-lookup"><span data-stu-id="554e4-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="554e4-248">**ノード ポート**</span><span class="sxs-lookup"><span data-stu-id="554e4-248">**Node Port**</span></span>|<span data-ttu-id="554e4-249">**ノード コンピューター/モニター**</span><span class="sxs-lookup"><span data-stu-id="554e4-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="554e4-250">**保存プロファイル**</span><span class="sxs-lookup"><span data-stu-id="554e4-250">**Persistence Profile**</span></span>|<span data-ttu-id="554e4-251">**注**</span><span class="sxs-lookup"><span data-stu-id="554e4-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="554e4-252">\<pool\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="554e4-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="554e4-253">443</span><span class="sxs-lookup"><span data-stu-id="554e4-253">443</span></span>  <br/> |<span data-ttu-id="554e4-254">4443</span><span class="sxs-lookup"><span data-stu-id="554e4-254">4443</span></span>  <br/> |<span data-ttu-id="554e4-255">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="554e4-255">Front End</span></span>  <br/> <span data-ttu-id="554e4-256">5061</span><span class="sxs-lookup"><span data-stu-id="554e4-256">5061</span></span>  <br/> |<span data-ttu-id="554e4-257">なし</span><span class="sxs-lookup"><span data-stu-id="554e4-257">None</span></span>  <br/> |<span data-ttu-id="554e4-258">HTTPS</span><span class="sxs-lookup"><span data-stu-id="554e4-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="554e4-259">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="554e4-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="554e4-260">80</span><span class="sxs-lookup"><span data-stu-id="554e4-260">80</span></span>  <br/> |<span data-ttu-id="554e4-261">8080</span><span class="sxs-lookup"><span data-stu-id="554e4-261">8080</span></span>  <br/> |<span data-ttu-id="554e4-262">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="554e4-262">Front End</span></span>  <br/> <span data-ttu-id="554e4-263">5061</span><span class="sxs-lookup"><span data-stu-id="554e4-263">5061</span></span>  <br/> |<span data-ttu-id="554e4-264">なし</span><span class="sxs-lookup"><span data-stu-id="554e4-264">None</span></span>  <br/> |<span data-ttu-id="554e4-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="554e4-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="554e4-266">ハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="554e4-266">Hardware and software requirements</span></span>

<span data-ttu-id="554e4-267">[Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)の全体的なサーバー要件と Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md)のシステム要件に関するドキュメントでは、エッジ サーバーのハードウェア要件とソフトウェア要件について説明しました。</span><span class="sxs-lookup"><span data-stu-id="554e4-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="554e4-268">Collocation</span><span class="sxs-lookup"><span data-stu-id="554e4-268">Collocation</span></span>

<span data-ttu-id="554e4-269">「Topology [Basics for Skype for Business Server」](../../plan-your-deployment/topology-basics/topology-basics.md) のドキュメントで、エッジ サーバーのコロケーションについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="554e4-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
