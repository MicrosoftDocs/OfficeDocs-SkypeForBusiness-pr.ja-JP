---
title: Skype for Business Server 2015 でのネットワーク地域間ルートの作成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク interregional ルートを変更します。
ms.openlocfilehash: 112c74c07956073fee3e51a6e0856d875b6268ff
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-interregional-routes-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのネットワーク地域間ルートの作成
 
作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク interregional ルートを変更します。 
  
Interregional のネットワーク ルートは、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。
  
地域のリンクが地域間の接続に対する帯域幅制限を設定し、地域間ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。
  
トポロジの例では、北アメリカ/EMEA、EMEA/APAC、および北アメリカ/APAC の 3 つの各地域ペアにネットワーク地域間ルートを定義する必要があります。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>ビジネス サーバー管理シェルの Skype を使用して、interregional のルートのネットワークを作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 必要なルートを定義する**新しい CsNetworkInterRegionRoute**コマンドレットを実行します。 たとえば、以下を実行します。
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > 北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、interregional のルートのネットワークを作成するには

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. [**地域ルート**] ナビゲーション ボタンをクリックします。
    
4. [**新規**] をクリックします。
    
5. [**新しい地域ルート**] ページで、[**名前**] をクリックし、ネットワーク地域間ルートの名前を入力します。
    
6. [**ネットワーク地域 #1**] をクリックし、一覧でネットワーク地域 #2 にルーティングするネットワーク地域をクリックします。
    
7. [**ネットワーク地域 #2**] をクリックし、一覧でネットワーク地域 #1 にルーティングするネットワーク地域をクリックします。
    
8. [**ネットワーク地域リンク**] フィールドの横の [**追加**] をクリックし、ネットワーク地域間ルートで使用するネットワーク地域リンクを追加します。
    
    > [!NOTE]
    > 2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。たとえば、北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。 
  
9. [**確定**] をクリックします。
    
10. トポロジのネットワーク地域間ルートを作成するには、他のネットワーク地域間ルートについてステップ 4 ～ 9 を繰り返します。
    
## <a name="see-also"></a>関連項目

#### 

[新しい-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[セット CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[削除 CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

