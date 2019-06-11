---
title: 'Lync Server 2013: IP 電話のトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3247783acb0f65fb069f418c4a66a4c53b1a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="c53d5-102">Lync Server 2013 の IP 電話のトポロジ</span><span class="sxs-lookup"><span data-stu-id="c53d5-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c53d5-103">_**最終更新日:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="c53d5-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="c53d5-104">このセクションでは、接続プロセスの概要について説明し、IP 電話が内部と外部のネットワークで接続する方法の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c53d5-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c53d5-105">Lync Server では、次の IP 電話のサポートが提供されます: Aastra 6721ip 共通エリアフォン、Aastra 6721ip 卓上電話、HP 4110 IP 電話 (共通エリア電話)、HP 4120 IP 電話 (卓上電話)、Polycom CX600 ip 卓上電話、Polycom CX700 ip 卓上電話、Polycom CX500 IP一般的なエリア電話と Polycom CX3000 IP 会議電話。</span><span class="sxs-lookup"><span data-stu-id="c53d5-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="c53d5-106">これらの携帯電話では、Polycom CX700 以外はすべて Lync Phone Edition を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c53d5-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="c53d5-107">次の図は、企業環境内のデバイス接続に関連するすべてのコンポーネントについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="c53d5-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="c53d5-108">**内部トポロジ**</span><span class="sxs-lookup"><span data-stu-id="c53d5-108">**Internal Topology**</span></span>

<span data-ttu-id="c53d5-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="c53d5-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c53d5-110">上の図は論理的な表現であり、物理的な概要ではありません。</span><span class="sxs-lookup"><span data-stu-id="c53d5-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="c53d5-111">たとえば、Active Directory ドメインサービス (AD DS) は、Lync Server コンポーネントと同じコンピューター上に存在することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="c53d5-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="c53d5-112">ユーザーストアはバックエンドサーバーまたはアーカイブおよび監視サーバー上に配置できます。</span><span class="sxs-lookup"><span data-stu-id="c53d5-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="c53d5-113">Lync Server 管理シェル、web サーバー、更新サービスはすべて、フロントエンドサーバーの役割の一部です。</span><span class="sxs-lookup"><span data-stu-id="c53d5-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="c53d5-114">次の図は、デバイスが企業ネットワークの外部にある場合に関連するコンポーネントの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="c53d5-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="c53d5-115">**外部トポロジ**</span><span class="sxs-lookup"><span data-stu-id="c53d5-115">**External Topology**</span></span>

<span data-ttu-id="c53d5-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="c53d5-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c53d5-117">デバイス更新 Web サービスでは、外部と内部の web サイトが提供されますが、外部の web サイトのみがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c53d5-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="c53d5-118">外部アクセスを有効にするには、レジストラーの場所と、組織のデバイス更新 Web サービスの URL が DNS に公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c53d5-118">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled.</span></span> <span data-ttu-id="c53d5-119">さらに、エッジサーバーを展開し、デバイスから企業環境への外部通信を許可するように適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c53d5-119">Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back.</span></span> <span data-ttu-id="c53d5-120">Edge の展開はデバイス接続に固有ではないため、前の図では省略します。</span><span class="sxs-lookup"><span data-stu-id="c53d5-120">This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

