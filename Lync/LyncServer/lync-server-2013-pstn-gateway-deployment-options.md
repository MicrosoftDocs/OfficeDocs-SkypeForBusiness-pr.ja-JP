---
title: 'Lync Server 2013: PSTN ゲートウェイの展開オプション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137c9996429e953db22bea0c0dbd382f5a7af9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="64c79-102">Lync Server 2013 の PSTN ゲートウェイの展開オプション</span><span class="sxs-lookup"><span data-stu-id="64c79-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64c79-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="64c79-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="64c79-104">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="64c79-104">PSTN Gateways</span></span>

<span data-ttu-id="64c79-105">公衆交換電話網 (PSTN) ゲートウェイは、エンタープライズボイスインフラストラクチャと PSTN との間で、または SIP trunks への接続を介して、信号とメディアを変換するサードパーティ製のハードウェアコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="64c79-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="64c79-106">どちらのトポロジでも、ゲートウェイは PSTN を終了します。</span><span class="sxs-lookup"><span data-stu-id="64c79-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="64c79-107">ゲートウェイは専用のサブネットで分離され、仲介サーバー経由で企業ネットワークに接続されます。</span><span class="sxs-lookup"><span data-stu-id="64c79-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="64c79-108">通常、複数のサイトを持つ企業は、各サイトに1つ以上のゲートウェイを展開します。</span><span class="sxs-lookup"><span data-stu-id="64c79-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="64c79-109">ブランチサイトは、ゲートウェイまたは Survivable ブランチアプライアンス経由で PSTN に接続できます。これにより、ゲートウェイとサーバーが1つのボックスに結合されます。</span><span class="sxs-lookup"><span data-stu-id="64c79-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="64c79-110">ブランチサイトにゲートウェイが使用されている場合は、WAN リンクが回復できる場合を除き、レジストラーと仲介サーバーの両方がサイトで必要になります。</span><span class="sxs-lookup"><span data-stu-id="64c79-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="64c79-111">フロントエンドサーバーに併置されている1つ以上の仲介サーバーは、各サイトの1つ以上のゲートウェイへの通話をルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="64c79-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="64c79-112">サイトで必要とされるレジストラー、仲介サーバー、ゲートウェイは、Survivable Branch Appliance として展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64c79-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="64c79-113">PSTN ゲートウェイの数、サイズ、および場所を決定することは、多くの場合、エンタープライズ Voip インフラストラクチャを計画するときに行う必要がある最も重要であり、コストが高いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="64c79-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="64c79-114">次に、考慮すべき主な質問を示します。</span><span class="sxs-lookup"><span data-stu-id="64c79-114">Here are the main questions to consider.</span></span> <span data-ttu-id="64c79-115">これらの質問に対する回答はすべて相互に依存していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="64c79-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="64c79-116">必要な PSTN ゲートウェイはいくつですか?</span><span class="sxs-lookup"><span data-stu-id="64c79-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="64c79-117">この答えは、ユーザーの数、同時呼び出しの予想数 (トラフィックの負荷)、およびサイトの数によって異なります (各サイトには1つ必要です)。</span><span class="sxs-lookup"><span data-stu-id="64c79-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="64c79-118">ゲートウェイのサイズを指定してください。</span><span class="sxs-lookup"><span data-stu-id="64c79-118">What size should the gateways be?</span></span> <span data-ttu-id="64c79-119">この答えは、サイトのユーザー数とトラフィック負荷によって異なります。</span><span class="sxs-lookup"><span data-stu-id="64c79-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="64c79-120">ゲートウェイはどこに配置されますか?</span><span class="sxs-lookup"><span data-stu-id="64c79-120">Where should the gateways be located?</span></span> <span data-ttu-id="64c79-121">この回答は、トポロジの一部と、組織の地理的分布の一部によって異なります。</span><span class="sxs-lookup"><span data-stu-id="64c79-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="64c79-122">ゲートウェイのトポロジオプションについても考慮する必要があります (詳しくは、このトピックで後述する「ゲートウェイトポロジ」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="64c79-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="64c79-123">M:N トランクのサポート</span><span class="sxs-lookup"><span data-stu-id="64c79-123">M:N Trunk Support</span></span>

<span data-ttu-id="64c79-124">仲介サーバーは、複数のゲートウェイ、インターネットテレフォニーサービスプロバイダーによって提供されるセッション境界コントローラー (SBCs)、またはこの2つの組み合わせを経由して通話をルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="64c79-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="64c79-125">さらに、プール内の複数の仲介サーバーは、複数のゲートウェイとやり取りできます。</span><span class="sxs-lookup"><span data-stu-id="64c79-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="64c79-126">仲介サーバーとゲートウェイの間で定義される論理ルートは*トランク*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="64c79-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="64c79-127">内部ユーザーが PSTN 通話を発信すると、フロントエンドプールの送信ルーティングロジックによって、特定の呼び出しをルーティングするために利用可能なすべての組み合わせからルーティングされるトランクが選択されます。</span><span class="sxs-lookup"><span data-stu-id="64c79-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="64c79-128">DNS の負荷分散によって、プール内の特定の仲介サーバーに問題が発生したために、通話がゲートウェイに到達しなかった場合、その呼び出しはプール内の別の仲介サーバーに再試行されます。</span><span class="sxs-lookup"><span data-stu-id="64c79-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="64c79-129">複数のゲートウェイの計画の詳細については、「 [Lync Server 2013 の M:N トランク](lync-server-2013-m-n-trunk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c79-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="64c79-130">その他の送信ルーティングの拡張機能の詳細については、「 [Lync Server 2013 の音声ルート](lync-server-2013-voice-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c79-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="64c79-131">ゲートウェイトポロジ</span><span class="sxs-lookup"><span data-stu-id="64c79-131">Gateway Topologies</span></span>

<span data-ttu-id="64c79-132">ゲートウェイ展開の基本的な質問については、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64c79-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="64c79-133">エンタープライズ Voip を使用して、PSTN 接続を提供するサイトの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="64c79-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="64c79-134">各サイトのトラフィック (ユーザー数と1時間あたりの平均通話回数) を見積もります。</span><span class="sxs-lookup"><span data-stu-id="64c79-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="64c79-135">各サイトに1つ以上のゲートウェイを展開して、予想されるトラフィックを処理します。</span><span class="sxs-lookup"><span data-stu-id="64c79-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="64c79-136">次の図に、このような分散型ゲートウェイのトポロジを示します。</span><span class="sxs-lookup"><span data-stu-id="64c79-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="64c79-137">**分散ゲートウェイトポロジ**</span><span class="sxs-lookup"><span data-stu-id="64c79-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="64c79-138">![分散ゲートウェイトポロジの図](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "分散ゲートウェイトポロジの図")</span><span class="sxs-lookup"><span data-stu-id="64c79-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="64c79-139">このトポロジを使用すると、各サイトの従業員とサイト間の通話はすべて、イントラネット経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="64c79-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="64c79-140">PSTN への通話は、送信先の番号の場所に最も近いゲートウェイに、エンタープライズ IP ネットワーク経由でルーティングされます。ただし、組織が1つまたは複数の大陸に分散している多数のサイトをサポートしている場合、多くの金融機関やその他の大企業の場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="64c79-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="64c79-141">このような場合は、各サイトに個別のゲートウェイを展開することは現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="64c79-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="64c79-142">この問題に対処するために、多くの大企業は、次の図に示すように、1つまたは複数の大規模なテレフォニーセントラルサイトを展開することを希望しています。</span><span class="sxs-lookup"><span data-stu-id="64c79-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="64c79-143">**テレフォニーセントラルサイトトポロジ**</span><span class="sxs-lookup"><span data-stu-id="64c79-143">**Telephony central site topology**</span></span>

<span data-ttu-id="64c79-144">![Data center ゲートウェイのトポロジ](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center ゲートウェイのトポロジ")</span><span class="sxs-lookup"><span data-stu-id="64c79-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="64c79-145">このトポロジでは、予想されるユーザーロードに対応するために十分な数の大きなゲートウェイがセントラルサイトに展開されます。</span><span class="sxs-lookup"><span data-stu-id="64c79-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="64c79-146">企業内のユーザーへのすべての通話は、会社の電話サービスプロバイダによって中央サイトに転送されます。</span><span class="sxs-lookup"><span data-stu-id="64c79-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="64c79-147">セントラルサイトのルーティングロジックは、通話がイントラネット上または PSTN 上にルーティングされるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="64c79-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="64c79-148">ゲートウェイの場所</span><span class="sxs-lookup"><span data-stu-id="64c79-148">Gateway Location</span></span>

<span data-ttu-id="64c79-149">ゲートウェイの場所では、選択したゲートウェイの種類とその構成方法も決定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="64c79-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="64c79-150">さまざまな PSTN プロトコルがあります。いずれも世界標準ではありません。</span><span class="sxs-lookup"><span data-stu-id="64c79-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="64c79-151">すべてのゲートウェイが1つの国/地域に配置されている場合、これは問題ではありませんが、複数の国/地域でゲートウェイを指定する場合は、それぞれの国/地域の PSTN 標準に従って構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c79-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="64c79-152">さらに、カナダなどで操作が認められているゲートウェイは、インド、ブラジル、または欧州連合で認定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64c79-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="64c79-153">ゲートウェイのサイズと番号</span><span class="sxs-lookup"><span data-stu-id="64c79-153">Gateway Size and Number</span></span>

<span data-ttu-id="64c79-154">ほとんどの組織では、サイズが2から最大960ポートまでの範囲の展開を検討しています。</span><span class="sxs-lookup"><span data-stu-id="64c79-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="64c79-155">(大規模なゲートウェイもありますが、主に電話サービスプロバイダーによって使用されます)。組織で必要なポートの数を見積もるときは、次のガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="64c79-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="64c79-156">電話の使用量が少ない組織 (1 時間あたりの PSTN 通話1つ) は、15ユーザーごとに1つのポートを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c79-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="64c79-157">たとえば、ユーザーが20人いる場合は、2つのポートを持つゲートウェイが必要になります。</span><span class="sxs-lookup"><span data-stu-id="64c79-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="64c79-158">中程度のテレフォニー (1 時間あたりの2つの PSTN 通話) が使用されている組織では、10ユーザーごとに1つのポートを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c79-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="64c79-159">たとえば、100ユーザーがいる場合は、1つ以上のゲートウェイの間に合計10個のポートを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c79-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="64c79-160">テレフォニー使用量が多い組織 (1 時間あたりのユーザーあたりの PSTN 通話3つ以上) では、5人ごとに1つのポートを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c79-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="64c79-161">たとえば、47000ユーザーがいる場合、少なくとも10個の大規模なゲートウェイの間に割り当てられた9400ポートの合計が必要になります。</span><span class="sxs-lookup"><span data-stu-id="64c79-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="64c79-162">組織内のユーザー数またはトラフィック量の増加に応じて、追加のポートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="64c79-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="64c79-163">指定したユーザーの数についてサポートが必要な場合は、少なくとも大きいゲートウェイを展開するか、それより小さいものを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="64c79-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="64c79-164">1つのゲートウェイに障害が発生した場合は、1つの組織に対して少なくとも2つのゲートウェイを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64c79-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="64c79-165">展開する各 PSTN ゲートウェイには、少なくとも1つの対応する仲介サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="64c79-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

