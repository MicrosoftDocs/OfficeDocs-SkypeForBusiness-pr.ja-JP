---
title: 'Lync Server 2013: 仲介サーバー向けの展開ガイドライン'
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
ms.openlocfilehash: 3c91ea4368d96e6a558a25eda86d163e4ced4cb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="79f1e-102">Lync Server 2013 での仲介サーバーの展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="79f1e-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79f1e-103">_**最終更新日:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="79f1e-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="79f1e-104">このトピックでは、仲介サーバーの展開に関する計画ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="79f1e-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="79f1e-105">これらのガイドラインを確認した後、計画ツールを使用して、展開する予定の最終的なトポロジがどのように表示されるかのモデルとして利用できる、可能な代替トポロジを作成して表示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="79f1e-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="79f1e-106">併置またはスタンドアロンの仲介サーバーですか?</span><span class="sxs-lookup"><span data-stu-id="79f1e-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="79f1e-107">仲介サーバーは、既定では、Standard Edition サーバーまたはフロントエンドサーバーの中央サイトのフロントエンドプールにあります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="79f1e-108">処理することができる公衆交換電話網 (PSTN) 通話の数およびプール内で必要なコンピューターの数は、以下に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="79f1e-109">仲介サーバープールが制御するゲートウェイピアの数</span><span class="sxs-lookup"><span data-stu-id="79f1e-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="79f1e-110">それらのゲートウェイを経由する高ボリューム トラフィックの期間</span><span class="sxs-lookup"><span data-stu-id="79f1e-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="79f1e-111">仲介サーバーを使用していないメディアを含む通話の割合</span><span class="sxs-lookup"><span data-stu-id="79f1e-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="79f1e-112">計画するときは、メディアのバイパス用に構成されていない PSTN 通話と A/V 会議のメディア処理要件、およびサポートする必要がある時間帯を含む通話のシグナル操作を処理するために必要な処理について必ず考慮してください。</span><span class="sxs-lookup"><span data-stu-id="79f1e-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="79f1e-113">CPU が不足している場合は、スタンドアロンのプールサーバーを展開する必要があります。また、PSTN ゲートウェイ、IP Pbx、および SBCs は、1つのプール内の併置されている仲介サーバーによって制御されるサブセットと1つ以上のスタンドアロンプールでスタンドアロンの仲介サーバーによって制御されるサブセットに分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="79f1e-114">次に示すように、仲介サーバーのプールを操作するための適切な機能をサポートしていない PSTN ゲートウェイ、IP Pbx、またはセッション境界コントローラー (SBCs) を展開した場合は、次のように構成されている単体プールと関連付ける必要があります。単一の仲介サーバーの場合:</span><span class="sxs-lookup"><span data-stu-id="79f1e-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="79f1e-115">プール内の仲介サーバー間でネットワークレイヤーのドメインネームシステム (DNS) 負荷分散を実行する (または、プール内のすべての仲介サーバーに対して一律にトラフィックをルーティングする)</span><span class="sxs-lookup"><span data-stu-id="79f1e-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="79f1e-116">プール内の任意の仲介サーバーからのトラフィックを受け入れる</span><span class="sxs-lookup"><span data-stu-id="79f1e-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="79f1e-117">Microsoft Lync Server 2013 の計画ツールを使用すると、フロントエンドプールで仲介サーバーを検索して負荷を処理できるかどうかを評価できます。</span><span class="sxs-lookup"><span data-stu-id="79f1e-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="79f1e-118">環境がこれらの要件を満たしていない場合は、スタンドアロンの仲介サーバープールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="79f1e-119">中央サイトとブランチ サイトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="79f1e-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="79f1e-120">セントラルサイトの仲介サーバーを使用すると、支社または PSTN ゲートウェイの着信をブランチサイトでルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="79f1e-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="79f1e-121">ただし、SIP trunks を展開する場合は、各トランクが終了するサイトに仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="79f1e-122">ブランチサイトで、IP PBX または PSTN ゲートウェイのセントラルサイトルートに仲介サーバーがある場合は、メディアバイパスの使用は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="79f1e-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="79f1e-123">ただし、メディアのバイパスを有効にできる場合は、メディアパスの遅延を減らすことができます。その結果、メディアパスはシグナリングパスの追跡には必要なくなったため、メディアの品質が向上します。</span><span class="sxs-lookup"><span data-stu-id="79f1e-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="79f1e-124">メディア バイパスにより、プールの処理負荷も軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="79f1e-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="79f1e-125">メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="79f1e-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="79f1e-126">マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="79f1e-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="79f1e-127">メディアのバイパスは、統合された通信のオープンな相互運用性プログラム– Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>の製品とバージョンでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="79f1e-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="79f1e-128">ブランチサイトの回復力が必要な場合は、Survivable Branch Appliance またはフロントエンドサーバー、仲介サーバー、ゲートウェイをブランチサイトに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="79f1e-129">(ブランチサイトの回復力を前提として、サイトでのプレゼンスと会議の弾力性がないことを前提としています)。ボイスのブランチサイトの計画に関するガイダンスについては、「 [Lync Server 2013 でのブランチサイトの音声回復の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79f1e-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="79f1e-130">Ip pbx との相互操作については、ip pbx で、複数の初期ダイアログと RFC 3960 の相互作用との早いメディア操作が適切にサポートされていない場合、IP PBX から Lync エンドポイントへの着信通話について、応答メッセージの最初のいくつかの単語をクリッピングすることができます。</span><span class="sxs-lookup"><span data-stu-id="79f1e-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="79f1e-131">この動作は、ルーティングを完了するためにより多くの時間が必要となるため、セントラルサイトの仲介サーバーが、ブランチサイトで終了する IP PBX の呼び出しをルーティングしている場合、より重大な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="79f1e-132">この問題が発生した場合は、最初のいくつかの単語のクリッピングを減らす唯一の方法は、ブランチサイトに仲介サーバーを展開することだけです。</span><span class="sxs-lookup"><span data-stu-id="79f1e-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="79f1e-133">最後に、セントラルサイトに TDM PBX がある場合、または、IP PBX で PSTN ゲートウェイを使用する必要がない場合は、仲介サーバーと PBX を接続する通話ルートにゲートウェイを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="79f1e-134">スタンドアロン仲介サーバーのメディア パフォーマンスを向上させるには、これらのサーバーのネットワーク アダプターの Receive-side Scaling (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f1e-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="79f1e-135">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="79f1e-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="79f1e-136">詳細については、の「Windows Server の受信側スケーリングの<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>拡張機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79f1e-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="79f1e-137">RSS を有効にする方法の詳細については、ネットワーク アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79f1e-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

