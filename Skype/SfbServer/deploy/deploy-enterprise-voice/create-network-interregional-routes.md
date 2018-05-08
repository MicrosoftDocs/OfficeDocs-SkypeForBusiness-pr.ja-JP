---
title: Skype for Business Server 2015 でのネットワーク地域間ルートの作成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク interregional ルートを変更します。
ms.openlocfilehash: 22e7872c6faa989779a93b6524c1740386f32d7d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="create-network-interregional-routes-in-skype-for-business-server-2015"></a><span data-ttu-id="ffb5c-103">Skype for Business Server 2015 でのネットワーク地域間ルートの作成</span><span class="sxs-lookup"><span data-stu-id="ffb5c-103">Create network interregional routes in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ffb5c-104">作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク interregional ルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ffb5c-105">Interregional のネットワーク ルートは、ネットワーク地域のペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="ffb5c-106">通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="ffb5c-107">これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="ffb5c-108">地域のリンクが地域間の接続に対する帯域幅制限を設定し、地域間ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="ffb5c-109">トポロジの例では、北アメリカ/EMEA、EMEA/APAC、および北アメリカ/APAC の 3 つの各地域ペアにネットワーク地域間ルートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ffb5c-110">ビジネス サーバー管理シェルの Skype を使用して、interregional のルートのネットワークを作成するには</span><span class="sxs-lookup"><span data-stu-id="ffb5c-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ffb5c-111">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ffb5c-112">必要なルートを定義する**新しい CsNetworkInterRegionRoute**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="ffb5c-113">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-113">For example, run:</span></span>
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="ffb5c-114">北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ffb5c-115">ビジネス サーバーのコントロール パネルの Skype を使用して、interregional のルートのネットワークを作成するには</span><span class="sxs-lookup"><span data-stu-id="ffb5c-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ffb5c-116">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ffb5c-117">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="ffb5c-118">[**地域ルート**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="ffb5c-119">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-119">Click **New**.</span></span>
    
5. <span data-ttu-id="ffb5c-120">[**新しい地域ルート**] ページで、[**名前**] をクリックし、ネットワーク地域間ルートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="ffb5c-121">[**ネットワーク地域 #1**] をクリックし、一覧でネットワーク地域 #2 にルーティングするネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="ffb5c-122">[**ネットワーク地域 #2**] をクリックし、一覧でネットワーク地域 #1 にルーティングするネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="ffb5c-123">[**ネットワーク地域リンク**] フィールドの横の [**追加**] をクリックし、ネットワーク地域間ルートで使用するネットワーク地域リンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ffb5c-p103">2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。たとえば、北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-p103">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="ffb5c-126">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="ffb5c-127">トポロジのネットワーク地域間ルートを作成するには、他のネットワーク地域間ルートについてステップ 4 ～ 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ffb5c-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ffb5c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffb5c-128">See also</span></span>

#### 

[<span data-ttu-id="ffb5c-129">新しい-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ffb5c-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ffb5c-130">Get CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ffb5c-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ffb5c-131">セット CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ffb5c-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ffb5c-132">削除 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ffb5c-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

