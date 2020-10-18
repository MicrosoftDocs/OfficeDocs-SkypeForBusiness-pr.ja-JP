---
title: 'Lync Server 2013: 仲介サーバーの展開ガイドライン'
description: 'Lync Server 2013: 仲介サーバーの展開ガイドライン。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8198431b24714666c9411029aecd12835014fef4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575773"
---
# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="ceed5-103">Lync Server 2013 の仲介サーバーの展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="ceed5-103">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceed5-104">_**トピックの最終更新日:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="ceed5-104">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="ceed5-105">このトピックでは、仲介サーバーの展開の計画ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-105">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="ceed5-106">これらのガイドラインを確認した後、計画ツールを使用して、展開することを決定した最終的な調整トポロジのモデルとして利用できる代替トポロジを作成および表示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-106">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="ceed5-107">併置またはスタンドアロンの仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="ceed5-107">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="ceed5-108">仲介サーバーは、既定では、Standard Edition サーバーまたは中央サイトのフロント エンド プール内のフロント エンド サーバーに併置されます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-108">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="ceed5-109">処理できる公衆交換電話網 (PSTN) 通話の数と、プールで必要なコンピューターの数は、以下によって決まります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-109">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="ceed5-110">仲介サーバープールが制御するゲートウェイピアの数</span><span class="sxs-lookup"><span data-stu-id="ceed5-110">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="ceed5-111">これらのゲートウェイを通過する、ボリュームの大きいトラフィック期間</span><span class="sxs-lookup"><span data-stu-id="ceed5-111">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="ceed5-112">仲介サーバーをバイパスしているメディアを持つ通話の割合</span><span class="sxs-lookup"><span data-stu-id="ceed5-112">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="ceed5-113">計画時には、メディアバイパスを使用するように構成されていない PSTN 通話と音声ビデオ会議のためのメディア処理要件と、サポートする必要のある時間外呼び出しの数に対するシグナリング通信を処理するために必要な処理を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-113">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="ceed5-114">CPU が十分でない場合は、仲介サーバーのスタンドアロンプールを展開する必要があります。および PSTN ゲートウェイ、IP-PBX、および sbc は、1つのプール内の併置された仲介サーバーによって制御されるサブセット、または1つまたは複数のスタンドアロンプールにあるスタンドアロン仲介サーバーによって制御されるサブセットに分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-114">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="ceed5-115">PSTN ゲートウェイ、IP-PBX、またはセッションボーダーコントローラー (sbc) を展開した場合は、次に示すように、仲介サーバーのプールを操作するための適切な機能がサポートされていない場合は、1つの仲介サーバーから成るスタンドアロンプールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-115">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="ceed5-116">プール内の仲介サーバーでネットワーク層のドメインネームシステム (DNS) 負荷分散を実行する (または、プール内のすべての仲介サーバーにトラフィックを均等にルーティングする)</span><span class="sxs-lookup"><span data-stu-id="ceed5-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="ceed5-117">プール内のすべての仲介サーバーからのトラフィックを受け付ける</span><span class="sxs-lookup"><span data-stu-id="ceed5-117">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="ceed5-118">Microsoft Lync Server 2013、計画ツールを使用して、仲介サーバーをフロントエンドプールと併置することで負荷を処理できるかどうかを評価できます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="ceed5-119">これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="ceed5-120">中央サイトとブランチ サイトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ceed5-120">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="ceed5-p105">中央サイトの仲介サーバーを使用して、ブランチ サイトの IP-PBX ゲートウェイまたは PSTN ゲートウェイの通話をルーティングできます。 ただし、SIP トランクを展開する場合は、各トランクが終了するサイトに仲介サーバーを展開する必要があります。 中央サイトの仲介サーバーでブランチ サイトの IP-PBX ゲートウェイまたは PSTN ゲートウェイの通話をルーティングする場合は、メディア バイパスを使用する必要はありません。 ただし、メディア バイパスを有効にできる場合は、有効にすると、メディア パスが信号パスを通過する必要がなくなるため、メディア パスの遅延を低減して、メディアの品質を高めることができます。 メディア バイパスにより、プールの処理負荷も軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ceed5-126">メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="ceed5-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="ceed5-127">Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="ceed5-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="ceed5-128">メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at の製品およびバージョンのみです <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A> 。</span><span class="sxs-lookup"><span data-stu-id="ceed5-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="ceed5-129">ブランチサイトの復元が必要な場合は、ブランチサイトに存続可能ブランチアプライアンスまたはフロントエンドサーバー、仲介サーバー、ゲートウェイの組み合わせを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="ceed5-130">(ブランチサイトの復元には、サイトでのプレゼンスと会議の弾力性がありません)。音声のブランチサイトの計画のガイダンスについては、「 [Lync Server 2013 でのブランチサイトの音声の復元の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="ceed5-131">Ip-pbx との対話の場合、ip-pbx が、複数の初期ダイアログと RFC 3960 の相互作用との早いメディア操作を適切にサポートしていない場合は、ip-pbx から Lync エンドポイントへの着信呼び出しについて、応答メッセージの最初の数文字をクリッピングすることができます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="ceed5-132">中央サイトの仲介サーバーがブランチ サイトでルートが終了する IP-PBX の通話をルーティングしている場合、信号が完了するのにより長い時間が必要になるため、この動作はさらに深刻になります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="ceed5-133">この現象が見られる場合は、最初の少数の単語のクリッピングを減らす唯一の方法は、ブランチサイトに仲介サーバーを展開することだけです。</span><span class="sxs-lookup"><span data-stu-id="ceed5-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="ceed5-134">また、中央サイトに TDM PBX がある場合や、IP-PBX によって PSTN ゲートウェイの必要性がなくならない場合は、仲介サーバーおよび PBX に接続する通話ルートにゲートウェイを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ceed5-135">スタンドアロンの仲介サーバーのメディアパフォーマンスを向上させるには、これらのサーバーのネットワークアダプターで受信側スケーリング (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="ceed5-136">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="ceed5-137">詳細については、「」の「Windows Server の受信側スケーリングの拡張機能」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A> 。</span><span class="sxs-lookup"><span data-stu-id="ceed5-137">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="ceed5-138">RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-138">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

