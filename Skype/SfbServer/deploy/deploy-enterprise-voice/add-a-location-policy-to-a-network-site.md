---
title: サイト内のネットワーク サイトに場所ポリシーを追加Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: E9-1-1 の場所ポリシーをネットワーク サイトに割り当Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 543fc8dca7c1e4a06f73ba9d55ccaf6e1ad0ec3d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62405889"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>サイト内のネットワーク サイトに場所ポリシーを追加Skype for Business Server
 
E9-1-1 の場所ポリシーをネットワーク サイトに割り当Skype for Business Server エンタープライズ VoIP。 
  
次の例は、「Skype for Business Server で場所ポリシーを作成する」で定義されている **Redmond** 場所ポリシーを既存のネットワーク サイトに追加する方法と、[Redmond](create-location-policies.md) の場所ポリシーを使用する新しいネットワーク サイトを作成する方法を示しています。
  
ネットワーク サイトの操作の詳細については、次のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>場所のポリシーを既存のネットワーク サイトに割り当てるには

1. 管理シェルをSkype for Business Serverする **: [スタート**] をクリックし、[すべてのプログラム] をクリックし、[**2015** 年Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。
    
    **Redmond タグ付き** 場所ポリシーを Redmond という名前の既存のネットワーク サイトに **割り当てる**。
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>場所のポリシーを新しいネットワーク サイトに割り当てるには

1. 管理シェルをSkype for Business Serverする **: [スタート**] をクリックし、[すべてのプログラム] をクリックし、[**2015** 年Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。
    
    ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


