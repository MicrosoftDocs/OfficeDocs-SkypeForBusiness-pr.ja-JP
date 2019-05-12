---
title: Skype ビジネス サーバーのトポロジの基本
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '概要: は、Skype のビジネス サーバーのトポロジを選択します。 Skype のビジネス サーバー用のサーバーのコロケーションについて説明します。'
ms.openlocfilehash: 070f93867a841a3706dd9e3144ec5ba3a2e70da2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895090"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="360b8-104">Skype ビジネス サーバーのトポロジの基本</span><span class="sxs-lookup"><span data-stu-id="360b8-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="360b8-105">**の概要:** Skype のビジネス サーバーのトポロジを選択します。</span><span class="sxs-lookup"><span data-stu-id="360b8-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="360b8-106">Skype のビジネス サーバー用のサーバーのコロケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="360b8-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="360b8-107">その他の準備をする前に行う適切なトポロジの Skype のビジネス サーバーの配置を知りたいでしょう。</span><span class="sxs-lookup"><span data-stu-id="360b8-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="360b8-108">決定する必要があります最初には、ビジネスのサーバー用に Skype の設置型展開をする場合、またはハイブリッド展開でのサーバーをオンラインでビジネスの展開に、Skype でこれを結合しようとしている場合です。</span><span class="sxs-lookup"><span data-stu-id="360b8-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="360b8-109">どちらにしても、しようとしているさらに、読み取ろうとする設置型のトポロジーをここでは、詳細に説明してありますが、ハイブリッドの詳細は、専用のセクションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="360b8-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="360b8-110">[Skype ビジネス サーバーのトポロジを参照](reference-topologies.md)のいくつかのサンプル トポロジを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="360b8-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="360b8-111">サイト</span><span class="sxs-lookup"><span data-stu-id="360b8-111">Sites</span></span>

<span data-ttu-id="360b8-112">ビジネス サーバーの Skype、Skype にはビジネス サーバー コンポーネントが含まれているネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="360b8-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="360b8-113">サイトとは、1 つのローカル エリア ネットワーク (LAN)、または高速の光ファイバー ネットワークで接続された 2 つのネットワークなど、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。</span><span class="sxs-lookup"><span data-stu-id="360b8-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="360b8-114">ビジネス サーバー サイトの Skype は Active Directory ドメイン サービスのサイトおよび Microsoft Exchange Server サイトから別の概念であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="360b8-115">ビジネス サーバー サイトに、Skype は、Active Directory サイトに対応する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="360b8-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="360b8-116">Skype ビジネス サーバーの高可用性を実現し、場所の要件に応じて調整が可能、1 つまたは複数のサイトの設置型の展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="360b8-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="360b8-117">展開は、少なくとも 1 つのセントラル サイトが (データ センターとも呼ばれ、これは、データ ・ センターに含まれているすべてのサーバー) になり、各中央サイトを展開に 1 つの Standard Edition サーバーまたはエンタープライズ エディションのフロント エンド プールを少なくとも 1 つ。</span><span class="sxs-lookup"><span data-stu-id="360b8-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="360b8-118">以下に各オプションの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="360b8-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="360b8-119">標準エディションのサーバーに配置されている SQL Server Express データベースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="360b8-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="360b8-120">エンタープライズ エディションのフロント エンド プールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="360b8-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="360b8-121">1 つまたは複数フロント エンド サーバー (理想的には少なくとも 3 つ、拡張性のため)、最大 12 個のです。</span><span class="sxs-lookup"><span data-stu-id="360b8-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="360b8-122">サーバーが 2 台以上の場合は、負荷分散が必要になります。</span><span class="sxs-lookup"><span data-stu-id="360b8-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="360b8-123">個別バック エンド サーバーです。</span><span class="sxs-lookup"><span data-stu-id="360b8-123">A separate Back End Server.</span></span>

<span data-ttu-id="360b8-124">各サーバーの役割の詳細については、このセクションで後述します。</span><span class="sxs-lookup"><span data-stu-id="360b8-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="360b8-125">だけでなく、中央のサイトもにより、1 つまたは複数のブランチ サイトがセントラル サイトに関連付けられている終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="360b8-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="360b8-126">依存セントラル サイトのほぼすべての機能のため、構成を正確にどのようなですか。</span><span class="sxs-lookup"><span data-stu-id="360b8-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="360b8-127">リカバリ性に優れたブランチ アプライアンス ビジネス サーバーの機能のいくつかの Skype で、公衆交換電話網 (PSTN) ゲートウェイを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="360b8-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="360b8-128">存続可能ブランチ サーバー、それは、Skype をビジネス サーバーのレジストラーと仲介サーバー ソフトウェアがインストールされている Windows Server を実行するサーバーです。</span><span class="sxs-lookup"><span data-stu-id="360b8-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="360b8-129">スタンドアロン PSTN ゲートウェイ (リカバリ性に優れたブランチ アプライアンスの一部ではない)。</span><span class="sxs-lookup"><span data-stu-id="360b8-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="360b8-130">スタンドアロンの仲介サーバーまたはスタンドアロンの仲介サーバー プール (リカバリ性に優れたブランチ アプライアンスにこの役割に集約したくない) 場合。</span><span class="sxs-lookup"><span data-stu-id="360b8-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="360b8-131">ビジネス サーバー サイトに、Skype で何ですか。</span><span class="sxs-lookup"><span data-stu-id="360b8-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="360b8-132">詳細を得るには、セントラル サイトもあります。</span><span class="sxs-lookup"><span data-stu-id="360b8-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="360b8-133">(前述のとおり計画で、プールのバック エンド サーバーとフロント エンド プール内のすべてのフロント エンド サーバーが同じドメインにインストールする必要は) 別のドメイン、同じドメイン内の複数のフロント エンド プールです。</span><span class="sxs-lookup"><span data-stu-id="360b8-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="360b8-134">複数の Standard Edition サーバーです。</span><span class="sxs-lookup"><span data-stu-id="360b8-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="360b8-135">Office Web アプリケーション サーバー用に使用される Skype で Office の Web アプリを使用してビジネスのサーバーの共有と PowerPoint プレゼンテーションの表示。</span><span class="sxs-lookup"><span data-stu-id="360b8-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="360b8-136">エッジ サーバーまたはエッジ プールを (境界ネットワーク) です。</span><span class="sxs-lookup"><span data-stu-id="360b8-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="360b8-137">展開で、フェデレーション パートナー、パブリック IM 接続、XMPP (eXtensible Messaging and Presence Protocol) ゲートウェイ、およびリモート ユーザー アクセスをサポートする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="360b8-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="360b8-138">詳細については、エッジ サーバーの計画のドキュメントで参照できます。</span><span class="sxs-lookup"><span data-stu-id="360b8-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="360b8-139">永続的なチャット サーバーです。</span><span class="sxs-lookup"><span data-stu-id="360b8-139">Persistent Chat Server.</span></span> <span data-ttu-id="360b8-140">トピックに基づく長時間のマルチパーティ会話にユーザーが参加できるようにする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="360b8-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="360b8-141">「永続的なチャット サーバーの計画の詳細については。</span><span class="sxs-lookup"><span data-stu-id="360b8-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="360b8-142">監視。</span><span class="sxs-lookup"><span data-stu-id="360b8-142">Monitoring.</span></span> <span data-ttu-id="360b8-143">オーディオ/ビデオのデータの収集をサポートするために使用 (A/V) エクスペリエンスの品質 (QoE)、および呼び出しのエンタープライズ VoIP と記録 (CDR) の詳細と、展開での V 会議。</span><span class="sxs-lookup"><span data-stu-id="360b8-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="360b8-144">「計画」のドキュメントの「監視」トピックで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="360b8-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="360b8-145">ディレクターまたはディレクター プールです。</span><span class="sxs-lookup"><span data-stu-id="360b8-145">Director or Director pool.</span></span> <span data-ttu-id="360b8-146">必須ではありませんが便利な弾力性を向上し、Skype のユーザーのホーム プールにビジネス ユーザーの要求のリダイレクトを有効にする場合。</span><span class="sxs-lookup"><span data-stu-id="360b8-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="360b8-147">ダイレクタを展開する場合は、10 プールあたりの最大はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="360b8-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="360b8-148">必要がある場合は、確実で続行して取締役のトピックを計画します。</span><span class="sxs-lookup"><span data-stu-id="360b8-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="360b8-149">リバース プロキシです。</span><span class="sxs-lookup"><span data-stu-id="360b8-149">Reverse proxy.</span></span> <span data-ttu-id="360b8-150">Business Server のコンポーネントを Skype ではありませんが、これは、リモート ユーザーがアドレス帳、会議の参加などを使用する場合、トラフィックの移動をサポートする場合、フェデレーション ユーザーは、web コンテンツの共有をサポートする場合は、何かがわかるお客様の環境で便利です。</span><span class="sxs-lookup"><span data-stu-id="360b8-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="360b8-151">チェック アウトする詳細については、準備ができたら「リバース プロキシ サーバーの設定があります。</span><span class="sxs-lookup"><span data-stu-id="360b8-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="360b8-152">これらのサーバーの併置に関する追加情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="360b8-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="360b8-153">すべてのフロント エンド プールと Standard Edition サーバーが中央サイトで展開されている、次の共有に展開したと仮定した場合します。</span><span class="sxs-lookup"><span data-stu-id="360b8-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="360b8-154">ディレクターまたはディレクター プール</span><span class="sxs-lookup"><span data-stu-id="360b8-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="360b8-155">スタンドアロンの仲介サーバーまたは仲介サーバー プール</span><span class="sxs-lookup"><span data-stu-id="360b8-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="360b8-156">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="360b8-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="360b8-157">エッジ サーバーまたはエッジ プール</span><span class="sxs-lookup"><span data-stu-id="360b8-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="360b8-158">永続的なチャット サーバーまたは永続的なチャット サーバーのプール</span><span class="sxs-lookup"><span data-stu-id="360b8-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="360b8-159">監視</span><span class="sxs-lookup"><span data-stu-id="360b8-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="360b8-160">このボックスの一覧で Exchange ユニファイド メッセージング (UM) サーバーとは?</span><span class="sxs-lookup"><span data-stu-id="360b8-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="360b8-161">もちろん使用できます、Skype でビジネスのサーバーの Exchange UM と統合する場合は、コンポーネントではないビジネス サーバー サイトの場合は、Skype のため、私たちしているいないに言及している、ここで。</span><span class="sxs-lookup"><span data-stu-id="360b8-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="360b8-162">可能性があることを計画して、複数の中央サイトが存在して場合は、共有すること、以下のサーバーの役割、曲がることにより、セントラル サイトの場合。</span><span class="sxs-lookup"><span data-stu-id="360b8-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="360b8-163">スタンドアロンの仲介サーバーまたは仲介サーバー プール</span><span class="sxs-lookup"><span data-stu-id="360b8-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="360b8-164">エッジ サーバーまたはエッジ プール</span><span class="sxs-lookup"><span data-stu-id="360b8-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="360b8-165">永続的なチャット サーバーまたは永続的なチャット サーバーのプール</span><span class="sxs-lookup"><span data-stu-id="360b8-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="360b8-166">監視</span><span class="sxs-lookup"><span data-stu-id="360b8-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="360b8-167">最後のボックスの一覧と同じようにビジネス サーバー展開では、Skype の一部ではありませんが、すぎてここでは、同じカテゴリになったので、Exchange UM サーバーは、ここを含む私たちは。</span><span class="sxs-lookup"><span data-stu-id="360b8-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="360b8-168">もちろん、展開にはその他のコンポーネントやオプションを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="360b8-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="360b8-169">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="360b8-169">Firewalls</span></span>  <br/> |<span data-ttu-id="360b8-170">PSTN ゲートウェイ (エンタープライズ VoIP を展開する場合)</span><span class="sxs-lookup"><span data-stu-id="360b8-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="360b8-171">Exchange UM サーバー (Exchange UM と統合するには)</span><span class="sxs-lookup"><span data-stu-id="360b8-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="360b8-172">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="360b8-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="360b8-173">ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="360b8-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="360b8-174">SQL Server データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="360b8-175">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="360b8-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="360b8-176">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="360b8-176">Server roles</span></span>

<span data-ttu-id="360b8-177">Skype をビジネスのサーバーを実行する各サーバーでは、1 つまたは複数のサーバーの役割を実行します。</span><span class="sxs-lookup"><span data-stu-id="360b8-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="360b8-178">サーバーの役割は、そのサーバーによって提供されるビジネス サーバー機能の Skype の定義済みセットです。</span><span class="sxs-lookup"><span data-stu-id="360b8-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="360b8-179">ネットワークで使用できるサーバーの役割をすべて展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="360b8-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="360b8-180">必要な機能が含まれているサーバーの役割のみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="360b8-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="360b8-181">多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプールを展開して、スケーラビリティと高可用性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="360b8-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="360b8-182">プール内の各サーバーは同じサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="360b8-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="360b8-183">Skype ビジネス サーバー用のプールのほとんどの種類、プール内のさまざまなサーバー間のトラフィックを分散するロード バランサーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="360b8-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="360b8-184">Skype ビジネス サーバーは、ドメイン ネーム システム (DNS) の負荷分散とロード バランサーの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="360b8-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="360b8-185">フロントエンド サーバーおよびバックエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="360b8-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="360b8-186">ビジネス サーバー Enterprise Edition の Skype は、フロント エンド サーバーは、コア サーバーの役割. ビジネス サーバーの機能の多くの基本的な Skype を実行</span><span class="sxs-lookup"><span data-stu-id="360b8-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="360b8-187">バック エンド サーバーとフロント エンド サーバーは、すべての Skype ビジネス サーバー Enterprise Edition の展開に必要な唯一のサーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="360b8-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="360b8-188">フロント エンド プールは、ユーザーの一般的なグループのサービスを提供する連携して動作するフロント エンド サーバー、同じように構成のセットです。</span><span class="sxs-lookup"><span data-stu-id="360b8-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="360b8-189">同じ役割を実行している複数のサーバーのプールには、スケーラビリティとフェールオーバー機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="360b8-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="360b8-190">フロント エンド サーバーには次のものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="360b8-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="360b8-191">ユーザーの認証および登録。</span><span class="sxs-lookup"><span data-stu-id="360b8-191">User authentication and registration.</span></span>

- <span data-ttu-id="360b8-192">プレゼンス情報および連絡先カードの交換。</span><span class="sxs-lookup"><span data-stu-id="360b8-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="360b8-193">アドレス帳サービスおよび配布リスト展開。</span><span class="sxs-lookup"><span data-stu-id="360b8-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="360b8-194">IM 機能 (マルチパーティ IM 会議など)。</span><span class="sxs-lookup"><span data-stu-id="360b8-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="360b8-195">Web 会議、PSTN ダイヤルイン会議、および音声ビデオ会議 (展開されている場合)。</span><span class="sxs-lookup"><span data-stu-id="360b8-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="360b8-196">アプリケーションをホストしている、Skype ビジネス サーバー (たとえば、会議アテンダントや応答グループ アプリケーション) に含まれるアプリケーションとサードパーティ製のアプリケーションの両方にします。</span><span class="sxs-lookup"><span data-stu-id="360b8-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="360b8-197">オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。</span><span class="sxs-lookup"><span data-stu-id="360b8-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="360b8-198">この情報メディア (オーディオおよびビデオ) の品質に関するメトリックを提供するエンタープライズ VoIP 通話および A の両方のネットワークを通過する/V 会議。</span><span class="sxs-lookup"><span data-stu-id="360b8-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="360b8-199">Web Scheduler、Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="360b8-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="360b8-p119">オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。詳細については、「計画」のドキュメントの「[Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-p119">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons. For details, see [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in the Planning documentation.</span></span>

    <span data-ttu-id="360b8-202">Lync Server 2010 と以前のバージョンでは、監視およびアーカイブがないフロント エンド サーバーで同じ場所に別のサーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="360b8-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="360b8-203">オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。</span><span class="sxs-lookup"><span data-stu-id="360b8-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="360b8-p120">フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="360b8-p120">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="360b8-206">さらに、展開内の 1 つのフロント エンド サーバーはまた、中央管理サーバーを管理し、ビジネスのサーバーの Skype を実行しているすべてのサーバーに基本的な構成データを配置を実行します。</span><span class="sxs-lookup"><span data-stu-id="360b8-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="360b8-207">サーバーの全体管理サーバーでは、Lync Server 管理シェルとファイル転送の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="360b8-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="360b8-208">バック エンド サーバーは、フロント エンド プールのデータベース サービスを提供するように Microsoft SQL Server を実行しているデータベース サーバーです。</span><span class="sxs-lookup"><span data-stu-id="360b8-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="360b8-209">バック エンド サーバーはプールのユーザーおよび会議データのストアをバックアップとして、応答グループのデータベースなどの他のデータベースのプライマリ ストアです。</span><span class="sxs-lookup"><span data-stu-id="360b8-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="360b8-210">1 つバック エンド サーバーを持つことができますが、フェイル オーバー用[に Skype ビジネス サーバーのバック エンド サーバーの高可用性](../high-availability-and-disaster-recovery/back-end-server.md)をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="360b8-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="360b8-211">バック エンド サーバーでは、ビジネス ・ サーバ ・ ソフトウェアのすべての Skype は実行されません。</span><span class="sxs-lookup"><span data-stu-id="360b8-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="360b8-212">他のデータベースとビジネスのサーバー データベースの配置の Skype はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="360b8-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="360b8-213">併置すると、可用性とパフォーマンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="360b8-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="360b8-214">SQL ミラーリング ビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="360b8-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="360b8-215">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リング手法は、ビジネス サーバー 2019 の Skype で優先します。</span><span class="sxs-lookup"><span data-stu-id="360b8-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="360b8-216">バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="360b8-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="360b8-217">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="360b8-217">Edge Server</span></span>

<span data-ttu-id="360b8-218">エッジ サーバーは、通信し、組織のファイアウォールの外部のユーザーと共同作業するユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="360b8-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="360b8-219">これらの外部ユーザーは、現在オフサイトでの作業、フェデレーション パートナー組織のユーザーおよびビジネスのサーバーの展開に、Skype でホストされている会議に参加する招待されたユーザーの他のユーザーは、組織のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="360b8-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="360b8-220">エッジ サーバーを展開するにより、モバイル サービス、モバイル デバイスで Lync 機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="360b8-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="360b8-221">ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="360b8-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="360b8-222">さらに、モバイル デバイスは、クリックすると、会議、作業時間、1 つの数値に到達、ボイス メール、通話、不在着信の参加など、一部のエンタープライズ VoIP 機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="360b8-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="360b8-223">モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="360b8-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="360b8-224">プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="360b8-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="360b8-225">エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。</span><span class="sxs-lookup"><span data-stu-id="360b8-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="360b8-226">Skype は、インスタント メッセージングとプレゼンスの XMPP ベースのパートナーから連絡先を追加するのにはビジネスのサーバーのユーザーを有効にするには、これら XMPP コンポーネントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="360b8-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="360b8-227">XMPP ゲートウェイとプロキシ サーバー 2015 のビジネス用の Skype では利用ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="360b8-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="360b8-228">詳細については、[移行する XMPP フェデレーション](../../../SfBServer2019/migration/migrating-xmpp-federation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="360b8-229">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="360b8-229">Mediation Server</span></span>

<span data-ttu-id="360b8-230">仲介サーバーは、エンタープライズ VoIP、電話を使用して作業時間、およびダイヤルイン会議を実装するために必要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="360b8-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="360b8-231">仲介サーバーがシグナル、および、構成によっては、内部の Skype ビジネス サーバー インフラストラクチャの間でのメディアを変換し、パブリックの交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはセッション開始プロトコル (SIP) トランク。</span><span class="sxs-lookup"><span data-stu-id="360b8-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="360b8-232">仲介サーバーを実行するフロント エンド サーバーと同じサーバーに併設されているか、スタンドアロンの仲介サーバー プールに分離します。</span><span class="sxs-lookup"><span data-stu-id="360b8-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="360b8-233">詳細については、 [Skype のビジネス サーバーの仲介サーバーのコンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="360b8-234">ビデオ相互運用サーバー</span><span class="sxs-lookup"><span data-stu-id="360b8-234">Video Interop Server</span></span>

<span data-ttu-id="360b8-235">ビデオの相互運用機能のサーバーは、ビジネス サーバー 2015 の Skype の時点での新しい役割です。</span><span class="sxs-lookup"><span data-stu-id="360b8-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="360b8-236">特定のサード ・ パーティ製 VTC (ビデオ会議システム) のソリューションとビジネス サーバーの展開について、Skype を統合することができます。</span><span class="sxs-lookup"><span data-stu-id="360b8-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="360b8-237">VIS では、サード パーティ製のテレビ会議システムと、Skype ビジネス サーバーの展開の間の媒介手段として機能します。</span><span class="sxs-lookup"><span data-stu-id="360b8-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="360b8-238">このリリースでは、VIS は Cisco/Tandberg ビデオ システムとの相互運用性に焦点を合わせています。</span><span class="sxs-lookup"><span data-stu-id="360b8-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="360b8-239">詳細については、[ビジネス サーバーの Skype でのビデオの相互運用機能のサーバーの計画](../../plan-your-deployment/video-interop-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="360b8-240">ディレクター</span><span class="sxs-lookup"><span data-stu-id="360b8-240">Director</span></span>

<span data-ttu-id="360b8-241">ダイレクタは、サーバーのビジネス ユーザーの要求の Skype を認証できますが、ユーザー アカウントのホームやプレゼンスまたは会議サービスを提供できません。</span><span class="sxs-lookup"><span data-stu-id="360b8-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="360b8-242">ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="360b8-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="360b8-243">内部サーバーに要求を送信する前にディレクターで認証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="360b8-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="360b8-244">サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。</span><span class="sxs-lookup"><span data-stu-id="360b8-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="360b8-245">永続的なチャット サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="360b8-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="360b8-246">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="360b8-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="360b8-247">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="360b8-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="360b8-248">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-248">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="360b8-249">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="360b8-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="360b8-p133">常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="360b8-p133">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="360b8-254">ビジネス サーバーの標準エディションでは、永続的なチャットは実行可能も、Skype を実行しているサーバーは、同じサーバーに併設されています。</span><span class="sxs-lookup"><span data-stu-id="360b8-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="360b8-255">永続的なチャット フロント エンド サーバーとエンタープライズ エディションのフロント エンド サーバーを連結できません。</span><span class="sxs-lookup"><span data-stu-id="360b8-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="360b8-256">詳細については、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="360b8-257">高可用性および障害復旧のサポート</span><span class="sxs-lookup"><span data-stu-id="360b8-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="360b8-258">Skype ビジネス サーバーのプールを使用してサーバーの冗長性によって高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="360b8-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="360b8-259">特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。</span><span class="sxs-lookup"><span data-stu-id="360b8-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="360b8-260">同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。</span><span class="sxs-lookup"><span data-stu-id="360b8-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="360b8-261">Skype ビジネス サーバーも提供災害復旧対策プールの組み合わせを有効にするとします。</span><span class="sxs-lookup"><span data-stu-id="360b8-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="360b8-262">このトポロジを展開する場合は、フロント エンド プール、各プールを別のデータ センターと別の地理的な領域にある 2 つのペアを指定します。</span><span class="sxs-lookup"><span data-stu-id="360b8-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="360b8-263">1 つのプールまたはサイトで障害が発生した場合は、サービスの中断を最小限に抑えると、ペアで、他のプールを使用して、そのプールのユーザーをリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="360b8-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="360b8-264">ビジネス サーバーの Skype では、バック エンド サーバーの高可用性をいくつかのオプションもサポートします。</span><span class="sxs-lookup"><span data-stu-id="360b8-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="360b8-265">たとえば、以下のようなものです。</span><span class="sxs-lookup"><span data-stu-id="360b8-265">These include the following:</span></span>

- <span data-ttu-id="360b8-266">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="360b8-266">Database mirroring</span></span>

- <span data-ttu-id="360b8-267">AlwaysOn 可用性グループ</span><span class="sxs-lookup"><span data-stu-id="360b8-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="360b8-268">AlwaysOn フェールオーバー クラスターのインスタンス (FCI)</span><span class="sxs-lookup"><span data-stu-id="360b8-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="360b8-269">SQL フェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="360b8-269">SQL failover clustering</span></span>

<span data-ttu-id="360b8-270">プールの組み合わせとバック エンド サーバーの高可用性に関する詳細については、[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="360b8-271">Skype でビジネス サーバー用のサーバーのコロケーション</span><span class="sxs-lookup"><span data-stu-id="360b8-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="360b8-272">使用した用語が既に、まとめてですが、これはどういう意味でしょうか。</span><span class="sxs-lookup"><span data-stu-id="360b8-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="360b8-273">Skype ビジネス サーバーのでは、コロケーションでは、同じサーバー上または別のサーバー上にいくつかのサーバーの役割と機能を検索することができます。 が、Standard Edition または Enterprise Edition server を実行しているかどうかと、アウトを開始しているとき、混乱することができます。(それぞれが付属して、独自のルール) を展開します。</span><span class="sxs-lookup"><span data-stu-id="360b8-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="360b8-274">計画を支援するための Standard Edition サーバーの展開およびエンタープライズ エディションのフロント エンド プール展開サーバー コロケーションを含めています (この情報は、同じですが、ほとんどの場合と別である場合に呼び出されます具体的に)。</span><span class="sxs-lookup"><span data-stu-id="360b8-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="360b8-275">サーバーの役割の併置</span><span class="sxs-lookup"><span data-stu-id="360b8-275">Collocation of server roles</span></span>

<span data-ttu-id="360b8-276">Standard Edition サーバーには次の役割が 1 か所に配置 (追加の構成が必要ですが)、エンタープライズ エディションのフロント エンド プールの中にこのロールを 1 か所に配置したりできる別のサーバーに展開します。</span><span class="sxs-lookup"><span data-stu-id="360b8-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="360b8-277">仲介</span><span class="sxs-lookup"><span data-stu-id="360b8-277">Mediation</span></span>

<span data-ttu-id="360b8-278">次のサーバーの役割は、それぞれ別のサーバーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="360b8-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="360b8-279">ディレクター</span><span class="sxs-lookup"><span data-stu-id="360b8-279">Director</span></span>

- <span data-ttu-id="360b8-280">Edge</span><span class="sxs-lookup"><span data-stu-id="360b8-280">Edge</span></span>

- <span data-ttu-id="360b8-281">ビデオ相互運用サーバー</span><span class="sxs-lookup"><span data-stu-id="360b8-281">Video Interop Server</span></span>

- <span data-ttu-id="360b8-282">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="360b8-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="360b8-283">データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-283">Databases</span></span>

<span data-ttu-id="360b8-284">これは、する必要があります下にある 2 つのセクションでいくつか追加の規則の両方の後に、Standard Edition サーバーの展開と、Enterprise Edition サーバー プールの展開の間の実際の違いを持つ領域です。</span><span class="sxs-lookup"><span data-stu-id="360b8-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="360b8-285">Standard</span><span class="sxs-lookup"><span data-stu-id="360b8-285">Standard</span></span>

<span data-ttu-id="360b8-286">SQL Server Express は、Standard Edition サーバーに併設されているし、移動することはできません、ためこれは、非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="360b8-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="360b8-287">さらに、Standard Edition サーバー上で永続的なチャット サーバーを展開すると、進め方についても、永続的なチャットと Standard Edition サーバー上の永続的なチャット コンプライアンス データベースを連結することが必要はありません。</span><span class="sxs-lookup"><span data-stu-id="360b8-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

<span data-ttu-id="360b8-288">これらは、Standard Edition サーバー上に共存させることはできませんが、独自の 1 つのデータベース サーバーに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="360b8-288">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="360b8-289">監視データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-289">Monitoring database</span></span>

- <span data-ttu-id="360b8-290">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-290">Archiving database</span></span>

- <span data-ttu-id="360b8-291">エンタープライズ エディションのフロント エンド プールのバックエンド データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-291">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="360b8-292">Enterprise</span><span class="sxs-lookup"><span data-stu-id="360b8-292">Enterprise</span></span>

<span data-ttu-id="360b8-293">同じバックエンド SQL Server には、次のデータベースを共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="360b8-293">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="360b8-294">バックエンド データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-294">Back End database</span></span>

- <span data-ttu-id="360b8-295">監視データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-295">Monitoring database</span></span>

- <span data-ttu-id="360b8-296">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-296">Archiving database</span></span>

- <span data-ttu-id="360b8-297">永続的なチャット データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-297">Persistent Chat database</span></span>

- <span data-ttu-id="360b8-298">永続的なチャット コンプライアンス データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-298">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="360b8-299">両方</span><span class="sxs-lookup"><span data-stu-id="360b8-299">Both</span></span>

<span data-ttu-id="360b8-300">ここでは、Skype をビジネスのサーバー データベースの 1 つの SQL インスタンス、または同じ SQL Server データベース内の複数の SQL インスタンスに配置するときに準拠するいくつか追加の規則があります。</span><span class="sxs-lookup"><span data-stu-id="360b8-300">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="360b8-301">各 SQL インスタンスは、エンタープライズ エディションのフロント エンド プール、1 つの監視データベース、アーカイブ データベースを 1 つ、1 つの永続的なチャット データベース、および 1 つの永続的なチャット コンプライアンス データベースの 1 つのバック エンド データベースを含めることができますのみです。</span><span class="sxs-lookup"><span data-stu-id="360b8-301">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="360b8-302">データベース ・ サーバは、1 つ以上のエンタープライズ エディションのフロント エンド プール、アーカイブ、監視、1 つの永続的なチャット データベース、および永続的なチャット コンプライアンス、単一データベースを実行している 1 つのサーバーを実行している 1 つのサーバーをサポートできませんが、それぞれのいずれかをサポート関係なくかどうかデータベースを使用して SQL Server の同じインスタンスまたは SQL Server の個別のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="360b8-302">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="360b8-303">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="360b8-303">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="360b8-304">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="360b8-304">The same functionality is available in Teams.</span></span> <span data-ttu-id="360b8-305">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-305">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="360b8-306">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="360b8-306">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="360b8-307">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="360b8-307">File shares</span></span>

<span data-ttu-id="360b8-308">ファイル共有は、別個のサーバーに配置することも、次の一部またはすべてと同じサーバーに併置することもできます。</span><span class="sxs-lookup"><span data-stu-id="360b8-308">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="360b8-309">エンタープライズ エディションのフロント エンド プールのバック エンド サーバーを含む、データベース ・ サーバ</span><span class="sxs-lookup"><span data-stu-id="360b8-309">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="360b8-310">監視データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-310">Monitoring database</span></span>

- <span data-ttu-id="360b8-311">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-311">Archiving database</span></span>

- <span data-ttu-id="360b8-312">永続的なチャット データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-312">Persistent Chat database</span></span>

- <span data-ttu-id="360b8-313">永続的なチャット コンプライアンス データベース</span><span class="sxs-lookup"><span data-stu-id="360b8-313">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="360b8-p141">これらのサーバー上にファイル共有を並置することはできますが、この方法は推奨されていないことに注意してください。他のサーバーの役割を持つサーバー上にファイル共有を並置する場合は、ディスク空き容量と性能に関する問題を定期的に監視してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-p141">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it. If you'd collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="360b8-316">注意が必要な点</span><span class="sxs-lookup"><span data-stu-id="360b8-316">Keep in mind</span></span>

- <span data-ttu-id="360b8-317">Business Server のコンポーネントを Skype をされていないとできない場合がある場合でも、トポロジに、リバース プロキシ サーバーを連結できません。</span><span class="sxs-lookup"><span data-stu-id="360b8-317">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="360b8-318">リバース プロキシは、フェデレーション ユーザーを他の多くのものの中の web コンテンツの共有をサポートする場合は、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="360b8-318">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="360b8-319">必要がある場合は、既に他のアプリケーションによって使用されている、組織内にある既存のリバース プロキシ サーバーを構成することによって Skype のビジネス サーバー用のリバース プロキシ サポートを実装してください。</span><span class="sxs-lookup"><span data-stu-id="360b8-319">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="360b8-320">すべての Exchange UM のコンポーネントとビジネスのサーバーの役割に、Skype での SharePoint サーバーのコンポーネントを連結できません。</span><span class="sxs-lookup"><span data-stu-id="360b8-320">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="360b8-321">関連項目</span><span class="sxs-lookup"><span data-stu-id="360b8-321">See also</span></span>

[<span data-ttu-id="360b8-322">Skype ビジネス サーバーのトポロジを参照</span><span class="sxs-lookup"><span data-stu-id="360b8-322">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)
