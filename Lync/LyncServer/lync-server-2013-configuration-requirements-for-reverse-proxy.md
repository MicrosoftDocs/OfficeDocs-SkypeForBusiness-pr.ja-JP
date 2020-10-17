---
title: 'Lync Server 2013: リバースプロキシの構成要件'
description: 'Lync Server 2013: リバースプロキシの構成要件。'
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
ms.openlocfilehash: 75f3f5b9437ba4518e3feffc193853b446b702d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552143"
---
# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="efab2-103">Lync Server 2013 でのリバースプロキシの構成要件</span><span class="sxs-lookup"><span data-stu-id="efab2-103">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efab2-104">_**トピックの最終更新日:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="efab2-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="efab2-105">Lync Server 2013 は、ディレクター、ディレクタープール、フロントエンドサーバー、またはフロントエンドプールでホストされている外部 Web サービスに渡される、外部クライアントからの通信に関していくつかの要件を課しています。</span><span class="sxs-lookup"><span data-stu-id="efab2-105">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="efab2-106">また、リバースプロキシは、ユーザーに電話会議を提供している場合は、Office Web Apps サーバーを公開する役割も担います。</span><span class="sxs-lookup"><span data-stu-id="efab2-106">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="efab2-107">Lync Server 2013 では、使用する必要がある特定のリバースプロキシが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="efab2-107">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="efab2-108">Lync Server 2013 では、リバースプロキシが実行できる運用要件のみが定義されています。</span><span class="sxs-lookup"><span data-stu-id="efab2-108">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="efab2-109">通常、インフラストラクチャに既に展開されているリバースプロキシが要件を満たすことができる場合があります。</span><span class="sxs-lookup"><span data-stu-id="efab2-109">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="efab2-110">リバース プロキシの要件</span><span class="sxs-lookup"><span data-stu-id="efab2-110">Reverse Proxy Requirements</span></span>

<span data-ttu-id="efab2-111">Lync Server 2013 によって実行されるリバースプロキシが必要とする機能の操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="efab2-111">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="efab2-112">Secure socket layer (SSL) とトランスポート層セキュリティ (TLS) を使用します。これは、パブリック証明機関から取得した証明書を使用して、ディレクター、ディレクタープール、フロントエンドサーバー、またはフロントエンドプールの公開された外部 Web サービスに接続することによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="efab2-112">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="efab2-113">ディレクターおよびフロントエンドサーバーは、ハードウェアロードバランサーを使用して負荷分散されたプールに配置できます。</span><span class="sxs-lookup"><span data-stu-id="efab2-113">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="efab2-114">暗号化用の証明書を使用して内部 Web サイトを公開するか、必要に応じて暗号化されていない方法で公開することができます。</span><span class="sxs-lookup"><span data-stu-id="efab2-114">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="efab2-115">完全修飾ドメイン名 (FQDN) を使用して、内部でホストされている web サイトを外部に公開できます。</span><span class="sxs-lookup"><span data-stu-id="efab2-115">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="efab2-116">ホストされている web サイトのすべてのコンテンツを公開できます。</span><span class="sxs-lookup"><span data-stu-id="efab2-116">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="efab2-117">既定では、 **/\*** ほとんどの web サーバーで認識されるディレクティブを使用して、"web サーバー上のすべてのコンテンツを公開" という意味を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="efab2-117">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="efab2-118">また、ディレクティブ ( \*\*/Uwca/ \* \*\*など) を変更することもできます。これは、「仮想ディレクトリの下にあるすべてのコンテンツを公開する」という意味です。</span><span class="sxs-lookup"><span data-stu-id="efab2-118">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="efab2-119">公開された web サイトのコンテンツを要求するクライアントとの Secure Sockets Layer (SSL) またはトランスポート層セキュリティ (TLS) 接続が必要な場合は、構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efab2-119">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="efab2-120">サブジェクトの別名 (SAN) エントリで証明書を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="efab2-120">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="efab2-121">外部 web サービスの FQDN が解決されるリスナーまたはインターフェイスに証明書のバインドを許可できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="efab2-121">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="efab2-122">リスナー構成は、インターフェイスに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="efab2-122">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="efab2-123">多くのリスナーは、1つのインターフェイスで構成できます。</span><span class="sxs-lookup"><span data-stu-id="efab2-123">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="efab2-124">ホストヘッダー処理の構成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efab2-124">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="efab2-125">多くの場合、要求元のクライアントによって送信される元のホストヘッダーは、リバースプロキシによって変更されるのではなく、透過的に渡される必要があります。</span><span class="sxs-lookup"><span data-stu-id="efab2-125">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="efab2-126">外部で定義された1つのポート (たとえば、tcp 443) から別の定義済みポート (たとえば、TCP 4443) への SSL および TLS トラフィックのブリッジ。</span><span class="sxs-lookup"><span data-stu-id="efab2-126">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="efab2-127">リバースプロキシは、受信時にパケットの暗号化を解除し、送信時にパケットを再度暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="efab2-127">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="efab2-128">1つのポート (たとえば、tcp 80) から別のポート (たとえば、TCP 8080) への暗号化されていない TCP トラフィックのブリッジ。</span><span class="sxs-lookup"><span data-stu-id="efab2-128">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="efab2-129">NTLM 認証の構成を許可するか、認証を行わずに認証を行い、パススルー認証を許可します。</span><span class="sxs-lookup"><span data-stu-id="efab2-129">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

