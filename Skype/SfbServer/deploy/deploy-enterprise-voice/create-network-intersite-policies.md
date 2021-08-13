---
title: ネットワークのサイト間ポリシーを作成Skype for Business Server
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
description: ネットワークサイト間ポリシーを作成します。このポリシーは、エンタープライズ VoIPの通話受付管理でSkype for Business Server。
ms.openlocfilehash: 8e5fb020ece1762868f9d943eb2aad955903b91329d636a981e644b2e9892b67
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338755"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>ネットワークのサイト間ポリシーを作成Skype for Business Server
 
ネットワークサイト間ポリシーを作成します。このポリシーは、エンタープライズ VoIPの通話受付管理でSkype for Business Server。 
  
ネットワークサイト間ポリシーは、サイト間の直接 WAN リンクを持つサイト間の帯域幅制限を定義します。
  
> [!IMPORTANT]
> ネットワークサイト間ポリシーは、2つのネットワーク サイト間に直接クロス リンクがある場合にのみ必要です。
  
North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。 これら 2 つのサイトには、適切な帯域幅ポリシー プロファイルを適用するサイト間ポリシーが必要です。 次の例は、20Mb_Link プロファイルを適用します。
  
### <a name="to-create-a-network-inter-site-policy"></a>ネットワークサイト間ポリシーを作成するには

1. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
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