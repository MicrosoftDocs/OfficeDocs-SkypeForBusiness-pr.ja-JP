---
title: Skype for Business Server で E9-1-1 の SIP トランクを設計する
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用する E9-1-1 展開の SIP トランキング トポロジを計画します。
ms.openlocfilehash: ef30d721b59f29885004ee948055a91ca8af9490
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825797"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="91aef-103">Skype for Business Server で E9-1-1 の SIP トランクを設計する</span><span class="sxs-lookup"><span data-stu-id="91aef-103">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="91aef-104">Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用する E9-1-1 展開の SIP トランキング トポロジを計画します。</span><span class="sxs-lookup"><span data-stu-id="91aef-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="91aef-105">Skype for Business Server は SIP トランクを使用して、緊急通話を E9-1-1 サービス プロバイダーに接続します。</span><span class="sxs-lookup"><span data-stu-id="91aef-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="91aef-106">E9-1-1 用の緊急サービス SIP トランクは、1 つのセントラル サイト、複数のセントラル サイト、または各ブランチ サイトにセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="91aef-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="91aef-107">ただし、発信者のサイトと緊急サービス SIP トランクをホストするサイト間の WAN リンクが使用できない場合、切断されたサイトのユーザーが発信した通話には、ローカルの公衆交換電話網 (PSTN) ゲートウェイを介して ECRC に通話をルーティングする、ユーザーの音声ポリシー内の特別な電話使用法レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="91aef-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="91aef-108">通話受付管理で同時通話数制限が有効な場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="91aef-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="91aef-109">Skype for Business Server 環境に SIP トランクを実装するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="91aef-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="91aef-110">SIP トランク プロバイダーと通信するには、外向きの公開ルーティング インターフェイスを使用するマルチホーム仲介サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="91aef-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="91aef-111">オンプレミスのセッション ボーダー コントローラー (SBC) を使用して、仲介サーバーと SIP トランク プロバイダーのサービス間に安全な境界ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="91aef-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="91aef-112">後者の方法を選択した場合は、選択する SBC の型とモデルが認定済みであり、SIP INVITE の一部としてプレゼンス情報データ フォーマット位置オブジェクト (PIDF-LO) 場所データの通過がサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91aef-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="91aef-113">サポートされてない場合、緊急サービスのサービス プロバイダーに到着した通話から場所情報が除去されます。</span><span class="sxs-lookup"><span data-stu-id="91aef-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="91aef-114">認定 SPC の詳細については   [、「Infrastructure Qualified for Microsoft Lync」](https://go.microsoft.com/fwlink/p/?LinkId=248425) および [「Telephony Infrastructure for Skype for Business」](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91aef-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
<span data-ttu-id="91aef-115">E9-1-1 サービス プロバイダーは、冗長性を確保するために SBC のペアへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="91aef-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="91aef-116">仲介サーバーのトポロジと通話ルーティング構成に関して、いくつかの決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="91aef-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="91aef-117">たとえば、2 つの SBC を同等のピアとして扱い、SBC 間の通話にラウンドロビン ルーティングを使用するのか、または一方の SBC をプライマリ、もう一方をセカンダリとして指定するのかを決定します。</span><span class="sxs-lookup"><span data-stu-id="91aef-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="91aef-118">Skype for Business Server での SIP トランクの展開の詳細については、「Skype for Business Server での SIP トランキング」 [を参照してください](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="91aef-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span> <span data-ttu-id="91aef-119">E9-1-1 用 SIP トランクの展開方法を決定する際に次の質問が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="91aef-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="91aef-120">**SIP トランクの展開に、専用接続を使用するか、それとも共有のインターネット接続を使用するか。**</span><span class="sxs-lookup"><span data-stu-id="91aef-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="91aef-p105">緊急電話は常につながることが重要です。専用線で接続すれば、ネットワーク上の他のトラフィックによって回線が専有されることがなくなり、サービス品質 (QoS) も実装できます。パブリック インターネット経由で緊急サービスのサービス プロバイダーに接続し、緊急電話の機密性を保証する必要がある場合は、IPsec 暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="91aef-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="91aef-124">**E9-1-1 展開は障害許容度を目的として設計されていますか?**</span><span class="sxs-lookup"><span data-stu-id="91aef-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="91aef-125">これは緊急時向けのソリューションなので、回復性が重要です。</span><span class="sxs-lookup"><span data-stu-id="91aef-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="91aef-126">プライマリおよびセカンダリの仲介サーバーと SIP トランクを障害許容の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="91aef-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="91aef-127">プライマリ仲介サーバーは、サポートしているユーザーに最も近い場所に展開し、フェールオーバー呼び出しを (地理的に異なる場所にある) セカンダリ仲介サーバーを経由してルーティングする方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="91aef-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="91aef-128">**ブランチ オフィスごとに個別に SIP トランクを展開するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="91aef-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="91aef-129">Skype for Business Server は、ブランチ オフィスでの音声の復元に対応するためのいくつかの戦略を提供します。たとえば、回復力のあるデータ ネットワークの確保、各ブランチでの SIP トランクの展開、停止時のローカル ゲートウェイへの通話のプッシュなどです。</span><span class="sxs-lookup"><span data-stu-id="91aef-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="91aef-130">詳細については、Skype for Business Server の [SIP トランキングを参照してください](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="91aef-130">For details, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
    
 <span data-ttu-id="91aef-131">**通話受付管理 (CAC) を有効にするかどうか。**</span><span class="sxs-lookup"><span data-stu-id="91aef-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="91aef-132">Skype for Business Server は、通常の通話と異なる方法で緊急電話を処理しません。</span><span class="sxs-lookup"><span data-stu-id="91aef-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="91aef-133">そのため、帯域幅管理や通話受付管理 (CAC) が E9-1-1 の構成に悪影響を与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="91aef-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="91aef-134">CAC が有効になっており、緊急電話がルーティングされているリンク上に構成された制限数を超過した場合は、緊急電話がブロックされたり、ローカル PSTN ゲートウェイにルーティングされたりします。</span><span class="sxs-lookup"><span data-stu-id="91aef-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="91aef-135">前述のように、このような通話には場所データが含まれていないので、ECRC に手動でルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="91aef-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

