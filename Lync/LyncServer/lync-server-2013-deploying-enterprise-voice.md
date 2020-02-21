---
title: 'Lync Server 2013: エンタープライズ Voip の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a19016a095e38a0df70a561976c6b03d59fdfd1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3d940-102">Lync Server 2013 でのエンタープライズ Voip の展開</span><span class="sxs-lookup"><span data-stu-id="3d940-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d940-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3d940-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3d940-104">Lync Server 2013、エンタープライズ Voip は Lync Server 2013 インフラストラクチャの一部です。</span><span class="sxs-lookup"><span data-stu-id="3d940-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="3d940-105">エンタープライズ VoIP の展開には以下のことが必要になります。</span><span class="sxs-lookup"><span data-stu-id="3d940-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="3d940-106">「計画」のドキュメントの「 [Lync Server 2013 でのエンタープライズ voip の計画](lync-server-2013-planning-for-enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d940-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="3d940-107">このワークロードで展開する機能およびコンポーネントの計画が完了していること。</span><span class="sxs-lookup"><span data-stu-id="3d940-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="3d940-108">計画ツールを実行して、展開の決定を反映するトポロジを設計します。</span><span class="sxs-lookup"><span data-stu-id="3d940-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="3d940-109">「展開」のドキュメントの「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」の説明に従って、トポロジビルダーでトポロジ設計を開きます。</span><span class="sxs-lookup"><span data-stu-id="3d940-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d940-110">トポロジビルダーのインストールは、内部プールの展開プロセスの一部です。</span><span class="sxs-lookup"><span data-stu-id="3d940-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="3d940-111">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 管理ツール</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d940-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="3d940-112">また、展開するために選択した参照トポロジに対応する、中央サイトとブランチサイトに Lync Server、Enterprise Edition が既に展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d940-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="3d940-113">エンタープライズ Voip コンポーネントを展開するには、少なくとも1つの内部プールに対してファイルを定義、発行、およびインストールする必要があります。また、トポロジビルダーを使用して内部プールを定義して発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d940-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="3d940-114">エンタープライズ Voip サーバーの役割を展開できる場所 (およびそれらの関係と、他の Lync Server 2013 のサーバーの役割との関係) を示す参照トポロジを表示するには、「計画」のドキュメントの「 [reference トポロジ In Lync server 2013](lync-server-2013-reference-topologies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d940-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="3d940-115">ネットワーク地域、ネットワークサイト、およびサブネットを含む、通話受付管理の展開の例について説明する参照トポロジを表示するには、「計画」のドキュメントの「 [Example: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d940-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d940-116">中央サイトにエンタープライズ Voip を展開するには、このセクションのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d940-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="3d940-117">ブランチサイトでエンタープライズ Voip を展開するには、「展開」のドキュメントの「 <A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 でブランチサイト</A>を展開する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="3d940-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="3d940-118">このセクションには、推奨に従って、各フロントエンド サーバーまたは各 Standard Edition サーバー上に仲介サーバーを併置する展開の手順、およびスタンドアロンの仲介サーバー プールでの展開の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d940-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="3d940-119">トポロジビルダーを使用して、各フロントエンドサーバーまたは Standard Edition サーバーに仲介サーバーを配置したトポロジを定義して公開している場合は、次のコンテンツをスキップすることができます。これは、展開ウィザードが既にファイルをフロントエンドサーバープールまたは Standard Edition サーバーのファイルをインストールした場合の仲介サーバー:</span><span class="sxs-lookup"><span data-stu-id="3d940-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="3d940-120">Lync Server 2013 でのトランクの構成</span><span class="sxs-lookup"><span data-stu-id="3d940-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="3d940-121">トポロジビルダーを使用してスタンドアロンプールで仲介サーバーを定義して公開した場合は、次のコンテンツを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d940-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="3d940-122">「 [Lync Server 2013 のエンタープライズ voip の前提条件](lync-server-2013-enterprise-voice-prerequisites.md)」で説明されているように、トポロジがソフトウェアおよび環境の前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d940-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3d940-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3d940-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="3d940-124">Lync Server 2013 のエンタープライズ Voip の前提条件</span><span class="sxs-lookup"><span data-stu-id="3d940-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="3d940-125">Lync Server 2013 での仲介サーバーの展開とピアの定義</span><span class="sxs-lookup"><span data-stu-id="3d940-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="3d940-126">Lync Server 2013 でのトランクの構成</span><span class="sxs-lookup"><span data-stu-id="3d940-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="3d940-127">Lync Server 2013 でのダイヤルプランの構成</span><span class="sxs-lookup"><span data-stu-id="3d940-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="3d940-128">Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成</span><span class="sxs-lookup"><span data-stu-id="3d940-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="3d940-129">Lync Server 2013 での音声ルーティング構成のエクスポートとインポート</span><span class="sxs-lookup"><span data-stu-id="3d940-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="3d940-130">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="3d940-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="3d940-131">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="3d940-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="3d940-132">社内 Exchange UM を展開して Lync Server 2013 ボイスメールを提供する</span><span class="sxs-lookup"><span data-stu-id="3d940-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="3d940-133">Lync Server 2013 ユーザーに hosted Exchange UM のボイスメールを提供する</span><span class="sxs-lookup"><span data-stu-id="3d940-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="3d940-134">社内の Lync Server 2013 と Exchange Online との統合の構成</span><span class="sxs-lookup"><span data-stu-id="3d940-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="3d940-135">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="3d940-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="3d940-136">Lync Server 2013 のネットワーク地域、サイト、およびサブネットについて</span><span class="sxs-lookup"><span data-stu-id="3d940-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="3d940-137">Lync Server 2013 でネットワーク地域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="3d940-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="3d940-138">Lync Server 2013 でのネットワークサイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="3d940-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="3d940-139">Lync Server 2013 でのサブネットとネットワークサイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="3d940-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="3d940-140">Lync Server 2013 で通話受付管理を構成する</span><span class="sxs-lookup"><span data-stu-id="3d940-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="3d940-141">Lync Server 2013 での拡張9-1-1 の構成</span><span class="sxs-lookup"><span data-stu-id="3d940-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="3d940-142">Lync Server 2013 でメディアバイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="3d940-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="3d940-143">Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="3d940-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d940-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d940-144">See Also</span></span>


[<span data-ttu-id="3d940-145">Lync Server 2013 でのブランチサイトの展開</span><span class="sxs-lookup"><span data-stu-id="3d940-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="3d940-146">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="3d940-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="3d940-147">Lync Server 2013 でのコールパークの構成</span><span class="sxs-lookup"><span data-stu-id="3d940-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="3d940-148">Lync Server 2013 で割り当てられていない番号のアナウンスを構成する</span><span class="sxs-lookup"><span data-stu-id="3d940-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="3d940-149">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="3d940-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

