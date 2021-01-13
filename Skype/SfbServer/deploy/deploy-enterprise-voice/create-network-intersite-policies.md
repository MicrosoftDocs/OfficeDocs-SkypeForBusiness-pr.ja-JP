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
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Skype for Business Server でネットワーク サイト間ポリシーを作成する
 
Skype for Business Server の通話受付管理で使用エンタープライズ VoIPネットワーク サイト間ポリシーを作成します。 
  
ネットワーク サイト間ポリシーは、WAN リンクが直接接続されているサイト間の帯域幅制限を定義します。
  
> [!IMPORTANT]
> ネットワーク サイト間ポリシーは、2 つのネットワーク サイト間に直接クロス リンクがある場合にのみ必要です。 
  
North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。 これら 2 つのサイトには、適切な帯域幅ポリシー プロファイルを適用するサイト間ポリシーが必要です。 次の例は、20Mb_Link プロファイルを適用します。
  
### <a name="to-create-a-network-inter-site-policy"></a>ネットワーク サイト間ポリシーを作成するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
2. New-CsNetworkInterSitePolicy コマンドレットを実行して、ネットワーク サイト間ポリシーを作成し、直接クロス リンクを持つ 2 つのサイトに適切な帯域幅ポリシー プロファイルを適用します。 たとえば、以下を実行します。
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 必要に応じて手順 2 を繰り返して、直接クロス リンクを持つすべてのネットワーク サイト ペアに対してネットワーク サイト間ポリシーを作成します。
    
## <a name="see-also"></a>関連項目

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
