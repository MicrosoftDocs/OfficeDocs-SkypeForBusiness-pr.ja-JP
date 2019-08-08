---
title: Skype for Business Server で VIS プールを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '概要: トポロジビルダーを使用して、Skype for Business Server でビデオ相互運用機能サーバープールを作成します。'
ms.openlocfilehash: dc97fde4447778be20cb60d86cddac65b663c321
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235663"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="919c8-103">Skype for Business Server で VIS プールを作成する</span><span class="sxs-lookup"><span data-stu-id="919c8-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="919c8-104">**概要:** トポロジビルダーを使用して、Skype for Business Server でビデオ相互運用サーバープールを作成します。</span><span class="sxs-lookup"><span data-stu-id="919c8-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="919c8-105">トポロジ ビルダーを使用して VIS または VIS プールを作成する</span><span class="sxs-lookup"><span data-stu-id="919c8-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="919c8-106">フロントエンド サーバーでトポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="919c8-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="919c8-107">Topology Builder の左側のウィンドウで、[**ビデオ相互運用機能サーバー**プール] を右クリックし、[**新しいビデオ相互運用機能サーバープール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="919c8-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="919c8-108">この操作を行うと、[**ビデオ相互運用サーバー プールの新規作成**] ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="919c8-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="919c8-109">新しいビデオ相互運用サーバーのプール FQDN を指定し、**このプールに1つのサーバーが**あるか、またはこのプールに要件に基づいて**複数のサーバーが**あるかを選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919c8-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="919c8-110">高可用性を実現するためにビデオ相互運用機能サーバープールを展開する場合は、[**このプールは複数のサーバー**を使用する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="919c8-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="919c8-111">このオプションを使用する場合は次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="919c8-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="919c8-112">ビデオ相互運用サーバープールをサポートするには、DNS の負荷分散を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="919c8-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="919c8-113">次のページの [**このプール内のコンピューターを定義します**] の項目で、プール内の各サーバーの**コンピューターの FQDN** をテキスト フィールドに入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919c8-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="919c8-114">この手順を繰り返して、別のビデオ相互運用サーバーをプールに追加します。</span><span class="sxs-lookup"><span data-stu-id="919c8-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="919c8-115">プール内のすべてのコンピューターを定義したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919c8-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="919c8-116">高可用性を必要としないため、プールに1つのビデオ相互運用サーバーのみを展開する場合は、[**このプールは1台のサーバー**を使用する] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919c8-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="919c8-117">ドロップダウン リストから次ホップ プール/FE を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919c8-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="919c8-118">VIS と関連付けるエッジ プールを選択して、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919c8-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="919c8-119">TCP ポートまたは TLS ポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="919c8-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="919c8-120">新しく追加された [トポロジビルダー] の左側のウィンドウから、新しく追加したビデオ相互運用サーバーを選び、右クリックして、[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="919c8-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="919c8-121">要件に応じて TCP ポートまたは TLS ポートを有効にするか更新して、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="919c8-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="919c8-122">既定では TLS が追加されますが、Cisco ユニファイドコミュニケーションマネージャー (CallManager、または CUCM) を使用して、TCP のみが完全にテストされています。</span><span class="sxs-lookup"><span data-stu-id="919c8-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="919c8-p106">ビデオ ゲートウェイを追加します。この操作を行うには、[共有コンポーネント] を展開して、[**ビデオ ゲートウェイ**] を右クリックして、[**新しいビデオ ゲートウェイ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="919c8-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="919c8-p107">ビデオ ゲートウェイの FQDN または IP アドレスを指定します。ビデオ ゲートウェイは、サブドメインまたは別のドメインに含めることができます。システムの VTC により使用される CUCM は、ビデオ ゲートウェイの役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="919c8-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="919c8-p108">IPv4 と IPv6 のいずれか適切な方を選択します。すべての構成済み IP アドレスを使用するか、サービスの使用を選択済みの IP アドレスに限定することができます。</span><span class="sxs-lookup"><span data-stu-id="919c8-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="919c8-130">ビデオ ゲートウェイのリッスン ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="919c8-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="919c8-131">トランスポートプロトコル (TCP または TLS) を選択して、ビデオ SIP トランク用に設定されたビデオ相互運用サーバーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="919c8-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="919c8-132">ビデオ ゲートウェイのトランスポート プロトコルは、VIS 向けに構成されているトランスポート プロトコルと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="919c8-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="919c8-133">上記の手順の完了後、対応する SIP ビデオ トランクが追加されます。</span><span class="sxs-lookup"><span data-stu-id="919c8-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="919c8-134">その SIP ビデオ トランクを右クリックして、追加されたばかりのトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="919c8-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="919c8-135">ビデオ SIP トランク名、関連付けられたビデオ相互運用サーバー、SIP トランスポートプロトコル、ポートのすべてを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="919c8-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="919c8-136">ビデオ相互運用機能サーバーでは、1: N trunks がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="919c8-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="919c8-137">このため、複数の trunks を追加できます。これは、各トランクが異なるビデオゲートウェイ上で終了する1つのビデオ相互運用サーバーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="919c8-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="919c8-138">制限として、特定のビデオゲートウェイには、Skype for Business Server の展開に定義できるトランクが1つだけ含まれていることが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="919c8-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="919c8-139">「 [Skype For Business Server 2015 で新しいトポロジを作成して発行する](../../deploy/install/create-and-publish-new-topology.md)」の説明に従って、トポロジドキュメントを公開します。</span><span class="sxs-lookup"><span data-stu-id="919c8-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="919c8-140">回復性を向上させるために、2つ目のビデオ相互運用サーバーまたは VIS プール、またはバックアップフロントエンドプールを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="919c8-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="919c8-141">詳細については、「[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919c8-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="919c8-142">トポロジ ビルダーを使用して実行するすべてのタスクはこれで完了します。</span><span class="sxs-lookup"><span data-stu-id="919c8-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="919c8-143">新しい VIS サーバー (複数可) へのソフトウェアのインストール作業に進みます。</span><span class="sxs-lookup"><span data-stu-id="919c8-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="919c8-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="919c8-144">See also</span></span>

[<span data-ttu-id="919c8-145">VIS server の役割を Skype for Business Server に展開する</span><span class="sxs-lookup"><span data-stu-id="919c8-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="919c8-146">Skype for Business Server のビデオ相互運用機能サーバーを計画する</span><span class="sxs-lookup"><span data-stu-id="919c8-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="919c8-147">Skype for Business Server 2015 での新しいトポロジの作成および公開</span><span class="sxs-lookup"><span data-stu-id="919c8-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
