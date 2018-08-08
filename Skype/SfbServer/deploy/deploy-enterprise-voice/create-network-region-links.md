---
title: Skype のビジネス サーバーのネットワーク地域リンクを作成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
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
ms.openlocfilehash: f184e18da816bae693fd209a97704681240538e7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965430"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Skype のビジネス サーバーのネットワーク地域リンクを作成します。
 
作成または、Skype でのエンタープライズ VoIP 通話受付制御ビジネスのサーバーの使用は、ネットワーク地域リンクを変更します。 
  
ネットワーク内の地域は、物理的な WAN 接続を経由してリンクされます。ネットワーク地域リンクは、通話受付管理 (CAC) 用に構成された 2 つの地域間のリンクを作成し、これらの地域間の音声トラフィックとビデオ トラフィックに帯域幅制限を設定します。
  
トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。 地域リンクの帯域幅情報の表に示すよう WAN の帯域幅が指定されている各地域のこれらのリンクの[の使用例: ビジネス サーバー Skype の呼受付制御の要件の収集](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
  
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

[新しい-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[セット CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[削除 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)