---
title: 'Lync Server 2013: PSTN ゲートウェイの展開オプション'
description: 'Lync Server 2013: PSTN ゲートウェイの展開オプション。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871bc4d573e927f83cdb07d4fb2b5d5b954e6383
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565593"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="3a052-103">Lync Server 2013 の PSTN ゲートウェイの展開オプション</span><span class="sxs-lookup"><span data-stu-id="3a052-103">PSTN gateway deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a052-104">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3a052-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="3a052-105">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="3a052-105">PSTN Gateways</span></span>

<span data-ttu-id="3a052-106">公衆交換電話網 (PSTN) ゲートウェイは、エンタープライズ Voip インフラストラクチャと PSTN との間で、直接または SIP トランクへの接続によって、信号とメディアを変換するサードパーティ製のハードウェアコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="3a052-106">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="3a052-107">どちらのトポロジでも、ゲートウェイは PSTN を終了します。</span><span class="sxs-lookup"><span data-stu-id="3a052-107">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="3a052-108">ゲートウェイは独自のサブネット内で分離され、仲介サーバーを介してエンタープライズネットワークに接続されます。</span><span class="sxs-lookup"><span data-stu-id="3a052-108">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="3a052-109">複数のサイトがあるエンタープライズでは、通常、各サイトに1つ以上のゲートウェイを展開します。</span><span class="sxs-lookup"><span data-stu-id="3a052-109">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="3a052-110">ブランチサイトは、ゲートウェイまたは存続可能ブランチアプライアンスを介して PSTN に接続できます。これにより、ゲートウェイとサーバーが1つのボックスに統合されます。</span><span class="sxs-lookup"><span data-stu-id="3a052-110">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="3a052-111">ブランチサイトでゲートウェイを使用する場合、WAN リンクが回復可能でない限り、サイトにはレジストラーと仲介サーバーの両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="3a052-111">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="3a052-112">フロントエンドサーバーに併置されている1つ以上の仲介サーバーは、各サイトの1つ以上のゲートウェイに対して呼び出しをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="3a052-112">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="3a052-113">サイトで必要とされるレジストラー、仲介サーバー、およびゲートウェイは、存続可能ブランチアプライアンスとして展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a052-113">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="3a052-114">PSTN ゲートウェイの数、サイズ、および場所を決定することは、エンタープライズ Voip インフラストラクチャを計画するときに行う必要のある最も重要かつ費用の高い判断です。</span><span class="sxs-lookup"><span data-stu-id="3a052-114">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="3a052-115">考慮すべき主な質問を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a052-115">Here are the main questions to consider.</span></span> <span data-ttu-id="3a052-116">これらの質問に対する回答はすべて相互に依存していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3a052-116">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="3a052-117">必要な PSTN ゲートウェイの数</span><span class="sxs-lookup"><span data-stu-id="3a052-117">How many PSTN gateways are needed?</span></span> <span data-ttu-id="3a052-118">この答えは、ユーザーの数、予想される同時通話数 (トラフィック負荷)、およびサイト数 (各サイトで1つ必要) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3a052-118">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="3a052-119">ゲートウェイのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a052-119">What size should the gateways be?</span></span> <span data-ttu-id="3a052-120">この答えは、サイトのユーザー数とトラフィック負荷によって決まります。</span><span class="sxs-lookup"><span data-stu-id="3a052-120">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="3a052-121">ゲートウェイはどこに配置すればよいですか。</span><span class="sxs-lookup"><span data-stu-id="3a052-121">Where should the gateways be located?</span></span> <span data-ttu-id="3a052-122">この答えは、トポロジの一部と、組織の地理的な分散における一部に依存します。</span><span class="sxs-lookup"><span data-stu-id="3a052-122">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="3a052-123">また、ゲートウェイトポロジのオプションについても検討する必要があります (詳細については、このトピックで後述する「ゲートウェイトポロジ」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3a052-123">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="3a052-124">M:N トランクのサポート</span><span class="sxs-lookup"><span data-stu-id="3a052-124">M:N Trunk Support</span></span>

<span data-ttu-id="3a052-125">仲介サーバーは、複数のゲートウェイ、インターネットテレフォニーサービスプロバイダーから提供されたセッションボーダーコントローラー (sbc)、またはその2つの組み合わせを経由して通話をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="3a052-125">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="3a052-126">さらに、プール内の複数の仲介サーバーは、複数のゲートウェイと対話できます。</span><span class="sxs-lookup"><span data-stu-id="3a052-126">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="3a052-127">仲介サーバーとゲートウェイの間で定義される論理ルートは、 *トランク*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3a052-127">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="3a052-128">内部ユーザーが PSTN 通話を行うと、フロントエンドプールの送信ルーティングロジックによって、その特定の呼び出しについてルーティングに使用できるすべての可能な組み合わせから、どのトランクをルーティングするかが選択されます。</span><span class="sxs-lookup"><span data-stu-id="3a052-128">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="3a052-129">DNS 負荷分散では、プール内の特定の仲介サーバーに問題があるために、ゲートウェイへの通話が失敗した場合、その呼び出しはプール内の別の仲介サーバーに再試行されます。</span><span class="sxs-lookup"><span data-stu-id="3a052-129">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="3a052-130">複数ゲートウェイの計画の詳細については、「 [M:N トランク In Lync Server 2013](lync-server-2013-m-n-trunk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a052-130">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="3a052-131">その他の送信ルーティングの拡張機能の詳細については、「 [Lync Server 2013 の音声ルート](lync-server-2013-voice-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a052-131">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="3a052-132">ゲートウェイトポロジ</span><span class="sxs-lookup"><span data-stu-id="3a052-132">Gateway Topologies</span></span>

<span data-ttu-id="3a052-133">ゲートウェイの展開に関する基本的な質問を検討する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a052-133">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="3a052-134">エンタープライズ Voip を使用して PSTN 接続を提供するサイトをカウントします。</span><span class="sxs-lookup"><span data-stu-id="3a052-134">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="3a052-135">各サイトのトラフィックを見積もります (ユーザー数および1時間あたりの平均通話数)。</span><span class="sxs-lookup"><span data-stu-id="3a052-135">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="3a052-136">各サイトに1つ以上のゲートウェイを展開し、予想されるトラフィックを処理します。</span><span class="sxs-lookup"><span data-stu-id="3a052-136">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="3a052-137">その結果、次の図に示すように、分散ゲートウェイトポロジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a052-137">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="3a052-138">**分散ゲートウェイトポロジ**</span><span class="sxs-lookup"><span data-stu-id="3a052-138">**Distributed gateway topology**</span></span>

<span data-ttu-id="3a052-139">![分散ゲートウェイトポロジの図](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "分散ゲートウェイトポロジの図")</span><span class="sxs-lookup"><span data-stu-id="3a052-139">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="3a052-140">このトポロジでは、各サイトでのワーカー間の呼び出しはすべてイントラネット経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3a052-140">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="3a052-141">PSTN への通話は、エンタープライズ IP ネットワーク経由で、宛先番号の場所に最も近いゲートウェイにルーティングされます。しかし、組織が1つまたは複数の大陸に分散している数十または数百のサイトをサポートしている場合、多くの金融機関やその他の大規模な企業では、</span><span class="sxs-lookup"><span data-stu-id="3a052-141">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="3a052-142">このような場合は、サイトごとに個別のゲートウェイを展開するのは現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="3a052-142">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="3a052-143">この問題に対処するために、多くの大企業では、次の図に示すように、1つまたは複数の大規模なテレフォニーセンターサイトを展開することを希望しています。</span><span class="sxs-lookup"><span data-stu-id="3a052-143">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="3a052-144">**テレフォニー中央サイトのトポロジ**</span><span class="sxs-lookup"><span data-stu-id="3a052-144">**Telephony central site topology**</span></span>

<span data-ttu-id="3a052-145">![データセンターゲートウェイトポロジ](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "データセンターゲートウェイトポロジ")</span><span class="sxs-lookup"><span data-stu-id="3a052-145">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="3a052-146">このトポロジでは、予想されるユーザー負荷に対応するのに十分な数の大規模なゲートウェイが、各中央サイトに展開されています。</span><span class="sxs-lookup"><span data-stu-id="3a052-146">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="3a052-147">企業内のユーザーに対するすべての呼び出しは、会社の電話サービスプロバイダーによって中央サイトに転送されます。</span><span class="sxs-lookup"><span data-stu-id="3a052-147">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="3a052-148">中央サイトのルーティングロジックは、呼び出しをイントラネット上または PSTN にルーティングするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3a052-148">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="3a052-149">ゲートウェイの場所</span><span class="sxs-lookup"><span data-stu-id="3a052-149">Gateway Location</span></span>

<span data-ttu-id="3a052-150">ゲートウェイの場所では、選択したゲートウェイの種類とその構成方法も決定することがあります。</span><span class="sxs-lookup"><span data-stu-id="3a052-150">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="3a052-151">さまざまな PSTN プロトコルがありますが、そのいずれもワールドワイド標準ではありません。</span><span class="sxs-lookup"><span data-stu-id="3a052-151">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="3a052-152">すべてのゲートウェイが1つの国/地域に配置されている場合は問題ではありませんが、複数の国/地域にゲートウェイがある場合は、それぞれの国/地域の PSTN 標準に従ってそれぞれを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a052-152">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="3a052-153">さらに、カナダなどのの操作が認定されているゲートウェイは、インド、ブラジル、または欧州連合では認定されていません。</span><span class="sxs-lookup"><span data-stu-id="3a052-153">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="3a052-154">ゲートウェイのサイズと番号</span><span class="sxs-lookup"><span data-stu-id="3a052-154">Gateway Size and Number</span></span>

<span data-ttu-id="3a052-155">ほとんどの組織では、範囲のサイズを2から960のポートに展開することを検討しています。</span><span class="sxs-lookup"><span data-stu-id="3a052-155">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="3a052-156">(大規模なゲートウェイもありますが、これらは主に電話サービスプロバイダーによって使用されます)。組織が必要とするポート数を見積もる場合は、次のガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a052-156">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="3a052-157">軽いテレフォニー使用状況 (ユーザーごとに1時間あたり1つの PSTN 通話) を使用している組織は、15ユーザーごとに1つのポートを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a052-157">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="3a052-158">たとえば、20人のユーザーがいる場合は、2つのポートを持つゲートウェイが必要になります。</span><span class="sxs-lookup"><span data-stu-id="3a052-158">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="3a052-159">電話の使用状況が中程度の組織 (1 時間に1ユーザーあたり2つの PSTN 通話) は、10ユーザーごとに1つのポートを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a052-159">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="3a052-160">たとえば、100ユーザーがいる場合は、1つ以上のゲートウェイに割り当てられる合計10ポートが必要になります。</span><span class="sxs-lookup"><span data-stu-id="3a052-160">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="3a052-161">テレフォニー使用率が高い組織 (1 時間あたりのユーザーごとに3つ以上の PSTN 通話) は、5ユーザーごとに1つのポートを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a052-161">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="3a052-162">たとえば、47000ユーザーがいる場合は、少なくとも10個の大規模なゲートウェイに割り当てられている合計9400ポートが必要になります。</span><span class="sxs-lookup"><span data-stu-id="3a052-162">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="3a052-163">組織内のユーザー数またはトラフィック量の増加に応じて、追加のポートを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="3a052-163">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="3a052-164">サポートする必要がある特定の数のユーザーについては、より少ない、より大きなゲートウェイ、またはそれより小さいものを展開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3a052-164">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="3a052-165">1つのゲートウェイに障害が発生した場合に可用性を維持するには、1つのルールとして、少なくとも2つの組織のゲートウェイが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="3a052-165">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="3a052-166">展開する各 PSTN ゲートウェイには、少なくとも1つの対応する仲介サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="3a052-166">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

