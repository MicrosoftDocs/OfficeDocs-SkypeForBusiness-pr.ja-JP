---
title: Skype for Business Server でネットワークの国間ルートを作成する
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Create or modify network interregional routes, which are used by エンタープライズ VoIP call admission control in Skype for Business Server.
ms.openlocfilehash: 86b7cf9e41cb20d82f0c3c6edd6bcbd74331d553
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822497"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="ed051-103">Skype for Business Server でネットワークの国間ルートを作成する</span><span class="sxs-lookup"><span data-stu-id="ed051-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="ed051-104">Create or modify network interregional routes, which are used by エンタープライズ VoIP call admission control in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ed051-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ed051-105">ネットワーク地域間ルートは、ネットワーク地域のペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="ed051-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="ed051-106">通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed051-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="ed051-107">これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ed051-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="ed051-108">地域リンクは地域間の接続に帯域幅制限を設定しますが、地域間ルートは、接続が地域間を通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="ed051-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="ed051-109">トポロジ例では、北アメリカ/EMEA、EMEA/APAC、および北アメリカ/APAC の 3 つの地域ペアごとにネットワーク地域間ルートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed051-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ed051-110">Skype for Business Server 管理シェルを使用してネットワークの国間ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="ed051-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ed051-111">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed051-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ed051-112">**New-CsNetworkInterRegionRoute** コマンドレットを実行して、必要なルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="ed051-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="ed051-113">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed051-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="ed051-114">北アメリカ/APAC 間には直接のネットワーク地域リンクがないので、北アメリカ/APAC ネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed051-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ed051-115">Skype for Business Server コントロール パネルを使用してネットワークの国間ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="ed051-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ed051-116">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ed051-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ed051-117">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed051-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="ed051-118">[**地域ルート**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed051-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="ed051-119">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed051-119">Click **New**.</span></span>
    
5. <span data-ttu-id="ed051-120">[新 **しい地域ルート]** ページで、[名前] **をクリック** し、ネットワーク地域間ルートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ed051-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="ed051-121">[**ネットワーク地域 #1**] をクリックし、一覧でネットワーク地域 #2 にルーティングするネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed051-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="ed051-122">[**ネットワーク地域 #2**] をクリックし、一覧でネットワーク地域 #1 にルーティングするネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed051-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="ed051-123">[ **ネットワーク地域** リンク **] フィールド** の横にある [追加] をクリックし、ネットワーク地域間ルートで使用されるネットワーク地域リンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ed051-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ed051-124">2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed051-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="ed051-125">たとえば、北アメリカ/APAC 間には直接のネットワーク地域リンクがないので、北アメリカ/APAC ネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed051-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="ed051-126">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed051-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="ed051-127">トポロジのネットワークの国間ルートの作成を完了するには、他のネットワークの国間ルートの設定を使用して手順 4 から 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ed051-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ed051-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed051-128">See also</span></span>

[<span data-ttu-id="ed051-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ed051-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ed051-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ed051-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ed051-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ed051-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ed051-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ed051-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
