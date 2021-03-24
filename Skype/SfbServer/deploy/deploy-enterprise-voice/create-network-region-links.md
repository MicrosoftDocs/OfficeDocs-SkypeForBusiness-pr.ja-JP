---
title: Skype for Business Server でネットワーク地域リンクを作成する
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Skype for Business Server の通話受付管理で使用エンタープライズ VoIPネットワーク地域リンクを作成または変更します。
ms.openlocfilehash: 5fd9657b3919e80552a82912550e7314297182cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093105"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="50b0e-103">Skype for Business Server でネットワーク地域リンクを作成する</span><span class="sxs-lookup"><span data-stu-id="50b0e-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="50b0e-104">Skype for Business Server の通話受付管理で使用エンタープライズ VoIPネットワーク地域リンクを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="50b0e-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="50b0e-105">ネットワーク内の地域は、物理的な WAN 接続でリンクされています。</span><span class="sxs-lookup"><span data-stu-id="50b0e-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="50b0e-106">ネットワーク領域リンクは、通話受付管理 (CAC) 用に構成された 2 つの地域間のリンクを作成し、これらの地域間のオーディオおよびビデオ トラフィックの帯域幅制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="50b0e-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="50b0e-107">トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。</span><span class="sxs-lookup"><span data-stu-id="50b0e-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="50b0e-108">これらの各地域リンクは、 [例: Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)での通話受付制御の要件の収集の「地域リンク帯域幅情報」の表で説明されているとおり、WAN 帯域幅によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="50b0e-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="50b0e-109">Skype for Business Server 管理シェルを使用してネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="50b0e-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="50b0e-110">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="50b0e-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="50b0e-111">New-CsNetworkRegionLink コマンドレットを実行して、地域リンクを作成し、適切な帯域幅ポリシー プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="50b0e-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="50b0e-112">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="50b0e-112">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="50b0e-113">Skype for Business Server コントロール パネルを使用してネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="50b0e-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="50b0e-114">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="50b0e-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="50b0e-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50b0e-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="50b0e-116">[**地域リンク**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50b0e-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="50b0e-117">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50b0e-117">Click **New**.</span></span>
    
5. <span data-ttu-id="50b0e-118">[**新しい地域リンク**] ページで、[**名前**] をクリックし、ネットワーク地域リンクの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="50b0e-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="50b0e-119">[**ネットワーク地域 #1**] をクリックし、一覧でネットワーク地域 #2 にリンクするネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50b0e-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="50b0e-120">[**ネットワーク地域 #2**] をクリックし、一覧でネットワーク地域 #1 にリンクするネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50b0e-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="50b0e-121">オプションで、[**帯域幅ポリシー**] をクリックし、ネットワーク地域リンクに適用する帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="50b0e-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50b0e-122">帯域幅ポリシーは、ネットワーク地域リンクの帯域幅に制約があり、そのリンクのメディア トラフィックを CAC を使用して操作する場合に限り、適用します。</span><span class="sxs-lookup"><span data-stu-id="50b0e-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="50b0e-123">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50b0e-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="50b0e-124">他の地域についての設定を二間してステップ 4 ～ 9 を繰り返し、ご使用のトポロジのネットワーク地域リンクの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="50b0e-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="50b0e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="50b0e-125">See also</span></span>

[<span data-ttu-id="50b0e-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="50b0e-126">New-CsNetworkRegionLink</span></span>](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="50b0e-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="50b0e-127">Get-CsNetworkRegionLink</span></span>](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="50b0e-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="50b0e-128">Set-CsNetworkRegionLink</span></span>](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="50b0e-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="50b0e-129">Remove-CsNetworkRegionLink</span></span>](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)