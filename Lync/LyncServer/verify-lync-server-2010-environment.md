---
title: Lync Server 2010 環境の確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce56a23120df813d3c3d8107de67d202afb5d663
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="8cb67-102">Lync Server 2010 環境の確認</span><span class="sxs-lookup"><span data-stu-id="8cb67-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cb67-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8cb67-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8cb67-104">Lync server 2010 を使用して Lync Server 2013 を共存状態に展開する前に、lync Server 2010 サービスが構成され、起動していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cb67-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="8cb67-105">Lync Server 2013 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8cb67-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="8cb67-106">レガシ XMPP 展開を使用して、Microsoft Lync Server 2013 XMPP を共存状態に展開する前に、従来の XMPP サービスが構成されて起動していることを確認し、従来の XMPP 構成がサポートしているフェデレーションパートナーを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cb67-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="8cb67-107">従来の Lync Server 2010 の展開を確認するには、次のことが伴います。</span><span class="sxs-lookup"><span data-stu-id="8cb67-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="8cb67-108">Lync Server 2010 サービスが開始されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="8cb67-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="8cb67-109">Lync Server 2010 のトポロジとユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="8cb67-110">フェデレーションとエッジ サーバーの設定を確認する。</span><span class="sxs-lookup"><span data-stu-id="8cb67-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="8cb67-111">XMPP サービスとフェデレーション パートナーを確認する。</span><span class="sxs-lookup"><span data-stu-id="8cb67-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="8cb67-112">**Lync Server 2010 サービスが開始されていることを確認する**</span><span class="sxs-lookup"><span data-stu-id="8cb67-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="8cb67-113">Lync Server 2010 フロントエンドサーバーから、[管理ツール\\] [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="8cb67-114">次のサービスがフロントエンド サーバーで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="8cb67-115">![フロントエンドサーバーで実行されているサービスの一覧](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "フロントエンドサーバーで実行されているサービスの一覧")</span><span class="sxs-lookup"><span data-stu-id="8cb67-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="8cb67-116">**Lync Server コントロールパネルで Lync Server 2010 トポロジを確認する**</span><span class="sxs-lookup"><span data-stu-id="8cb67-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="8cb67-117">RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8cb67-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="8cb67-118">Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8cb67-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="8cb67-119">[**トポロジ**] クリックします。</span><span class="sxs-lookup"><span data-stu-id="8cb67-119">Select **Topology**.</span></span> <span data-ttu-id="8cb67-120">Lync Server 2010 の展開に含まれるさまざまなサーバーが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="8cb67-121">![Lync Server 2010 コントロールパネルのトポロジページ](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 コントロールパネルのトポロジページ")</span><span class="sxs-lookup"><span data-stu-id="8cb67-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="8cb67-122">**Lync server コントロールパネルで Lync Server 2010 ユーザーを確認するには**</span><span class="sxs-lookup"><span data-stu-id="8cb67-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="8cb67-123">Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8cb67-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="8cb67-124">[**ユーザー**]、[**検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cb67-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="8cb67-125">[**レジストラープール**] 列が、表示されている各ユーザーの Lync Server 2010 プールを指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="8cb67-126">![Lync Server 2010 コントロールパネルのユーザー一覧](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 コントロールパネルのユーザー一覧")</span><span class="sxs-lookup"><span data-stu-id="8cb67-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="8cb67-127">**Lync Server 2010 のエッジとフェデレーションの設定を確認するには**</span><span class="sxs-lookup"><span data-stu-id="8cb67-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="8cb67-128">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="8cb67-129">[**既存の展開からトポロジをダウンロードする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cb67-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="8cb67-130">ファイル名を選択して、既定のファイルの種類である .tbxml でトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="8cb67-131">[Lync Server 2010] ノードを展開して、展開に含まれるさまざまなサーバーの役割を確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="8cb67-132">サイト ノードを選択して、[**サイトのフェデレーション ルートの割り当て**] に値が設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="8cb67-133">![トポロジビルダー、サイトのフェデレーションルート](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "トポロジビルダー、サイトのフェデレーションルート")</span><span class="sxs-lookup"><span data-stu-id="8cb67-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="8cb67-p103">次に、Standard Edition Server または Enterprise Edition のフロントエンド プールを選択します。[**関連付け**] の下のメディアに対してエッジ プールが構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="8cb67-136">![トポロジビルダー、サーバーとプールが表示されている](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "トポロジビルダー、サーバーとプールが表示されている")</span><span class="sxs-lookup"><span data-stu-id="8cb67-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="8cb67-137">最後に、エッジ プールを選択して、[**次ホップの選択**] の下に次ホップ プールが構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="8cb67-138">![トポロジビルダー、次ホップの選択](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "トポロジビルダー、次ホップの選択")</span><span class="sxs-lookup"><span data-stu-id="8cb67-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="8cb67-139">**レガシ XMPP フェデレーション パートナーの構成を確認する**</span><span class="sxs-lookup"><span data-stu-id="8cb67-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="8cb67-140">従来の XMPP サーバーから、[管理ツール\\] [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="8cb67-141">Office Communications Server XMPP Gateway サービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb67-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="8cb67-142">![Office Communications Server XMPP ゲートウェイサービス](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP ゲートウェイサービス")</span><span class="sxs-lookup"><span data-stu-id="8cb67-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

