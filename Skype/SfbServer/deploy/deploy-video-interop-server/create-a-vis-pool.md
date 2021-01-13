---
title: Skype for Business Server で VIS プールを作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '概要: トポロジ ビルダーを使用して、Skype for Business Server にビデオ相互運用サーバー プールを作成します。'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802057"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="5c0b7-103">Skype for Business Server で VIS プールを作成する</span><span class="sxs-lookup"><span data-stu-id="5c0b7-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="5c0b7-104">**概要:** トポロジ ビルダーを使用して、Skype for Business Server にビデオ相互運用サーバー プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="5c0b7-105">トポロジ ビルダーを使用して VIS または VIS プールを作成する</span><span class="sxs-lookup"><span data-stu-id="5c0b7-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="5c0b7-106">フロントエンド サーバーでトポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="5c0b7-107">トポロジ ビルダーの左側のウィンドウで、[ビデオ相互運用サーバー プール] を右クリックし、[新しいビデオ相互運用サーバー プール]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="5c0b7-108">これにより、新しいビデオ相互運用サーバー **プールの作成ウィザードが開** きます。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="5c0b7-109">新しいビデオ相互運用サーバーのプール FQDN を指定し、このプールに 1 つのサーバーが含まれるか、このプールの要件に基づいて複数のサーバーを持つサーバーを選択して、[次へ] を押 **します**。 </span><span class="sxs-lookup"><span data-stu-id="5c0b7-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="5c0b7-110">高可用性を実現するためにビデオ相互運用サーバー プールを展開する場合は、[このプールには複数のサーバーがあります] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="5c0b7-111">このオプションには、次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="5c0b7-112">ビデオ相互運用サーバー プールをサポートするには、DNS 負荷分散を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="5c0b7-113">次のページで、[このプール内のコンピューターの定義] 項目で、プール内の各サーバーのコンピューター **FQDN** をテキスト フィールドに入力し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="5c0b7-114">この手順を繰り返して、別のビデオ相互運用サーバーをプールに追加します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="5c0b7-115">プール内のすべてのコンピューターを定義した後、[次へ] を **押します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="5c0b7-116">高可用性を必要としないので、プールにビデオ相互運用サーバーを 1 つしか展開しない場合は、[このプールに 1 つのサーバーがある] を選択し、[次へ] を押 **します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="5c0b7-117">ドロップダウン リストから次ホップ プール/FE を選択し、[次へ] を押 **します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="5c0b7-118">VIS に関連付けるエッジ プールを選択し、[完了] を **押します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="5c0b7-119">TCP ポートまたは TLS ポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="5c0b7-120">トポロジ ビルダーの左側のウィンドウから新しく追加したビデオ相互運用サーバーを選択し、右クリックして [プロパティの編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="5c0b7-121">要件に従って TCP ポートまたは TLS ポートを有効または更新し **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="5c0b7-122">既定では TLS が追加されます。ただし、CISCO Unified Communications Manager (CallManager または CUCM) を使用して完全にテストされたのは TCP のみです。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="5c0b7-123">ビデオ ゲートウェイを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-123">Add a video gateway.</span></span> <span data-ttu-id="5c0b7-124">これを行うには、[共有コンポーネント] を展開し、[ **ビデオ** ゲートウェイ] を右クリックして [新しいビデオ ゲートウェイ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="5c0b7-125">ビデオ ゲートウェイの FQDN または IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="5c0b7-126">ビデオ ゲートウェイは、サブドメインまたは別のドメインに含めできます。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="5c0b7-127">システムの VTC で使用される CUCM は、ビデオ ゲートウェイとして機能します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="5c0b7-128">必要に応じて、IPv4 または IPv6 を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="5c0b7-129">構成済みのすべての IP アドレスを使用するか、サービスの使用を選択した IP アドレスに制限できます。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="5c0b7-130">ビデオ ゲートウェイのリッスン ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="5c0b7-131">トランスポート プロトコル (TCP または TLS) を選択し、ビデオ SIP トランク用に設定されたビデオ相互運用サーバーに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="5c0b7-132">ビデオ ゲートウェイのトランスポート プロトコルは、VIS 用に構成されたトランスポート プロトコルと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="5c0b7-133">上記の手順が完了すると、対応する SIP ビデオ トランクが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="5c0b7-134">SIP ビデオ トランクを右クリックし、追加したトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="5c0b7-135">ビデオ SIP トランク名、関連付けられたビデオ相互運用サーバー、SIP トランスポート プロトコル、およびポートはすべて変更できます。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="5c0b7-136">ビデオ相互運用サーバーは、1:N トランクをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="5c0b7-137">したがって、複数のトランクを追加できます。複数のトランクは 1 つのビデオ相互運用サーバーに関連付けられるため、各トランクは異なるビデオ ゲートウェイで終了します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="5c0b7-138">この制限は、特定のビデオ ゲートウェイに、Skype for Business Server 展開に定義できるトランクが 1 つしか含めないという制限です。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="5c0b7-139">「Skype [for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)での新しいトポロジの作成と公開」の説明に従ってトポロジ ドキュメントを公開します。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c0b7-140">回復性を向上させるために、2 つ目のビデオ相互運用サーバーまたは VIS プール、またはバックアップ フロントエンド プールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="5c0b7-141">詳細 [については、「復元メカニズム」](../../plan-your-deployment/video-interop-server.md#resiliency) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="5c0b7-142">トポロジ ビルダーを使用して実行したタスクはすべて完了です。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="5c0b7-143">新しい VIS サーバーへのソフトウェアのインストールに進みます。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="5c0b7-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c0b7-144">See also</span></span>

[<span data-ttu-id="5c0b7-145">Skype for Business Server で VIS サーバーの役割を展開する</span><span class="sxs-lookup"><span data-stu-id="5c0b7-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="5c0b7-146">Skype for Business Server でのビデオ相互運用サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="5c0b7-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="5c0b7-147">Skype for Business Server 2015 での新しいトポロジの作成と公開</span><span class="sxs-lookup"><span data-stu-id="5c0b7-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
