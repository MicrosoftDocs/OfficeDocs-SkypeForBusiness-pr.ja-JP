---
title: Skype for Business Server での E9-1 の SIP トランクの設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Skype for Business Server Enterprise Voice で SIP トランクプロバイダーを使用する E9 展開用の SIP トランクトポロジを計画します。
ms.openlocfilehash: 1d3b55fd6bb61fbf83f1a2294c96503b816f9c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276979"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="61809-103">Skype for Business Server での E9-1 の SIP トランクの設計</span><span class="sxs-lookup"><span data-stu-id="61809-103">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="61809-104">Skype for Business Server Enterprise Voice で SIP トランクプロバイダーを使用する E9 展開用の SIP トランクトポロジを計画します。</span><span class="sxs-lookup"><span data-stu-id="61809-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="61809-105">Skype for Business Server は、SIP trunks を使用して、緊急通話を E9 サービスプロバイダに接続します。</span><span class="sxs-lookup"><span data-stu-id="61809-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="61809-106">E9-1-1 用の緊急サービス SIP トランクは、1 つの中央サイト、複数の中央サイト、または各ブランチ サイトにセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="61809-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="61809-107">ただし、発信者のサイトと緊急対応の SIP トランクをホストしているサイトとの間の WAN リンクが利用できない場合は、接続されていないサイトのユーザーによって発信される電話には、ユーザーの音声ポリシーに、通話をルーティングするための特別な電話の使用状況レコードが必要になります。[ローカル公衆交換電話網 (PSTN) ゲートウェイからの ECRC] を選びます。</span><span class="sxs-lookup"><span data-stu-id="61809-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="61809-108">通話受付管理で同時通話数制限が有効な場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="61809-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="61809-109">Skype for Business Server 環境で SIP トランクを実装するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="61809-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="61809-110">外部向けのパブリックルーティングインターフェイスを使用して、SIP トランクプロバイダーと通信するマルチホーム仲介サーバーを使います。</span><span class="sxs-lookup"><span data-stu-id="61809-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="61809-111">オンプレミスセッションボーダーコントローラー (SBC) を使って、仲介サーバーと SIP トランクプロバイダーのサービス間に安全な境界点を指定します。</span><span class="sxs-lookup"><span data-stu-id="61809-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="61809-112">後者の方法を選択した場合は、選択する SBC の型とモデルが認定済みであり、SIP INVITE の一部としてプレゼンス情報データ フォーマット位置オブジェクト (PIDF-LO) 場所データの通過がサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61809-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="61809-113">サポートされてない場合、緊急サービスのサービス プロバイダーに到着した通話から場所情報が除去されます。</span><span class="sxs-lookup"><span data-stu-id="61809-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="61809-114">認定された SBCs の詳細については、「 [Microsoft Lync 用に認定](https://go.microsoft.com/fwlink/p/?LinkId=248425)されたインフラストラクチャ」および[「Skype For Business のテレフォニーインフラストラクチャ](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61809-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
<span data-ttu-id="61809-115">E9-1-1 サービス プロバイダーは、冗長性を確保するために SBC のペアへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="61809-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="61809-116">仲介サーバートポロジと通話ルーティング構成について、いくつかの決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="61809-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="61809-117">たとえば、2 つの SBC を同等のピアとして扱い、SBC 間の通話にラウンドロビン ルーティングを使用するのか、または一方の SBC をプライマリ、もう一方をセカンダリとして指定するのかを決定します。</span><span class="sxs-lookup"><span data-stu-id="61809-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="61809-118">Skype for Business Server での SIP トランクの展開の詳細については、「 [skype For Business server の sip トランク](sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61809-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span> <span data-ttu-id="61809-119">E9-1-1 用 SIP トランクの展開方法を決定する際に次の質問が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="61809-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="61809-120">**SIP トランクの展開に、専用接続を使用するか、それとも共有のインターネット接続を使用するか。**</span><span class="sxs-lookup"><span data-stu-id="61809-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="61809-p105">緊急電話は常につながることが重要です。専用線で接続すれば、ネットワーク上の他のトラフィックによって回線が専有されることがなくなり、サービス品質 (QoS) も実装できます。パブリック インターネット経由で緊急サービスのサービス プロバイダーに接続し、緊急電話の機密性を保証する必要がある場合は、IPsec 暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="61809-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="61809-124">**E9 展開は、耐障害性のために設計されていますか?**</span><span class="sxs-lookup"><span data-stu-id="61809-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="61809-125">これは緊急時向けのソリューションなので、回復性が重要です。</span><span class="sxs-lookup"><span data-stu-id="61809-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="61809-126">プライマリおよびセカンダリの仲介サーバーと SIP trunks を、ディザスタートレラントな場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="61809-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="61809-127">サポート対象のユーザーに最も近いプライマリ仲介サーバーを展開し、セカンダリ仲介サーバー (別の地理的な場所にある) 経由でフェールオーバー通話をルーティングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61809-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="61809-128">**ブランチ オフィスごとに個別に SIP トランクを展開するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="61809-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="61809-129">Skype for Business Server には、回復可能なデータネットワークが存在する場合、各ブランチに SIP トランクを展開する場合、または停止中にローカルゲートウェイへの呼び出しをプッシュする場合など、支店での音声回復性を処理するためのいくつかの戦略が用意されています。</span><span class="sxs-lookup"><span data-stu-id="61809-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="61809-130">詳細については、「 [Skype For Business Server の SIP トランキング](sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61809-130">For details, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
    
 <span data-ttu-id="61809-131">**通話受付管理 (CAC) を有効にするかどうか。**</span><span class="sxs-lookup"><span data-stu-id="61809-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="61809-132">Skype for Business Server では、通常の通話とは異なる方法で緊急通話を処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="61809-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="61809-133">そのため、帯域幅管理や通話受付管理 (CAC) が E9-1-1 の構成に悪影響を与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="61809-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="61809-134">CAC が有効になっており、緊急電話がルーティングされているリンク上に構成された制限数を超過した場合は、緊急電話がブロックされたり、ローカル PSTN ゲートウェイにルーティングされたりします。</span><span class="sxs-lookup"><span data-stu-id="61809-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="61809-135">前述のように、このような通話には場所データが含まれていないので、ECRC に手動でルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61809-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

