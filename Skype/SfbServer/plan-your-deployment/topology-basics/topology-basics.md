---
title: Skype for Business Server のトポロジの基礎
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
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '概要: Skype for Business Server のトポロジを選択します。 Skype for Business Server のサーバー collocation について説明します。'
ms.openlocfilehash: 5c8c4b7cc2a0bf1c392e3fad70a179b838a64606
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296624"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="a5849-104">Skype for Business Server のトポロジの基礎</span><span class="sxs-lookup"><span data-stu-id="a5849-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="a5849-105">**概要:** Skype for Business Server のトポロジを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5849-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="a5849-106">Skype for Business Server のサーバー collocation について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5849-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="a5849-107">他のものを準備する前に、Skype for Business Server の展開に適したトポロジを計画していることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="a5849-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="a5849-108">事前に決定する必要があるのは、Skype for Business Server のオンプレミス展開を使用する場合、またはハイブリッド展開で Skype for Business Server Online の展開に統合する場合です。</span><span class="sxs-lookup"><span data-stu-id="a5849-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="a5849-109">どちらの場合も、ここではオンプレミスのトポロジについて詳しく説明しますが、ここでは、ハイブリッドの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5849-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="a5849-110">また、 [Skype For Business Server 用のリファレンストポロジ](reference-topologies.md)でも、いくつかのトポロジの例を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="a5849-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="a5849-111">サイト</span><span class="sxs-lookup"><span data-stu-id="a5849-111">Sites</span></span>

<span data-ttu-id="a5849-112">Skype for Business Server では、Skype for business Server コンポーネントが含まれているネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a5849-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="a5849-113">サイトとは、1 つのローカル エリア ネットワーク (LAN)、または高速の光ファイバー ネットワークで接続された 2 つのネットワークなど、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。</span><span class="sxs-lookup"><span data-stu-id="a5849-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="a5849-114">Skype for Business Server サイトは、Active Directory ドメインサービスサイトと Microsoft Exchange Server サイトとは別の概念です。</span><span class="sxs-lookup"><span data-stu-id="a5849-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="a5849-115">お使いの Skype for Business Server サイトは、お使いの Active Directory サイトに対応している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a5849-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="a5849-116">Skype for Business Server は、高可用性と場所の要件に従って拡大縮小できる1つ以上のサイトのオンプレミス展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a5849-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="a5849-117">展開には、少なくとも1つのセントラルサイト (データセンターとも呼ばれます) があります。また、展開の各セントラルサイトには、1つの Standard Edition サーバー、または少なくとも1つの Enterprise Edition のフロントエンドプールがあります。</span><span class="sxs-lookup"><span data-stu-id="a5849-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="a5849-118">以下に各オプションの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="a5849-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="a5849-119">Standard Edition server には、併置された SQL Server Express データベースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5849-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="a5849-120">Enterprise Edition のフロントエンドプールには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5849-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="a5849-121">1つ以上のフロントエンドサーバー (理想的には、スケーラビリティの場合は最低3つ)、最大値は12です。</span><span class="sxs-lookup"><span data-stu-id="a5849-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="a5849-122">サーバーが 2 台以上の場合は、負荷分散が必要になります。</span><span class="sxs-lookup"><span data-stu-id="a5849-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="a5849-123">別のバックエンドサーバー。</span><span class="sxs-lookup"><span data-stu-id="a5849-123">A separate Back End Server.</span></span>

<span data-ttu-id="a5849-124">各サーバーの役割の詳細については、このセクションで後述します。</span><span class="sxs-lookup"><span data-stu-id="a5849-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="a5849-125">セントラルサイトに加えて、サイトに関連付けられた1つ以上の分岐サイトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5849-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="a5849-126">ほぼすべての機能についてセントラルサイトに依存しているため、完全にはどのような機能を備えていますか。</span><span class="sxs-lookup"><span data-stu-id="a5849-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="a5849-127">Survivable Branch Appliance: 公衆交換電話網 (PSTN) ゲートウェイと一部の Skype for Business Server 機能を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="a5849-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="a5849-128">Survivable Branch Server は、Skype for Business Server レジストラーと仲介サーバーソフトウェアがインストールされている Windows Server を実行しているサーバーです。</span><span class="sxs-lookup"><span data-stu-id="a5849-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="a5849-129">スタンドアロン PSTN ゲートウェイ (Survivable Branch アプライアンスの一部ではありません)。</span><span class="sxs-lookup"><span data-stu-id="a5849-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="a5849-130">スタンドアロンの仲介サーバーまたはスタンドアロンの仲介サーバープール (この役割を Survivable Branch アプライアンスで検索したくない場合)。</span><span class="sxs-lookup"><span data-stu-id="a5849-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="a5849-131">Skype for Business Server サイトには何がありますか?</span><span class="sxs-lookup"><span data-stu-id="a5849-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="a5849-132">さらに詳しい情報を得るには、セントラルサイトで次の操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="a5849-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="a5849-133">複数のフロントエンドプール、同じドメインまたは異なるドメイン内 (フロントエンドプールのすべてのフロントエンドサーバーと、プールのバックエンドサーバーが同じドメインに存在することを計画することを忘れないでください)。</span><span class="sxs-lookup"><span data-stu-id="a5849-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="a5849-134">複数の Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="a5849-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="a5849-135">Office Web Apps Server。 Skype for Business Server の Office Web Apps で PowerPoint プレゼンテーションの共有やレンダリングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="a5849-136">エッジサーバーまたはエッジプール (境界ネットワーク)。</span><span class="sxs-lookup"><span data-stu-id="a5849-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="a5849-137">展開で、フェデレーション パートナー、パブリック IM 接続、XMPP (eXtensible Messaging and Presence Protocol) ゲートウェイ、およびリモート ユーザー アクセスをサポートする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="a5849-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="a5849-138">詳細については、「microsoft Edge Server の計画ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="a5849-139">常設チャットサーバー。</span><span class="sxs-lookup"><span data-stu-id="a5849-139">Persistent Chat Server.</span></span> <span data-ttu-id="a5849-140">トピックに基づく長時間のマルチパーティ会話にユーザーが参加できるようにする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a5849-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="a5849-141">常設チャットサーバーの計画についての詳細はこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a5849-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="a5849-142">監視。</span><span class="sxs-lookup"><span data-stu-id="a5849-142">Monitoring.</span></span> <span data-ttu-id="a5849-143">オーディオ/ビデオ (A/V) Quality of Experience (QoE) のデータ収集、および展開でのエンタープライズ Voip 会議および通話の詳細記録 (CDR) をサポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="a5849-144">「計画」のドキュメントの「監視」トピックで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="a5849-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="a5849-145">ディレクターまたはディレクタープール。</span><span class="sxs-lookup"><span data-stu-id="a5849-145">Director or Director pool.</span></span> <span data-ttu-id="a5849-146">これは必須ではありませんが、回復性を向上させ、ユーザーのホームプールへの Skype for Business ユーザー要求のリダイレクションを有効にする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a5849-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="a5849-147">ディレクターを展開する場合は、1つのプールあたり最大10個のプールがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a5849-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="a5849-148">これが必要な場合は、ディレクターの計画に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="a5849-149">リバースプロキシ。</span><span class="sxs-lookup"><span data-stu-id="a5849-149">Reverse proxy.</span></span> <span data-ttu-id="a5849-150">これは Skype for Business Server コンポーネントではありませんが、フェデレーションされたユーザーのために web コンテンツを共有する場合、リモートユーザーがアドレス帳を使用したり、会議に参加したりする必要がある場合は、これを行うことをお勧めします。環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5849-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="a5849-151">リバースプロキシサーバーのトピックを設定すると、準備が整った時点で詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="a5849-152">これらのサーバーの併置に関する追加情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a5849-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="a5849-153">セントラルサイトに展開されているすべてのフロントエンドプールおよび標準エディションのサーバーは、展開済みであれば、次のものを共有します。</span><span class="sxs-lookup"><span data-stu-id="a5849-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="a5849-154">ディレクターまたはディレクタープール</span><span class="sxs-lookup"><span data-stu-id="a5849-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="a5849-155">スタンドアロンの仲介サーバーまたは仲介サーバープール</span><span class="sxs-lookup"><span data-stu-id="a5849-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="a5849-156">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="a5849-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="a5849-157">エッジサーバーまたはエッジプール</span><span class="sxs-lookup"><span data-stu-id="a5849-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="a5849-158">常設チャットサーバーまたは常設チャットサーバープール</span><span class="sxs-lookup"><span data-stu-id="a5849-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="a5849-159">監視</span><span class="sxs-lookup"><span data-stu-id="a5849-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="a5849-160">このリストでは、Exchange ユニファイドメッセージング (UM) サーバーはどこにありますか?</span><span class="sxs-lookup"><span data-stu-id="a5849-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="a5849-161">確かに、Exchange UM と統合する場合は、Skype for Business Server でも使用できますが、Skype for Business Server サイトのコンポーネントではないため、ここでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="a5849-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="a5849-162">複数のセントラルサイトを作成することを計画している可能性があります。そのため、セントラルサイトに展開されている場合は、次のサーバーとロールを共有できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a5849-163">スタンドアロンの仲介サーバーまたは仲介サーバープール</span><span class="sxs-lookup"><span data-stu-id="a5849-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="a5849-164">エッジサーバーまたはエッジプール</span><span class="sxs-lookup"><span data-stu-id="a5849-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="a5849-165">常設チャットサーバーまたは常設チャットサーバープール</span><span class="sxs-lookup"><span data-stu-id="a5849-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="a5849-166">監視</span><span class="sxs-lookup"><span data-stu-id="a5849-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="a5849-167">最後の一覧と同じように、ここには Exchange UM サーバーを含めません。これは、Skype for Business Server の展開の一部ではないため、ここでも同じカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="a5849-168">もちろん、展開にはその他のコンポーネントやオプションを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a5849-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5849-169">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="a5849-169">Firewalls</span></span>  <br/> |<span data-ttu-id="a5849-170">PSTN ゲートウェイ (エンタープライズ VoIP を展開する場合)</span><span class="sxs-lookup"><span data-stu-id="a5849-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="a5849-171">Exchange UM サーバー (Exchange UM と統合する場合)</span><span class="sxs-lookup"><span data-stu-id="a5849-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="a5849-172">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="a5849-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="a5849-173">ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="a5849-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="a5849-174">SQL Server データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="a5849-175">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="a5849-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="a5849-176">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="a5849-176">Server roles</span></span>

<span data-ttu-id="a5849-177">Skype for Business Server を実行している各サーバーは、1つ以上のサーバーの役割を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5849-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="a5849-178">サーバーの役割は、そのサーバーによって提供される、定義済みの Skype for Business Server 機能のセットです。</span><span class="sxs-lookup"><span data-stu-id="a5849-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="a5849-179">ネットワークで使用できるサーバーの役割をすべて展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a5849-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="a5849-180">必要な機能が含まれているサーバーの役割のみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5849-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="a5849-181">多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプールを展開して、スケーラビリティと高可用性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="a5849-182">プール内の各サーバーは同じサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5849-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="a5849-183">Skype for Business Server のほとんどの種類のプールでは、プール内のさまざまなサーバー間でトラフィックを分散させるために、ロードバランサーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5849-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="a5849-184">Skype for Business Server は、ドメインネームシステム (DNS) 負荷分散とハードウェアロードバランサーの両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a5849-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="a5849-185">フロントエンド サーバーおよびバックエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="a5849-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="a5849-186">Skype for Business Server Enterprise Edition では、フロントエンドサーバーは主要サーバーの役割であり、多くの基本的な Skype for Business Server 機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5849-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="a5849-187">フロントエンドサーバーはバックエンドサーバーと共に、Skype for Business Server Enterprise Edition の展開に必要な唯一のサーバーロールです。</span><span class="sxs-lookup"><span data-stu-id="a5849-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="a5849-188">フロントエンドプールは、共通して構成される一連のフロントエンドサーバーであり、共通のユーザーグループに対してサービスを提供するために一緒に動作します。</span><span class="sxs-lookup"><span data-stu-id="a5849-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="a5849-189">同じ役割を実行する複数のサーバーのプールでは、スケーラビリティとフェールオーバー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="a5849-190">フロントエンドサーバーには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5849-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="a5849-191">ユーザーの認証および登録。</span><span class="sxs-lookup"><span data-stu-id="a5849-191">User authentication and registration.</span></span>

- <span data-ttu-id="a5849-192">プレゼンス情報および連絡先カードの交換。</span><span class="sxs-lookup"><span data-stu-id="a5849-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="a5849-193">アドレス帳サービスおよび配布リスト展開。</span><span class="sxs-lookup"><span data-stu-id="a5849-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="a5849-194">IM 機能 (マルチパーティ IM 会議など)。</span><span class="sxs-lookup"><span data-stu-id="a5849-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="a5849-195">Web 会議、PSTN ダイヤルイン会議、および音声ビデオ会議 (展開されている場合)。</span><span class="sxs-lookup"><span data-stu-id="a5849-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="a5849-196">Skype for Business Server に含まれているアプリケーション (会議アテンダントと応答グループアプリケーションなど) とサードパーティアプリケーションの両方のアプリケーションホスト。</span><span class="sxs-lookup"><span data-stu-id="a5849-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="a5849-197">オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。</span><span class="sxs-lookup"><span data-stu-id="a5849-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="a5849-198">この情報には、企業の音声通話と A/V 会議の両方について、ネットワーク上を通過するメディア (音声およびビデオ) の品質に関する基準が記載されています。</span><span class="sxs-lookup"><span data-stu-id="a5849-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="a5849-199">Web Scheduler、Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a5849-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="a5849-p119">オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。詳細については、「計画」のドキュメントの「[Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-p119">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons. For details, see [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in the Planning documentation.</span></span>

    <span data-ttu-id="a5849-202">Lync Server 2010 以前のバージョンでは、監視とアーカイブは個別のサーバーロールであり、フロントエンドサーバーには併置されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5849-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="a5849-203">オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。</span><span class="sxs-lookup"><span data-stu-id="a5849-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="a5849-p120">フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="a5849-p120">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="a5849-206">さらに、展開に含まれる1台のフロントエンドサーバーも中央管理サーバーを実行します。これは、Skype for Business Server を実行しているすべてのサーバーの基本構成データを管理し、展開します。</span><span class="sxs-lookup"><span data-stu-id="a5849-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="a5849-207">サーバーの全体管理サーバーでは、Lync Server 管理シェルとファイル転送機能も提供されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="a5849-208">バックエンドサーバーは、フロントエンドプールのデータベースサービスを提供する Microsoft SQL Server を実行しているデータベースサーバーです。</span><span class="sxs-lookup"><span data-stu-id="a5849-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="a5849-209">バックエンドサーバーは、プールのユーザーと会議データのバックアップストアとして機能し、応答グループデータベースなど、他のデータベースのプライマリストアです。</span><span class="sxs-lookup"><span data-stu-id="a5849-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="a5849-210">バックエンドサーバーは1つしかありませんが、フェールオーバーには、 [Skype For Business Server のバックエンドサーバーの高可用性](../high-availability-and-disaster-recovery/back-end-server.md)が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="a5849-211">バックエンドサーバーでは、Skype for Business Server ソフトウェアは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a5849-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5849-212">Skype for Business Server データベースを他のデータベースに配置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a5849-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="a5849-213">併置すると、可用性とパフォーマンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="a5849-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="a5849-214">SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a5849-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a5849-215">AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="a5849-216">バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="a5849-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="a5849-217">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="a5849-217">Edge Server</span></span>

<span data-ttu-id="a5849-218">エッジサーバーにより、ユーザーは組織のファイアウォール外のユーザーと通信して共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a5849-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="a5849-219">これらの外部ユーザーは、現在オフサイトで作業している組織の独自のユーザー、フェデレーションパートナー組織のユーザー、Skype for Business Server 展開でホストされている会議に参加するよう招待された外部ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a5849-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="a5849-220">エッジサーバーを展開すると、モバイルデバイスで Lync 機能をサポートするモビリティサービスも有効になります。</span><span class="sxs-lookup"><span data-stu-id="a5849-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="a5849-221">ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="a5849-222">さらに、モバイルデバイスでは、クリックして電話会議に参加したり、勤務先の電話による通話、ボイスメール、不在着信など、一部のエンタープライズ音声機能をサポートしたりします。</span><span class="sxs-lookup"><span data-stu-id="a5849-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="a5849-223">モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a5849-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="a5849-224">プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="a5849-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="a5849-225">エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5849-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="a5849-226">これらの XMPP コンポーネントを構成することで、Skype for Business Server ユーザーは、インスタントメッセージ (im) とプレゼンスのために、XMPP ベースのパートナーから連絡先を追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a5849-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="a5849-227">XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a5849-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a5849-228">詳細については、「 [XMPP フェデレーションを移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="a5849-229">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="a5849-229">Mediation Server</span></span>

<span data-ttu-id="a5849-230">仲介サーバーは、エンタープライズ Voip を実装するために必要なコンポーネントであり、勤務先からの通話、およびダイヤルイン会議に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="a5849-231">仲介サーバーは、内部の Skype for Business Server インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイ、IP PBX、またはセッション開始プロトコル (SIP) トランク間のメディアを変換します。</span><span class="sxs-lookup"><span data-stu-id="a5849-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="a5849-232">仲介サーバーは、フロントエンドサーバーと同じサーバーまたはスタンドアロンの仲介サーバープールに分けて実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a5849-233">詳細については、「 [Skype For Business server の仲介サーバーコンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="a5849-234">ビデオ相互運用サーバー</span><span class="sxs-lookup"><span data-stu-id="a5849-234">Video Interop Server</span></span>

<span data-ttu-id="a5849-235">ビデオ相互運用機能サーバーは、Skype for Business Server 2015 の新しい役割です。</span><span class="sxs-lookup"><span data-stu-id="a5849-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="a5849-236">Skype for Business Server の展開を特定のサードパーティの VTC (ビデオ会議システム) ソリューションに統合することができます。</span><span class="sxs-lookup"><span data-stu-id="a5849-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="a5849-237">VIS は、サードパーティの電話会議システムと Skype for Business Server の展開の間の媒介として機能します。</span><span class="sxs-lookup"><span data-stu-id="a5849-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="a5849-238">このリリースでは、VIS は Cisco/Tandberg ビデオ システムとの相互運用性に焦点を合わせています。</span><span class="sxs-lookup"><span data-stu-id="a5849-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="a5849-239">詳細については、「 [Skype For Business server でのビデオ相互運用機能の計画](../../plan-your-deployment/video-interop-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="a5849-240">ディレクター</span><span class="sxs-lookup"><span data-stu-id="a5849-240">Director</span></span>

<span data-ttu-id="a5849-241">ディレクターは、Skype for Business Server ユーザー要求を認証することができますが、ユーザーアカウントをホームにしたり、プレゼンスや会議サービスを提供したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="a5849-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="a5849-242">ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a5849-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="a5849-243">内部サーバーに要求を送信する前にディレクターで認証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="a5849-244">サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。</span><span class="sxs-lookup"><span data-stu-id="a5849-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="a5849-245">常設チャットサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="a5849-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="a5849-246">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a5849-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a5849-247">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="a5849-248">詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-248">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="a5849-249">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="a5849-p133">常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-p133">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="a5849-254">Skype for Business Server Standard Edition を実行しているサーバーでも、同じサーバー上で同一の常設チャットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="a5849-255">Enterprise Edition フロントエンドサーバーでは、常設チャットフロントエンドサーバーを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5849-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="a5849-256">詳細については、「 [Skype For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="a5849-257">高可用性および障害復旧のサポート</span><span class="sxs-lookup"><span data-stu-id="a5849-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="a5849-258">Skype for Business Server は、プールを介したサーバーの冗長性によって高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="a5849-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="a5849-259">特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。</span><span class="sxs-lookup"><span data-stu-id="a5849-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a5849-260">同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。</span><span class="sxs-lookup"><span data-stu-id="a5849-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="a5849-261">Skype for Business Server は、プールのペアリングを有効にすることで、障害回復の手段も提供します。</span><span class="sxs-lookup"><span data-stu-id="a5849-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="a5849-262">このトポロジを展開する場合、フロントエンドプールのペアを指定します。各プールは、別々のデータセンターにあり、各プールは別々の地理的領域に配置されています。</span><span class="sxs-lookup"><span data-stu-id="a5849-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="a5849-263">1つのプールまたはサイトがダウンした場合は、サービスの中断を最小限に抑えて、そのプールのユーザーを、ペア内の他のプールを使用するようにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5849-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="a5849-264">Skype for Business Server では、バックエンドサーバーの高可用性を実現するためのいくつかのオプションもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a5849-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="a5849-265">たとえば、以下のようなものです。</span><span class="sxs-lookup"><span data-stu-id="a5849-265">These include the following:</span></span>

- <span data-ttu-id="a5849-266">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="a5849-266">Database mirroring</span></span>

- <span data-ttu-id="a5849-267">AlwaysOn 可用性グループ</span><span class="sxs-lookup"><span data-stu-id="a5849-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="a5849-268">AlwaysOn フェールオーバークラスターインスタンス (FCI)</span><span class="sxs-lookup"><span data-stu-id="a5849-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="a5849-269">SQL フェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="a5849-269">SQL failover clustering</span></span>

<span data-ttu-id="a5849-270">プールのペアリングとバックエンドサーバーの高可用性の詳細については、「 [Skype For Business Server で高可用性と障害回復を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="a5849-271">Skype for Business Server のサーバー collocation</span><span class="sxs-lookup"><span data-stu-id="a5849-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="a5849-272">用語の概要は既に使用していますが、これは何を意味していますか?</span><span class="sxs-lookup"><span data-stu-id="a5849-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="a5849-273">Skype for Business Server を使用すると、サーバーの役割と機能の一部を同じサーバー (collocation または別のサーバー) で検索できますが、作業を開始したときや、標準エディションと Enterprise Edition サーバーのどちらを実行しているかがわかりにくくなることがあります。展開 (それぞれに独自のルールが付属しています)。</span><span class="sxs-lookup"><span data-stu-id="a5849-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="a5849-274">お客様の計画を支援するため、Standard Edition server の展開と Enterprise Edition のフロントエンドプール展開にはサーバーの collocation が含まれています (ほとんどの場合、この情報は同一であり、特定の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="a5849-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="a5849-275">サーバーの役割の併置</span><span class="sxs-lookup"><span data-stu-id="a5849-275">Collocation of server roles</span></span>

<span data-ttu-id="a5849-276">Standard Edition サーバーには、次の役割が含まれています (ただし、その他の構成が必要です)。 Enterprise Edition のフロントエンドプールでは、この役割を併置したり、別のサーバーに展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5849-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="a5849-277">仲介</span><span class="sxs-lookup"><span data-stu-id="a5849-277">Mediation</span></span>

<span data-ttu-id="a5849-278">次のサーバーの役割は、それぞれ別のサーバーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5849-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="a5849-279">ディレクター</span><span class="sxs-lookup"><span data-stu-id="a5849-279">Director</span></span>

- <span data-ttu-id="a5849-280">Edge</span><span class="sxs-lookup"><span data-stu-id="a5849-280">Edge</span></span>

- <span data-ttu-id="a5849-281">ビデオ相互運用サーバー</span><span class="sxs-lookup"><span data-stu-id="a5849-281">Video Interop Server</span></span>

- <span data-ttu-id="a5849-282">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="a5849-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="a5849-283">データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-283">Databases</span></span>

<span data-ttu-id="a5849-284">この領域では、Standard Edition server 展開と Enterprise Edition server プールの展開の相違点について説明します。次に、2つのセクションに加えて、両方について追加ルールをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="a5849-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="a5849-285">Standard</span><span class="sxs-lookup"><span data-stu-id="a5849-285">Standard</span></span>

<span data-ttu-id="a5849-286">SQL Server Express は Standard Edition Server に併置されているため、移動できません。これは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="a5849-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="a5849-287">さらに、標準エディションのサーバーに常設チャットサーバーを展開すると、常設チャットと常設チャットのコンプライアンスデータベースも Standard Edition サーバーで検索することができますが、必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a5849-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

<span data-ttu-id="a5849-288">これらは標準エディションのサーバー上では使用できませんが、1つのデータベースサーバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a5849-288">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="a5849-289">監視データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-289">Monitoring database</span></span>

- <span data-ttu-id="a5849-290">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-290">Archiving database</span></span>

- <span data-ttu-id="a5849-291">Enterprise Edition フロントエンドプールの任意のバックエンドデータベース</span><span class="sxs-lookup"><span data-stu-id="a5849-291">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="a5849-292">Enterprise</span><span class="sxs-lookup"><span data-stu-id="a5849-292">Enterprise</span></span>

<span data-ttu-id="a5849-293">次のデータベースは、同じバックエンド SQL Server に併置できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-293">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="a5849-294">バックエンド データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-294">Back End database</span></span>

- <span data-ttu-id="a5849-295">監視データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-295">Monitoring database</span></span>

- <span data-ttu-id="a5849-296">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-296">Archiving database</span></span>

- <span data-ttu-id="a5849-297">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="a5849-297">Persistent Chat database</span></span>

- <span data-ttu-id="a5849-298">常設チャットのコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="a5849-298">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="a5849-299">両方</span><span class="sxs-lookup"><span data-stu-id="a5849-299">Both</span></span>

<span data-ttu-id="a5849-300">ここでは、1つの SQL インスタンスで、または同じ SQL Server データベース内の複数の SQL インスタンスで、Skype for Business Server データベースを検索する場合に、いくつかの追加の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5849-300">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="a5849-301">各 SQL インスタンスには、Enterprise Edition フロントエンドプール用のバックエンドデータベースを1つだけ含めることができます。1つの監視データベース、1つのアーカイブデータベース、1つの常設チャットデータベース、1つの永続的なチャットのコンプライアンスデータベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5849-301">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="a5849-302">データベースサーバーでは、複数の Enterprise Edition フロントエンドプールをサポートしていません。アーカイブを実行しているサーバー1台、監視を実行している1台のサーバー、1つの常設チャットデータベース、1つの永続的なチャットのコンプライアンスデータベースがサポートされています。データベースで SQL Server の同じインスタンスと SQL Server の別のインスタンスのどちらを使うかに関係なく、</span><span class="sxs-lookup"><span data-stu-id="a5849-302">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a5849-303">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a5849-303">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a5849-304">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-304">The same functionality is available in Teams.</span></span> <span data-ttu-id="a5849-305">詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-305">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="a5849-306">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a5849-306">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="a5849-307">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="a5849-307">File shares</span></span>

<span data-ttu-id="a5849-308">ファイル共有は、別個のサーバーに配置することも、次の一部またはすべてと同じサーバーに併置することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5849-308">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="a5849-309">データベースサーバー (Enterprise Edition フロントエンドプールのバックエンドサーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="a5849-309">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="a5849-310">監視データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-310">Monitoring database</span></span>

- <span data-ttu-id="a5849-311">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="a5849-311">Archiving database</span></span>

- <span data-ttu-id="a5849-312">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="a5849-312">Persistent Chat database</span></span>

- <span data-ttu-id="a5849-313">常設チャットのコンプライアンスデータベース</span><span class="sxs-lookup"><span data-stu-id="a5849-313">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="a5849-p141">これらのサーバー上にファイル共有を並置することはできますが、この方法は推奨されていないことに注意してください。他のサーバーの役割を持つサーバー上にファイル共有を並置する場合は、ディスク空き容量と性能に関する問題を定期的に監視してください。</span><span class="sxs-lookup"><span data-stu-id="a5849-p141">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it. If you'd collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="a5849-316">注意が必要な点</span><span class="sxs-lookup"><span data-stu-id="a5849-316">Keep in mind</span></span>

- <span data-ttu-id="a5849-317">Skype for Business Server コンポーネントではなく、逆プロキシサーバーを作成することはできません。また、トポロジに含まれていない可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="a5849-317">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="a5849-318">フェデレーションされたユーザーのための web コンテンツの共有をサポートしたい場合は、リバースプロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="a5849-318">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="a5849-319">必要な場合は、他のアプリケーションで既に使用されている既存のリバースプロキシサーバーを構成して、Skype for Business Server のリバースプロキシサポートを実装します。</span><span class="sxs-lookup"><span data-stu-id="a5849-319">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="a5849-320">任意の Skype for Business Server の役割を持つ Exchange UM コンポーネントまたは SharePoint Server コンポーネントを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5849-320">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5849-321">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5849-321">See also</span></span>

[<span data-ttu-id="a5849-322">Skype for Business Server のリファレンストポロジ</span><span class="sxs-lookup"><span data-stu-id="a5849-322">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)
