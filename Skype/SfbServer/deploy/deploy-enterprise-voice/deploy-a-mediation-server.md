---
title: Skype for Business Server のトポロジ ビルダーで仲介サーバーを展開する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: '概要: Skype for Business Server のトポロジ ビルダーで仲介サーバーを定義および展開する方法について学習します。'
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836917"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="f81cf-103">Skype for Business Server のトポロジ ビルダーで仲介サーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="f81cf-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="f81cf-104">**概要:** Skype for Business Server のトポロジ ビルダーで仲介サーバーを定義および展開する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="f81cf-105">フロント エンタープライズ VoIP プールでは、エンタープライズ VoIP ワークロード、ダイヤルイン会議、および高度な エンタープライズ VoIP アプリケーション (応答グループ アプリケーション、コール パーク アプリケーション、通話受付管理 (CAC) など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f81cf-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="f81cf-106">仲介サーバーの機能は、フロントエンド サーバーに組み込されています。</span><span class="sxs-lookup"><span data-stu-id="f81cf-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="f81cf-107">独立したスタンドアロンの仲介サーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f81cf-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="f81cf-108">唯一の例外は、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コントローラーに接続する SIP トランクを構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="f81cf-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="f81cf-109">SIP トランク プロバイダーエンタープライズ VoIPインフラストラクチャを接続するには、別の仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f81cf-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="f81cf-110">Skype for Business Server (フロントエンド プールまたはスタンドアロンの仲介サーバーに展開された仲介サーバー) とゲートウェイの間の接続は、トランクと呼ばれる論理関連付けとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="f81cf-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="f81cf-111">このセクションのトピックでは、トランクを定義する方法と、SIP トランクに接続する場合にスタンドアロンの仲介サーバーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="f81cf-112">トポロジ ビルダーを使用した仲介サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="f81cf-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="f81cf-113">仲介サーバーは、フロントエンド プール上の同じ役割として追加するか、独立したスタンドアロンの仲介サーバー プールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f81cf-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="f81cf-114">仲介サーバーをフロントエンド プールに追加するには</span><span class="sxs-lookup"><span data-stu-id="f81cf-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="f81cf-115">トポロジ ビルダーを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server 2015Topology Builder]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f81cf-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="f81cf-116">トポロジ ビルダーのコンソール ツリーで、フロントエンド プールを定義するサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="f81cf-117">コンソール ツリーで、使用するフロントエンド プールの種類を右クリックし、[新しいフロントエンド プール] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="f81cf-118">[**併置されたサーバーの役割の選択**] ページが表示されるまで、**新しいフロントエンド プールの定義** ウィザードを進めます。</span><span class="sxs-lookup"><span data-stu-id="f81cf-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="f81cf-119">[Select **collocated server roles] (** サーバーの役割の選択) で、[仲介サーバーを **一覧に表示する] オプションをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f81cf-120">選択したフロントエンド プールの種類が Enterprise Edition の場合、仲介サーバー コンポーネントはそのフロントエンド プールのすべてのフロントエンド サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f81cf-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="f81cf-121">仲介 **サーバーによって使用** される次ホップ プールは、仲介サーバーが同じ場所にあるフロントエンド プールになります。</span><span class="sxs-lookup"><span data-stu-id="f81cf-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="f81cf-122">仲介 **サーバーによって** 使用されるエッジ プールは、仲介サーバーが一緒に展開されているフロントエンド プールに関連付けられたエッジ プールと同じになります。</span><span class="sxs-lookup"><span data-stu-id="f81cf-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="f81cf-123">この **フロントエンド プールを使用** して通話を PSTN にルーティングするには、[既定値にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f81cf-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="f81cf-124">**1** つ以上のピアをフロントエンド プールに関連付け終わったら、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f81cf-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f81cf-125">エンタープライズ VoIP 展開プロセスの次の手順に進む前に、仲介サーバー プール (仲介サーバー コンポーネントが配置されたフロントエンド プール) が、指定した FQDN を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="f81cf-126">Skype for **Business Server 2015 ノード** を右クリックし、[トポロジの公開] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="f81cf-127">スタンドアロンの仲介サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="f81cf-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="f81cf-128">トポロジ ビルダーを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server 2015Topology Builder]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f81cf-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="f81cf-129">トポロジ ビルダーのコンソール ツリーで、仲介サーバーを定義するサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="f81cf-130">コンソール ツリーで、[仲介プール]ノードを右クリックし、[仲介サーバー プール]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="f81cf-131">[ **新しい仲介プールの** 定義] に、仲介サーバー プールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="f81cf-132">次に、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f81cf-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="f81cf-133">高可用性を実現するためにプールに複数の仲介サーバーを展開する場合は、[複数のコンピューター プール] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f81cf-134">複数の [仲介サーバー](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) を持つ仲介サーバー プールをサポートするために展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f81cf-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="f81cf-135">高可用性を必要としないので、仲介サーバーをプールに 1 台だけ展開する場合は、[単一コンピューター のプール] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="f81cf-136">以下のステップは省略してください。</span><span class="sxs-lookup"><span data-stu-id="f81cf-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="f81cf-137">前の手順で[複数のコンピューター プール] を選択した場合は、[このプール内のコンピューターの定義] 項目で、[コンピューター **の FQDN]** をクリックし、プール内の各サーバーの FQDN を入力して、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f81cf-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="f81cf-138">プールに追加する他のすべての仲介サーバーに対して、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="f81cf-139">プール内のすべてのコンピューターを定義した後、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="f81cf-140">[次ホップ **の** 選択] ページで、[次ホップ プール] をクリックし、この仲介サーバー プールを使用するフロントエンド プールの FQDN をクリックして、[次へ]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="f81cf-141">[**エッジ サーバーの選択**] ページで、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f81cf-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="f81cf-142">エンタープライズ VoIP が有効になっている外部ユーザーに PSTN 接続を提供する場合は、この仲介サーバーで使用されるエッジ プールの選択で、この仲介サーバー プールを使用してこれらの外部ユーザーに PSTN 接続を提供するエッジ サーバー プールのFQDN をクリックし、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f81cf-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="f81cf-143">エンタープライズ VoIP に対して外部ユーザーを有効にしない場合、またはユーザーが内部ネットワーク外のユーザーに PSTN 接続を提供しない場合は、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="f81cf-144">Skype for **Business Server 2015 ノード** を右クリックし、[トポロジの公開] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f81cf-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="f81cf-145">仲介サーバーのリッスン ポートの定義</span><span class="sxs-lookup"><span data-stu-id="f81cf-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="f81cf-146">このトピックの手順に従って、トポロジ ビルダーを使用して、仲介サーバーまたはプールがゲートウェイ ピアからの着信接続を受け入れるリッスン ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="f81cf-147">仲介サーバーのリッスン ポートを変更するには</span><span class="sxs-lookup"><span data-stu-id="f81cf-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="f81cf-148">トポロジ ビルダーを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server 2015Topology Builder]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f81cf-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="f81cf-149">トポロジ ビルダーのコンソール ツリーで、[仲介プール]ノードを展開し、前に作成した仲介サーバーを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f81cf-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="f81cf-150">既定では、仲介サーバーの SIP リッスン ポートは、Skype for Business Server からの TLS トラフィックの場合は 5070、ピア (ゲートウェイ、PBX、SBC など) からの TLS トラフィックの場合は 5067 です。</span><span class="sxs-lookup"><span data-stu-id="f81cf-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="f81cf-151">TCP ポートは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f81cf-151">TCP port is disabled by default.</span></span> <span data-ttu-id="f81cf-152">TLS をサポートしていないゲートウェイがある場合は、TCP ポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f81cf-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="f81cf-153">仲介サーバーが PSTN ゲートウェイからの着信接続を受け付ける目的の TLS または TCP リッスン ポート範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="f81cf-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f81cf-154">[**TCP ポートの有効化**] がオフになっている場合は、TCP ポート範囲を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f81cf-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="f81cf-155">この設定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="f81cf-155">This setting is optional.</span></span>
  

