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
ms.openlocfilehash: e066249498febbd5e622546533f49422320c7c87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813767"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="872f7-103">Skype for Business Server のエッジ サーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="872f7-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="872f7-104">**概要:** Skype for Business Server のエッジ サーバーのシステム要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="872f7-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="872f7-105">Skype for Business Server エッジ サーバーの展開に関しては、環境構造の計画に加え、環境内のサーバーに対して行う必要がある操作を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="872f7-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="872f7-106">トポロジ、DNS、証明書、その他のインフラストラクチャに関する問題の詳細については、環境要件のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="872f7-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="872f7-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="872f7-107">Components</span></span>

<span data-ttu-id="872f7-108">エッジ サーバー環境について説明する場合、大部分は境界ネットワークに展開されているコンポーネントを参照しています (つまり、ワークグループまたは Skype for Business Server ドメイン構造の外部にあるドメインのいずれかです)。</span><span class="sxs-lookup"><span data-stu-id="872f7-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="872f7-109">次のコンポーネントを念頭に置いて、Edge を正常に展開するために注意する必要があるコンポーネントを示します。</span><span class="sxs-lookup"><span data-stu-id="872f7-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="872f7-110">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="872f7-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="872f7-111">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="872f7-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="872f7-112">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="872f7-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="872f7-113">[ディレクター](system-requirements.md#Directors) (これらはオプションであり、含まれている場合は内部ネットワークに保存されます)</span><span class="sxs-lookup"><span data-stu-id="872f7-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="872f7-114">[ロード バランサー](system-requirements.md#LoadBalancers) (DNS 負荷分散またはハードウェア ロード バランサー (HLB) を使用できますが、単一のエッジ サーバーの場合は必要ない)</span><span class="sxs-lookup"><span data-stu-id="872f7-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="872f7-115">以下では、これらのそれぞれについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="872f7-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="872f7-116">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="872f7-116">Edge Servers</span></span>
<span data-ttu-id="872f7-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="872f7-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="872f7-118">これらは、境界環境に展開されている Skype for Business サーバーです。</span><span class="sxs-lookup"><span data-stu-id="872f7-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="872f7-119">その役割は、内部の Skype for Business Server 展開によって提供されるサービスの外部ユーザーとの間でネットワーク トラフィックを送受信する役割です。</span><span class="sxs-lookup"><span data-stu-id="872f7-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="872f7-120">これを正常に行うには、各エッジ サーバーが次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="872f7-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="872f7-121">**アクセス エッジ サービス**: 送信と受信の両方のセッション開始プロトコル (SIP) トラフィックに対して、単一の信頼できる接続ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="872f7-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="872f7-122">**Web 会議エッジ サービス**: 外部ユーザーが内部 Skype for Business Server 環境でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="872f7-123">**音声ビデオ エッジ サービス**: 音声、ビデオ、アプリケーション共有、およびファイル転送を外部ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="872f7-124">**XMPP プロキシ サービス: XMPP** フェデレーション パートナーとの間で XMPP (Extensible Messaging and Presence Protocol) メッセージを受け入れて送信します。</span><span class="sxs-lookup"><span data-stu-id="872f7-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="872f7-125">承認された外部ユーザーは、エッジ サーバーを使用して内部の Skype for Business Server 展開に接続できますが、それ以外の場合は、すべてのユーザーに内部ネットワークへの他のアクセスを提供しません。</span><span class="sxs-lookup"><span data-stu-id="872f7-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="872f7-126">エッジ サーバーは、有効な Skype for Business クライアントおよび他のエッジ サーバー (フェデレーション シナリオの場合) に接続を提供するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="872f7-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="872f7-127">他のエンド ポイント クライアントやサーバーの種類から接続できません。</span><span class="sxs-lookup"><span data-stu-id="872f7-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="872f7-128">XMPP ゲートウェイ サーバーは、構成済みの XMPP パートナーとの接続を許可できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="872f7-129">ただし、これらは、動作する唯一のクライアントとフェデレーションの種類です。</span><span class="sxs-lookup"><span data-stu-id="872f7-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="872f7-130">XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="872f7-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="872f7-131">詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="872f7-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="872f7-132">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="872f7-132">Reverse proxies</span></span>
<span data-ttu-id="872f7-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="872f7-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="872f7-134">リバース プロキシ (RP) サーバーは Skype for Business Server の役割を持たませんが、エッジ サーバー展開の重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="872f7-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="872f7-135">リバース プロキシを使用すると、外部ユーザーは次の機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="872f7-136">簡易 URL を使用して会議またはダイヤルイン会議に接続します。</span><span class="sxs-lookup"><span data-stu-id="872f7-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="872f7-137">会議コンテンツをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="872f7-137">download meeting content.</span></span>
    
- <span data-ttu-id="872f7-138">配布グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="872f7-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="872f7-139">クライアント証明書ベースの認証用にユーザーベースの証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="872f7-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="872f7-140">アドレス帳サーバーからファイルをダウンロードするか、アドレス帳 Web クエリ サービスにクエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="872f7-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="872f7-141">クライアントおよびデバイス ソフトウェアの更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="872f7-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="872f7-142">モバイル デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="872f7-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="872f7-143">これにより、モビリティ サービスを提供するフロントエンド サーバーを自動的に検出できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="872f7-144">Microsoft 365 または Office 365 からモバイル デバイスへのプッシュ通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="872f7-144">it enables push notifications from Microsoft 365 or Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="872f7-145">現在のリバース プロキシに関する推奨事項については、Skype for Business のテレフォニー [インフラストラクチャページをご覧](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) ください。</span><span class="sxs-lookup"><span data-stu-id="872f7-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="872f7-146">そのため、リバース プロキシは次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="872f7-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="872f7-147">は、パブリック証明書を介して環境に導入されたトランスポート層セキュリティ (TLS) を使用して、次の公開された外部 Web サービスに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="872f7-148">ディレクターまたはディレクター プール</span><span class="sxs-lookup"><span data-stu-id="872f7-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="872f7-149">フロントエンド サーバーまたはフロントエンド プール</span><span class="sxs-lookup"><span data-stu-id="872f7-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="872f7-150">暗号化のために証明書を使用して内部 Web サイトを公開したり、必要に応じて暗号化されていない方法で公開したりできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="872f7-151">は、完全修飾ドメイン名 (FQDN) を使用して、内部ホスト型 Web サイトを外部に公開できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="872f7-152">ホストされた Web サイトのすべてのコンテンツを発行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="872f7-153">既定では、 _ ディレクティブを使用できます。_ ディレクティブは、ほとんどの Web サーバーで認識され、"Web サーバー上のすべてのコンテンツを公開する" ことを **/\\** 意味します。</span><span class="sxs-lookup"><span data-stu-id="872f7-153">By default, you can use the **/\\** _ directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="872f7-154">また、ディレクティブ _*(/Uwca/ \\* \*_ など) を変更できます。これは、"仮想ディレクトリ Ucwa の下のすべてのコンテンツを公開する" を意味します。</span><span class="sxs-lookup"><span data-stu-id="872f7-154">You can also modify the directive—for example, _*/Uwca/\\*\*_, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="872f7-155">は、公開された Web サイトからコンテンツを要求するクライアントとの TLS 接続を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="872f7-156">は、サブジェクトの代替名 (SAN) エントリを持つ証明書を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="872f7-157">外部 Web サービスの FQDN が解決されるリスナーまたはインターフェイスへの証明書のバインドを許可できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="872f7-158">リスナーの構成は、インターフェイスの方が望ましいです。</span><span class="sxs-lookup"><span data-stu-id="872f7-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="872f7-159">多くのリスナーは、1 つのインターフェイスで構成できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="872f7-160">ホスト ヘッダー処理の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="872f7-161">多くの場合、要求元のクライアントによって送信される元のホスト ヘッダーは、リバース プロキシによって変更されるのではなく、透過的に渡される必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="872f7-162">1 つの外部で定義されたポート (たとえば、TCP 443) から別の定義済みポート (たとえば、TCP 4443) への TLS トラフィックのブリッジを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="872f7-163">リバース プロキシは、受信時にパケットの暗号化を解除し、送信時にパケットを再暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="872f7-164">1 つのポート (たとえば、TCP 80) から別のポート (たとえば、TCP 8080) への暗号化されていない TCP トラフィックのブリッジを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="872f7-165">NTLM 認証、認証なし、およびパススルー認証の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="872f7-166">リバース プロキシでこの一覧のすべてのニーズに対応できる場合は、必ず実行してください。ただし、上記のリンクにある推奨事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="872f7-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="872f7-167">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="872f7-167">Firewalls</span></span>
<span data-ttu-id="872f7-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="872f7-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="872f7-169">エッジ展開は外部ファイアウォールの内側に配置する必要がありますが、エッジ環境と内部環境の間には 2 つのファイアウォール、1 つは外部、もう 1 つは内部ファイアウォールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="872f7-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="872f7-170">シナリオに含まれていますすべてのドキュメントには、2 つのファイアウォールがあります。</span><span class="sxs-lookup"><span data-stu-id="872f7-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="872f7-171">2 つのファイアウォールをお勧めします。このファイアウォールは、ネットワーク エッジ間の厳密なルーティングを保証し、内部ネットワークのファイアウォール保護を 2 倍にします。</span><span class="sxs-lookup"><span data-stu-id="872f7-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="872f7-172">ディレクター</span><span class="sxs-lookup"><span data-stu-id="872f7-172">Directors</span></span>
<span data-ttu-id="872f7-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="872f7-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="872f7-174">これはオプションの役割です。</span><span class="sxs-lookup"><span data-stu-id="872f7-174">This is an optional role.</span></span> <span data-ttu-id="872f7-175">単一サーバーまたはディレクターの役割を実行するサーバーのプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="872f7-176">これは、内部の Skype for Business Server 環境で見つかった役割です。</span><span class="sxs-lookup"><span data-stu-id="872f7-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="872f7-177">ディレクターは、Skype for Business Server の内部サーバー宛てのエッジ サーバーから受信 SIP トラフィックを受信する内部の次ホップ サーバーです。</span><span class="sxs-lookup"><span data-stu-id="872f7-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="872f7-178">受信要求を事前認証し、ユーザーのホーム プールまたはサーバーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="872f7-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="872f7-179">この事前認証を使用すると、未確認のユーザー アカウント要求を削除できます。</span><span class="sxs-lookup"><span data-stu-id="872f7-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="872f7-180">なぜそれが重要なのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="872f7-180">Why does that matter?</span></span> <span data-ttu-id="872f7-181">ディレクターにとって重要な機能は、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックから Standard Edition サーバーとフロントエンド サーバーまたはフロントエンド プールを保護する機能です。</span><span class="sxs-lookup"><span data-stu-id="872f7-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="872f7-182">ネットワークに無効な外部トラフィックが流された場合、トラフィックはディレクターで停止します。</span><span class="sxs-lookup"><span data-stu-id="872f7-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="872f7-183">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="872f7-183">Load Balancers</span></span>
<span data-ttu-id="872f7-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="872f7-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="872f7-185">Skype for Business Server の拡張統合エッジ トポロジは、新しい展開用に DNS 負荷分散用に最適化されています。この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="872f7-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="872f7-186">高可用性が必要な場合は、特定の状況に合ったハードウェア ロード バランサーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="872f7-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="872f7-187">Exchange UM _prior \*\*\* to Exchange 2013 を使用するリモート ユーザーの Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="872f7-187">Exchange UM for remote users using Exchange UM _ *prior*\* to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="872f7-188">ロード バランサーを混在できない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="872f7-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="872f7-189">Skype for Business Server 環境では、すべてのインターフェイスで DNS または HLB を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="872f7-190">直接サーバー リターン (DSR) NAT は、Skype for Business Server ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="872f7-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="872f7-191">A/V エッジ サービスを実行するエッジ サーバーエッジ サーバーのハードウェア ロード バランサー要件</span><span class="sxs-lookup"><span data-stu-id="872f7-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="872f7-192">A/V エッジ サービスを実行しているエッジ サーバーの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="872f7-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="872f7-193">内部ポートと外部ポート 443 の両方に対して TCP ネーグリングをオフにします (ネーグリングは、送信効率を向上するために、複数の小さなパケットを 1 つの大きなパケットに結合するプロセスです)。</span><span class="sxs-lookup"><span data-stu-id="872f7-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="872f7-194">外部ポート範囲 50000 ~ 59999 の TCP の入れ子をオフにします。</span><span class="sxs-lookup"><span data-stu-id="872f7-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="872f7-195">内部または外部のファイアウォールで NAT を使用しない。</span><span class="sxs-lookup"><span data-stu-id="872f7-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="872f7-196">エッジの内部インターフェイスは、エッジ サーバーの外部インターフェイスとは異なるネットワーク上に用意する必要があります。また、エッジ間のルーティングを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="872f7-197">A/V エッジ サービスを実行しているエッジ サーバーの外部インターフェイスは、パブリックにログアウト可能な IP アドレスを使用する必要があります。また、エッジの外部 IP アドレスに NAT またはポート変換を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="872f7-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="872f7-198">HLB の要件</span><span class="sxs-lookup"><span data-stu-id="872f7-198">HLB requirements</span></span>

<span data-ttu-id="872f7-199">Skype for Business Server には、Cookie ベースのアフィニティ要件があまり存在しません。</span><span class="sxs-lookup"><span data-stu-id="872f7-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="872f7-200">そのため、Skype for Business Server 環境に Lync Server 2010 フロントエンド サーバーまたはフロント エンド プールが含まれる **(これは** Skype for Business Server 2015 固有の場合) ない限り、Cookie ベースの永続性を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="872f7-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="872f7-201">Lync Server 2010 に推奨される構成方法では、Cookie ベースのアフィニティが必要になります。</span><span class="sxs-lookup"><span data-stu-id="872f7-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="872f7-202">HLB に対して Cookie ベースのアフィニティを有効にしても、環境に必要ない場合でも問題はありません。</span><span class="sxs-lookup"><span data-stu-id="872f7-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="872f7-203">環境に Cookie **ベースのアフィニティ** が必要ない場合:</span><span class="sxs-lookup"><span data-stu-id="872f7-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="872f7-204">ポート 443 のリバース プロキシ公開ルールで、転送ホスト ヘッダーを True **に** 設定 **します**。</span><span class="sxs-lookup"><span data-stu-id="872f7-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="872f7-205">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="872f7-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="872f7-206">Cookie ベースのアフィニティ **が必要** な展開の場合:</span><span class="sxs-lookup"><span data-stu-id="872f7-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="872f7-207">ポート 443 のリバース プロキシ公開ルールで、転送ホスト ヘッダーを True **に** 設定 **します**。</span><span class="sxs-lookup"><span data-stu-id="872f7-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="872f7-208">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="872f7-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="872f7-209">ロード バランサーのハードウェア Cookie **は** httpOnly とマークしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="872f7-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="872f7-210">ハードウェア ロード バランサー Cookie **には有効期限** を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="872f7-211">ロード バランサーハードウェア **Cookie** には **MS-WSMAN** という名前を付けます (これは Web サービスが期待する値であり、変更できません)。</span><span class="sxs-lookup"><span data-stu-id="872f7-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="872f7-212">ハードウェア ロード バランサー  Cookie は、同じ TCP 接続上の以前の HTTP 応答が Cookie を取得したかどうかに関係なく、受信 HTTP 要求に Cookie が設定されなかったすべての HTTP 応答で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="872f7-213">ハードウェア ロード バランサーが COOKIE の挿入を TCP 接続ごとに 1 回だけ行う最適化を行う場合は、その最適化 **を** 使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="872f7-214">HLB 構成では、ソース アフィニティと 20 分間の TCP セッションの有効期間を使用するのが一般的です。これは、クライアントの使用状況やアプリケーションの操作によってセッション状態が維持される場合に、Skype for Business Server とそのクライアントで問題ありません。</span><span class="sxs-lookup"><span data-stu-id="872f7-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="872f7-215">モバイル デバイスを展開する場合、HLB は TCP セッション内の個々の要求を負荷分散できる必要があります (実際には、ターゲット IP アドレスに基づいて個々の要求を負荷分散できる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="872f7-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="872f7-216">F5 HLB には OneConnect という機能があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="872f7-217">これにより、TCP 接続内の各要求が個別に負荷分散されます。</span><span class="sxs-lookup"><span data-stu-id="872f7-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="872f7-218">モバイル デバイスを展開する場合は、HLB ベンダーが同じ機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="872f7-219">最新の iOS モバイル アプリには TLS バージョン 1.2 が必要です。</span><span class="sxs-lookup"><span data-stu-id="872f7-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="872f7-220">詳細を知る必要がある場合は、F5 キーを押してこの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="872f7-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="872f7-221">(オプション) ディレクターと (必須) フロントエンド プール Web サービスの HLB 要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="872f7-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="872f7-222">内部 Web サービスの VIP については、HLB Source_addr永続性 (内部ポート 80、443) を設定します。</span><span class="sxs-lookup"><span data-stu-id="872f7-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="872f7-223">Skype for Business Server の場合、Source_addrは、セッション状態を維持するために、1 つの IP アドレスから複数の接続が常に 1 つのサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="872f7-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="872f7-224">1800 秒の TCP アイドル タイムアウトを使用します。</span><span class="sxs-lookup"><span data-stu-id="872f7-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="872f7-225">リバース プロキシと次ホップ プールの HLB の間のファイアウォールで、リバース プロキシから HLB への https: ポート 4443 のトラフィックを許可するルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="872f7-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="872f7-226">HLB は、ポート 80、443、および 4443 をリッスンするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="872f7-227">HLB アフィニティ要件の概要</span><span class="sxs-lookup"><span data-stu-id="872f7-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="872f7-228">**クライアント/ユーザーの場所**</span><span class="sxs-lookup"><span data-stu-id="872f7-228">**Client/user location**</span></span>|<span data-ttu-id="872f7-229">**外部 Web サービスの FQDN のアフィニティ要件**</span><span class="sxs-lookup"><span data-stu-id="872f7-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="872f7-230">**内部 Web サービスの FQSN アフィニティ要件**</span><span class="sxs-lookup"><span data-stu-id="872f7-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="872f7-231">Skype for Business Web App (内部ユーザーと外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="872f7-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="872f7-232">モバイル デバイス (内部ユーザーと外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="872f7-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="872f7-233">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="872f7-233">No affinity</span></span>  <br/> |<span data-ttu-id="872f7-234">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="872f7-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="872f7-235">Skype for Business Web App (外部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="872f7-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="872f7-236">モバイル デバイス (内部ユーザーと外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="872f7-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="872f7-237">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="872f7-237">No affinity</span></span>  <br/> |<span data-ttu-id="872f7-238">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="872f7-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="872f7-239">Skype for Business Web App (内部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="872f7-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="872f7-240">モバイル デバイス (展開しない)</span><span class="sxs-lookup"><span data-stu-id="872f7-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="872f7-241">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="872f7-241">No affinity</span></span>  <br/> |<span data-ttu-id="872f7-242">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="872f7-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="872f7-243">HLB のポート監視</span><span class="sxs-lookup"><span data-stu-id="872f7-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="872f7-244">ハードウェア ロード バランサーでポート監視を定義し、ハードウェアまたは通信の障害が原因で特定のサービスが使用できなくなった状況を判断します。</span><span class="sxs-lookup"><span data-stu-id="872f7-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="872f7-245">たとえば、フロントエンド サーバーまたはフロント エンド プールに障害が発生してフロントエンド サーバー サービス (RTCSRV) が停止した場合、HLB 監視は Web サービス上のトラフィックの受信も停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="872f7-246">HLB の外部インターフェイスを監視するには、HLB にポート監視を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872f7-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="872f7-247">**仮想 IP/ポート**</span><span class="sxs-lookup"><span data-stu-id="872f7-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="872f7-248">**ノード ポート**</span><span class="sxs-lookup"><span data-stu-id="872f7-248">**Node Port**</span></span>|<span data-ttu-id="872f7-249">**ノード コンピューター/モニター**</span><span class="sxs-lookup"><span data-stu-id="872f7-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="872f7-250">**保存プロファイル**</span><span class="sxs-lookup"><span data-stu-id="872f7-250">**Persistence Profile**</span></span>|<span data-ttu-id="872f7-251">**注**</span><span class="sxs-lookup"><span data-stu-id="872f7-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="872f7-252">\<pool\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="872f7-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="872f7-253">443</span><span class="sxs-lookup"><span data-stu-id="872f7-253">443</span></span>  <br/> |<span data-ttu-id="872f7-254">4443</span><span class="sxs-lookup"><span data-stu-id="872f7-254">4443</span></span>  <br/> |<span data-ttu-id="872f7-255">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="872f7-255">Front End</span></span>  <br/> <span data-ttu-id="872f7-256">5061</span><span class="sxs-lookup"><span data-stu-id="872f7-256">5061</span></span>  <br/> |<span data-ttu-id="872f7-257">なし</span><span class="sxs-lookup"><span data-stu-id="872f7-257">None</span></span>  <br/> |<span data-ttu-id="872f7-258">HTTPS</span><span class="sxs-lookup"><span data-stu-id="872f7-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="872f7-259">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="872f7-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="872f7-260">80</span><span class="sxs-lookup"><span data-stu-id="872f7-260">80</span></span>  <br/> |<span data-ttu-id="872f7-261">8080</span><span class="sxs-lookup"><span data-stu-id="872f7-261">8080</span></span>  <br/> |<span data-ttu-id="872f7-262">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="872f7-262">Front End</span></span>  <br/> <span data-ttu-id="872f7-263">5061</span><span class="sxs-lookup"><span data-stu-id="872f7-263">5061</span></span>  <br/> |<span data-ttu-id="872f7-264">なし</span><span class="sxs-lookup"><span data-stu-id="872f7-264">None</span></span>  <br/> |<span data-ttu-id="872f7-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="872f7-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="872f7-266">ハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="872f7-266">Hardware and software requirements</span></span>

<span data-ttu-id="872f7-267">[Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)のサーバーの全体的な要件と、Skype for Business [Server 2019](../../../SfBServer2019/plan/system-requirements.md)のシステム要件に関するドキュメントでは、エッジ サーバーのハードウェア要件とソフトウェア要件について説明しました。</span><span class="sxs-lookup"><span data-stu-id="872f7-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="872f7-268">Collocation</span><span class="sxs-lookup"><span data-stu-id="872f7-268">Collocation</span></span>

<span data-ttu-id="872f7-269">Skype for Business Server のトポロジの基本に関するドキュメントでは、エッジ サーバーのコロケーション [について説明](../../plan-your-deployment/topology-basics/topology-basics.md) しました。</span><span class="sxs-lookup"><span data-stu-id="872f7-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

