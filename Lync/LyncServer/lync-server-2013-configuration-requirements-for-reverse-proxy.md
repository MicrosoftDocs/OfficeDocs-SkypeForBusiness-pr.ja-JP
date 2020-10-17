---
title: 'Lync Server 2013: リバースプロキシの構成要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 555169f6de67ae23bc63d81aad549b0033a6696c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507744"
---
# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="2c3ac-102">Lync Server 2013 でのリバースプロキシの構成要件</span><span class="sxs-lookup"><span data-stu-id="2c3ac-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c3ac-103">_**トピックの最終更新日:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="2c3ac-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="2c3ac-104">Lync Server 2013 は、ディレクター、ディレクタープール、フロントエンドサーバー、またはフロントエンドプールでホストされている外部 Web サービスに渡される、外部クライアントからの通信に関していくつかの要件を課しています。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="2c3ac-105">また、リバースプロキシは、ユーザーに電話会議を提供している場合は、Office Web Apps サーバーを公開する役割も担います。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c3ac-106">Lync Server 2013 では、使用する必要がある特定のリバースプロキシが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="2c3ac-107">Lync Server 2013 では、リバースプロキシが実行できる運用要件のみが定義されています。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="2c3ac-108">通常、インフラストラクチャに既に展開されているリバースプロキシが要件を満たすことができる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="2c3ac-109">リバース プロキシの要件</span><span class="sxs-lookup"><span data-stu-id="2c3ac-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="2c3ac-110">Lync Server 2013 によって実行されるリバースプロキシが必要とする機能の操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="2c3ac-111">Secure socket layer (SSL) とトランスポート層セキュリティ (TLS) を使用します。これは、パブリック証明機関から取得した証明書を使用して、ディレクター、ディレクタープール、フロントエンドサーバー、またはフロントエンドプールの公開された外部 Web サービスに接続することによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="2c3ac-112">ディレクターおよびフロントエンドサーバーは、ハードウェアロードバランサーを使用して負荷分散されたプールに配置できます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="2c3ac-113">暗号化用の証明書を使用して内部 Web サイトを公開するか、必要に応じて暗号化されていない方法で公開することができます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="2c3ac-114">完全修飾ドメイン名 (FQDN) を使用して、内部でホストされている web サイトを外部に公開できます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="2c3ac-115">ホストされている web サイトのすべてのコンテンツを公開できます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="2c3ac-116">既定では、 **/\*** ほとんどの web サーバーで認識されるディレクティブを使用して、"web サーバー上のすべてのコンテンツを公開" という意味を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="2c3ac-117">また、ディレクティブ ( \*\*/Uwca/ \* \*\*など) を変更することもできます。これは、「仮想ディレクトリの下にあるすべてのコンテンツを公開する」という意味です。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="2c3ac-118">公開された web サイトのコンテンツを要求するクライアントとの Secure Sockets Layer (SSL) またはトランスポート層セキュリティ (TLS) 接続が必要な場合は、構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="2c3ac-119">サブジェクトの別名 (SAN) エントリで証明書を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="2c3ac-120">外部 web サービスの FQDN が解決されるリスナーまたはインターフェイスに証明書のバインドを許可できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="2c3ac-121">リスナー構成は、インターフェイスに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="2c3ac-122">多くのリスナーは、1つのインターフェイスで構成できます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="2c3ac-123">ホストヘッダー処理の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="2c3ac-124">多くの場合、要求元のクライアントによって送信される元のホストヘッダーは、リバースプロキシによって変更されるのではなく、透過的に渡される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="2c3ac-125">外部で定義された1つのポート (たとえば、tcp 443) から別の定義済みポート (たとえば、TCP 4443) への SSL および TLS トラフィックのブリッジ。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="2c3ac-126">リバースプロキシは、受信時にパケットの暗号化を解除し、送信時にパケットを再度暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="2c3ac-127">1つのポート (たとえば、tcp 80) から別のポート (たとえば、TCP 8080) への暗号化されていない TCP トラフィックのブリッジ。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="2c3ac-128">NTLM 認証の構成を許可するか、認証を行わずに認証を行い、パススルー認証を許可します。</span><span class="sxs-lookup"><span data-stu-id="2c3ac-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

