---
title: Skype for Business Server でネットワーク サイト間ポリシーを作成する
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Skype for Business Server の通話受付管理で使用エンタープライズ VoIPネットワーク サイト間ポリシーを作成します。
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822477"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="1240a-103">Skype for Business Server でネットワーク サイト間ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1240a-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="1240a-104">Skype for Business Server の通話受付管理で使用エンタープライズ VoIPネットワーク サイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1240a-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="1240a-105">ネットワーク サイト間ポリシーは、WAN リンクが直接接続されているサイト間の帯域幅制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="1240a-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1240a-106">ネットワーク サイト間ポリシーは、2 つのネットワーク サイト間に直接クロス リンクがある場合にのみ必要です。 </span><span class="sxs-lookup"><span data-stu-id="1240a-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="1240a-107">North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。</span><span class="sxs-lookup"><span data-stu-id="1240a-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="1240a-108">これら 2 つのサイトには、適切な帯域幅ポリシー プロファイルを適用するサイト間ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="1240a-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="1240a-109">次の例は、20Mb_Link プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="1240a-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="1240a-110">ネットワーク サイト間ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="1240a-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="1240a-111">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1240a-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1240a-112">New-CsNetworkInterSitePolicy コマンドレットを実行して、ネットワーク サイト間ポリシーを作成し、直接クロス リンクを持つ 2 つのサイトに適切な帯域幅ポリシー プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="1240a-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="1240a-113">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="1240a-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="1240a-114">必要に応じて手順 2 を繰り返して、直接クロス リンクを持つすべてのネットワーク サイト ペアに対してネットワーク サイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1240a-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1240a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1240a-115">See also</span></span>

[<span data-ttu-id="1240a-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1240a-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="1240a-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1240a-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="1240a-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1240a-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="1240a-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1240a-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
