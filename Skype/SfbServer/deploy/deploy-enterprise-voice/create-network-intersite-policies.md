---
title: ビジネス サーバーの Skype のネットワーク サイト間ポリシーを作成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: サイト間ポリシー、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用するネットワークを作成します。
ms.openlocfilehash: 455caaf624c463bdb1c32ca8fbce70c88626c774
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892966"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="b57ce-103">ビジネス サーバーの Skype のネットワーク サイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b57ce-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="b57ce-104">サイト間ポリシー、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用するネットワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="b57ce-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="b57ce-105">ネットワーク サイト間ポリシーは、WAN リンクで直接接続されたサイト間の帯域幅制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="b57ce-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b57ce-106">ネットワーク サイト間ポリシーは、2 つのネットワーク サイト間に直接クロス リンクがある場合に必要な*だけ*です。</span><span class="sxs-lookup"><span data-stu-id="b57ce-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="b57ce-p101">North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。この 2 つのサイトでは、適切な帯域幅ポリシー プロファイルを適用するサイト間ポリシーが必要です。次の例は、20Mb_Link プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="b57ce-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="b57ce-110">ネットワーク サイト間ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="b57ce-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="b57ce-111">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b57ce-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b57ce-p102">New-CsNetworkInterSitePolicy コマンドレットを実行してネットワーク サイト間ポリシーを作成し、直接クロス リンクで接続された 2 つのサイトに対して適切な帯域幅ポリシー プロファイルを適用します。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="b57ce-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="b57ce-114">必要に応じてステップ 2 を繰り返し、直接クロス リンクで接続されたすべてのネットワーク サイトのペアに対してネットワーク サイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b57ce-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b57ce-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b57ce-115">See also</span></span>

[<span data-ttu-id="b57ce-116">新しい-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b57ce-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="b57ce-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b57ce-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="b57ce-118">セット CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b57ce-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="b57ce-119">削除 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b57ce-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
