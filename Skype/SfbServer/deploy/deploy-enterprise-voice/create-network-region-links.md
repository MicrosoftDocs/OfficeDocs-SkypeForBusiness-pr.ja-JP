---
title: Skype for Business Server 2015 でのネットワーク地域リンクの作成
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク地域リンクを変更します。
ms.openlocfilehash: e0fbabb811ec604b3a0155074a01bc4b02bd6152
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="create-network-region-links-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのネットワーク地域リンクの作成
 
作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク地域リンクを変更します。 
  
ネットワーク内の地域は、物理的な WAN 接続を経由してリンクされます。 地域のネットワーク リンクでは、電話受付制御 (CAC) 用に構成されている 2 つの領域間のリンクを作成し、これらの領域間でのオーディオおよびビデオのトラフィックの帯域幅の制限を設定します。
  
トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。 地域リンクの帯域幅情報の表に示すよう WAN の帯域幅が指定されている各地域のこれらのリンクの[の使用例: ビジネス サーバー 2015 の Skype の呼受付制御の要件を収集する](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用してネットワーク地域リンクを作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. New-CsNetworkRegionLink コマンドレットを実行して、地域リンクを作成し、適切な帯域幅ポリシー プロファイルを適用します。たとえば、以下を実行します。
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用してネットワーク地域リンクを作成するには

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. [**地域リンク**] ナビゲーション ボタンをクリックします。
    
4. [**新規**] をクリックします。
    
5. [**新しい地域リンク**] ページで、[**名前**] をクリックし、ネットワーク地域リンクの名前を入力します。
    
6. [**ネットワーク地域 #1**] をクリックし、一覧でネットワーク地域 #2 にリンクするネットワーク地域をクリックします。
    
7. [**ネットワーク地域 #2**] をクリックし、一覧でネットワーク地域 #1 にリンクするネットワーク地域をクリックします。
    
8. オプションで、[**帯域幅ポリシー**] をクリックし、ネットワーク地域リンクに適用する帯域幅ポリシーのプロファイルを選択します。
    
    > [!NOTE]
    > 帯域幅ポリシーは、ネットワーク地域リンクの帯域幅に制約があり、そのリンクのメディア トラフィックを CAC を使用して操作する場合に限り、適用します。 
  
9. [**確定**] をクリックします。
    
10. 他の地域についての設定でステップ 4 ～ 9 を繰り返し、ご使用のトポロジのネットワーク地域リンクの作成を完了します。
    
## <a name="see-also"></a>関連項目

#### 

[新しい-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[セット CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[削除 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)

