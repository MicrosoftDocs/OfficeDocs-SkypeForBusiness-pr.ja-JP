---
title: 'Lync Server 2013: IP 電話のトポロジ'
description: 'Lync Server 2013: IP 電話のトポロジ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a151a83a69e1f7e14dcbed8d8ab1038157fa839
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549133"
---
# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="2897d-103">Lync Server 2013 での IP 電話のトポロジ</span><span class="sxs-lookup"><span data-stu-id="2897d-103">Topologies for IP phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2897d-104">_**トピックの最終更新日:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="2897d-104">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="2897d-105">ここでは、接続プロセスの概要を示し、内部ネットワークと外部ネットワークでの IP 電話の接続方法の違いを説明します。</span><span class="sxs-lookup"><span data-stu-id="2897d-105">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2897d-106">Lync Server は、次の IP 電話のサポートを提供します。 Aastra 6721ip 共通領域電話、Aastra 6721ip 卓上電話、HP 4110 IP 電話 (共通領域電話)、HP 4120 IP 電話 (卓上電話)、Polycom CX600 IP デスク電話、Polycom CX700 IP 卓上電話、Polycom CX500 IP 共通領域電話、Polycom CX3000 IP 電話会議電話。</span><span class="sxs-lookup"><span data-stu-id="2897d-106">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="2897d-107">これらの電話の場合、Polycom CX700 以外はすべて Lync Phone Edition を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2897d-107">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="2897d-108">次の図では、企業環境内でのデバイス接続に関係するすべてのコンポーネントを説明します。</span><span class="sxs-lookup"><span data-stu-id="2897d-108">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="2897d-109">**内部トポロジ**</span><span class="sxs-lookup"><span data-stu-id="2897d-109">**Internal Topology**</span></span>

<span data-ttu-id="2897d-110">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="2897d-110">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2897d-111">前の図は論理的な表現であり、物理的な概要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2897d-111">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="2897d-112">たとえば、Active Directory ドメインサービス (AD DS) は、ほとんどの場合、すべての Lync Server コンポーネントと同じコンピューターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="2897d-112">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="2897d-113">ユーザー ストアは、バックエンド サーバー上、またはアーカイブ サーバーおよび監視サーバー上に配置できます。</span><span class="sxs-lookup"><span data-stu-id="2897d-113">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="2897d-114">Lync Server 管理シェル、web サーバー、更新サービスは、すべてフロントエンドサーバーの役割の一部です。</span><span class="sxs-lookup"><span data-stu-id="2897d-114">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="2897d-115">次の図では、デバイスが企業ネットワークの外部に配置される場合に関係するコンポーネントの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="2897d-115">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="2897d-116">**外部トポロジ**</span><span class="sxs-lookup"><span data-stu-id="2897d-116">**External Topology**</span></span>

<span data-ttu-id="2897d-117">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="2897d-117">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2897d-118">デバイス更新 Web サービスは、外部および内部の Web サイトを提供しますが、ここでは外部の Web サイトだけを示しています。</span><span class="sxs-lookup"><span data-stu-id="2897d-118">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="2897d-p103">外部アクセスを有効にする場合は、レジストラーの場所、および組織に対するデバイス更新 Web サービスの URL を DNS で公開する必要があります。さらに、エッジ サーバーを展開し、デバイスと企業環境の間の双方向の外部通信を許可するように適切に構成する必要があります。エッジの展開がデバイスの接続に固有ではないので、前の図ではこれは省略されています。</span><span class="sxs-lookup"><span data-stu-id="2897d-p103">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled. Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back. This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

