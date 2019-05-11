---
title: Skype のビジネス サーバーの VIS プールを作成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '概要: は、トポロジ ビルダーを使用してビジネスのサーバーの Skype でビデオの相互運用機能のサーバー プールを作成します。'
ms.openlocfilehash: f290da287dc4e45a35d5d088e331d2c2540585ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894713"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="a96b8-103">Skype のビジネス サーバーの VIS プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="a96b8-104">**の概要:** トポロジ ビルダーを使用してビジネス サーバーの Skype でのビデオの相互運用機能のサーバー プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="a96b8-105">トポロジ ビルダーを使用して VIS または VIS プールを作成する</span><span class="sxs-lookup"><span data-stu-id="a96b8-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="a96b8-106">フロントエンド サーバーでトポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="a96b8-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="a96b8-107">トポロジ ビルダーの左ペインで、**ビデオの相互運用機能のサーバー プール**を右クリックし、**新しいビデオの相互運用機能のサーバー プール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="a96b8-108">この操作を行うと、[**ビデオ相互運用サーバー プールの新規作成**] ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a96b8-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="a96b8-109">新しいビデオの相互運用機能のサーバーのプールの FQDN を提供し、**このプールには 1 つのサーバー**または**このプールが複数のサーバーには**、お客様の要件に基づいて選択し、[**次**] を押します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="a96b8-110">高可用性を提供するビデオの相互運用機能のサーバー プールを展開する場合は、**このプールには複数のサーバー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="a96b8-111">このオプションを使用する場合は次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a96b8-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="a96b8-112">ビデオの相互運用機能のサーバー プールをサポートするための DNS 負荷分散を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a96b8-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="a96b8-113">次のページの [**このプール内のコンピューターを定義します**] の項目で、プール内の各サーバーの**コンピューターの FQDN** をテキスト フィールドに入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a96b8-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="a96b8-114">ビデオの相互運用機能の別のサーバーをプールに追加するには、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="a96b8-115">プール内のすべてのコンピューターを定義したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a96b8-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="a96b8-116">高可用性を必要としないために、プール内の 1 つだけのビデオの相互運用機能サーバーを配置する場合は、**このプールには 1 つのサーバー**を選択し、**次**のキーを押します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="a96b8-117">ドロップダウン リストから次ホップ プール/FE を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a96b8-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="a96b8-118">VIS と関連付けるエッジ プールを選択して、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a96b8-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="a96b8-119">TCP ポートまたは TLS ポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="a96b8-120">トポロジ ビルダーの左ウィンドウから新しく追加されたビデオの相互運用機能のサーバーを選択して右クリックして、**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="a96b8-121">要件に応じて TCP ポートまたは TLS ポートを有効にするか更新して、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="a96b8-122">既定で TLS の追加は、TCP のみが完全にテストされてシスコ ユニファイド コミュニケーション マネージャーを使用して (CallManager、または CUCM)。</span><span class="sxs-lookup"><span data-stu-id="a96b8-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="a96b8-p106">ビデオ ゲートウェイを追加します。この操作を行うには、[共有コンポーネント] を展開して、[**ビデオ ゲートウェイ**] を右クリックして、[**新しいビデオ ゲートウェイ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="a96b8-p107">ビデオ ゲートウェイの FQDN または IP アドレスを指定します。ビデオ ゲートウェイは、サブドメインまたは別のドメインに含めることができます。システムの VTC により使用される CUCM は、ビデオ ゲートウェイの役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="a96b8-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="a96b8-p108">IPv4 と IPv6 のいずれか適切な方を選択します。すべての構成済み IP アドレスを使用するか、サービスの使用を選択済みの IP アドレスに限定することができます。</span><span class="sxs-lookup"><span data-stu-id="a96b8-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="a96b8-130">ビデオ ゲートウェイのリッスン ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="a96b8-131">トランスポート プロトコル (TCP または TLS) を選択し、SIP トランクをビデオに設定されているビデオの相互運用サーバーに関連付けることです。</span><span class="sxs-lookup"><span data-stu-id="a96b8-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="a96b8-132">ビデオ ゲートウェイのトランスポート プロトコルは、VIS 向けに構成されているトランスポート プロトコルと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a96b8-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="a96b8-133">上記の手順の完了後、対応する SIP ビデオ トランクが追加されます。</span><span class="sxs-lookup"><span data-stu-id="a96b8-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="a96b8-134">その SIP ビデオ トランクを右クリックして、追加されたばかりのトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="a96b8-135">ビデオの SIP トランクの名前に関連するビデオの相互運用機能のサーバー、SIP トランスポート プロトコルとポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a96b8-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="a96b8-136">ビデオの相互運用機能のサーバーでは、1: n のトランクをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a96b8-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="a96b8-137">したがって複数のトランクを追加できる別のビデオ ゲートウェイの各トランクが終了する、1 つのビデオ相互運用サーバーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="a96b8-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="a96b8-138">制限は、特定のビデオ ゲートウェイがビジネスのサーバーの展開の Skype には、1 つのトランクを持っています。</span><span class="sxs-lookup"><span data-stu-id="a96b8-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="a96b8-139">説明したように、トポロジ ドキュメントを公開[を作成するビジネス サーバー 2015 の Skype の新しいトポロジを公開し、](../../deploy/install/create-and-publish-new-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="a96b8-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a96b8-140">弾力性を高めるためには、2 番目のビデオの相互運用機能のサーバーまたは VIS プール、またはバックアップのフロント エンド プールを構成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a96b8-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="a96b8-141">詳細については、「[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a96b8-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="a96b8-142">トポロジ ビルダーを使用して実行するすべてのタスクはこれで完了します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="a96b8-143">新しい VIS サーバー (複数可) へのソフトウェアのインストール作業に進みます。</span><span class="sxs-lookup"><span data-stu-id="a96b8-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="a96b8-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="a96b8-144">See also</span></span>

[<span data-ttu-id="a96b8-145">Skype で VIS のサーバーの役割をビジネスのサーバーの展開します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="a96b8-146">ビジネス サーバーに、Skype でのビデオの相互運用サーバーを計画します。</span><span class="sxs-lookup"><span data-stu-id="a96b8-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="a96b8-147">Skype for Business Server 2015 での新しいトポロジの作成および公開</span><span class="sxs-lookup"><span data-stu-id="a96b8-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
