---
title: ビジネス サーバーの Skype で帯域幅ポリシー プロファイルの作成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 作成または、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用する帯域幅ポリシーを変更します。
ms.openlocfilehash: ac1c5ab43e810ca152097c256e087ee176caa2d3
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885360"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="92d19-103">ビジネス サーバーの Skype で帯域幅ポリシー プロファイルの作成します。</span><span class="sxs-lookup"><span data-stu-id="92d19-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="92d19-104">作成または、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用する帯域幅ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="92d19-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="92d19-105">帯域幅ポリシーは、リアルタイムのオーディオおよびビデオのモダリティについて、帯域幅使用量の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="92d19-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="92d19-106">帯域幅ポリシーは、tobandwidth が適用されているポリシー プロファイルは、呼受付制御の複数のネットワーク サイトに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="92d19-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="92d19-107">ガイドラインについて、どのような帯域幅を制限する必要があります、CAC の展開の設定は、[ビジネス サーバーの Skype で通話受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d19-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="92d19-p102">次の手順で作成されるポリシーの例は、オーディオ トラフィック全体、個々のオーディオ セッション、ビデオ トラフィック全体、および個々のビデオ セッションに制限を設定します。たとえば、5Mb_Link の帯域幅のポリシーのプロファイルは次の制限値を設定します。</span><span class="sxs-lookup"><span data-stu-id="92d19-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="92d19-110">オーディオ リミット: 2,000 kbps</span><span class="sxs-lookup"><span data-stu-id="92d19-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="92d19-111">オーディオ セッション リミット: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="92d19-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="92d19-112">ビデオ リミット: 1,400 kbps</span><span class="sxs-lookup"><span data-stu-id="92d19-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="92d19-113">ビデオ セッション リミット: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="92d19-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="92d19-p103">オーディオ セッション リミットの最小値は 40 kbps です。 ビデオ セッション リミットの最小値は 100 kbps です。</span><span class="sxs-lookup"><span data-stu-id="92d19-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="92d19-116">Skype ビジネス サーバー管理シェルを使用して帯域幅ポリシーのプロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="92d19-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="92d19-117">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d19-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="92d19-p104">作成する帯域幅ポリシーのプロファイルごとに、New-CsNetworkBandwidthPolicyProfile コマンドレットを実行します。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="92d19-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="92d19-120">ビジネス サーバーのコントロール パネルの Skype を使用して、帯域幅ポリシーのプロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="92d19-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="92d19-121">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="92d19-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="92d19-122">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d19-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="92d19-123">[**ポリシーのプロファイル**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d19-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="92d19-124">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d19-124">Click **New**.</span></span>
    
5. <span data-ttu-id="92d19-125">[**新しいポリシーのプロファイル**] ページで、[**名前**] をクリックし、帯域幅ポリシー プロファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d19-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="92d19-126">[**オーディオ リミット**] をクリックし、すべてのオーディオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d19-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="92d19-127">[**オーディオ セッション リミット**] をクリックし、個々のオーディオ セッションに対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d19-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="92d19-128">[**ビデオ リミット**] をクリックし、すべてのビデオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d19-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="92d19-129">[**ビデオ セッション リミット**] をクリックし、個々のビデオ セッションに対して許可する最大値 (kbps) を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d19-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="92d19-130">必要に応じて、[**説明**] をクリックし、この帯域幅ポリシーのプロファイルを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d19-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="92d19-131">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d19-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="92d19-132">トポロジの帯域幅ポリシーのプロファイル作成を完了するには、他の帯域幅ポリシーのプロファイルの設定値を使用してステップ 4 ～ 11 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="92d19-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="92d19-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="92d19-133">See also</span></span>

[<span data-ttu-id="92d19-134">新しい-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="92d19-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="92d19-135">Get CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="92d19-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="92d19-136">セット CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="92d19-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="92d19-137">削除 CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="92d19-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)