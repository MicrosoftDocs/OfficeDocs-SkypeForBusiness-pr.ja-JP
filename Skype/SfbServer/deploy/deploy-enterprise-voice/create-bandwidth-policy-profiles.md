---
title: Skype for Business Server で帯域幅ポリシープロファイルを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Skype for Business Server のエンタープライズボイス通話受付制御によって使用される帯域幅ポリシーを作成または変更します。
ms.openlocfilehash: 86ab5d7fc7ae46223118250626d12107c35b9ef8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001767"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="74057-103">Skype for Business Server で帯域幅ポリシープロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="74057-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="74057-104">Skype for Business Server のエンタープライズボイス通話受付制御によって使用される帯域幅ポリシーを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="74057-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="74057-105">帯域幅ポリシーは、リアルタイムのオーディオおよびビデオのモダリティについて、帯域幅使用量の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="74057-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="74057-106">帯域幅ポリシーは、通話受付制御のために複数のネットワークサイトに適用できる帯域幅ポリシープロファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="74057-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="74057-107">CAC 展開で設定する必要がある帯域幅制限のガイドラインについては、「 [Skype For Business Server での通話受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74057-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="74057-p102">次の手順で作成されるポリシーの例は、オーディオ トラフィック全体、個々のオーディオ セッション、ビデオ トラフィック全体、および個々のビデオ セッションに制限を設定します。たとえば、5Mb_Link の帯域幅のポリシーのプロファイルは次の制限値を設定します。</span><span class="sxs-lookup"><span data-stu-id="74057-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="74057-110">オーディオ リミット: 2,000 kbps</span><span class="sxs-lookup"><span data-stu-id="74057-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="74057-111">オーディオ セッション リミット: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="74057-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="74057-112">ビデオ リミット: 1,400 kbps</span><span class="sxs-lookup"><span data-stu-id="74057-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="74057-113">ビデオ セッション リミット: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="74057-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="74057-p103">オーディオ セッション リミットの最小値は 40 kbps です。 ビデオ セッション リミットの最小値は 100 kbps です。</span><span class="sxs-lookup"><span data-stu-id="74057-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="74057-116">Skype for Business Server 管理シェルを使用して帯域幅ポリシープロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="74057-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="74057-117">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="74057-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="74057-118">作成する帯域幅ポリシーのプロファイルごとに、New-CsNetworkBandwidthPolicyProfile コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="74057-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="74057-119">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="74057-119">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="74057-120">Skype for Business Server コントロールパネルを使用して帯域幅ポリシープロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="74057-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="74057-121">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="74057-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="74057-122">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74057-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="74057-123">[**ポリシーのプロファイル**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="74057-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="74057-124">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74057-124">Click **New**.</span></span>
    
5. <span data-ttu-id="74057-125">[**新しいポリシーのプロファイル**] ページで、[**名前**] をクリックし、帯域幅ポリシー プロファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="74057-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="74057-126">[**オーディオ リミット**] をクリックし、すべてのオーディオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="74057-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="74057-127">[**オーディオ セッション リミット**] をクリックし、個々のオーディオ セッションに対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="74057-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="74057-128">[**ビデオ リミット**] をクリックし、すべてのビデオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="74057-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="74057-129">[**ビデオ セッション リミット**] をクリックし、個々のビデオ セッションに対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="74057-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="74057-130">必要に応じて、[**説明**] をクリックし、この帯域幅ポリシーのプロファイルを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="74057-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="74057-131">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74057-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="74057-132">トポロジの帯域幅ポリシーのプロファイル作成を完了するには、他の帯域幅ポリシーのプロファイルの設定値を使用してステップ 4 ～ 11 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="74057-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="74057-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="74057-133">See also</span></span>

[<span data-ttu-id="74057-134">新規-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="74057-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="74057-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="74057-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="74057-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="74057-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="74057-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="74057-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
