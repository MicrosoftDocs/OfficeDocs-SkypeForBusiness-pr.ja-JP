---
title: Skype for Business Server での仲介サーバーの展開ガイドライン
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: このトピックでは、仲介サーバーの展開の計画ガイドラインについて説明します。
ms.openlocfilehash: 245916286fe5f1590581989b8a09daf637c03aa9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800092"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="784b1-103">Skype for Business Server での仲介サーバーの展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="784b1-103">Deployment guidelines for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="784b1-104">このトピックでは、仲介サーバーの展開の計画ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="784b1-104">This topic describes planning guidelines for Mediation Server deployment.</span></span>
  
## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="784b1-105">Collocated or Stand-alone Mediation Server?</span><span class="sxs-lookup"><span data-stu-id="784b1-105">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="784b1-106">仲介サーバーは、既定では、中央サイトのフロント エンド プールの Standard Edition サーバーまたはフロントエンド サーバーに同時に展開されます。</span><span class="sxs-lookup"><span data-stu-id="784b1-106">Mediation Server is, by default, collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="784b1-107">処理できる公衆交換電話網 (PSTN) 通話の数とプールに必要なコンピューターの数は、次の条件によって異なっています。</span><span class="sxs-lookup"><span data-stu-id="784b1-107">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on:</span></span>
  
- <span data-ttu-id="784b1-108">仲介サーバー プールが制御するゲートウェイ ピアの数。</span><span class="sxs-lookup"><span data-stu-id="784b1-108">The number of gateway peers that the Mediation Server pool controls.</span></span>
    
- <span data-ttu-id="784b1-109">これらのゲートウェイを経由する高ボリューム トラフィック期間。</span><span class="sxs-lookup"><span data-stu-id="784b1-109">The high-volume traffic periods through those gateways.</span></span>
    
- <span data-ttu-id="784b1-110">メディアが仲介サーバーをバイパスする通話の割合。</span><span class="sxs-lookup"><span data-stu-id="784b1-110">The percentage of calls that are calls whose media bypass the Mediation Server.</span></span>
    
<span data-ttu-id="784b1-111">計画時には、メディア バイパスをサポートしない PSTN 通話および音声ビデオ会議のメディア処理要件と、サポートが必要なビジー時の通話数に対する信号やり取りを処理するために必要な処理を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-111">When you're planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that don't support media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="784b1-112">CPU が十分ではない場合は、仲介サーバーのスタンドアロン プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-112">If you don't have enough CPU, you'll need to deploy a stand-alone pool of Mediation Servers.</span></span> <span data-ttu-id="784b1-113">さらに、PSTN ゲートウェイ、IP-PBX、および SBC は、1 つのプール内の仲介サーバーと、1 つ以上のスタンドアロン プール内のスタンドアロン仲介サーバーによって制御されるサブセットに分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-113">Additionally, PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>
  
<span data-ttu-id="784b1-114">仲介サーバーのプールと対話する機能がない PSTN ゲートウェイ、IP-PBX、またはセッション ボーダー コントローラー (SBC) を展開した場合は、単一の仲介サーバーで構成されるスタンドアロン プールに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that lack the ability to interact with a pool of Mediation Servers, they'll need to be associated with a stand-alone pool consisting of a single Mediation Server.</span></span> <span data-ttu-id="784b1-115">PSTN ゲートウェイ、PSTN ゲートウェイ、または SPC IP-PBXs実行する必要があるものには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="784b1-115">Some of the things your PSTN gateways, IP-PBXs or SBCs would need to do include:</span></span>
  
- <span data-ttu-id="784b1-116">プール内の仲介サーバー間でネットワーク層ドメイン ネーム システム (DNS) 負荷分散を実行します (それ以外の場合は、プール内のすべての仲介サーバーにトラフィックを均等にルーティングします)。</span><span class="sxs-lookup"><span data-stu-id="784b1-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool).</span></span>
    
- <span data-ttu-id="784b1-117">プール内の仲介サーバーからのトラフィックを受け入れる。</span><span class="sxs-lookup"><span data-stu-id="784b1-117">Accept traffic from any Mediation Server in a pool.</span></span>
    
<span data-ttu-id="784b1-118">Skype for Business Planning Tool を使用して、仲介サーバーとフロントエンド プールを一緒に展開して負荷を処理できるかどうかを評価できます。</span><span class="sxs-lookup"><span data-stu-id="784b1-118">You can use the Skype for Business Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="784b1-119">環境がこれらの要件を満たできない場合は、スタンドアロンの仲介サーバー プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-119">If your environment can't meet these requirements, then you'll need to deploy a stand-alone Mediation Server pool.</span></span>
  
## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="784b1-120">中央サイトとブランチ サイトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="784b1-120">Central Site and Branch Site Considerations</span></span>

 <span data-ttu-id="784b1-121">中央サイトの仲介サーバーを使用して、ブランチ サイトの IP-PBX ゲートウェイまたは PSTN ゲートウェイの通話をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="784b1-121">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="784b1-122">ただし、SIP トランクを展開する場合は、各トランクが終了するサイトに仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-122">If you deploy SIP trunks, however, you have to deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="784b1-123">中央サイトに仲介サーバーを使用すると、ブランチ サイトの IP-PBX または PSTN ゲートウェイの通話がルーティングされますが、メディア バイパスを使用する必要は生じしませんが、メディア バイパスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="784b1-123">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site doesn't require the use of media bypass, but a media bypass is recommended.</span></span> <span data-ttu-id="784b1-124">これは、メディア バイパスを有効にできると、メディア パスの待機時間が短くなるので、メディア パスが信号パスに従う必要がならないため、メディアの品質が向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-124">That's because, if you can enable media bypass, it'll reduce media path latency and, consequently, result in improved media quality because the media path isn't required to follow the signaling path.</span></span> <span data-ttu-id="784b1-125">メディア バイパスにより、プールの処理負荷も軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="784b1-125">Media bypass will also decrease the processing load on the pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="784b1-126">メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは言えな。</span><span class="sxs-lookup"><span data-stu-id="784b1-126">Media bypass won't interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="784b1-127">Microsoft は、認定パートナーと一連の PSTN ゲートウェイと SBC をテストし、Cisco IP-PBX でいくつかのテストを行っています。</span><span class="sxs-lookup"><span data-stu-id="784b1-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="784b1-128">メディア バイパスは [、Unified](http://partnersolutions.skypeforbusiness.com/solutionscatalog)Communications Open Interoperability Program に記載されている製品とバージョンでのみサポートされます。Lync Server は、Skype for Business エクスペリエンスをサポートおよび拡張するテスト済みデバイス、インフラストラクチャ、およびツールを参照してください。</span><span class="sxs-lookup"><span data-stu-id="784b1-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog).</span></span> 
  
<span data-ttu-id="784b1-129">ブランチ サイトの復元が必要な場合は、存続可能ブランチ アプライアンスまたはフロントエンド サーバー、仲介サーバー、およびゲートウェイの組み合わせをブランチ サイトに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="784b1-130">(ブランチ サイトの復元の前提は、プレゼンスと会議がサイトで回復性を持たないという前提です)。音声のブランチ サイトの計画に関するガイダンスについては [、「Plan for エンタープライズ VoIP resiliency in Skype for Business Server 」を参照してください](../enterprise-voice-solution/enterprise-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="784b1-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Plan for Enterprise Voice resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).</span></span>
  
<span data-ttu-id="784b1-131">IP-PBX とのやり取りでは、IP-PBX が複数の早期ダイアログや RFC 3960 の対話による早期メディア操作を正しくサポートしていない場合、IP-PBX から Lync エンドポイントへの着信呼び出しに対して、最初の数語の案内応答がクリッピングされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="784b1-132">中央サイトの仲介サーバーがブランチ サイトでルートが終了する IP-PBX の通話をルーティングしている場合、信号が完了するのにより長い時間が必要になるため、この動作はさらに深刻になります。</span><span class="sxs-lookup"><span data-stu-id="784b1-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="784b1-133">この動作が発生した場合、最初の数語のクリッピングを減らす唯一の方法は、ブランチ サイトに仲介サーバーを展開することです。</span><span class="sxs-lookup"><span data-stu-id="784b1-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>
  
<span data-ttu-id="784b1-134">また、中央サイトに TDM PBX がある場合や、IP-PBX によって PSTN ゲートウェイの必要性がなくならない場合は、仲介サーバーおよび PBX に接続する通話ルートにゲートウェイを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>
  
> [!NOTE]
> <span data-ttu-id="784b1-135">スタンドアロンの仲介サーバーのメディア パフォーマンスを向上するには、これらのサーバーのネットワーク アダプターで受信側スケーリング (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="784b1-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="784b1-136">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="784b1-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="784b1-137">詳細については[、「Windows Server の受信側スケーリングの拡張機能」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=268731)。</span><span class="sxs-lookup"><span data-stu-id="784b1-137">For details, see "[Receive-Side Scaling Enhancements in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)".</span></span> <span data-ttu-id="784b1-138">RSS を有効にする方法の詳細については、ネットワーク アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="784b1-138">For details about how to enable RSS, see your network adapter documentation.</span></span> 
  

