---
title: Skype for Business Server 2015 でのネットワーク サイト間ポリシーの作成
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: サイト間ポリシー、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用するネットワークを作成します。
ms.openlocfilehash: f8c09f850a001b634ee63199210733000775fd0a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="create-network-intersite-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="f7dee-103">Skype for Business Server 2015 でのネットワーク サイト間ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="f7dee-103">Create network intersite policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f7dee-104">サイト間ポリシー、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用するネットワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7dee-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="f7dee-105">ネットワーク サイト間ポリシーは、それらの間の直接の WAN リンクが含まれるサイト間の帯域幅の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="f7dee-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f7dee-106">ネットワーク サイト間ポリシーは、2 つのネットワーク サイト間に直接クロス リンクがある場合に必要な*だけ*です。</span><span class="sxs-lookup"><span data-stu-id="f7dee-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="f7dee-p101">North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。この 2 つのサイトでは、適切な帯域幅ポリシー プロファイルを適用するサイト間ポリシーが必要です。次の例は、20Mb_Link プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="f7dee-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="f7dee-110">ネットワーク サイト間ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="f7dee-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="f7dee-111">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7dee-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f7dee-p102">New-CsNetworkInterSitePolicy コマンドレットを実行してネットワーク サイト間ポリシーを作成し、直接クロス リンクで接続された 2 つのサイトに対して適切な帯域幅ポリシー プロファイルを適用します。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7dee-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="f7dee-114">必要に応じてステップ 2 を繰り返し、直接クロス リンクで接続されたすべてのネットワーク サイトのペアに対してネットワーク サイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7dee-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f7dee-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7dee-115">See also</span></span>

#### 

[<span data-ttu-id="f7dee-116">新しい-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f7dee-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="f7dee-117">Get CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f7dee-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="f7dee-118">セット CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f7dee-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="f7dee-119">削除 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f7dee-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)

