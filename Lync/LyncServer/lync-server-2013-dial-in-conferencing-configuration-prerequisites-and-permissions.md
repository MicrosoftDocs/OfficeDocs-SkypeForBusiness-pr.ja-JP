---
title: ダイヤルイン会議の前提条件とアクセス許可
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6610272c39583b70c1ab20d8271551796f65372
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="95133-102">Lync Server 2013 のダイヤルイン会議の前提条件とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="95133-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95133-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="95133-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="95133-104">ダイヤルイン会議は、Lync Server 2013 会議のワークロードのオプションコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="95133-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="95133-105">トポロジビルダーを使用してトポロジを設計し、フロントエンドプールまたは Standard Edition サーバーをセットアップするときに、ダイヤルイン会議を構成する前にインストールする必要があるコンポーネントを展開します。</span><span class="sxs-lookup"><span data-stu-id="95133-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="95133-106">このトピックでは、ダイヤルイン会議を構成する前に完了しておく必要があることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="95133-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="95133-107">このセクションでは、会議のワークロードとダイヤルイン会議に関連する計画セクションを既に読んでいることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="95133-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="95133-108">ダイヤルイン会議構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="95133-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="95133-109">ダイヤルイン会議には、次の Lync Server 2013 コンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="95133-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="95133-110">統合コミュニケーション アプリケーション サービス (UCAS) (*アプリケーション サービス*と呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="95133-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="95133-111">会議アテンダント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="95133-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="95133-112">会議アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="95133-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="95133-113">ダイヤルイン会議設定 Web ページ</span><span class="sxs-lookup"><span data-stu-id="95133-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="95133-114">少なくとも1つの Lync Server 2013 仲介サーバーと1つの PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="95133-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="95133-115">トポロジビルダーを使用してトポロジを定義および公開し、フロントエンドプールまたは Standard Edition サーバーを展開するときに、これらのコンポーネントを展開します。</span><span class="sxs-lookup"><span data-stu-id="95133-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="95133-116">エンタープライズ Voip を展開する場合は、ダイヤルイン会議を構成する前に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95133-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="95133-117">エンタープライズ Voip を展開していない場合は、フロントエンドプールまたは Standard Edition サーバーを展開するときに、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイを展開できます。</span><span class="sxs-lookup"><span data-stu-id="95133-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="95133-118">Office Communications Server 2007 R2 から Lync Server 2013 にアップグレードする場合は、Lync Server 2013 会議のホストに使用する予定のすべてのプールにダイヤルイン会議を展開します。</span><span class="sxs-lookup"><span data-stu-id="95133-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="95133-119">ダイヤルイン会議の移行の詳細については、「 <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Office Communications Server 2007 R2 から Lync Server 2013 への移行</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95133-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="95133-120">このセクションでは、次の作業を行っていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="95133-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="95133-121">Lync Server 2013 に移行している場合は、Office Communications Server 2007 R2 環境に最新の更新プログラムを適用しました。</span><span class="sxs-lookup"><span data-stu-id="95133-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="95133-122">トポロジの設計と構成に使用されるトポロジビルダー。</span><span class="sxs-lookup"><span data-stu-id="95133-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="95133-123">会議のワークロードを指定しているときに、[ダイヤルイン会議] オプションを選択しました。</span><span class="sxs-lookup"><span data-stu-id="95133-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="95133-124">トポロジの定義の詳細については、展開ドキュメントの「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95133-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="95133-125">トポロジを公開し、フロントエンドプールまたは Standard Edition サーバーをセットアップしました。</span><span class="sxs-lookup"><span data-stu-id="95133-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="95133-126">トポロジの発行と Lync Server 2013 のインストールの詳細については、「展開ドキュメントに[Lync server 2013 を展開](lync-server-2013-deploying-lync-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95133-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="95133-127">公開されたトポロジをインストールすると、ダイヤルイン会議の設定の web ページは、Web サービスの一部としてフロントエンドサーバーまたは Standard Edition サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="95133-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="95133-128">Lync Server 2013 を展開した後に、トポロジビルダーでファイルストアのパスを変更する場合は、新しいパスを使用するために、会議アテンダントと会議のアナウンスメントアプリケーションを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95133-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="95133-129">展開されたエンタープライズ Voip。</span><span class="sxs-lookup"><span data-stu-id="95133-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="95133-130">エンタープライズ Voip を展開していない場合は、Enterprise Edition フロントエンドサーバーまたは Standard Edition サーバーで仲介サーバーを使用しているか、スタンドアロンの仲介サーバーを展開して、PSTN ゲートウェイを展開しています。</span><span class="sxs-lookup"><span data-stu-id="95133-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="95133-131">エンタープライズ Voip の展開の詳細については、展開ドキュメントの「 [Lync Server 2013 でのエンタープライズ voip の展開](lync-server-2013-deploying-enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95133-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="95133-132">スタンドアロンの仲介サーバーと PSTN ゲートウェイのインストールの詳細については、展開ドキュメントの「 [Lync server 2013 での仲介サーバーの展開とピアの定義](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95133-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="95133-133">次のフローチャートは、ダイヤルイン会議を構成する前に実行する必要のある手順と、ダイヤルイン会議を構成するために実行する手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="95133-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="95133-134">**ダイヤルイン会議の展開**</span><span class="sxs-lookup"><span data-stu-id="95133-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="95133-135">![ダイヤルイン会議の展開フローチャート](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "ダイヤルイン会議の展開フローチャート")</span><span class="sxs-lookup"><span data-stu-id="95133-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="95133-136">ダイヤルイン会議の権限</span><span class="sxs-lookup"><span data-stu-id="95133-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="95133-137">ダイヤルイン会議を構成するには、次の管理ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95133-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="95133-138">Lync Server 2013 コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="95133-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="95133-139">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="95133-139">Lync Server Management Shell</span></span>

<span data-ttu-id="95133-140">これらの管理ツールを使用して、ダイヤルイン会議の設定、ダイヤルイン会議に必要なダイヤルプラン、ポリシー、その他の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="95133-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="95133-141">ダイヤルイン会議を構成するには、タスクに応じて次の管理者ロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="95133-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="95133-142">\*\*\*\*   この管理者の役割を CsVoiceAdministrator すると、音声関連の設定とポリシーを作成、構成、管理できます。</span><span class="sxs-lookup"><span data-stu-id="95133-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="95133-143">**Csuseradministrator**   この管理者ロールは、Lync Server のユーザーを有効または無効にして、会議ポリシーや PIN ポリシーなどの既存のポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="95133-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="95133-144">**Csadministrator**   この管理者ロールは、CsVoiceAdministrator と csuseradministrator のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="95133-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95133-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="95133-145">See Also</span></span>


[<span data-ttu-id="95133-146">Lync Server 2013 でのエンタープライズボイスの展開</span><span class="sxs-lookup"><span data-stu-id="95133-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

