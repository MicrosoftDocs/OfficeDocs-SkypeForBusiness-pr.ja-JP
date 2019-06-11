---
title: Lync Server 2010 環境の確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="d9ea5-102">Lync Server 2010 環境の確認</span><span class="sxs-lookup"><span data-stu-id="d9ea5-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9ea5-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d9ea5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d9ea5-104">Lync server 2010 を使用した共存状態で lync server 2013 を展開する前に、lync Server 2010 サービスが構成され、開始されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="d9ea5-105">Lync Server 2013 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="d9ea5-106">従来の XMPP 展開で Microsoft Lync Server 2013 XMPP を共存状態で展開する前に、以前の xmpp サービスが構成されて開始されていることを確認して、従来の XMPP 構成でサポートされているフェデレーションパートナーを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="d9ea5-107">従来の Lync Server 2010 の展開を確認するには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="d9ea5-108">Lync Server 2010 サービスが開始されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="d9ea5-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="d9ea5-109">Lync Server 2010 でトポロジとユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="d9ea5-110">フェデレーションとエッジサーバーの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="d9ea5-111">XMPP サービスおよびフェデレーションパートナーを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="d9ea5-112">**Lync Server 2010 サービスが開始されていることを確認する**</span><span class="sxs-lookup"><span data-stu-id="d9ea5-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="d9ea5-113">Lync Server 2010 フロントエンドサーバーから、管理ツール\\の [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="d9ea5-114">フロントエンドサーバーで次のサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="d9ea5-115">![フロントエンドサーバーで実行されているサービスの一覧](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "フロントエンドサーバーで実行されているサービスの一覧")</span><span class="sxs-lookup"><span data-stu-id="d9ea5-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="d9ea5-116">**Lync server のコントロールパネルで Lync Server 2010 トポロジを確認する**</span><span class="sxs-lookup"><span data-stu-id="d9ea5-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="d9ea5-117">RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="d9ea5-118">Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="d9ea5-119">[**トポロジ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-119">Select **Topology**.</span></span> <span data-ttu-id="d9ea5-120">Lync Server 2010 の展開に含まれるさまざまなサーバーが一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="d9ea5-121">![Lync Server 2010 コントロールパネルのトポロジページ](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 コントロールパネルのトポロジページ")</span><span class="sxs-lookup"><span data-stu-id="d9ea5-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="d9ea5-122">**Lync server の [コントロールパネル] の Lync Server 2010 ユーザーを確認するには**</span><span class="sxs-lookup"><span data-stu-id="d9ea5-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="d9ea5-123">Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="d9ea5-124">[**ユーザー** ] を選択し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="d9ea5-125">**レジストラー pool**列が、表示されている各ユーザーの Lync Server 2010 プールをポイントしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="d9ea5-126">![Lync Server 2010 コントロールパネルのユーザーの一覧](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 コントロールパネルのユーザーの一覧")</span><span class="sxs-lookup"><span data-stu-id="d9ea5-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="d9ea5-127">**Lync Server 2010 Edge およびフェデレーション設定を確認するには**</span><span class="sxs-lookup"><span data-stu-id="d9ea5-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="d9ea5-128">トポロジビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="d9ea5-129">[**既存の展開からトポロジをダウンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="d9ea5-130">ファイル名を選択し、tbxml ファイルの種類が設定されたトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="d9ea5-131">[Lync Server 2010] ノードを展開して、展開内のさまざまなサーバーの役割を表示します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="d9ea5-132">サイトノードを選択し、[**サイトフェデレーションルートの割り当て**] の値が設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="d9ea5-133">![トポロジビルダー、サイトフェデレーションルート](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "トポロジビルダー、サイトフェデレーションルート")</span><span class="sxs-lookup"><span data-stu-id="d9ea5-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="d9ea5-134">次に、Standard Edition Server または Enterprise Edition のフロントエンドプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="d9ea5-135">エッジプールが**関連付け**の下にあるメディアに対して構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="d9ea5-136">![サーバーとプールを表示するトポロジビルダー](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "サーバーとプールを表示するトポロジビルダー")</span><span class="sxs-lookup"><span data-stu-id="d9ea5-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="d9ea5-137">最後に、エッジプールを選択して、次ホッププールが**次ホップの選択**の下に構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="d9ea5-138">![トポロジビルダー、次ホップの選択](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "トポロジビルダー、次ホップの選択")</span><span class="sxs-lookup"><span data-stu-id="d9ea5-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="d9ea5-139">**従来の XMPP フェデレーションパートナーの構成を確認する**</span><span class="sxs-lookup"><span data-stu-id="d9ea5-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="d9ea5-140">従来の XMPP サーバーから、管理ツール\\の [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="d9ea5-141">Office Communications Server XMPP ゲートウェイサービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ea5-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="d9ea5-142">![Office Communications Server XMPP ゲートウェイサービス](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP ゲートウェイサービス")</span><span class="sxs-lookup"><span data-stu-id="d9ea5-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

