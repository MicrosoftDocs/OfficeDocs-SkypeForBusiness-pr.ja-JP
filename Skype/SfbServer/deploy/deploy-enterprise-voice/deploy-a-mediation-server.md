---
title: ビジネス サーバーのトポロジ ビルダーで Skype に仲介サーバーを展開します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: '概要: を定義し、ビジネスのサーバーのトポロジ ビルダーで Skype に仲介サーバーを展開する方法を説明します。'
ms.openlocfilehash: 5e4221230fbaf993b5bf3d2b647e6d7e6e7ada51
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371922"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="40e0a-103">ビジネス サーバーのトポロジ ビルダーで Skype に仲介サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="40e0a-104">**の概要:** 定義し、ビジネスのサーバーのトポロジ ビルダーで Skype に仲介サーバーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="40e0a-105">エンタープライズ VoIP のワークロード、ダイヤルイン会議、および高度なエンタープライズ VoIP のアプリケーション (応答グループ アプリケーション、コール パーク アプリケーション、呼受付制御 (CAC)、およびなど) は、フロント エンド プールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="40e0a-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="40e0a-106">フロント エンド サーバーには、仲介サーバーの機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="40e0a-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="40e0a-107">個別のスタンドアロン仲介サーバーが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="40e0a-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="40e0a-108">唯一の例外は、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コントローラーに接続する SIP トランクを構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="40e0a-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="40e0a-109">SIP トランク プロバイダーに、エンタープライズ VoIP インフラストラクチャを接続して、別の仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40e0a-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="40e0a-110">Skype (か、仲介サーバーはフロント エンド プールまたはスタンドアロンの仲介サーバーに併設されている) ビジネス サーバーとゲートウェイ間の接続は、トランクと呼ばれる論理的な関連付けとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="40e0a-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="40e0a-111">このセクションのトピックでは、SIP トランクに接続する場合、トランクを定義する方法と、スタンドアロンの仲介サーバーを展開する方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="40e0a-112">トポロジ ビルダーでの仲介サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="40e0a-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="40e0a-113">仲介サーバーをフロント エンド プールに配置されている役割として追加するか、独立したスタンドアロンの仲介サーバー プールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="40e0a-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="40e0a-114">フロント エンド プールに仲介サーバーを追加するのには</span><span class="sxs-lookup"><span data-stu-id="40e0a-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="40e0a-115">開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**を**Skype ビジネス サーバー 2015Topology ビルダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="40e0a-116">トポロジ ビルダーでは、コンソール ツリーで、フロント エンド プールを定義するサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="40e0a-117">コンソール ツリーで、フロント エンド プールの種類を右クリックし、**新しいフロント エンド プール..**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="40e0a-118">[**併置されたサーバーの役割の選択**] ページが表示されるまで、**新しいフロントエンド プールの定義**ウィザードを進めます。</span><span class="sxs-lookup"><span data-stu-id="40e0a-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="40e0a-119">**選択配置されているサーバーの役割**では、**仲介サーバーの連結**のオプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40e0a-120">選択したフロント エンド プールの種類が、Enterprise Edition の場合は、仲介サーバーのコンポーネントはそのフロント エンド プールのすべてのフロント エンド サーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="40e0a-121">仲介サーバーで使用される**次ホップ プール**の仲介サーバーが併設されているフロント エンド プールとなります。</span><span class="sxs-lookup"><span data-stu-id="40e0a-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="40e0a-122">仲介サーバーによって使用される**エッジ プール**の仲介サーバーが併設されているフロント エンド プールに関連付けられている同じエッジ プールとなります。</span><span class="sxs-lookup"><span data-stu-id="40e0a-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="40e0a-123">PSTN への呼び出しをルーティングするのには、このフロント エンド プールを使用する**既定**のをクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="40e0a-124">フロント エンド プールに 1 つまたは複数のピアに関連付けることが終了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40e0a-125">エンタープライズ VoIP 展開プロセスの次の手順を続行する前に、仲介サーバー プール (つまりフロント エンド プールに仲介サーバー コンポーネントが 1 か所に配置) で指定した Fqdn を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="40e0a-126">**Skype**ビジネス サーバー 2015 のノードを右クリックし、**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="40e0a-127">スタンドアロン仲介サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="40e0a-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="40e0a-128">開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**を**Skype ビジネス サーバー 2015Topology ビルダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="40e0a-129">トポロジ ビルダーでは、コンソール ツリーで、仲介サーバーを定義するサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="40e0a-130">コンソール ツリーで、**仲介プール**] ノードを右クリックし、**仲介サーバー プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="40e0a-131">**新しい仲介プールの定義**には、仲介サーバー プールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="40e0a-132">次に、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="40e0a-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="40e0a-133">高可用性を提供する、プール内の複数の仲介サーバーを展開する場合は、**複数コンピューターのプール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="40e0a-134">[展開](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)を複数の仲介サーバーを持つ仲介サーバー プールをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40e0a-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="40e0a-135">高可用性を必要としないために、プール内の 1 つだけの仲介サーバーを展開する場合は、 **1 台のコンピューターのプール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="40e0a-136">以下のステップは省略してください。</span><span class="sxs-lookup"><span data-stu-id="40e0a-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="40e0a-137">**このプール内のコンピューターを定義する**アイテムで、前の手順で**複数のコンピューターのプール**を選択した場合は、**コンピューターの FQDN**をクリックし、プール内の各サーバーの FQDN を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="40e0a-138">プールに追加する他のすべての仲介サーバーに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="40e0a-139">プール内のすべてのコンピューターを定義したら、**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="40e0a-140">**次ホップの選択**] ページで [**次ホップ プール**] をクリックして、[この仲介サーバーのプールを使用し、[**次へ**] をクリックするフロント エンド プールの FQDN] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="40e0a-141">[**エッジ サーバーの選択**] ページで、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="40e0a-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="40e0a-142">エンタープライズ VoIP を有効にする外部のユーザーに PSTN 接続を提供する場合は、 **[この仲介サーバーによって使用されるエッジ プール**] の下をクリックしてに PSTN 接続を提供するこの仲介サーバー プールを使用するエッジ サーバー プールの FQDN外部ユーザー、し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="40e0a-143">外部ユーザーをエンタープライズ VoIP を有効にする予定がない場合、または内部ネットワーク外のユーザーに PSTN への接続を提供したくない場合は、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="40e0a-144">**Skype**ビジネス サーバー 2015 のノードを右クリックし、**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="40e0a-145">仲介サーバーのリッスン ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="40e0a-146">仲介サーバーをリッスンしているポートを定義するのにはトポロジ ビルダーを使用するには、このトピックの手順に従って、またはプールは、ゲートウェイ ピアからの着信接続が許可されます。</span><span class="sxs-lookup"><span data-stu-id="40e0a-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="40e0a-147">仲介サーバーのリッスン ポートを変更するのには</span><span class="sxs-lookup"><span data-stu-id="40e0a-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="40e0a-148">開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**を**Skype ビジネス サーバー 2015Topology ビルダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="40e0a-149">トポロジ ビルダーでは、コンソール ツリーで、**仲介プール**] ノードを展開し、以前に作成した仲介サーバーを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="40e0a-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="40e0a-150">既定では、仲介サーバー上の SIP リッスン ポートは、ビジネス サーバー、Skype からの TLS トラフィックの 5070 5067 (ゲートウェイなど、PBXes、または SBCs) のピアからの TLS トラフィック用です。</span><span class="sxs-lookup"><span data-stu-id="40e0a-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="40e0a-151">TCP ポートは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="40e0a-151">TCP port is disabled by default.</span></span> <span data-ttu-id="40e0a-152">TLS をサポートしていないゲートウェイがある場合は、TCP ポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40e0a-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="40e0a-153">TLS または TCP リスニング ポート範囲、仲介サーバーは PSTN ゲートウェイからの着信接続を受け入れるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="40e0a-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40e0a-p107">[**TCP ポートの有効化**] がオフになっている場合は、TCP ポート範囲を入力する必要はありません。この設定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="40e0a-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

