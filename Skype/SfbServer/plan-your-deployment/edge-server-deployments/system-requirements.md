---
title: Skype for Business Server での Edge Server システム要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: '概要: Skype for Business Server の Edge Server のシステム要件について説明します。'
ms.openlocfilehash: 01a5cce8dd1ccb85d322b6c66615d022c8d6c2df
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "34277147"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="7f071-103">Skype for Business Server での Edge Server システム要件</span><span class="sxs-lookup"><span data-stu-id="7f071-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="7f071-104">**概要:** Skype for Business Server の Edge Server のシステム要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f071-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="7f071-105">Skype for Business Server Edge Server の展開については、環境内のサーバーまたはサーバーに対して必要なことと、環境構造の計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f071-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="7f071-106">トポロジ、DNS、証明書、およびその他のインフラストラクチャに関する考慮事項の詳細については、環境の要件のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f071-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="7f071-107">Components</span><span class="sxs-lookup"><span data-stu-id="7f071-107">Components</span></span>

<span data-ttu-id="7f071-108">エッジサーバー環境について話し合うときは、境界ネットワークに展開されているコンポーネント (ワークグループ内か、または Skype for Business Server ドメイン構造の外部のドメイン) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="7f071-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="7f071-109">以下に示すコンポーネントは、エッジの展開を成功させるために留意する必要があるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="7f071-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="7f071-110">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="7f071-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="7f071-111">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="7f071-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="7f071-112">Firewalls</span><span class="sxs-lookup"><span data-stu-id="7f071-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="7f071-113">[Directors](system-requirements.md#Directors) (オプションで、含まれる場合は内部ネットワーク上に存在します)</span><span class="sxs-lookup"><span data-stu-id="7f071-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="7f071-114">[ロードバランサー](system-requirements.md#LoadBalancers) (DNS 負荷分散またはハードウェアロードバランサー (hlb) を使用できますが、1台のエッジサーバーの場合、これは必要ありません)</span><span class="sxs-lookup"><span data-stu-id="7f071-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="7f071-115">上記の各コンポーネントに関する詳細を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7f071-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="7f071-116">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="7f071-116">Edge Servers</span></span>
<span data-ttu-id="7f071-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="7f071-117"></span></span>

<span data-ttu-id="7f071-118">これらは、境界環境に展開された Skype for Business サーバーです。</span><span class="sxs-lookup"><span data-stu-id="7f071-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="7f071-119">自分の Skype for Business Server の展開によって提供されているサービスについて、外部ユーザーへのネットワークトラフィックを送受信します。</span><span class="sxs-lookup"><span data-stu-id="7f071-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="7f071-120">この操作を正常に実行するには、各エッジサーバーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7f071-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="7f071-121">**Access Edge サービス**: 送受信セッション開始プロトコル (SIP) トラフィックの単一の信頼できる接続ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="7f071-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="7f071-122">[ **Web 会議エッジサービス**: 外部ユーザーが、社内の Skype For business Server 環境でホストされている会議に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7f071-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="7f071-123">**A/V Edge サービス**: 外部ユーザーがオーディオ、ビデオ、アプリケーション共有、ファイル転送を利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7f071-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="7f071-124">**Xmpp プロキシサービス**: 構成済みの Xmpp フェデレーションパートナーとの間での拡張可能なメッセージングとプレゼンスプロトコル (xmpp) メッセージを受け入れて送信します。</span><span class="sxs-lookup"><span data-stu-id="7f071-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="7f071-125">承認された外部ユーザーは、Edge サーバーを使用して、内部の Skype for Business Server 展開に接続できますが、それ以外の場合は、社内ネットワークへの他のアクセスは一切提供されません。</span><span class="sxs-lookup"><span data-stu-id="7f071-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f071-126">エッジサーバーは、有効になっている Skype for Business クライアントおよび他のエッジサーバー (フェデレーションシナリオ) への接続を提供するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="7f071-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="7f071-127">他のエンド ポイント クライアントやサーバーの種類からは接続できません。</span><span class="sxs-lookup"><span data-stu-id="7f071-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="7f071-128">XMPP ゲートウェイ サーバーにより、構成済みの XMPP パートナーとの接続を実現できます。</span><span class="sxs-lookup"><span data-stu-id="7f071-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="7f071-129">ただしこの場合も、フェデレーション シナリオで有効なものだけが、実際に機能するクライアントとフェデレーションの種類です。</span><span class="sxs-lookup"><span data-stu-id="7f071-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="7f071-130">XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7f071-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7f071-131">詳細については、「 [XMPP フェデレーションを移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f071-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="7f071-132">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="7f071-132">Reverse proxies</span></span>
<span data-ttu-id="7f071-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="7f071-133"></span></span>

<span data-ttu-id="7f071-134">リバースプロキシ (RP) サーバーには、Skype for Business Server の役割はありませんが、エッジサーバーの展開に不可欠なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="7f071-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="7f071-135">リバースプロキシを使用すると、外部ユーザーは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7f071-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="7f071-136">簡易 URL を使用して会議またはダイヤルイン会議に接続する。</span><span class="sxs-lookup"><span data-stu-id="7f071-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="7f071-137">会議コンテンツをダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="7f071-137">download meeting content.</span></span>
    
- <span data-ttu-id="7f071-138">配布グループを拡張する。</span><span class="sxs-lookup"><span data-stu-id="7f071-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="7f071-139">クライアント証明書ベースの認証用のユーザーベースの証明書を取得する。</span><span class="sxs-lookup"><span data-stu-id="7f071-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="7f071-140">アドレス帳サーバーから、またはアドレス帳 Web クエリサービスにクエリを送信するために、ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7f071-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="7f071-141">クライアントおよびデバイス ソフトウェアの更新プログラムを取得する。</span><span class="sxs-lookup"><span data-stu-id="7f071-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="7f071-142">また、モバイル デバイスに関しては以下の操作が可能になります。</span><span class="sxs-lookup"><span data-stu-id="7f071-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="7f071-143">これにより、モビリティサービスを提供するフロントエンドサーバーを自動的に検出できます。</span><span class="sxs-lookup"><span data-stu-id="7f071-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="7f071-144">Office 365 からモバイルデバイスへのプッシュ通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7f071-144">it enables push notifications from Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="7f071-145">現在のリバースプロキシの推奨事項は、「 [Skype For business のテレフォニーインフラストラクチャ](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」ページに記載されています。</span><span class="sxs-lookup"><span data-stu-id="7f071-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="7f071-146">リバースプロキシ:</span><span class="sxs-lookup"><span data-stu-id="7f071-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="7f071-147">以下から構成される公開済みの外部 Web サービスに接続するために、公開証明書を介して、環境に導入されているトランスポート層セキュリティ (TLS) を使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="7f071-148">ディレクターまたはディレクタープール</span><span class="sxs-lookup"><span data-stu-id="7f071-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="7f071-149">フロントエンドサーバーまたはフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="7f071-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="7f071-150">暗号化用の証明書を使用するか、必要に応じて暗号化されない方法で内部 Web サイトを公開できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="7f071-151">完全修飾ドメイン名 (FQDN) を使用して、内部的にホストされている Web サイトを外部に公開できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="7f071-152">ホストされた web サイトのすべてのコンテンツを公開できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="7f071-153">既定では、ほとんどの web \*\* /\*\* サーバーによって認識される \* ディレクティブを使うことができます。これは、web サーバー上のすべてのコンテンツを公開することを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f071-153">By default, you can use the **/\\**\* directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="7f071-154">また、ディレクティブ (\* */Uwca/\\* \* など) を変更することもできます。これは、「仮想ディレクトリのすべてのコンテンツを公開する」という意味です。</span><span class="sxs-lookup"><span data-stu-id="7f071-154">You can also modify the directive—for example, \*\*/Uwca/\\*\*\*, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="7f071-155">公開された Web サイトのコンテンツを要求するクライアントで TLS 接続を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="7f071-156">サブジェクトの別名 (SAN) エントリを持つ証明書を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="7f071-p108">外部 Web サービスの FQDN が解決されるリスナーまたはインターフェイスに対して証明書をバインドできる必要があります。インターフェイスの構成よりリスナーの構成をお勧めします。多くのリスナーは、単一のインターフェイスで構成できます。</span><span class="sxs-lookup"><span data-stu-id="7f071-p108">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve. Listener configurations are preferable to interfaces. Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="7f071-160">ホスト ヘッダー処理の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="7f071-161">通常、要求側のクライアントによって送信された元のホストヘッダーは、リバースプロキシによって変更されるのではなく、透過的に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="7f071-162">外部で定義された 1 つのポート (例: TCP 443) から別の定義されたポート (例: TCP 4443) への TLS トラフィックのブリッジを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="7f071-163">リバースプロキシは、受信時にパケットの暗号化を解除し、送信時にパケットを再度暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="7f071-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="7f071-164">1 つのポート (例: TCP 80) から別のポート (例: TCP 8080) への暗号化されていない TCP トラフィックのブリッジを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="7f071-165">NTLM 認証、認証なし、およびパススルー認証の構成を許可または受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="7f071-166">リバースプロキシによってこのリストのすべてのニーズを解決できる場合は、上記のリンクを参照してください。お勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f071-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="7f071-167">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="7f071-167">Firewalls</span></span>
<span data-ttu-id="7f071-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="7f071-168"></span></span>

<span data-ttu-id="7f071-p111">外部ファイアウォールの内側にエッジ展開を配置する必要がありますが、1 つの外部ファイアウォールと、エッジ環境と内部環境の間に配置する 1 つの内部ファイアウォールの、2 つのファイアウォールを使用することをお勧めします。シナリオのすべてのドキュメントには 2 つのファイアウォールが含まれます。2 つのファイアウォールをお勧めするのは、ネットワーク エッジ間の厳密なルーティングが実現され、内部ネットワーク用にファイアウォール保護が二重になるからです。</span><span class="sxs-lookup"><span data-stu-id="7f071-p111">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment. All our documentation in our Scenarios will have two firewalls. We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="7f071-172">ディレクター</span><span class="sxs-lookup"><span data-stu-id="7f071-172">Directors</span></span>
<span data-ttu-id="7f071-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="7f071-173"></span></span>

<span data-ttu-id="7f071-174">これは、オプションの役割です。</span><span class="sxs-lookup"><span data-stu-id="7f071-174">This is an optional role.</span></span> <span data-ttu-id="7f071-175">1台のサーバーまたはディレクターの役割を実行しているサーバーのプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f071-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="7f071-176">このロールは、内部の Skype for Business Server 環境で検索されます。</span><span class="sxs-lookup"><span data-stu-id="7f071-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="7f071-177">ディレクターは、Skype for Business Server の内部サーバー向けのエッジサーバーから受信 SIP トラフィックを受信する、内部の次ホップサーバーです。</span><span class="sxs-lookup"><span data-stu-id="7f071-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="7f071-178">着信した要求を事前認証し、これをユーザーのホーム プールまたはサーバーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="7f071-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="7f071-179">この事前認証により、識別されていないユーザー アカウントの要求を破棄できます。</span><span class="sxs-lookup"><span data-stu-id="7f071-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="7f071-180">このことが問題になる理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f071-180">Why does that matter?</span></span> <span data-ttu-id="7f071-181">ディレクターの重要な機能は、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックから、標準エディションのサーバーとフロントエンドサーバーまたはフロントエンドプールを保護することです。</span><span class="sxs-lookup"><span data-stu-id="7f071-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="7f071-182">ネットワークに無効な外部トラフィックがあふれている場合、トラフィックはディレクターで停止します。</span><span class="sxs-lookup"><span data-stu-id="7f071-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="7f071-183">ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="7f071-183">Load Balancers</span></span>
<span data-ttu-id="7f071-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="7f071-184"></span></span>

<span data-ttu-id="7f071-185">Skype for Business Server の統合されたエッジトポロジは、新しい展開で DNS の負荷分散を最適化するために最適化されています。これをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f071-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="7f071-186">高可用性が必要な場合は、1つの特定の状況に対してハードウェアロードバランサーを使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f071-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="7f071-187">Exchange 2013 の**前**に exchange um を使用しているリモートユーザーの exchange um。</span><span class="sxs-lookup"><span data-stu-id="7f071-187">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="7f071-188">ロード バランサーを混在させることができない点に注意することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="7f071-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="7f071-189">Skype for Business Server 環境では、すべてのインターフェイスで DNS または HLB のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7f071-190">Skype for Business Server では、Direct server return (DSR) NAT はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7f071-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="7f071-191">A/V Edge サービスを実行しているエッジサーバーエッジサーバーのハードウェアロードバランサーの要件</span><span class="sxs-lookup"><span data-stu-id="7f071-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="7f071-192">A/V Edge サービスを実行しているエッジサーバーについては、次の要件があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="7f071-193">内部と外部の両方のポート 443 に対して TCP のネーグル処理がオフになっていること。ネーグル処理はいくつかの小さなパケットを 1 つの大きなパケットにまとめて転送効率を向上させるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="7f071-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="7f071-194">外部ポート範囲 50000 ～ 59999 の TCP のネーグル処理がオフになっていること。</span><span class="sxs-lookup"><span data-stu-id="7f071-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="7f071-195">内部または外部のファイアウォールで NAT が使用されていないこと。</span><span class="sxs-lookup"><span data-stu-id="7f071-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="7f071-196">Edge の内部インターフェイスは、Edge Server の外部インターフェイスとは異なるネットワーク上に存在する必要があります。また、このインターフェイス間のルーティングは無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="7f071-197">A/V Edge サービスを実行しているエッジサーバーの外部インターフェイスでは、公開ルーティング可能な IP アドレスを使用し、エッジ外部 IP アドレスには NAT やポートの変換を行わないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="7f071-198">HLB の要件</span><span class="sxs-lookup"><span data-stu-id="7f071-198">HLB requirements</span></span>

<span data-ttu-id="7f071-199">Skype for Business Server には、cookie ベースのアフィニティ要件はあまりありません。</span><span class="sxs-lookup"><span data-stu-id="7f071-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="7f071-200">したがって、cookie ベースの常設を使用する必要はありません (これは Skype for Business Server 2015 固有のものである)。 Skype for Business Server 環境で**は、Lync** Server 2010 フロントエンドサーバーまたはフロントエンドプールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="7f071-201">Lync Server 2010 で推奨される構成方法では、cookie ベースのアフィニティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7f071-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f071-202">HLB 用に Cookie ベースのアフィニティを有効にすることを決定した場合、環境で不要であっても、そのような操作に問題はありません。</span><span class="sxs-lookup"><span data-stu-id="7f071-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="7f071-203">環境で Cookie ベースのアフィニティが**不要**である場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7f071-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="7f071-204">ポート443のリバースプロキシ公開ルールで、 **Forward host header**を**True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f071-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="7f071-205">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="7f071-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="7f071-206">Cookie ベースのアフィニティが**必要**である展開の場合:</span><span class="sxs-lookup"><span data-stu-id="7f071-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="7f071-207">ポート443のリバースプロキシ公開ルールで、 **Forward host header**を**True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f071-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="7f071-208">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="7f071-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="7f071-209">ハードウェアロードバランサーの cookie は、httpOnly とマークさ**れていない必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="7f071-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="7f071-210">ハードウェアロードバランサーの cookie には、有効期限を設定することは**できません**。</span><span class="sxs-lookup"><span data-stu-id="7f071-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="7f071-211">ハードウェアロードバランサー cookie は、 **MS-WSMAN** (これは、Web サービスが期待する値であり、変更できません) という名前で**ある必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="7f071-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="7f071-212">ハードウェアロードバランサー cookie は、同じ TCP 接続に対する以前の HTTP 応答が cookie を取得したかどうかに関係なく、着信 HTTP 要求の cookie がないすべての HTTP 応答で設定**する必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="7f071-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="7f071-213">ハードウェアロードバランサーが、TCP 接続ごとに1回のみ cookie の挿入を最適化する場合は、その最適化を使用**しないでください**。</span><span class="sxs-lookup"><span data-stu-id="7f071-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7f071-214">HLB 構成では、ソースアフィニティと20分の TCP セッションの有効期間を使うのが一般的です。これは、Skype for Business Server とそのクライアントには適しています。これは、クライアントの使用状況やアプリケーションの操作によってセッションの状態が維持されるためです。</span><span class="sxs-lookup"><span data-stu-id="7f071-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="7f071-215">モバイル デバイスを展開する場合、HLB で、TCP セッション内の個々の要求を負荷分散できるようにする必要があります (実際には、ターゲット IP アドレスに基づいて個々の要求を負荷分散できる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="7f071-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7f071-p121">F5 HLB には、OneConnect と呼ばれる機能があります。この機能を使用すると、TCP 接続内の各要求が個々に負荷分散されます。モバイル デバイスを展開する場合、HLB のベンダーが同じ機能をサポートしていることを確認してください。最新の iOS モバイル アプリでは、TLS バージョン 1.2 が必要です。より詳細な情報が必要な場合は、F5 が、その固有の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f071-p121">F5 HLBs have a feature called OneConnect. It ensures that each request within a TCP connection is individually load balanced. If you're deploying mobile devices, ensure your HLB vendor supports the same functionality. The latest iOS mobile apps require TLS version 1.2. If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="7f071-221">以下に、(オプション) ディレクターと (必須) フロントエンドプール Web サービスの HLB 要件を示します。</span><span class="sxs-lookup"><span data-stu-id="7f071-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="7f071-222">内部の Web サービス Vip で、HLB 上に Source_addr persistence (内部ポート 80, 443) を設定します。</span><span class="sxs-lookup"><span data-stu-id="7f071-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="7f071-223">Skype for Business Server の場合、Source_addr persistence は、1つの IP アドレスからの複数の接続が常に1つのサーバーに送信され、セッションの状態を維持することを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f071-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="7f071-224">TCP アイドル タイムアウト 1800 秒を使用すること。</span><span class="sxs-lookup"><span data-stu-id="7f071-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="7f071-225">リバースプロキシと次ホッププールの HLB の間のファイアウォールで、https: ポート4443上のトラフィックを許可するルールを、リバースプロキシから HLB まで作成します。</span><span class="sxs-lookup"><span data-stu-id="7f071-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="7f071-226">ポート 80、443、および 4443 をリッスンするように HLB を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="7f071-227">HLB のアフィニティ要件の概要</span><span class="sxs-lookup"><span data-stu-id="7f071-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="7f071-228">**クライアント/ユーザーの場所**</span><span class="sxs-lookup"><span data-stu-id="7f071-228">**Client/user location**</span></span>|<span data-ttu-id="7f071-229">**外部 Web サービスの FQDN のアフィニティ要件**</span><span class="sxs-lookup"><span data-stu-id="7f071-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="7f071-230">**内部 Web サービスの FQDN のアフィニティ要件**</span><span class="sxs-lookup"><span data-stu-id="7f071-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7f071-231">Skype for Business Web App (内部と外部のユーザー)</span><span class="sxs-lookup"><span data-stu-id="7f071-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="7f071-232">モバイル デバイス (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="7f071-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="7f071-233">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="7f071-233">No affinity</span></span>  <br/> |<span data-ttu-id="7f071-234">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="7f071-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="7f071-235">Skype for Business Web App (外部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="7f071-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="7f071-236">モバイル デバイス (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="7f071-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="7f071-237">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="7f071-237">No affinity</span></span>  <br/> |<span data-ttu-id="7f071-238">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="7f071-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="7f071-239">Skype for Business Web App (内部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="7f071-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="7f071-240">モバイル デバイス (展開しない)</span><span class="sxs-lookup"><span data-stu-id="7f071-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="7f071-241">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="7f071-241">No affinity</span></span>  <br/> |<span data-ttu-id="7f071-242">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="7f071-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="7f071-243">HLB のポート監視</span><span class="sxs-lookup"><span data-stu-id="7f071-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="7f071-244">ハードウェアまたは通信の障害のため、ハードウェアロードバランサーでポート監視を定義して、特定のサービスが使用できなくなったタイミングを判断します。</span><span class="sxs-lookup"><span data-stu-id="7f071-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="7f071-245">たとえば、フロントエンドサーバーまたはフロントエンドプールに障害が発生したために、フロントエンドサーバーサービス (RTCSRV) が停止した場合、HLB の監視でも Web サービスのトラフィックの受信を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="7f071-246">HLB の外部インターフェイスに関する以下の部分を監視する目的で、HLB にポート監視を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f071-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="7f071-247">**仮想 IP/ポート**</span><span class="sxs-lookup"><span data-stu-id="7f071-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="7f071-248">**ノード ポート**</span><span class="sxs-lookup"><span data-stu-id="7f071-248">**Node Port**</span></span>|<span data-ttu-id="7f071-249">**ノード コンピューター/モニター**</span><span class="sxs-lookup"><span data-stu-id="7f071-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="7f071-250">**保存プロファイル**</span><span class="sxs-lookup"><span data-stu-id="7f071-250">**Persistence Profile**</span></span>|<span data-ttu-id="7f071-251">**メモ**</span><span class="sxs-lookup"><span data-stu-id="7f071-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7f071-252">\<プール\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="7f071-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="7f071-253">443</span><span class="sxs-lookup"><span data-stu-id="7f071-253">443</span></span>  <br/> |<span data-ttu-id="7f071-254">4443</span><span class="sxs-lookup"><span data-stu-id="7f071-254">4443</span></span>  <br/> |<span data-ttu-id="7f071-255">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="7f071-255">Front End</span></span>  <br/> <span data-ttu-id="7f071-256">5061</span><span class="sxs-lookup"><span data-stu-id="7f071-256">5061</span></span>  <br/> |<span data-ttu-id="7f071-257">なし</span><span class="sxs-lookup"><span data-stu-id="7f071-257">None</span></span>  <br/> |<span data-ttu-id="7f071-258">HTTPS</span><span class="sxs-lookup"><span data-stu-id="7f071-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="7f071-259">\<プール\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="7f071-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="7f071-260">80</span><span class="sxs-lookup"><span data-stu-id="7f071-260">80</span></span>  <br/> |<span data-ttu-id="7f071-261">8080</span><span class="sxs-lookup"><span data-stu-id="7f071-261">8080</span></span>  <br/> |<span data-ttu-id="7f071-262">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="7f071-262">Front End</span></span>  <br/> <span data-ttu-id="7f071-263">5061</span><span class="sxs-lookup"><span data-stu-id="7f071-263">5061</span></span>  <br/> |<span data-ttu-id="7f071-264">なし</span><span class="sxs-lookup"><span data-stu-id="7f071-264">None</span></span>  <br/> |<span data-ttu-id="7f071-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="7f071-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="7f071-266">ハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="7f071-266">Hardware and software requirements</span></span>

<span data-ttu-id="7f071-267">Skype for business [server 2015 の全体的なサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)および[Skype for business server 2019 ドキュメントのシステム要件](../../../SfBServer2019/plan/system-requirements.md)については、「エッジサーバーのハードウェアとソフトウェアの要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f071-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="7f071-268">併置</span><span class="sxs-lookup"><span data-stu-id="7f071-268">Collocation</span></span>

<span data-ttu-id="7f071-269">[Skype For Business Server ドキュメントのトポロジの基礎](../../plan-your-deployment/topology-basics/topology-basics.md)として、Edge server collocation について説明しました。</span><span class="sxs-lookup"><span data-stu-id="7f071-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

