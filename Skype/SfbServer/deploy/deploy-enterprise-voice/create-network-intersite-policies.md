---
title: Skype for Business Server でネットワークサイト間ポリシーを作成する
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
description: Skype for Business Server の通話受付管理で使用エンタープライズ VoIPサイト間ポリシーを作成します。
ms.openlocfilehash: 7c0ca45c691ab1ef70d3660c3d49a08c40bdd40d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093085"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Skype for Business Server でネットワークサイト間ポリシーを作成する
 
Skype for Business Server の通話受付管理で使用エンタープライズ VoIPサイト間ポリシーを作成します。 
  
ネットワークサイト間ポリシーは、サイト間の直接 WAN リンクを持つサイト間の帯域幅制限を定義します。
  
> [!IMPORTANT]
> ネットワークサイト間ポリシーは、2つのネットワーク サイト間に直接クロス リンクがある場合にのみ必要です。
  
North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。 これら 2 つのサイトには、適切な帯域幅ポリシー プロファイルを適用するサイト間ポリシーが必要です。 次の例は、20Mb_Link プロファイルを適用します。
  
### <a name="to-create-a-network-inter-site-policy"></a>ネットワークサイト間ポリシーを作成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. New-CsNetworkInterSitePolicy コマンドレットを実行して、ネットワークサイト間ポリシーを作成し、直接クロス リンクを持つ 2 つのサイトに適切な帯域幅ポリシー プロファイルを適用します。 たとえば、以下を実行します。
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 必要に応じて手順 2 を繰り返して、直接クロス リンクを持つすべてのネットワーク サイト ペアのネットワークサイト間ポリシーを作成します。
    
## <a name="see-also"></a>関連項目

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)