---
title: Skype for Business Server でのインスタント メッセージングとプレゼンスの計画
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '概要: Skype for Business Server でインスタント メッセージングとプレゼンスを計画する方法について説明します。'
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816277"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="f03eb-103">Skype for Business Server でのインスタント メッセージングとプレゼンスの計画</span><span class="sxs-lookup"><span data-stu-id="f03eb-103">Plan for instant messaging and presence in Skype for Business Server</span></span>
 
<span data-ttu-id="f03eb-104">**概要:** Skype for Business Server でインスタント メッセージングとプレゼンスを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f03eb-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server.</span></span>
  
<span data-ttu-id="f03eb-105">Skype for Business Server でインスタント メッセージングとプレゼンスを計画します。</span><span class="sxs-lookup"><span data-stu-id="f03eb-105">Plan for instant messaging and presence in Skype for Business Server.</span></span> <span data-ttu-id="f03eb-106">オフライン インスタント メッセージング (IM) の有効化や無効化などの特定の展開オプションについては [、「Skype for Business Server](../deploy/im-and-presence/im-and-presence.md)でのインスタント メッセージングとプレゼンスの展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f03eb-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="f03eb-107">Skype for Business Server でのインスタント メッセージングとプレゼンスの計画</span><span class="sxs-lookup"><span data-stu-id="f03eb-107">Plan for instant messaging and presence in Skype for Business Server</span></span>

<span data-ttu-id="f03eb-108">フロントエンド サーバーは、インスタント メッセージング (IM) やプレゼンスなどの Skype for Business Server のコア機能を提供し、すべての Skype for Business Server 展開に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f03eb-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="f03eb-109">利用できるエディションは 2 種類あり、主に大規模な組織向けに設計された Skype for Business Server Enterprise Edition と、ハードウェアへの投資が少ない、完全な高可用性オプションを必要としない小規模な組織向けに設計された Skype for Business Server Standard Edition があります。</span><span class="sxs-lookup"><span data-stu-id="f03eb-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="f03eb-110">どちらのエディションも、IM、プレゼンス、会議、および会議を含むすべての Skype for Business Server ワークロードをエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f03eb-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="f03eb-p103">インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。 2 パーティとマルチパーティの両方の IM セッションがサポートされています。 2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。 この際には、会議機能をサポートするように会話ウィンドウが変更されます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-p103">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="f03eb-115">プレゼンスは、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="f03eb-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="f03eb-116">ユーザーのプレゼンス状態は、他のユーザーがユーザーと連絡を取る必要があるかどうか、およびインスタント メッセージング、電話、または電子メールを使用するかどうかを決定するのに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f03eb-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="f03eb-117">プレゼンスにより、可能な場合は即時に通信しやすくなりますが、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="f03eb-118">このプレゼンス状態は、Skype for Business および Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Microsoft SharePoint テクノロジ、および Microsoft Office などの他のプレゼンス対応アプリケーションでプレゼンス アイコンとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="f03eb-119">プレゼンス アイコンは、ユーザーの現在の可用性と通信の意思を表します。</span><span class="sxs-lookup"><span data-stu-id="f03eb-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="f03eb-120">技術的要件</span><span class="sxs-lookup"><span data-stu-id="f03eb-120">Technical requirements</span></span>

<span data-ttu-id="f03eb-121">インスタント メッセージング (IM) とプレゼンスは、常に Enterprise Edition フロントエンド プールと Standard Edition サーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="f03eb-122">サポートされるハードウェア、オペレーティング システム、およびデータベース ソフトウェアの詳細については、「Certified  [Gateways」、Skype](../../SfbPartnerCertification/certification/infra-gateways.md)  [for Business 2015](requirements-for-your-environment/requirements-for-your-environment.md)環境の要件、 [および Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md)のインフラストラクチャ要件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f03eb-122">For information on supported hardware, operating systems, and database software, see  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="f03eb-123">外部ユーザーとの通信を有効にする</span><span class="sxs-lookup"><span data-stu-id="f03eb-123">Enabling communication with external users</span></span>

<span data-ttu-id="f03eb-124">ユーザーが外部ユーザーと通信できるようすることで、Skype for Business Server への投資のメリットを大幅に向上できます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-124">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="f03eb-125">外部ユーザーには次のユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-125">External users can include:</span></span>
  
- <span data-ttu-id="f03eb-126">リモート ユーザー: 組織のユーザーがファイアウォールの外側で作業し、ノート PC や他の Skype for Business Server デバイスを使用している場合。</span><span class="sxs-lookup"><span data-stu-id="f03eb-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="f03eb-127">フェデレーション ユーザー: Skype for Business Server も実行している、一緒に作業している会社のユーザー。</span><span class="sxs-lookup"><span data-stu-id="f03eb-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="f03eb-128">こちら側のユーザーがこれらのユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f03eb-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="f03eb-129">Skype ユーザー: Skype for Business ユーザーは、IM、音声、ビデオを使用して、Skype の数億人のユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f03eb-130">AOL、Yahoo、Google Talk はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f03eb-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f03eb-131">これらのシナリオの一部またはすべてを有効にするには、Skype for Business Server 展開と外部ユーザー間のセキュリティで保護された通信を有効にするのに役立つエッジ サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f03eb-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="f03eb-132">組織のリモート ユーザーとフェデレーション組織のユーザーは、IM を使用して互いにプレゼンスを確認し、通信することができます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f03eb-133">XMPP (Extensible Messaging and Presence Protocol) は、Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) 認定シナリオでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="f03eb-134">IM コンテンツのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="f03eb-134">Archiving IM content</span></span>

<span data-ttu-id="f03eb-135">Skype for Business Server は、組織がコンプライアンス規制に従う必要がある場合に使用できる機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f03eb-135">Skype for Business Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="f03eb-136">アーカイブを使用すると、組織内のすべてのユーザーまたは指定した特定のユーザーの IM メッセージの内容をアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-136">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="f03eb-137">詳細については [、「Skype for Business Server でのアーカイブの計画」を参照してください](archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="f03eb-137">For details, see [Plan for archiving in Skype for Business Server](archiving/archiving.md).</span></span> 
  
<span data-ttu-id="f03eb-138">Microsoft Exchange Server 2013 も展開している場合は、Exchange データのアーカイブと Skype for Business Server データのアーカイブを統合し、1 つのツールを使用して両方の種類のアーカイブ データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f03eb-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="f03eb-139">詳細については [、「Skype for Business Server を構成して](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)アーカイブを使用Exchange Server参照してください。</span><span class="sxs-lookup"><span data-stu-id="f03eb-139">For more information, see [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="f03eb-140">トポロジとコンポーネント</span><span class="sxs-lookup"><span data-stu-id="f03eb-140">Topologies and components</span></span>

<span data-ttu-id="f03eb-141">インスタント メッセージング (IM) とプレゼンスに必要なコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f03eb-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="f03eb-142">組織のフロントエンド サーバー (プールと呼ばれる) または Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="f03eb-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="f03eb-143">IM およびプレゼンス機能は、これらのサーバーで常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="f03eb-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="f03eb-144">フロントエンド プールのトポロジと管理の詳細については、「フロントエンド プールの高可用性と管理」 [を参照してください](high-availability-and-disaster-recovery/high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="f03eb-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="f03eb-145">ロード バランサー (Enterprise Edition フロントエンド プールがある場合)。</span><span class="sxs-lookup"><span data-stu-id="f03eb-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="f03eb-146">サポートされるコロケーション</span><span class="sxs-lookup"><span data-stu-id="f03eb-146">Supported collocation</span></span>

<span data-ttu-id="f03eb-147">複数の役割がインストールされた単一のサーバーまたはサーバーのグループが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f03eb-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="f03eb-148">コロケーションの詳細については [、「Topology Basics for Skype for Business Server」を参照してください](topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="f03eb-148">For details on collocation, see [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md).</span></span> 
  

