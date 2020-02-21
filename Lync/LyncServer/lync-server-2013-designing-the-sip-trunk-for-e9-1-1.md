---
title: 'Lync Server 2013: E9-1-1 の SIP トランクの設計'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c4191ed20497b4136b4e836da112054bef5a446
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="87347-102">Lync Server 2013 での E9-1-1 の SIP トランクの設計</span><span class="sxs-lookup"><span data-stu-id="87347-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87347-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="87347-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="87347-104">Lync Server は、SIP トランクを使用して、緊急電話を E9-1-1 サービスプロバイダーに接続します。</span><span class="sxs-lookup"><span data-stu-id="87347-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="87347-105">E9-1-1 用の緊急サービス SIP トランクは、1 つのセントラル サイト、複数のセントラル サイト、または各ブランチ サイトにセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="87347-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="87347-106">ただし、発信者のサイトと緊急サービス SIP トランクをホストするサイト間の WAN リンクが使用できない場合、切断されたサイトのユーザーが発信した通話では、ローカル公衆交換電話網 (PSTN) ゲートウェイ経由で ECRC に通話をルーティングする特別な電話使用法レコードがユーザーの音声ポリシーに必要です。</span><span class="sxs-lookup"><span data-stu-id="87347-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="87347-107">通話受付管理で同時通話数制限が有効な場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="87347-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87347-108">Lync Server 環境で SIP トランクを実装するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="87347-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="87347-109">SIP トランクプロバイダーと通信するために、外向きのパブリックにルーティングされたインターフェイスを使用する、マルチホームの仲介サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="87347-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="87347-110">仲介サーバーと SIP トランクプロバイダーのサービスとの間には、オンプレミスのセッションボーダーコントローラー (SBC) を使用して、安全な境界点を指定します。</span><span class="sxs-lookup"><span data-stu-id="87347-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="87347-111">後者の方法を選択した場合は、選択する SBC の型とモデルが認定済みであり、SIP INVITE の一部としてプレゼンス情報データ フォーマット位置オブジェクト (PIDF-LO) 場所データの通過がサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="87347-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="87347-112">サポートされてない場合、緊急サービスのサービス プロバイダーに到着した通話から場所情報が除去されます。</span><span class="sxs-lookup"><span data-stu-id="87347-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="87347-113">認定さ<A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>れた SBCs の詳細については、「」の「Microsoft Lync 向けのインフラストラクチャ認定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87347-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="87347-114">E9-1-1 サービス プロバイダーは、冗長性を確保するために SBC のペアへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="87347-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="87347-115">仲介サーバートポロジと通話ルーティング構成に関していくつかの決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="87347-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="87347-116">たとえば、2 つの SBC を同等のピアとして扱い、SBC 間の通話にラウンドロビン ルーティングを使用するのか、または一方の SBC をプライマリ、もう一方をセカンダリとして指定するのかを決定します。</span><span class="sxs-lookup"><span data-stu-id="87347-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="87347-117">Lync Server での SIP トランクの展開の詳細については、「 [Lync server 2013 で sip トランキングを実装する方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87347-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="87347-118">E9-1-1 用 SIP トランクの展開方法を決定する際に次の質問が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="87347-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="87347-119">**SIP トランクの展開に、専用接続を使用するか、それとも共有のインターネット接続を使用するか。**</span><span class="sxs-lookup"><span data-stu-id="87347-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="87347-p105">緊急電話は常につながることが重要です。専用線で接続すれば、ネットワーク上の他のトラフィックによって回線が専有されることがなくなり、サービス品質 (QoS) も実装できます。パブリック インターネット経由で緊急サービスのサービス プロバイダーに接続し、緊急電話の機密性を保証する必要がある場合は、IPsec 暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="87347-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="87347-123">**E9-1-1 展開は、障害許容を目的として設計されていますか?**</span><span class="sxs-lookup"><span data-stu-id="87347-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="87347-124">これは緊急時向けのソリューションなので、回復性が重要です。</span><span class="sxs-lookup"><span data-stu-id="87347-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="87347-125">プライマリおよびセカンダリの仲介サーバーと SIP トランクを、障害に対する耐性のある場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="87347-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="87347-126">サポートしているユーザーに最も近いプライマリ仲介サーバーを展開し、セカンダリ仲介サーバー (別の地理的な場所にある) を経由してフェールオーバー呼び出しをルーティングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="87347-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="87347-127">**ブランチ オフィスごとに個別に SIP トランクを展開するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="87347-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="87347-128">Lync Server には、回復可能なデータネットワークがある場合、各ブランチに SIP トランクを展開する場合、停止中にローカルゲートウェイに呼び出しをプッシュする場合など、ブランチオフィスの音声の復元を処理するためのいくつかの戦略が用意されています。</span><span class="sxs-lookup"><span data-stu-id="87347-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="87347-129">詳細については、「 [Lync Server 2013 のブランチサイト SIP トランキング](lync-server-2013-branch-site-sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87347-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="87347-130">**通話受付管理 (CAC) を有効にするかどうか。**</span><span class="sxs-lookup"><span data-stu-id="87347-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="87347-131">Lync Server は、通常の通話とは異なる方法で緊急通話を処理しません。</span><span class="sxs-lookup"><span data-stu-id="87347-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="87347-132">そのため、帯域幅管理や通話受付管理 (CAC) が E9-1-1 の構成に悪影響を与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="87347-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="87347-133">CAC が有効になっており、緊急電話がルーティングされているリンク上に構成された制限数を超過した場合は、緊急電話がブロックされたり、ローカル PSTN ゲートウェイにルーティングされたりします。</span><span class="sxs-lookup"><span data-stu-id="87347-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="87347-134">前述のように、このような通話には場所データが含まれていないので、ECRC に手動でルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="87347-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

