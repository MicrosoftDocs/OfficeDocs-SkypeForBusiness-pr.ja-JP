---
title: Skype for Business Server のトポロジの基本
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
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '概要: Skype for Business Server のトポロジを選択します。 Skype for Business Server のサーバーのコロケーションについて学習します。'
ms.openlocfilehash: 39a75de6162f51d5d838ace557a546db3500ac01
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103993"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="c7655-104">Skype for Business Server のトポロジの基本</span><span class="sxs-lookup"><span data-stu-id="c7655-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="c7655-105">**概要:** Skype for Business Server のトポロジを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7655-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="c7655-106">Skype for Business Server のサーバーのコロケーションについて学習します。</span><span class="sxs-lookup"><span data-stu-id="c7655-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="c7655-107">他に何かを準備する前に、Skype for Business Server の展開に適切なトポロジを計画している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7655-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="c7655-108">最初に決定する必要があるのは、Skype for Business Server のオンプレミス展開を行う場合か、ハイブリッド展開で Skype for Business Server Online 展開と組み合わせる場合です。</span><span class="sxs-lookup"><span data-stu-id="c7655-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="c7655-109">いずれにしろ、ここではオンプレミス のトポロジについて詳しく説明しますが、ハイブリッドの詳細は独自のセクションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="c7655-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="c7655-110">トポロジの例については [、「Skype for Business Server のリファレンス トポロジ」でも確認できます](reference-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="c7655-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="c7655-111">サイト</span><span class="sxs-lookup"><span data-stu-id="c7655-111">Sites</span></span>

<span data-ttu-id="c7655-112">Skype for Business Server では、Skype for Business Server コンポーネントを含むネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c7655-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="c7655-113">サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。</span><span class="sxs-lookup"><span data-stu-id="c7655-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="c7655-114">Skype for Business Server サイトは、Active Directory ドメイン サービス サイトおよびサイトと別の概念Microsoft Exchange Server注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7655-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="c7655-115">Skype for Business Server サイトは、Active Directory サイトに対応する必要はない。</span><span class="sxs-lookup"><span data-stu-id="c7655-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="c7655-116">Skype for Business Server は、高可用性と場所の要件に応じて拡張できる 1 つ以上のサイトのオンプレミス展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c7655-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="c7655-117">展開には、少なくとも 1 つの中央サイト (データセンターとも呼ばれるデータセンター)が存在し、展開内の各中央サイトには Standard Edition サーバーが 1 つ、または少なくとも 1 つの Enterprise Edition フロント エンド プールがあります。</span><span class="sxs-lookup"><span data-stu-id="c7655-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="c7655-118">以下の各オプションの違いを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="c7655-119">Standard Edition サーバーには、Express データベースにSQL Serverが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7655-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="c7655-120">Enterprise Edition フロントエンド プールには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c7655-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="c7655-121">1 つ以上のフロント エンド サーバー (スケーラビリティの場合は 3 つ以上が理想的です)。最大 12 個。</span><span class="sxs-lookup"><span data-stu-id="c7655-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="c7655-122">複数のサーバーで負荷分散が必要になります。</span><span class="sxs-lookup"><span data-stu-id="c7655-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="c7655-123">別のバック エンド サーバー。</span><span class="sxs-lookup"><span data-stu-id="c7655-123">A separate Back End Server.</span></span>

<span data-ttu-id="c7655-124">このセクションでは、さまざまなサーバーの役割について少し後で説明します。</span><span class="sxs-lookup"><span data-stu-id="c7655-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="c7655-125">中央サイトに加えて、1 つ以上のブランチ サイトが中央サイトに関連付けられる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c7655-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="c7655-126">これらは、ほぼすべての機能について中央サイトに依存しています。したがって、それらは正確に何で構成されていますか?</span><span class="sxs-lookup"><span data-stu-id="c7655-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="c7655-127">一部の Skype for Business Server 機能と公衆交換電話網 (PSTN) ゲートウェイを組み合わせた存続可能ブランチ アプライアンス。</span><span class="sxs-lookup"><span data-stu-id="c7655-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="c7655-128">存続可能ブランチ サーバー、Skype for Business Server レジストラーと仲介サーバー ソフトウェアがインストールされている Windows Server を実行しているサーバーです。</span><span class="sxs-lookup"><span data-stu-id="c7655-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="c7655-129">スタンドアロン PSTN ゲートウェイ (存続可能ブランチ アプライアンスの一部ではありません)。</span><span class="sxs-lookup"><span data-stu-id="c7655-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="c7655-130">スタンドアロン仲介サーバーまたはスタンドアロンの仲介サーバー プール (この役割を存続可能ブランチ アプライアンスに関連付けたくない場合)。</span><span class="sxs-lookup"><span data-stu-id="c7655-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="c7655-131">Skype for Business Server サイトの内容</span><span class="sxs-lookup"><span data-stu-id="c7655-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="c7655-132">詳細を確認するには、中央サイトに次の情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="c7655-133">同じドメインまたは異なるドメイン内の複数のフロントエンド プール (フロント エンド プール内のすべてのフロント エンド サーバーと、プールのバック エンド サーバーが同じドメイン内にいる必要があるという計画に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="c7655-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="c7655-134">複数の Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="c7655-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="c7655-135">Office Web Apps サーバーは、PowerPoint プレゼンテーションの共有とレンダリングOffice Skype for Business Server の Web アプリと一緒に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7655-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="c7655-136">エッジ サーバーまたはエッジ プール (境界ネットワーク内)。</span><span class="sxs-lookup"><span data-stu-id="c7655-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="c7655-137">展開でフェデレーション パートナー、パブリック IM 接続、拡張メッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイ、およびリモート ユーザー アクセスをサポートする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="c7655-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="c7655-138">詳細については、エッジ サーバー計画のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7655-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="c7655-139">常設チャット サーバー。</span><span class="sxs-lookup"><span data-stu-id="c7655-139">Persistent Chat Server.</span></span> <span data-ttu-id="c7655-140">ユーザーが、時間のかかる複数のトピックベースの会話に参加できる場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c7655-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="c7655-141">詳細については、「常設チャット サーバーの計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7655-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="c7655-142">監視。</span><span class="sxs-lookup"><span data-stu-id="c7655-142">Monitoring.</span></span> <span data-ttu-id="c7655-143">展開内の エンタープライズ VoIP 会議および音声ビデオ会議の音声/ビデオ (A/V) Quality of Experience (QoE) および通話詳細記録 (CDR) のデータ収集をサポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7655-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="c7655-144">詳細については、「監視の計画」トピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="c7655-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="c7655-145">ディレクターまたはディレクター プール。</span><span class="sxs-lookup"><span data-stu-id="c7655-145">Director or Director pool.</span></span> <span data-ttu-id="c7655-146">必要ありませんが、復元性を向上し、ユーザーのホーム プールへの Skype for Business ユーザー要求のリダイレクトを有効にする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c7655-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="c7655-147">ディレクターを展開する場合は、プールごとに最大 10 がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7655-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="c7655-148">これが必要な場合は、必ず「ディレクターの計画」のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c7655-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="c7655-149">リバース プロキシ。</span><span class="sxs-lookup"><span data-stu-id="c7655-149">Reverse proxy.</span></span> <span data-ttu-id="c7655-150">これは Skype for Business Server コンポーネントではなく、フェデレーション ユーザー用の Web コンテンツの共有をサポートする場合、Mobility トラフィックをサポートする場合、リモート ユーザーがアドレス帳を使用する場合、会議に参加する場合など、これは環境で必要になります。</span><span class="sxs-lookup"><span data-stu-id="c7655-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="c7655-151">準備ができたら、詳細を確認できるリバース プロキシ サーバーの設定に関するトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="c7655-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="c7655-152">これらのサーバーのコロケーションに関する追加情報は、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c7655-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="c7655-153">中央サイトに展開されているフロントエンド プールと Standard Edition サーバーはすべて、展開したと仮定して、次の情報を共有します。</span><span class="sxs-lookup"><span data-stu-id="c7655-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="c7655-154">ディレクターまたはディレクター プール</span><span class="sxs-lookup"><span data-stu-id="c7655-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="c7655-155">スタンドアロン仲介サーバーまたは仲介サーバー プール</span><span class="sxs-lookup"><span data-stu-id="c7655-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="c7655-156">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="c7655-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="c7655-157">エッジ サーバーまたはエッジ プール</span><span class="sxs-lookup"><span data-stu-id="c7655-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="c7655-158">常設チャット サーバーまたは常設チャット サーバー プール</span><span class="sxs-lookup"><span data-stu-id="c7655-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="c7655-159">監視</span><span class="sxs-lookup"><span data-stu-id="c7655-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="c7655-160">この一覧の Exchange ユニファイド メッセージング (UM) サーバーの場所</span><span class="sxs-lookup"><span data-stu-id="c7655-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="c7655-161">Exchange UM と統合する場合は、Skype for Business Server で使用できますが、Skype for Business Server サイトのコンポーネントではないので、ここでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="c7655-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="c7655-162">複数のセントラル サイトを使用する予定の場合、中央サイトに展開されている場合は、次のサーバーと役割を共有できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c7655-163">スタンドアロン仲介サーバーまたは仲介サーバー プール</span><span class="sxs-lookup"><span data-stu-id="c7655-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="c7655-164">エッジ サーバーまたはエッジ プール</span><span class="sxs-lookup"><span data-stu-id="c7655-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="c7655-165">常設チャット サーバーまたは常設チャット サーバー プール</span><span class="sxs-lookup"><span data-stu-id="c7655-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="c7655-166">監視</span><span class="sxs-lookup"><span data-stu-id="c7655-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="c7655-167">最後のリストと同様に、Exchange UM Server は Skype for Business Server 展開の一部ではないのでここには含めず、ここでも同じカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="c7655-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="c7655-168">もちろん、展開には他にもいくつかのコンポーネントとオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c7655-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c7655-169">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="c7655-169">Firewalls</span></span>  <br/> |<span data-ttu-id="c7655-170">PSTN ゲートウェイ (PSTN ゲートウェイを展開するエンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="c7655-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="c7655-171">Exchange UM Server (Exchange UM と統合する場合)</span><span class="sxs-lookup"><span data-stu-id="c7655-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="c7655-172">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="c7655-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="c7655-173">ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="c7655-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="c7655-174">SQL Server データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="c7655-175">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="c7655-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="c7655-176">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="c7655-176">Server roles</span></span>

<span data-ttu-id="c7655-177">Skype for Business Server を実行している各サーバーは、1 つ以上のサーバーの役割を実行します。</span><span class="sxs-lookup"><span data-stu-id="c7655-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="c7655-178">サーバーの役割は、そのサーバーによって提供される Skype for Business Server の機能の定義済みのセットです。</span><span class="sxs-lookup"><span data-stu-id="c7655-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="c7655-179">ネットワークで使用可能なすべてのサーバーの役割を展開する必要はない。</span><span class="sxs-lookup"><span data-stu-id="c7655-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="c7655-180">必要な機能が含まれているサーバーの役割のみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c7655-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="c7655-181">多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプールを展開して、スケーラビリティと高可用性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="c7655-182">プール内の各サーバーは同じサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7655-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="c7655-183">Skype for Business Server のほとんどの種類のプールでは、プール内のさまざまなサーバー間でトラフィックを分散するためにロード バランサーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7655-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="c7655-184">Skype for Business Server は、ドメイン ネーム システム (DNS) 負荷分散とハードウェア ロード バランサーの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c7655-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="c7655-185">フロントエンド サーバーおよびバック エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="c7655-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="c7655-186">Skype for Business Server Enterprise Edition では、フロント エンド サーバーがコア サーバーの役割であり、多くの基本的な Skype for Business Server 機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="c7655-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="c7655-187">フロントエンド サーバーは、バック エンド サーバーと共に、Skype for Business Server Enterprise Edition 展開に必要な唯一のサーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="c7655-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="c7655-188">フロントエンド プールは、同じ構成のフロント エンド サーバーのセットで、共通のユーザー グループにサービスを提供するために一緒に動作します。</span><span class="sxs-lookup"><span data-stu-id="c7655-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="c7655-189">同じ役割を実行している複数のサーバーのプールは、スケーラビリティとフェールオーバー機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c7655-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="c7655-190">フロントエンド サーバーには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="c7655-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="c7655-191">ユーザー認証と登録。</span><span class="sxs-lookup"><span data-stu-id="c7655-191">User authentication and registration.</span></span>

- <span data-ttu-id="c7655-192">プレゼンス情報と連絡先カード交換。</span><span class="sxs-lookup"><span data-stu-id="c7655-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="c7655-193">アドレス帳サービスと配布リストの拡張。</span><span class="sxs-lookup"><span data-stu-id="c7655-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="c7655-194">マルチパーティ IM 会議を含む IM 機能。</span><span class="sxs-lookup"><span data-stu-id="c7655-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="c7655-195">Web 会議、PSTN ダイヤルイン会議、音声ビデオ会議 (展開されている場合)。</span><span class="sxs-lookup"><span data-stu-id="c7655-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="c7655-196">Skype for Business Server に含まれる両方のアプリケーション (会議アテンダント アプリケーションと応答グループ アプリケーションなど) のアプリケーションホスティング、およびサードパーティ製アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c7655-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="c7655-197">オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。</span><span class="sxs-lookup"><span data-stu-id="c7655-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="c7655-198">この情報は、音声通話と音声ビデオ会議の両方でネットワークを通過するメディア (オーディオとビデオ) の品質に関するエンタープライズ VoIPを提供します。</span><span class="sxs-lookup"><span data-stu-id="c7655-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="c7655-199">Web スケジューラーや Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="c7655-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="c7655-200">オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。</span><span class="sxs-lookup"><span data-stu-id="c7655-200">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="c7655-201">詳細については、「計画」のドキュメントの「[Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7655-201">For details, see [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) in the Planning documentation.</span></span>

    <span data-ttu-id="c7655-202">Lync Server 2010 以前のバージョンでは、監視とアーカイブは、フロント エンド サーバー上ではなく、個別のサーバーの役割でした。</span><span class="sxs-lookup"><span data-stu-id="c7655-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="c7655-203">オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。</span><span class="sxs-lookup"><span data-stu-id="c7655-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="c7655-p120">フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="c7655-p120">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="c7655-206">さらに、展開内の 1 つのフロント エンド サーバーでは、サーバーの全体管理サーバーも実行され、Skype for Business Server を実行しているすべてのサーバーに基本的な構成データを管理および展開します。</span><span class="sxs-lookup"><span data-stu-id="c7655-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="c7655-207">また、サーバーの全体管理サーバーには、Lync Server 管理シェルとファイル転送機能も用意されています。</span><span class="sxs-lookup"><span data-stu-id="c7655-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="c7655-208">バック エンド サーバーは、フロントエンド Microsoft SQL Serverデータベース サービスを提供するデータベース サーバーです。</span><span class="sxs-lookup"><span data-stu-id="c7655-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="c7655-209">バック エンド サーバーは、プールのユーザーおよび会議データのバックアップ ストアとして機能し、応答グループ データベースなどの他のデータベースのプライマリ ストアです。</span><span class="sxs-lookup"><span data-stu-id="c7655-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="c7655-210">単一のバック エンド サーバーを使用できますが、フェールオーバーには [Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) のバック エンド サーバーの高可用性をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7655-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="c7655-211">バック エンド サーバーは、Skype for Business Server ソフトウェアを実行しません。</span><span class="sxs-lookup"><span data-stu-id="c7655-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7655-212">Skype for Business Server データベースを他のデータベースと照合はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="c7655-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="c7655-213">併置すると、可用性とパフォーマンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="c7655-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="c7655-214">SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c7655-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c7655-215">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、Skype for Business Server 2019 で優先されます。</span><span class="sxs-lookup"><span data-stu-id="c7655-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="c7655-216">バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="c7655-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="c7655-217">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="c7655-217">Edge Server</span></span>

<span data-ttu-id="c7655-218">エッジ サーバーを使用すると、ユーザーは組織のファイアウォール外のユーザーと通信して共同作業できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="c7655-219">これらの外部ユーザーには、現在オフサイトで作業している組織の独自のユーザー、フェデレーション パートナー組織のユーザー、Skype for Business Server 展開でホストされている会議に参加するために招待された外部ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c7655-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="c7655-220">エッジ サーバーを展開すると、モバイル デバイスで Lync 機能をサポートするモビリティ サービスも有効になります。</span><span class="sxs-lookup"><span data-stu-id="c7655-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="c7655-221">ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="c7655-222">また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7655-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="c7655-223">モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7655-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="c7655-224">プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="c7655-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="c7655-225">エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c7655-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="c7655-226">これらの XMPP コンポーネントを構成して、Skype for Business Server ユーザーがインスタント メッセージングとプレゼンスのために XMPP ベースのパートナーから連絡先を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="c7655-227">XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c7655-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c7655-228">詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7655-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="c7655-229">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="c7655-229">Mediation Server</span></span>

<span data-ttu-id="c7655-230">仲介サーバーは、電話会議、通話エンタープライズ VoIPダイヤルイン会議を実装するために必要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="c7655-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="c7655-231">仲介サーバーは、内部の Skype for Business Server インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはセッション開始プロトコル (SIP) トランクとの間で、シグナリングを変換し、一部の構成ではメディアを変換します。</span><span class="sxs-lookup"><span data-stu-id="c7655-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="c7655-232">フロントエンド サーバーと同じサーバーに配置されている、またはスタンドアロンの仲介サーバー プールに分離されている仲介サーバーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="c7655-233">詳細については [、「Skype for Business Server の仲介サーバー コンポーネント」を参照してください](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c7655-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="c7655-234">ビデオ相互運用サーバー</span><span class="sxs-lookup"><span data-stu-id="c7655-234">Video Interop Server</span></span>

<span data-ttu-id="c7655-235">ビデオ相互運用サーバーは、Skype for Business Server 2015 の新しい役割です。</span><span class="sxs-lookup"><span data-stu-id="c7655-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="c7655-236">これにより、Skype for Business Server 展開を特定のサードパーティ VTC (ビデオ 電話会議システム) ソリューションと統合できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="c7655-237">VIS は、サードパーティの電話会議システムと Skype for Business Server 展開の間の仲介者として機能します。</span><span class="sxs-lookup"><span data-stu-id="c7655-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="c7655-238">このリリースでは、VIS は、Cisco/Tandberg ビデオ システムとの相互運用性に重点を置いされています。</span><span class="sxs-lookup"><span data-stu-id="c7655-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="c7655-239">詳細については [、「Plan for Video Interop Server in Skype for Business Server」を参照してください](../../plan-your-deployment/video-interop-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c7655-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="c7655-240">ディレクター</span><span class="sxs-lookup"><span data-stu-id="c7655-240">Director</span></span>

<span data-ttu-id="c7655-241">ディレクターは Skype for Business Server ユーザー要求を認証できますが、ユーザー アカウントを使用したり、プレゼンスサービスや会議サービスを提供したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c7655-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="c7655-242">ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c7655-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="c7655-243">内部サーバーに要求を送信する前にディレクターで認証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="c7655-244">サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。</span><span class="sxs-lookup"><span data-stu-id="c7655-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="c7655-245">常設チャット サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="c7655-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="c7655-246">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c7655-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c7655-247">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="c7655-248">詳細については、「Microsoft Teams のアップグレードの [開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="c7655-248">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c7655-249">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="c7655-p133">常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-p133">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="c7655-254">Skype for Business Server Standard Edition を実行しているサーバーは、同じサーバー上で常設チャットを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7655-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="c7655-255">常設チャット フロント エンド サーバーを Enterprise Edition フロント エンド サーバーと照合することはできません。</span><span class="sxs-lookup"><span data-stu-id="c7655-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="c7655-256">詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015」を参照してください](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c7655-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="c7655-257">高可用性と障害復旧のサポート</span><span class="sxs-lookup"><span data-stu-id="c7655-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="c7655-258">Skype for Business Server は、プールを介してサーバーの冗長性によって高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="c7655-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="c7655-259">あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="c7655-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="c7655-260">これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c7655-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="c7655-261">Skype for Business Server は、プールのペアリングを有効にすることで障害復旧対策も提供します。</span><span class="sxs-lookup"><span data-stu-id="c7655-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="c7655-262">このトポロジを展開する場合は、フロント エンド プールのペアを指定します。各プールは、1 つのペア内の個別のデータ センター内にあり、別の地理的領域に配置されます。</span><span class="sxs-lookup"><span data-stu-id="c7655-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="c7655-263">1 つのプールまたはサイトがダウンした場合は、そのプールのユーザーをリダイレクトして、サービスの中断を最小限に抑え、ペアの他のプールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="c7655-264">Skype for Business Server では、バック エンド サーバーの高可用性に関する複数のオプションもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c7655-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="c7655-265">これらには次のコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="c7655-265">These include the following:</span></span>

- <span data-ttu-id="c7655-266">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="c7655-266">Database mirroring</span></span>

- <span data-ttu-id="c7655-267">AlwaysOn 可用性グループ</span><span class="sxs-lookup"><span data-stu-id="c7655-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="c7655-268">AlwaysOn フェールオーバー クラスター インスタンス (FCI)</span><span class="sxs-lookup"><span data-stu-id="c7655-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="c7655-269">SQLフェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="c7655-269">SQL failover clustering</span></span>

<span data-ttu-id="c7655-270">プールのペアリングとバック エンド サーバーの高可用性の詳細については、「Skype for Business Server で高可用性と障害復旧を計画する [」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c7655-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="c7655-271">Skype for Business Server でのサーバーのコロケーション</span><span class="sxs-lookup"><span data-stu-id="c7655-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="c7655-272">既に collocate という用語を使用していますが、これはどういう意味ですか?</span><span class="sxs-lookup"><span data-stu-id="c7655-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="c7655-273">Skype for Business Server を使用すると、同じサーバー上の一部のサーバーの役割と機能 (コロケーション、または異なるサーバー) を検索できますが、開始する際、および Standard Edition または Enterprise Edition サーバーの展開を行っているかどうか (それぞれに独自のルールが含まれています) 場合、混乱する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7655-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="c7655-274">計画を立て支援するために、Standard Edition サーバー展開と Enterprise Edition フロントエンド プール展開にサーバーコロケーションを含めます (ほとんどの場合、この情報は同一であり、異なる場合は特に呼び出されます)。</span><span class="sxs-lookup"><span data-stu-id="c7655-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="c7655-275">サーバーの役割のコロケーション</span><span class="sxs-lookup"><span data-stu-id="c7655-275">Collocation of server roles</span></span>

<span data-ttu-id="c7655-276">Standard Edition サーバーには次の役割があります (追加の構成が必要ですが、追加の構成が必要です)、Enterprise Edition フロント エンド プールでは、この役割をコロケーションするか、別のサーバーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="c7655-277">仲介</span><span class="sxs-lookup"><span data-stu-id="c7655-277">Mediation</span></span>

<span data-ttu-id="c7655-278">これらのサーバーの役割は、それぞれ別のサーバーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7655-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="c7655-279">ディレクター</span><span class="sxs-lookup"><span data-stu-id="c7655-279">Director</span></span>

- <span data-ttu-id="c7655-280">Edge</span><span class="sxs-lookup"><span data-stu-id="c7655-280">Edge</span></span>

- <span data-ttu-id="c7655-281">ビデオ相互運用サーバー</span><span class="sxs-lookup"><span data-stu-id="c7655-281">Video Interop Server</span></span>

- <span data-ttu-id="c7655-282">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="c7655-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="c7655-283">Databases</span><span class="sxs-lookup"><span data-stu-id="c7655-283">Databases</span></span>

<span data-ttu-id="c7655-284">これは、Standard Edition サーバーの展開と Enterprise Edition サーバー プールの展開の間に大きな違いがある領域なので、以下に 2 つのセクションを示し、その後に両方の追加ルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="c7655-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="c7655-285">標準</span><span class="sxs-lookup"><span data-stu-id="c7655-285">Standard</span></span>

<span data-ttu-id="c7655-286">Express SQL Serverは Standard Edition サーバー上にコロケーションされ、移動できないので、これは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="c7655-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="c7655-287">さらに、Standard Edition サーバーに常設チャット サーバーを展開する場合は、Standard Edition サーバー上の常設チャットと常設チャット コンプライアンス データベースを併合することもできますが、必要な必要は一つではありません。</span><span class="sxs-lookup"><span data-stu-id="c7655-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

> [!NOTE]
> <span data-ttu-id="c7655-288">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c7655-288">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c7655-289">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-289">The same functionality is available in Teams.</span></span> <span data-ttu-id="c7655-290">詳細については、「Microsoft Teams のアップグレードの [開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="c7655-290">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c7655-291">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-291">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="c7655-292">これらは Standard Edition サーバー上に同一に設定できませんが、独自の 1 つのデータベース サーバー上に移動できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-292">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="c7655-293">監視データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-293">Monitoring database</span></span>

- <span data-ttu-id="c7655-294">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-294">Archiving database</span></span>

- <span data-ttu-id="c7655-295">Enterprise Edition フロントエンド プールの任意のバック エンド データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-295">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="c7655-296">大企業</span><span class="sxs-lookup"><span data-stu-id="c7655-296">Enterprise</span></span>

<span data-ttu-id="c7655-297">次のデータベースは、同じバック エンド サーバーにSQL Server。</span><span class="sxs-lookup"><span data-stu-id="c7655-297">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="c7655-298">バック エンド データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-298">Back End database</span></span>

- <span data-ttu-id="c7655-299">監視データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-299">Monitoring database</span></span>

- <span data-ttu-id="c7655-300">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-300">Archiving database</span></span>

- <span data-ttu-id="c7655-301">常設チャット データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-301">Persistent Chat database</span></span>

- <span data-ttu-id="c7655-302">常設チャット コンプライアンス データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-302">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="c7655-303">Both/フォーム/データシート</span><span class="sxs-lookup"><span data-stu-id="c7655-303">Both</span></span>

<span data-ttu-id="c7655-304">1 つの SQL インスタンスで Skype for Business Server データベースを照合する場合、または同じ SQL Server データベース内の複数の SQL インスタンスで照合する場合に従う追加のSQL Serverがあります。</span><span class="sxs-lookup"><span data-stu-id="c7655-304">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="c7655-305">各 SQL インスタンスには、Enterprise Edition フロントエンド プール用の 1 つのバック エンド データベース、1 つの監視データベース、1 つのアーカイブ データベース、1 つの常設チャット データベース、および単一の常設チャット コンプライアンス データベースのみを含めできます。</span><span class="sxs-lookup"><span data-stu-id="c7655-305">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="c7655-306">データベース サーバーは、複数の Enterprise Edition フロントエンド プール、アーカイブを実行する 1 つのサーバー、監視を実行する 1 つのサーバー、1 つの常設チャット データベース、および 1 つの常設チャット コンプライアンス データベースをサポートすることはできませんが、データベースが SQL Server の同じインスタンスを使用するか、SQL Server のインスタンスを個別に使用するかに関係なく、それぞれ 1 つをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="c7655-306">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7655-307">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c7655-307">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c7655-308">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-308">The same functionality is available in Teams.</span></span> <span data-ttu-id="c7655-309">詳細については、「Microsoft Teams のアップグレードの [開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="c7655-309">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c7655-310">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-310">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="c7655-311">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="c7655-311">File shares</span></span>

<span data-ttu-id="c7655-312">ファイル共有は、別のサーバー上に含め、または次のサーバーの一部またはすべてと同じサーバー上に共有できます。</span><span class="sxs-lookup"><span data-stu-id="c7655-312">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="c7655-313">データベース サーバー (Enterprise Edition フロントエンド プールのバック エンド サーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="c7655-313">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="c7655-314">監視データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-314">Monitoring database</span></span>

- <span data-ttu-id="c7655-315">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-315">Archiving database</span></span>

- <span data-ttu-id="c7655-316">常設チャット データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-316">Persistent Chat database</span></span>

- <span data-ttu-id="c7655-317">常設チャット コンプライアンス データベース</span><span class="sxs-lookup"><span data-stu-id="c7655-317">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="c7655-318">これらのサーバーでファイル共有を共有することもできますが、お勧めしない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7655-318">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it.</span></span> <span data-ttu-id="c7655-319">ファイル共有を他のサーバーの役割と照合する場合は、ディスク領域とパフォーマンスの問題を定期的に監視してください。</span><span class="sxs-lookup"><span data-stu-id="c7655-319">If you're collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="c7655-320">注意点</span><span class="sxs-lookup"><span data-stu-id="c7655-320">Keep in mind</span></span>

- <span data-ttu-id="c7655-321">Skype for Business Server コンポーネントではなく、トポロジに含めなくても、リバース プロキシ サーバーを照合できません。</span><span class="sxs-lookup"><span data-stu-id="c7655-321">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="c7655-322">フェデレーション ユーザー向け Web コンテンツの共有をサポートする場合は、リバース プロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="c7655-322">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="c7655-323">必要な場合は、他のアプリケーションで使用されている既存のリバース プロキシ サーバーを組織に構成して、Skype for Business Server のリバース プロキシ サポートを実装します。</span><span class="sxs-lookup"><span data-stu-id="c7655-323">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="c7655-324">Exchange UM コンポーネントまたは SharePoint Server コンポーネントを Skype for Business Server の役割と照合できません。</span><span class="sxs-lookup"><span data-stu-id="c7655-324">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7655-325">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7655-325">See also</span></span>

[<span data-ttu-id="c7655-326">Skype for Business Server のリファレンス トポロジ</span><span class="sxs-lookup"><span data-stu-id="c7655-326">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)