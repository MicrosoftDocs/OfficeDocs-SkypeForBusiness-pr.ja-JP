---
title: Skype for Business Server の仲介サーバーの展開ガイドライン
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: このトピックでは、仲介サーバーの展開に関する計画ガイドラインについて説明します。
ms.openlocfilehash: 806886b7c7c5e8ae367a6e104f7fd9127f25c099
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816056"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="33a4f-103">Skype for Business Server の仲介サーバーの展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="33a4f-103">Deployment guidelines for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="33a4f-104">このトピックでは、仲介サーバーの展開に関する計画ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="33a4f-104">This topic describes planning guidelines for Mediation Server deployment.</span></span>
  
## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="33a4f-105">併置またはスタンドアロンの仲介サーバーですか?</span><span class="sxs-lookup"><span data-stu-id="33a4f-105">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="33a4f-106">既定では、仲介サーバーは、Standard Edition サーバーまたはフロントエンドサーバーに中央サイトのフロントエンドプールに併置されています。</span><span class="sxs-lookup"><span data-stu-id="33a4f-106">Mediation Server is, by default, collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="33a4f-107">処理することができる公衆交換電話網 (PSTN) 通話の数およびプール内で必要なコンピューターの数は、以下に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-107">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on:</span></span>
  
- <span data-ttu-id="33a4f-108">仲介サーバープールが制御するゲートウェイピアの数です。</span><span class="sxs-lookup"><span data-stu-id="33a4f-108">The number of gateway peers that the Mediation Server pool controls.</span></span>
    
- <span data-ttu-id="33a4f-109">それらのゲートウェイを経由する高ボリューム トラフィックの期間</span><span class="sxs-lookup"><span data-stu-id="33a4f-109">The high-volume traffic periods through those gateways.</span></span>
    
- <span data-ttu-id="33a4f-110">仲介サーバーを使用していないメディアを使用している電話への通話の割合。</span><span class="sxs-lookup"><span data-stu-id="33a4f-110">The percentage of calls that are calls whose media bypass the Mediation Server.</span></span>
    
<span data-ttu-id="33a4f-111">計画時には、メディア バイパスをサポートしない PSTN 通話および音声ビデオ会議のメディア処理要件、およびサポートする必要がある混雑時間帯の通話数に対する信号のやり取りに必要な処理を、考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-111">When you're planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that don't support media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="33a4f-112">十分な CPU がない場合は、スタンドアロンの仲介サーバーのプールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-112">If you don't have enough CPU, you'll need to deploy a stand-alone pool of Mediation Servers.</span></span> <span data-ttu-id="33a4f-113">さらに、PSTN ゲートウェイ、IP Pbx、および SBCs は、1つのプール内の併置されている仲介サーバーによって制御されるサブセットと1つ以上のスタンドアロンプールでスタンドアロンの仲介サーバーによって制御されるサブセットに分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-113">Additionally, PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>
  
<span data-ttu-id="33a4f-114">仲介サーバーのプールを操作する機能を備えていない PSTN ゲートウェイ、IP Pbx、またはセッション境界コントローラー (SBCs) を展開した場合は、1つの仲介サーバーで構成されるスタンドアロンプールに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that lack the ability to interact with a pool of Mediation Servers, they'll need to be associated with a stand-alone pool consisting of a single Mediation Server.</span></span> <span data-ttu-id="33a4f-115">PSTN ゲートウェイ、IP-PBX、SBC で必要な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33a4f-115">Some of the things your PSTN gateways, IP-PBXs or SBCs would need to do include:</span></span>
  
- <span data-ttu-id="33a4f-116">プール内の仲介サーバー間でネットワークレイヤーのドメインネームシステム (DNS) 負荷分散を実行します (または、プール内のすべての仲介サーバーに対して一律にトラフィックをルーティングします)。</span><span class="sxs-lookup"><span data-stu-id="33a4f-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool).</span></span>
    
- <span data-ttu-id="33a4f-117">プール内の任意の仲介サーバーからのトラフィックを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="33a4f-117">Accept traffic from any Mediation Server in a pool.</span></span>
    
<span data-ttu-id="33a4f-118">Skype for Business 計画ツールを使用すると、フロントエンドプールで仲介サーバーを検索して負荷を処理できるかどうかを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="33a4f-118">You can use the Skype for Business Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="33a4f-119">環境がこれらの要件を満たしていない場合は、スタンドアロンの仲介サーバープールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-119">If your environment can't meet these requirements, then you'll need to deploy a stand-alone Mediation Server pool.</span></span>
  
## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="33a4f-120">中央サイトとブランチ サイトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="33a4f-120">Central Site and Branch Site Considerations</span></span>

 <span data-ttu-id="33a4f-121">セントラルサイトの仲介サーバーを使用すると、支社または PSTN ゲートウェイの着信をブランチサイトでルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="33a4f-121">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="33a4f-122">ただし、SIP trunks を展開する場合は、各トランクが終了するサイトに仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-122">If you deploy SIP trunks, however, you have to deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="33a4f-123">ブランチサイトで、IP PBX または PSTN ゲートウェイのセントラルサイトルートへの呼び出しに仲介サーバーがある場合は、メディアのバイパスを使用する必要はありませんが、メディアバイパスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33a4f-123">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site doesn't require the use of media bypass, but a media bypass is recommended.</span></span> <span data-ttu-id="33a4f-124">メディア バイパスを有効にできれば、メディア パスが信号パスを通過する必要がなくなるため、メディア パスの遅延を低減して、メディアの品質を高めることができるためです。</span><span class="sxs-lookup"><span data-stu-id="33a4f-124">That's because, if you can enable media bypass, it'll reduce media path latency and, consequently, result in improved media quality because the media path isn't required to follow the signaling path.</span></span> <span data-ttu-id="33a4f-125">メディア バイパスにより、プールの処理負荷も軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="33a4f-125">Media bypass will also decrease the processing load on the pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33a4f-126">メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="33a4f-126">Media bypass won't interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="33a4f-127">マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="33a4f-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="33a4f-128">メディアのバイパスは、統合された通信に表示される製品とバージョンでのみサポートされています。 [Skype For business のエクスペリエンスをサポートおよび拡張するテスト済みのデバイス、インフラストラクチャ、およびツールについ](http://partnersolutions.skypeforbusiness.com/solutionscatalog)ては、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a4f-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog).</span></span> 
  
<span data-ttu-id="33a4f-129">ブランチサイトの回復力が必要な場合は、Survivable Branch Appliance またはフロントエンドサーバー、仲介サーバー、ゲートウェイをブランチサイトに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="33a4f-130">(ブランチサイトの回復力を前提として、サイトでのプレゼンスと会議の弾力性がないことを前提としています)。ボイスのブランチサイトの計画に関するガイダンスについては、「 [Skype For Business Server でのエンタープライズボイスの復元計画](../enterprise-voice-solution/enterprise-voice-resiliency.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a4f-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Plan for Enterprise Voice resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).</span></span>
  
<span data-ttu-id="33a4f-131">Ip pbx との相互操作については、ip pbx で、複数の初期ダイアログと RFC 3960 の相互作用との早いメディア操作が適切にサポートされていない場合、IP PBX から Lync エンドポイントへの着信通話について、応答メッセージの最初のいくつかの単語をクリッピングすることができます。</span><span class="sxs-lookup"><span data-stu-id="33a4f-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="33a4f-132">この動作は、ルーティングを完了するためにより多くの時間が必要となるため、セントラルサイトの仲介サーバーが、ブランチサイトで終了する IP PBX の呼び出しをルーティングしている場合、より重大な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="33a4f-133">この問題が発生した場合は、最初のいくつかの単語のクリッピングを減らす唯一の方法は、ブランチサイトに仲介サーバーを展開することだけです。</span><span class="sxs-lookup"><span data-stu-id="33a4f-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>
  
<span data-ttu-id="33a4f-134">最後に、セントラルサイトに TDM PBX がある場合、または、IP PBX で PSTN ゲートウェイを使用する必要がない場合は、仲介サーバーと PBX を接続する通話ルートにゲートウェイを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33a4f-135">スタンドアロン仲介サーバーのメディア パフォーマンスを向上させるには、これらのサーバーのネットワーク アダプターの Receive-side Scaling (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a4f-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="33a4f-136">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="33a4f-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="33a4f-137">詳細については、「[Windows Server の受信側スケーリングの拡張機能](https://go.microsoft.com/fwlink/p/?LinkId=268731)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a4f-137">For details, see "[Receive-Side Scaling Enhancements in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)".</span></span> <span data-ttu-id="33a4f-138">RSS を有効にする方法の詳細については、ネットワーク アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a4f-138">For details about how to enable RSS, see your network adapter documentation.</span></span> 
  

