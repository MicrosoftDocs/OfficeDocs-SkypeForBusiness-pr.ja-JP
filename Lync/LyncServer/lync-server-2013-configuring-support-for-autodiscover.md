---
title: 'Lync Server 2013: 自動検出のサポートの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee85d984f0d60d4275972982e4ff65b380f0f9b2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="37ea4-102">Lync Server 2013 での自動検出のサポートの構成</span><span class="sxs-lookup"><span data-stu-id="37ea4-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37ea4-103">_**トピックの最終更新日:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="37ea4-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="37ea4-104">Lync Server web services**自動検出サービス**は、lync server 2010 の累積更新プログラム:11 月2011に最初に表示されていました。</span><span class="sxs-lookup"><span data-stu-id="37ea4-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="37ea4-105">この更新プログラムには、Lync Mobile クライアントの最初のリリースが付属していました。</span><span class="sxs-lookup"><span data-stu-id="37ea4-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="37ea4-106">自動検出サービスは、Mcx サービスと呼ばれるモビリティサービスを公開しています。</span><span class="sxs-lookup"><span data-stu-id="37ea4-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="37ea4-107">自動検出サービスは、すべてのクライアントが利用可能なサービスと機能に関する情報を要求するための単一の場所として機能します。また、完全修飾ドメイン名または web uniform resource locator reference によって、その連絡先に連絡する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="37ea4-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="37ea4-108">自動検出では多数の機能が公開されており、各クライアントはクライアントが使用できる機能に基づいて要求を行います。</span><span class="sxs-lookup"><span data-stu-id="37ea4-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="37ea4-109">たとえば、デスクトップ Lync 2013 クライアントは autodiscvoer を使用して外部 web サービスを決定しますが、mobility (Mcx) サービスは使用しません。</span><span class="sxs-lookup"><span data-stu-id="37ea4-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="37ea4-110">クライアントで使用可能な機能を使用できるように適切に定義して有効にするには、クライアントが自動検出エントリを効果的に検索して使用できるようにするシナリオを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ea4-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="37ea4-111">Autodoscover を使用するには、リバースプロキシが Lync Server web サービスを公開する必要があります。この DNS レコードは、Lync Server 自動検出サービスおよび Lync Server web サービスの DNS クエリを解決するように構成されており、その証明書サービス特定のシナリオに対して適切に構成されている。</span><span class="sxs-lookup"><span data-stu-id="37ea4-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="37ea4-112">自動検出要求/応答に含まれる要素の技術的な詳細については、「 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013 の自動検出につい</A>て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37ea4-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="37ea4-113">次の情報と表は、シナリオごとに、自動検出サービスを完全かつ効果的に使用するために実装する必要がある構成 (存在する場合) を定義しています。</span><span class="sxs-lookup"><span data-stu-id="37ea4-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="37ea4-114">以下のトピックの情報は、Microsoft Lync Server 2013 に固有のものです。</span><span class="sxs-lookup"><span data-stu-id="37ea4-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="37ea4-115">Lync Server 2010 のモビリティを計画する方法のガイダンスについては、「 [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37ea4-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="37ea4-116">Lync Server 2010 のモビリティを展開するには、「」を参照してください。[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="37ea4-116">To deploy Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37ea4-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="37ea4-117">In This Section</span></span>

  - [<span data-ttu-id="37ea4-118">Lync Server 2013 での自動検出用の DNS の構成</span><span class="sxs-lookup"><span data-stu-id="37ea4-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="37ea4-119">Lync Server 2013 での自動検出用の証明書の構成</span><span class="sxs-lookup"><span data-stu-id="37ea4-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="37ea4-120">Lync Server 2013 での自動検出のリバースプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="37ea4-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="37ea4-121">Lync Server 2013 でのハイブリッド展開の自動検出の構成</span><span class="sxs-lookup"><span data-stu-id="37ea4-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

