---
title: Skype for Business Server 2015 でのネットワーク地域リンクの作成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク地域リンクを変更します。
ms.openlocfilehash: f2b9ba5d6ccf2c2648bf755306001350f82c2931
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-region-links-in-skype-for-business-server-2015"></a><span data-ttu-id="51989-103">Skype for Business Server 2015 でのネットワーク地域リンクの作成</span><span class="sxs-lookup"><span data-stu-id="51989-103">Create network region links in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="51989-104">作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク地域リンクを変更します。</span><span class="sxs-lookup"><span data-stu-id="51989-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="51989-105">ネットワーク内の地域は、物理的な WAN 接続を経由してリンクされます。</span><span class="sxs-lookup"><span data-stu-id="51989-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="51989-106">地域のネットワーク リンクでは、電話受付制御 (CAC) 用に構成されている 2 つの領域間のリンクを作成し、これらの領域間でのオーディオおよびビデオのトラフィックの帯域幅の制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="51989-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="51989-107">トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。</span><span class="sxs-lookup"><span data-stu-id="51989-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="51989-108">地域リンクの帯域幅情報の表に示すよう WAN の帯域幅が指定されている各地域のこれらのリンクの[の使用例: ビジネス サーバー 2015 の Skype の呼受付制御の要件を収集する](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51989-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="51989-109">Skype ビジネス サーバー管理シェルを使用してネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="51989-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="51989-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="51989-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="51989-p103">New-CsNetworkRegionLink コマンドレットを実行して、地域リンクを作成し、適切な帯域幅ポリシー プロファイルを適用します。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="51989-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="51989-113">ビジネス サーバーのコントロール パネルの Skype を使用してネットワーク地域リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="51989-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="51989-114">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="51989-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="51989-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51989-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="51989-116">[**地域リンク**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51989-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="51989-117">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51989-117">Click **New**.</span></span>
    
5. <span data-ttu-id="51989-118">[**新しい地域リンク**] ページで、[**名前**] をクリックし、ネットワーク地域リンクの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="51989-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="51989-119">[**ネットワーク地域 #1**] をクリックし、一覧でネットワーク地域 #2 にリンクするネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51989-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="51989-120">[**ネットワーク地域 #2**] をクリックし、一覧でネットワーク地域 #1 にリンクするネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51989-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="51989-121">オプションで、[**帯域幅ポリシー**] をクリックし、ネットワーク地域リンクに適用する帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="51989-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51989-122">帯域幅ポリシーは、ネットワーク地域リンクの帯域幅に制約があり、そのリンクのメディア トラフィックを CAC を使用して操作する場合に限り、適用します。</span><span class="sxs-lookup"><span data-stu-id="51989-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="51989-123">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51989-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="51989-124">他の地域についての設定でステップ 4 ～ 9 を繰り返し、ご使用のトポロジのネットワーク地域リンクの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="51989-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="51989-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="51989-125">See also</span></span>

#### 

[<span data-ttu-id="51989-126">新しい-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="51989-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="51989-127">Get CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="51989-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="51989-128">セット CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="51989-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="51989-129">削除 CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="51989-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)

