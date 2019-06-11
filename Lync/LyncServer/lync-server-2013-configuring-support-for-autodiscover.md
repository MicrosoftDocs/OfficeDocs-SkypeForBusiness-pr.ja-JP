---
title: 'Lync Server 2013: 自動検出のサポートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb83156d319db96a4c6ed79768193a24e5cc3e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="8bfb2-102">Lync Server 2013 での自動検出のサポートの構成</span><span class="sxs-lookup"><span data-stu-id="8bfb2-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bfb2-103">_**最終更新日:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="8bfb2-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="8bfb2-104">Lync Server web services**自動検出サービス**は、lync Server 2010 累積更新プログラム: 2011 年11月に最初に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="8bfb2-105">この更新プログラムには、Lync モバイルクライアントの最初のリリースが付随しています。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="8bfb2-106">自動検出サービスは、Mcx サービスと呼ばれるモバイルサービスを公開しています。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="8bfb2-107">自動検出サービスは、すべてのクライアントが利用可能なサービスや機能に関する情報を要求するための1つの場所として機能します。また、完全修飾ドメイン名または web の uri 参照によって、sevices いるリソースに連絡する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="8bfb2-108">自動検出はいくつかの機能を公開します。各クライアントは、クライアントが使用できる機能に基づいて要求を行います。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="8bfb2-109">たとえば、デスクトップ Lync 2013 クライアントでは、autodiscvoer を使って外部 web サービスを決定しますが、モビリティ (Mcx) サービスは使用しません。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="8bfb2-110">クライアントが利用可能な機能を使用できるように正しく定義して有効にするには、クライアントが自動検出エントリを効果的に検索して使用できるようにするシナリオを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="8bfb2-111">Autodoscover を使用するには、リバースプロキシによって Lync Server web サービスが公開されている必要があります。 DNS レコードは、Lync Server 自動検出サービスと Lync Server web サービスの DNS クエリを解決するように構成されており、その証明書サービスは、特定のシナリオに合わせて適切に構成されています。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8bfb2-112">自動検出要求/応答の要素の詳細については、「 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013 での自動検出の概要</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8bfb2-113">次の情報と表では、自動検出サービスを最大限に活用するために実装する必要がある構成 (存在する場合) について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="8bfb2-114">次のトピックの情報は、Microsoft Lync Server 2013 に固有の情報です。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="8bfb2-115">Lync Server 2010 のモビリティを計画する方法のガイダンスについては、「 [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bfb2-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="8bfb2-116">Lync Server 2010 のモバイル機能を導入するには、[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="8bfb2-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8bfb2-117">このセクション中</span><span class="sxs-lookup"><span data-stu-id="8bfb2-117">In This Section</span></span>

  - [<span data-ttu-id="8bfb2-118">Lync Server 2013 での自動検出用の DNS の構成</span><span class="sxs-lookup"><span data-stu-id="8bfb2-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="8bfb2-119">Lync Server 2013 で自動検出用の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="8bfb2-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="8bfb2-120">Lync Server 2013 での自動検出用のリバースプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="8bfb2-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="8bfb2-121">ハイブリッド展開用の Lync Server 2013 での自動検出の構成</span><span class="sxs-lookup"><span data-stu-id="8bfb2-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

