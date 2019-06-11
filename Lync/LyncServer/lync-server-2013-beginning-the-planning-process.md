---
title: 'Lync Server 2013: 計画プロセスの開始'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582769109a3792ddc2efdbef5d4a557b781c39b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="58422-102">Lync Server 2013 の計画プロセスの開始</span><span class="sxs-lookup"><span data-stu-id="58422-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58422-103">_**最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="58422-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="58422-104">オンプレミスのユニファイドコミュニケーションの展開を計画するときに、Lync Server には次のような便利なツールが2つ用意されています。</span><span class="sxs-lookup"><span data-stu-id="58422-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="58422-105">**計画ツール**は、組織、有効にする Lync Server 機能、キャパシティ計画についての一連の質問を表示するウィザードです。</span><span class="sxs-lookup"><span data-stu-id="58422-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="58422-106">次に、回答に基づいて推奨される展開トポロジを作成し、この展開の Microsoft Visio 図面を作成します。</span><span class="sxs-lookup"><span data-stu-id="58422-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="58422-107">**トポロジビルダー**は、Lync Server のインストールコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="58422-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="58422-108">トポロジビルダーを使用して、計画されたトポロジを作成、調整、および公開します。</span><span class="sxs-lookup"><span data-stu-id="58422-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="58422-109">また、サーバーのインストールを開始する前にトポロジを検証することもできます。</span><span class="sxs-lookup"><span data-stu-id="58422-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="58422-110">個々のサーバーに Lync Server をインストールすると、サーバーはインストールプロセスの一環として公開されたトポロジを読み取り、インストールプログラムはトポロジで指示されたとおりにサーバーを配置します。</span><span class="sxs-lookup"><span data-stu-id="58422-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="58422-111">Lync Server 計画ツール</span><span class="sxs-lookup"><span data-stu-id="58422-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="58422-112">計画ツールは、ツールの質問に対する回答を受け取り、Lync Server のガイドラインとベストプラクティスに基づいたトポロジを生成します。</span><span class="sxs-lookup"><span data-stu-id="58422-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="58422-113">また、お客様の回答に基づいて展開の複数のビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="58422-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="58422-114">すべてのサイト (セントラルサイトとブランチサイトを含む) のグローバルビューと、各サイトのサーバーやその他のコンポーネントを示す詳細ビューの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="58422-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="58422-115">計画ツールを実行しても、特定の展開またはプロセスを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="58422-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="58422-116">実際に、計画ツールを使用していない場合でも、計画を立てておく必要がある場合は、計画プロセスで考慮する必要がある質問の種類を理解することができます。</span><span class="sxs-lookup"><span data-stu-id="58422-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="58422-117">計画ツールを複数回実行したり、質問に回答したり、結果を比較したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="58422-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="58422-118">よく満足しているが、変更を加える必要があるデザインがある場合は、計画ツールに戻り、デザインを読み込んで、変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="58422-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="58422-119">計画ツールの完了には15分ほどかかります。</span><span class="sxs-lookup"><span data-stu-id="58422-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="58422-120">問題が解決したら、計画ツールを使用して、計画した展開の図を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="58422-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="58422-121">この図は、トポロジビルダーでの展開の作成時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="58422-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58422-122">このリリースの Lync Server 2013 に含まれている計画ツールはプレリリース版です。</span><span class="sxs-lookup"><span data-stu-id="58422-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="58422-123">計画ツールの処理能力の計画の数値は暫定値であり、最終リリースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="58422-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="58422-124">Lync Server トポロジビルダー</span><span class="sxs-lookup"><span data-stu-id="58422-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="58422-125">展開計画を決定したら、トポロジビルダーを使用して展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="58422-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="58422-126">完了したら、トポロジビルダーを使用してトポロジを検証し、合格した場合はトポロジを公開できます。</span><span class="sxs-lookup"><span data-stu-id="58422-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="58422-127">トポロジを公開すると、Lync Server によって、トポロジが、まだ存在していない場合は、この時点で作成されたセントラル管理ストアに配置されます。</span><span class="sxs-lookup"><span data-stu-id="58422-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="58422-128">展開の各サーバーに Lync Server をインストールすると、サーバーは中央管理ストアからトポロジを読み取り、それ自体を展開の役割に合わせてインストールします。</span><span class="sxs-lookup"><span data-stu-id="58422-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="58422-129">または、Lync Server についてよく理解していて、規範となるガイダンスが必要でない場合は、計画ツールをスキップし、展開の初期設計のためにトポロジビルダーのウィザードを使うことができます。また、検証と発行の手順を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="58422-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="58422-130">トポロジの計画と公開にトポロジビルダーを使用することは、必須の手順です。</span><span class="sxs-lookup"><span data-stu-id="58422-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="58422-131">展開内のサーバーにトポロジビルダーをスキップして Lync Server を個別にインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="58422-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="58422-132">各サーバーは、中央管理ストアの有効な公開トポロジからトポロジを読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="58422-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="58422-133">高レベルの計画プロセス</span><span class="sxs-lookup"><span data-stu-id="58422-133">High-Level Planning Process</span></span>

<span data-ttu-id="58422-134">ドキュメントと計画ツールの両方を使用して Lync Server の展開を計画する場合は、次の一般的なプロセスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58422-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="58422-135">以前のバージョンの Lync Server を使用している場合は、「lync server [2013 の新機能](lync-server-2013-new-features.md)」を参照して、lync server 2013 の新機能と要件について理解してください。</span><span class="sxs-lookup"><span data-stu-id="58422-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="58422-136">ドキュメントのこのセクションの他のトピックを参照してください。トポロジの基礎 lync server [2013 の計画](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [lync server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)、 [lync server 2013 の最初の計画決定](lync-server-2013-initial-planning-decisions.md)、および[Lync Server 2013 のクライアント](lync-server-2013-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="58422-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="58422-137">[Lync Server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)で採用されている計画の決定に注意してください。</span><span class="sxs-lookup"><span data-stu-id="58422-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="58422-138">Lync Server の機能と、回答する必要がある質問の種類について詳しく理解したら、計画ツールを実行し、結果として得られたトポロジとその詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="58422-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="58422-139">トポロジが組織の固有の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="58422-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="58422-140">特定のワークロードや機能が必要な場合、または詳しく知りたい場合は、「 [Lync Server 2013 の計画](lync-server-2013-planning.md)」の該当するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58422-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="58422-141">計画ツールをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="58422-141">Run the Planning Tool again.</span></span> <span data-ttu-id="58422-142">手順3で作成した展開から作業を開始し、結果を変更したり、最初からやり直すことができます。</span><span class="sxs-lookup"><span data-stu-id="58422-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="58422-143">必要に応じて、計画ツールを3回実行して、出力に問題がなければ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="58422-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="58422-144">トポロジ計画を完了したら、計画ツールを使用して、トポロジの Visio 図面を作成し、印刷します。</span><span class="sxs-lookup"><span data-stu-id="58422-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="58422-145">トポロジビルダーを操作しているときに、この印刷イメージを使用してトポロジを入力できます。</span><span class="sxs-lookup"><span data-stu-id="58422-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="58422-146">展開を始める前に、「 [Lync server 2013 のシステム要件を決定](lync-server-2013-determining-your-system-requirements.md)する」および「 [lync server 2013 のインフラストラクチャ要件を決定](lync-server-2013-determining-your-infrastructure-requirements.md)して、前提条件と必要なインフラストラクチャを理解する」を参照してください。Lync Server の場合。</span><span class="sxs-lookup"><span data-stu-id="58422-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="58422-147">さらに、展開する予定のワークロードと機能に適用される[Lync Server 2013 の計画に関する](lync-server-2013-planning.md)すべてのセクションを既にお読みになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58422-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="58422-148">以前のバージョンから移行する</span><span class="sxs-lookup"><span data-stu-id="58422-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="58422-149">以前のバージョンから Lync Server に移行する場合は、移行と展開に関する具体的な手順については、[移行](migration.md)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58422-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

