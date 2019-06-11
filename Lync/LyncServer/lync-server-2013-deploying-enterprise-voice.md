---
title: 'Lync Server 2013: エンタープライズ Voip の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="282ad-102">Lync Server 2013 でのエンタープライズボイスの展開</span><span class="sxs-lookup"><span data-stu-id="282ad-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="282ad-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="282ad-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="282ad-104">Lync Server 2013、エンタープライズボイスは Lync Server 2013 インフラストラクチャの一部です。</span><span class="sxs-lookup"><span data-stu-id="282ad-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="282ad-105">エンタープライズボイスを展開するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="282ad-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="282ad-106">計画ドキュメントの「 [Lync Server 2013 でのエンタープライズボイスの計画](lync-server-2013-planning-for-enterprise-voice.md)」セクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="282ad-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="282ad-107">この作業負荷と共に展開する機能とコンポーネントの計画を完了します。</span><span class="sxs-lookup"><span data-stu-id="282ad-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="282ad-108">計画ツールを実行して、展開の決定を反映するトポロジを設計します。</span><span class="sxs-lookup"><span data-stu-id="282ad-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="282ad-109">展開ドキュメントの「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」の説明に従って、トポロジビルダーでトポロジの設計を開きます。</span><span class="sxs-lookup"><span data-stu-id="282ad-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="282ad-110">トポロジビルダーのインストールは、内部プールの展開プロセスの一部です。</span><span class="sxs-lookup"><span data-stu-id="282ad-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="282ad-111">詳細については、「 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 管理ツール</A>を展開用のドキュメントにインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="282ad-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="282ad-112">さらに、展開するために選んだ参照トポロジに対応する、[セントラルサイト] と [ブランチサイト] に既に Lync Server、Enterprise Edition を展開している必要があります。</span><span class="sxs-lookup"><span data-stu-id="282ad-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="282ad-113">エンタープライズボイスコンポーネントは、少なくとも1つの内部プールに対して定義、発行、インストールされているファイルがあるまで展開できません。また、内部プールを定義して公開するには、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="282ad-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="282ad-114">エンタープライズ Voip サーバーの役割 (および他の Lync Server 2013 サーバーの役割との関係) を展開する方法の例を参照トポロジで確認するには、計画ドキュメントの「 [Lync server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="282ad-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="282ad-115">ネットワーク領域、ネットワークサイト、サブネットなど、通話受付制御の展開のサンプルについて説明している参照トポロジを表示する方法については、「[例: Lync Server 2013 の通話受付制御の要件を収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)する」を参照してください。計画ドキュメント</span><span class="sxs-lookup"><span data-stu-id="282ad-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="282ad-116">エンタープライズ Voip をセントラルサイトに展開するには、このセクションのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="282ad-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="282ad-117">ブランチサイトでエンタープライズボイスを展開するには、展開ドキュメントの<A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 でブランチサイト</A>を展開するに進みます。</span><span class="sxs-lookup"><span data-stu-id="282ad-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="282ad-118">このセクションには、推奨に従って、各フロントエンド サーバーまたは各 Standard Edition サーバー上に仲介サーバーを併置する展開の手順、およびスタンドアロンの仲介サーバー プールでの展開の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="282ad-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="282ad-119">トポロジビルダーを使用して、各フロントエンドサーバーまたは Standard Edition サーバー上で仲介サーバーを見つけて配布するトポロジを定義して公開している場合は、次のコンテンツをスキップできます。フロントエンドサーバープールまたは Standard Edition サーバーにファイルをインストールした場合の仲介サーバー:</span><span class="sxs-lookup"><span data-stu-id="282ad-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="282ad-120">Lync Server 2013 でのトランクの構成</span><span class="sxs-lookup"><span data-stu-id="282ad-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="282ad-121">単体プールで仲介サーバーを定義して公開するためにトポロジビルダーを使用している場合は、次のコンテンツを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="282ad-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="282ad-122">「 [Lync Server 2013 のエンタープライズボイスの前提条件](lync-server-2013-enterprise-voice-prerequisites.md)」で説明されているように、トポロジがソフトウェアと環境の前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="282ad-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="282ad-123">このセクション中</span><span class="sxs-lookup"><span data-stu-id="282ad-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="282ad-124">Lync Server 2013 のエンタープライズ VoIP の前提条件</span><span class="sxs-lookup"><span data-stu-id="282ad-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="282ad-125">Lync Server 2013 での仲介サーバーの展開とピアの定義</span><span class="sxs-lookup"><span data-stu-id="282ad-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="282ad-126">Lync Server 2013 でのトランクの構成</span><span class="sxs-lookup"><span data-stu-id="282ad-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="282ad-127">Lync Server 2013 でのダイヤル プランの構成</span><span class="sxs-lookup"><span data-stu-id="282ad-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="282ad-128">Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="282ad-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="282ad-129">Lync Server 2013 での音声ルーティング構成のエクスポートとインポート</span><span class="sxs-lookup"><span data-stu-id="282ad-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="282ad-130">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="282ad-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="282ad-131">Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する</span><span class="sxs-lookup"><span data-stu-id="282ad-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="282ad-132">内部設置型 Exchange UM を展開して Lync Server 2013 ボイス メールを提供する</span><span class="sxs-lookup"><span data-stu-id="282ad-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="282ad-133">Lync Server 2013 ユーザーに Hosted Exchange UM のボイス メールを提供する</span><span class="sxs-lookup"><span data-stu-id="282ad-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="282ad-134">オンプレミスの Lync Server 2013 と Exchange Online の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="282ad-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="282ad-135">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="282ad-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="282ad-136">Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成</span><span class="sxs-lookup"><span data-stu-id="282ad-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="282ad-137">Lync Server 2013 でネットワークの領域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="282ad-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="282ad-138">Lync Server 2013 でのネットワーク サイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="282ad-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="282ad-139">Lync Server 2013 でのネットワーク サイトとサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="282ad-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="282ad-140">Lync Server 2013 での通話受付制御の構成</span><span class="sxs-lookup"><span data-stu-id="282ad-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="282ad-141">Lync Server 2013 での Enhanced 9-1-1 の構成</span><span class="sxs-lookup"><span data-stu-id="282ad-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="282ad-142">Lync Server 2013 メディア バイパスの構成</span><span class="sxs-lookup"><span data-stu-id="282ad-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="282ad-143">Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="282ad-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="282ad-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="282ad-144">See Also</span></span>


[<span data-ttu-id="282ad-145">Lync Server 2013 でのブランチ サイトの展開</span><span class="sxs-lookup"><span data-stu-id="282ad-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="282ad-146">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="282ad-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="282ad-147">Lync Server 2013 でのコール パークの構成</span><span class="sxs-lookup"><span data-stu-id="282ad-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="282ad-148">Lync Server 2013 での、割り当てられていない番号用のアナウンスの構成</span><span class="sxs-lookup"><span data-stu-id="282ad-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="282ad-149">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="282ad-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

