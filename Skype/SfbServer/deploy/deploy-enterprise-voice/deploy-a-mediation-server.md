---
title: Skype for Business Server でのトポロジビルダーへの仲介サーバーの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server のトポロジビルダーで仲介サーバーを定義して展開する方法について説明します。'
ms.openlocfilehash: c651ff3e254165161642c4e729d0d4e3f2983023
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767690"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="111ab-103">Skype for Business Server でのトポロジビルダーへの仲介サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="111ab-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="111ab-104">**概要:** Skype for Business Server のトポロジビルダーで仲介サーバーを定義して展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="111ab-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="111ab-105">エンタープライズボイスワークロード、ダイヤルイン会議、高度なエンタープライズボイスアプリケーション (応答グループアプリケーション、コールパークアプリケーション、通話受付制御 (CAC) など) は、フロントエンドプールで利用できます。</span><span class="sxs-lookup"><span data-stu-id="111ab-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="111ab-106">仲介サーバーの機能は、フロントエンドサーバーに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="111ab-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="111ab-107">スタンドアロンの仲介サーバーは別途用意する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="111ab-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="111ab-108">唯一の例外は、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コントローラーに接続する SIP トランクを構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="111ab-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="111ab-109">エンタープライズ Voip インフラストラクチャを SIP トランクプロバイダに接続するには、個別の仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="111ab-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="111ab-110">Skype for Business Server (フロントエンドプールまたはスタンドアロンの仲介サーバーに併置されている仲介サーバー) とゲートウェイとの接続は、トランクと呼ばれる論理的な関連付けとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="111ab-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="111ab-111">このセクションのトピックでは、SIP トランクに接続している場合に、トランクを定義し、スタンドアロンの仲介サーバーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="111ab-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="111ab-112">トポロジ ビルダーでの仲介サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="111ab-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="111ab-113">仲介サーバーは、フロントエンドプールの併置された役割として追加することも、スタンドアロンの仲介サーバープールを個別に定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="111ab-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="111ab-114">フロントエンドプールに仲介サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="111ab-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="111ab-115">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology Builder] の**順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="111ab-116">[トポロジビルダー] のコンソールツリーで、フロントエンドプールを定義するサイト名を展開します。</span><span class="sxs-lookup"><span data-stu-id="111ab-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="111ab-117">コンソールツリーで、使用するフロントエンドプールの種類を右クリックし、[**新しいフロントエンドプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="111ab-118">[**併置されたサーバーの役割の選択**] ページが表示されるまで、**新しいフロントエンド プールの定義**ウィザードを進めます。</span><span class="sxs-lookup"><span data-stu-id="111ab-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="111ab-119">[併置された**サーバーの役割を選択**してください] で、オプションの [**仲介サーバーの検索**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="111ab-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="111ab-120">選択したフロントエンドプールの種類が Enterprise Edition の場合、仲介サーバーコンポーネントは、そのフロントエンドプールのすべてのフロントエンドサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="111ab-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="111ab-121">仲介サーバーによって使用される next-hop**プール**は、仲介サーバーが併置されているフロントエンドプールになります。</span><span class="sxs-lookup"><span data-stu-id="111ab-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="111ab-122">仲介サーバーで使用される**エッジプール**は、仲介サーバーが併置されているフロントエンドプールと同じエッジプールになります。</span><span class="sxs-lookup"><span data-stu-id="111ab-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="111ab-123">[**既定**にする] をクリックして、このフロントエンドプールを使用して PSTN への通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="111ab-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="111ab-124">1つまたは複数のピアのフロントエンドプールへの関連付けが終了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="111ab-125">エンタープライズ Voip 展開プロセスの次の手順に進む前に、指定した Fqdn を使用して、仲介サーバープール (たとえば、仲介サーバーコンポーネントが含まれているフロントエンドプール) であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="111ab-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="111ab-126">[ **Skype For Business Server 2015** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="111ab-127">スタンドアロン仲介サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="111ab-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="111ab-128">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology Builder] の**順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="111ab-129">[トポロジビルダー] のコンソールツリーで、仲介サーバーを定義するサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="111ab-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="111ab-130">コンソールツリーで、[**仲介プール**] ノードを右クリックし、[**仲介サーバープール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="111ab-131">[**新しい仲介プールの定義**] で、仲介サーバープールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="111ab-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="111ab-132">次に、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="111ab-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="111ab-133">プールに複数の仲介サーバーを展開して高可用性を提供する場合は、[**複数のコンピュータープール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="111ab-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="111ab-134">複数の仲介サーバーを含む仲介サーバープールをサポートするには、[展開](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="111ab-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="111ab-135">高可用性を必要としないため、プールに1つの仲介サーバーのみを展開する場合は、[**単一コンピュータープール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="111ab-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="111ab-136">以下のステップは省略してください。</span><span class="sxs-lookup"><span data-stu-id="111ab-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="111ab-137">前の手順**で複数のコンピュータープール**を選択した場合は、[**このプールのコンピューターを定義**する] 項目で [コンピューターの**fqdn**] をクリックし、プール内の各サーバーの fqdn を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="111ab-138">プールに追加するその他のすべての仲介サーバーについて、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="111ab-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="111ab-139">プール内のすべてのコンピューターを定義したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="111ab-140">[**次ホップの選択**] ページで、[**次ホッププール**] をクリックし、この仲介サーバープールを使用するフロントエンドプールの FQDN をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="111ab-141">[**エッジ サーバーの選択**] ページで、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="111ab-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="111ab-142">エンタープライズ Voip が有効になっている外部ユーザーに PSTN 接続を提供する場合は、[**この仲介サーバーで使用されるエッジプールを選択**してください] で、この仲介サーバープールを使用してそれらの外部ユーザーへの pstn 接続を提供するエッジサーバープールの FQDN をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="111ab-143">外部ユーザーをエンタープライズボイスとして有効にする予定がない場合、または内部ネットワークの外部にいるユーザーに PSTN 接続を提供しない場合は、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="111ab-144">[ **Skype For Business Server 2015** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="111ab-145">仲介サーバーのリッスンポートを定義する</span><span class="sxs-lookup"><span data-stu-id="111ab-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="111ab-146">このトピックの手順に従って、トポロジビルダーを使用してリッスンポートを定義します。仲介サーバーまたはプールは、ゲートウェイピアからの着信接続を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="111ab-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="111ab-147">仲介サーバーのリッスンポートを変更するには</span><span class="sxs-lookup"><span data-stu-id="111ab-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="111ab-148">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology Builder] の**順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="111ab-149">[トポロジビルダー] のコンソールツリーで、[**仲介プール**] ノードを展開し、前に作成した仲介サーバーを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="111ab-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="111ab-150">既定では、仲介サーバーの SIP リスニングポートは、Skype for Business Server からの TLS トラフィック用の5070であり、ピアからの TLS トラフィック (ゲートウェイ、PBXes、または SBCs など) を5067します。</span><span class="sxs-lookup"><span data-stu-id="111ab-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="111ab-151">TCP ポートは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="111ab-151">TCP port is disabled by default.</span></span> <span data-ttu-id="111ab-152">TLS をサポートしていないゲートウェイがある場合は、TCP ポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="111ab-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="111ab-153">目的の TLS または TCP リッスンポートの範囲を指定する仲介サーバーは、PSTN ゲートウェイからの着信接続を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="111ab-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="111ab-p107">[**TCP ポートの有効化**] がオフになっている場合は、TCP ポート範囲を入力する必要はありません。この設定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="111ab-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

