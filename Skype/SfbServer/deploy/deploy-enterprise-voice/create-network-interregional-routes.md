---
title: Skype for Business Server でネットワークの国間ルートを作成する
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
description: Create or modify network interregional routes, which are used by エンタープライズ VoIP call admission control in Skype for Business Server.
ms.openlocfilehash: 86b7cf9e41cb20d82f0c3c6edd6bcbd74331d553
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822497"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Skype for Business Server でネットワークの国間ルートを作成する
 
Create or modify network interregional routes, which are used by エンタープライズ VoIP call admission control in Skype for Business Server. 
  
ネットワーク地域間ルートは、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。
  
地域リンクは地域間の接続に帯域幅制限を設定しますが、地域間ルートは、接続が地域間を通過するリンクされたパスを決定します。
  
トポロジ例では、北アメリカ/EMEA、EMEA/APAC、および北アメリカ/APAC の 3 つの地域ペアごとにネットワーク地域間ルートを定義する必要があります。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワークの国間ルートを作成するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
2. **New-CsNetworkInterRegionRoute** コマンドレットを実行して、必要なルートを定義します。 たとえば、以下を実行します。
    
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
    > 北アメリカ/APAC 間には直接のネットワーク地域リンクがないので、北アメリカ/APAC ネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してネットワークの国間ルートを作成するには

1. Skype for Business Server コントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. [**地域ルート**] ナビゲーション ボタンをクリックします。
    
4. [**新規**] をクリックします。
    
5. [新 **しい地域ルート]** ページで、[名前] **をクリック** し、ネットワーク地域間ルートの名前を入力します。
    
6. [**ネットワーク地域 #1**] をクリックし、一覧でネットワーク地域 #2 にルーティングするネットワーク地域をクリックします。
    
7. [**ネットワーク地域 #2**] をクリックし、一覧でネットワーク地域 #1 にルーティングするネットワーク地域をクリックします。
    
8. [ **ネットワーク地域** リンク **] フィールド** の横にある [追加] をクリックし、ネットワーク地域間ルートで使用されるネットワーク地域リンクを追加します。
    
    > [!NOTE]
    > 2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。 たとえば、北アメリカ/APAC 間には直接のネットワーク地域リンクがないので、北アメリカ/APAC ネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。 
  
9. [**確定**] をクリックします。
    
10. トポロジのネットワークの国間ルートの作成を完了するには、他のネットワークの国間ルートの設定を使用して手順 4 から 9 を繰り返します。
    
## <a name="see-also"></a>関連項目

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
