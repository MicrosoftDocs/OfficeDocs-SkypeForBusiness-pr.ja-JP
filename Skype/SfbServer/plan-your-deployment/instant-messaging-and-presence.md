---
title: Skype for Business Server でインスタントメッセージとプレゼンスを計画する
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '概要: Skype for Business Server でインスタントメッセージングとプレゼンスを計画する方法について説明します。'
ms.openlocfilehash: d62559afe0c7767ee7863f41b41f2d1b64127643
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815905"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="73066-103">Skype for Business Server でインスタントメッセージとプレゼンスを計画する</span><span class="sxs-lookup"><span data-stu-id="73066-103">Plan for instant messaging and presence in Skype for Business Server</span></span>
 
<span data-ttu-id="73066-104">**概要:** Skype for Business Server でインスタントメッセージ (im) とプレゼンスを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73066-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server.</span></span>
  
<span data-ttu-id="73066-105">Skype for Business Server でインスタントメッセージとプレゼンスを計画します。</span><span class="sxs-lookup"><span data-stu-id="73066-105">Plan for instant messaging and presence in Skype for Business Server.</span></span> <span data-ttu-id="73066-106">オフラインインスタントメッセージング (IM) の有効化または無効化などの特定の展開オプションの詳細については、「 [Skype For Business Server でインスタントメッセージングとプレゼンスを展開](../deploy/im-and-presence/im-and-presence.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73066-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="73066-107">Skype for Business Server でインスタントメッセージとプレゼンスを計画する</span><span class="sxs-lookup"><span data-stu-id="73066-107">Plan for instant messaging and presence in Skype for Business Server</span></span>

<span data-ttu-id="73066-108">フロントエンドサーバーは、インスタントメッセージング (IM) やプレゼンスなどの Skype for business Server の主要な機能を提供し、すべての Skype for Business Server の展開に含まれています。</span><span class="sxs-lookup"><span data-stu-id="73066-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="73066-109">次の2つのエディションを使用できます。 Skype for Business Server Enterprise Edition は、主に大規模な組織向けに設計されており、Skype for Business Server Standard Edition 向けに設計されています。ハードウェアへの投資。高可用性の完全なオプションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="73066-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="73066-110">どちらのエディションも、IM、プレゼンス、会議、エンタープライズ Voip などのすべての Skype for Business Server のワークロードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="73066-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="73066-111">インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="73066-111">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="73066-112">2 パーティとマルチパーティの両方の IM セッションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73066-112">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="73066-113">2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。</span><span class="sxs-lookup"><span data-stu-id="73066-113">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="73066-114">この際には、会議機能をサポートするように会話ウィンドウが変更されます。</span><span class="sxs-lookup"><span data-stu-id="73066-114">When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="73066-115">プレゼンスは、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="73066-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="73066-116">ユーザーのプレゼンス状態は、ユーザーに連絡を試みる必要があるかどうか、またインスタントメッセージング、電話、メールのどちらを使用するかを他のユーザーが判断するのに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="73066-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="73066-117">プレゼンスにより、可能な場合にはすぐにやりとりできますが、他にも、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。</span><span class="sxs-lookup"><span data-stu-id="73066-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="73066-118">プレゼンス状態は、Skype for Business およびその他のプレゼンス対応のアプリケーション (Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Microsoft SharePoint テクノロジ、Microsoft Office など) で、プレゼンス アイコンとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="73066-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="73066-119">プレゼンスアイコンは、ユーザーの現在の可用性とコミュニケーションの意思を示します。</span><span class="sxs-lookup"><span data-stu-id="73066-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="73066-120">技術要件</span><span class="sxs-lookup"><span data-stu-id="73066-120">Technical requirements</span></span>

<span data-ttu-id="73066-121">インスタント メッセージング (IM) とプレゼンスは、常に Enterprise Edition フロントエンド プールと Standard Edition サーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="73066-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="73066-122">サポートされているハードウェア、オペレーティングシステム、データベースソフトウェアの詳細については、[認定ゲートウェイ](../../SfbPartnerCertification/certification/infra-gateways.md)、 [skype for business 2015 環境の要件](requirements-for-your-environment/requirements-for-your-environment.md)、および[skype For business Server 2019 のインフラストラクチャ要件](../../SfBServer2019/plan/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73066-122">For information on supported hardware, operating systems, and database software, see  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="73066-123">外部ユーザーとの通信を有効にする</span><span class="sxs-lookup"><span data-stu-id="73066-123">Enabling communication with external users</span></span>

<span data-ttu-id="73066-124">ユーザーが外部ユーザーと通信できるようにすることで、Skype for Business Server での投資のメリットを大幅に向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="73066-124">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="73066-125">外部ユーザーには次のユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="73066-125">External users can include:</span></span>
  
- <span data-ttu-id="73066-126">リモートユーザー: ファイアウォール外で作業していて、自分のラップトップやその他の Skype for Business Server デバイスを使っている場合に、組織の独自のユーザー。</span><span class="sxs-lookup"><span data-stu-id="73066-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="73066-127">フェデレーションユーザー: Skype for Business Server も実行している会社のユーザー。</span><span class="sxs-lookup"><span data-stu-id="73066-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="73066-128">自社ユーザーがこうしたユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73066-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="73066-129">Skype ユーザー:   Skype for Business ユーザーは、Skype で IM、音声、ビデオを使用して数億人のユーザーと連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="73066-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="73066-130">AOL、Yahoo、Google Talk はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="73066-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="73066-131">これらのシナリオのいずれか、またはすべてを有効にするには、microsoft Edge Server を展開して、Skype for Business Server の展開と外部ユーザー間の通信をセキュリティで保護できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73066-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="73066-132">組織のリモートユーザーとフェデレーションされた組織のユーザーは、互いのプレゼンスを表示して、IM を使って通信することができます。</span><span class="sxs-lookup"><span data-stu-id="73066-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="73066-133">XMPP (eXtensible Messaging and Presence Protocol) は、Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) 証明書シナリオでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="73066-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="73066-134">IM コンテンツをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="73066-134">Archiving IM content</span></span>

<span data-ttu-id="73066-135">Skype for Business Server には、組織が法令遵守法に準拠する必要がある場合に使用できる機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="73066-135">Skype for Business Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="73066-136">アーカイブを使用すると、組織内のすべてのユーザーまたは指定する特定のユーザーの IM メッセージの内容をアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="73066-136">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="73066-137">詳細については、「 [Skype For Business Server でのアーカイブの計画](archiving/archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73066-137">For details, see [Plan for archiving in Skype for Business Server](archiving/archiving.md).</span></span> 
  
<span data-ttu-id="73066-138">Microsoft Exchange Server 2013 が展開されている場合は、Exchange データのアーカイブを Skype for Business Server データのアーカイブと統合することができます。また、単一のツールを使用して、両方の種類のアーカイブデータを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="73066-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="73066-139">詳細については、「 [Exchange server のアーカイブを使用するように Skype For Business server を構成する](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73066-139">For more information, see [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="73066-140">トポロジとコンポーネント</span><span class="sxs-lookup"><span data-stu-id="73066-140">Topologies and components</span></span>

<span data-ttu-id="73066-141">インスタント メッセージング (IM) とプレゼンスに必要なコンポーネントは、次に示すものだけです。</span><span class="sxs-lookup"><span data-stu-id="73066-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="73066-142">組織のフロントエンドサーバー (プールとも呼ばれます) または Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="73066-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="73066-143">これらのサーバーで、IM およびプレゼンス機能は常にオンになっています。</span><span class="sxs-lookup"><span data-stu-id="73066-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="73066-144">フロントエンドプールのトポロジと管理の詳細については、「[フロントエンドプールの高可用性と管理](high-availability-and-disaster-recovery/high-availability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73066-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="73066-145">ロード バランサー (Enterprise Edition フロントエンド プールがある場合)</span><span class="sxs-lookup"><span data-stu-id="73066-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="73066-146">サポートされる併置</span><span class="sxs-lookup"><span data-stu-id="73066-146">Supported collocation</span></span>

<span data-ttu-id="73066-147">併置の定義は、複数の役割がインストールされた単一のサーバーまたはサーバー グループが存在することです。</span><span class="sxs-lookup"><span data-stu-id="73066-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="73066-148">Collocation の詳細については、「 [Skype For Business Server のトポロジの基礎](topology-basics/topology-basics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73066-148">For details on collocation, see [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md).</span></span> 
  

