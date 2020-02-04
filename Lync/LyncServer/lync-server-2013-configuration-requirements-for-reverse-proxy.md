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
ms.openlocfilehash: 37a2a535ddaa90efa2f4140236b52788fa58e41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="fb83c-102">Lync Server 2013 でのリバースプロキシの構成要件</span><span class="sxs-lookup"><span data-stu-id="fb83c-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb83c-103">_**最終更新日:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="fb83c-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="fb83c-104">Lync Server 2013 は、ディレクター、ディレクタープール、フロントエンドサーバー、フロントエンドプールでホストされる外部の Web サービスに渡される外部クライアントからの通信について、いくつかの要件を課しています。</span><span class="sxs-lookup"><span data-stu-id="fb83c-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="fb83c-105">リバースプロキシは、ユーザーに会議を提供している場合は、Office Web Apps サーバーを公開する責任も担います。</span><span class="sxs-lookup"><span data-stu-id="fb83c-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb83c-106">Lync Server 2013 は、使用する必要がある特定のリバースプロキシを指定していません。</span><span class="sxs-lookup"><span data-stu-id="fb83c-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="fb83c-107">Lync Server 2013 では、リバースプロキシが実行できる運用要件のみが定義されています。</span><span class="sxs-lookup"><span data-stu-id="fb83c-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="fb83c-108">通常、インフラストラクチャに既に展開されている逆プロキシは、要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="fb83c-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="fb83c-109">プロキシのリバース要件</span><span class="sxs-lookup"><span data-stu-id="fb83c-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="fb83c-110">Lync Server 2013 がリバースプロキシを実行することを期待する機能操作は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fb83c-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="fb83c-111">セキュリティで保護されたソケットレイヤー (SSL) とトランスポート層セキュリティ (TLS) を使用するには、パブリック証明機関から取得した証明書を使用して、ディレクター、ディレクタープール、フロントエンドサーバー、またはフロントエンドプールの公開された外部 Web サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="fb83c-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="fb83c-112">ディレクターとフロントエンドサーバーは、ハードウェアロードバランサーを使って、負荷分散プールに存在することができます。</span><span class="sxs-lookup"><span data-stu-id="fb83c-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="fb83c-113">暗号化用の証明書を使って内部 Web サイトを公開したり、必要に応じて暗号化されていない方法で公開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb83c-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="fb83c-114">完全修飾ドメイン名 (FQDN) を使用して、内部でホストされた web サイトを外部で公開することができます。</span><span class="sxs-lookup"><span data-stu-id="fb83c-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="fb83c-115">ホストされている web サイトのすべてのコンテンツを公開できます。</span><span class="sxs-lookup"><span data-stu-id="fb83c-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="fb83c-116">既定では、ほとんどの web \*\* / \*\*サーバーによって認識されるディレクティブを使用できます。これは、web サーバー上のすべてのコンテンツを公開することを意味します。</span><span class="sxs-lookup"><span data-stu-id="fb83c-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="fb83c-117">また、ディレクティブ (たとえば、 **/Uwca/\*** など) を変更することもできます。これは、「仮想ディレクトリのすべてのコンテンツを公開する」という意味です。</span><span class="sxs-lookup"><span data-stu-id="fb83c-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="fb83c-118">公開された web サイトのコンテンツを要求するクライアントとの Secure Sockets Layer (SSL) またはトランスポートレイヤーセキュリティ (TLS) 接続を要求するように構成できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb83c-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="fb83c-119">サブジェクトの代替名 (SAN) エントリを含む証明書を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb83c-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="fb83c-120">外部 web サービスの FQDN で解決されるリスナーまたはインターフェイスへの証明書のバインドを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb83c-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="fb83c-121">インターフェイスの構成よりリスナーの構成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fb83c-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="fb83c-122">多くのリスナーは、単一のインターフェイスで構成できます。</span><span class="sxs-lookup"><span data-stu-id="fb83c-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="fb83c-123">ホストヘッダー処理の構成が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb83c-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="fb83c-124">通常、要求側のクライアントによって送信された元のホストヘッダーは、リバースプロキシによって変更されるのではなく、透過的に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb83c-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="fb83c-125">外部定義のポート (たとえば、TCP 443) から別の定義済みポート (TCP 4443 など) への SSL および TLS トラフィックのブリッジ。</span><span class="sxs-lookup"><span data-stu-id="fb83c-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="fb83c-126">リバースプロキシは、受信時にパケットの暗号化を解除し、送信時にパケットを再度暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="fb83c-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="fb83c-127">1つのポート (たとえば、TCP 80) から別のポート (TCP 8080 など) への暗号化されていない TCP トラフィックのブリッジ。</span><span class="sxs-lookup"><span data-stu-id="fb83c-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="fb83c-128">NTLM 認証、認証、パススルー認証を許可しません。</span><span class="sxs-lookup"><span data-stu-id="fb83c-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

