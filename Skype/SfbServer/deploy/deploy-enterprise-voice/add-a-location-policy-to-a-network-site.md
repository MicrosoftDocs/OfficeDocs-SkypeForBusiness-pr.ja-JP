---
title: サイト内のネットワーク サイトに場所ポリシーを追加Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 9d248d91703284d58b27e5fd593af95ddf4edaf3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765955"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>サイト内のネットワーク サイトに場所ポリシーを追加Skype for Business Server
 
E9-1-1 の場所ポリシーをネットワーク サイトに割り当Skype for Business Server エンタープライズ VoIP。 
  
次の例は、「Skype for Business Server で場所ポリシーを作成する」で定義されている **Redmond** 場所ポリシーを既存のネットワーク サイトに追加する方法と [、Redmond](create-location-policies.md)の場所ポリシーを使用する新しいネットワーク サイトを作成する方法を示しています。
  
ネットワーク サイトの操作の詳細については、次のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>場所のポリシーを既存のネットワーク サイトに割り当てるには

1. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。
    
    Redmond タグ **付き** 場所ポリシーを Redmond という名前の既存のネットワーク サイトに **割り当てる**。
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>場所のポリシーを新しいネットワーク サイトに割り当てるには

1. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。
    
    ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


