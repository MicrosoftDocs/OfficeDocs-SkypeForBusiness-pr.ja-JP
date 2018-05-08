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
# <a name="create-network-intersite-policies-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのネットワーク サイト間ポリシーの作成
 
サイト間ポリシー、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用するネットワークを作成します。 
  
ネットワーク サイト間ポリシーは、それらの間の直接の WAN リンクが含まれるサイト間の帯域幅の制限を定義します。
  
> [!IMPORTANT]
> ネットワーク サイト間ポリシーは、2 つのネットワーク サイト間に直接クロス リンクがある場合に必要な*だけ*です。
  
North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。この 2 つのサイトでは、適切な帯域幅ポリシー プロファイルを適用するサイト間ポリシーが必要です。次の例は、20Mb_Link プロファイルを適用します。
  
### <a name="to-create-a-network-inter-site-policy"></a>ネットワーク サイト間ポリシーを作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. New-CsNetworkInterSitePolicy コマンドレットを実行してネットワーク サイト間ポリシーを作成し、直接クロス リンクで接続された 2 つのサイトに対して適切な帯域幅ポリシー プロファイルを適用します。たとえば、以下を実行します。
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 必要に応じてステップ 2 を繰り返し、直接クロス リンクで接続されたすべてのネットワーク サイトのペアに対してネットワーク サイト間ポリシーを作成します。
    
## <a name="see-also"></a>関連項目

#### 

[新しい-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[セット CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[削除 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)

