---
title: ネットワーク内にネットワークの異なるルートをSkype for Business Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: ネットワーク間ルートを作成または変更します。このルートは、エンタープライズ VoIPの通話受付管理でSkype for Business Server。
ms.openlocfilehash: 4d3451d43d364e5b9506289e7909456c8bdc657b8ac575dfea360a960352b8d8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294894"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>ネットワーク内にネットワークの異なるルートをSkype for Business Server
 
ネットワーク間ルートを作成または変更します。このルートは、エンタープライズ VoIPの通話受付管理でSkype for Business Server。 
  
ネットワーク地域間ルートは、一対のネットワーク領域間のルートを定義します。 通話受付管理展開内のネットワーク領域の各ペアには、ネットワーク地域間ルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。
  
地域リンクは地域間の接続に帯域幅の制限を設定しますが、地域間ルートによって、接続が 1 つの領域から別の領域に移動するリンク されたパスが決定されます。
  
トポロジの例では、北アメリカ/EMEA、EMEA/APAC、北アメリカ/APAC の 3 つの地域ペアごとにネットワーク地域間ルートを定義する必要があります。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用してネットワークのSkype for Business Server作成するには

1. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. **New-CsNetworkInterRegionRoute** コマンドレットを実行して、必要なルートを定義します。たとえば、以下を実行します。
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > 北アメリカ/APAC ネットワーク地域間ルートでは、ネットワーク領域間の直接のリンクがないので、2 つのネットワーク領域リンクが必要です。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用してネットワークのSkype for Business Server作成するには

1. [コントロール Skype for Business Server] を開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. [**地域ルート**] ナビゲーション ボタンをクリックします。
    
4. [**新規**] をクリックします。
    
5. [新しい **地域ルート] ページ** で、[ **名前** ] をクリックし、ネットワーク地域間ルートの名前を入力します。
    
6. [**ネットワーク地域 #1**] をクリックし、一覧でネットワーク地域 #2 にルーティングするネットワーク地域をクリックします。
    
7. [**ネットワーク地域 #2**] をクリックし、一覧でネットワーク地域 #1 にルーティングするネットワーク地域をクリックします。
    
8. [ **ネットワーク地域** リンク] **フィールドの横** にある [追加] をクリックし、ネットワーク地域間ルートで使用するネットワーク地域リンクを追加します。
    
    > [!NOTE]
    > 2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。 たとえば、北アメリカ/APAC ネットワークの地域間ルートでは、ネットワーク領域間の直接のリンクがないので、2 つのネットワーク領域リンクが必要です。 
  
9. [**確定**] をクリックします。
    
10. トポロジのネットワークの異なるルートの作成を完了するには、手順 4 ~ 9 を繰り返し、他のネットワークの異なるルートの設定を繰り返します。
    
## <a name="see-also"></a>関連項目

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)