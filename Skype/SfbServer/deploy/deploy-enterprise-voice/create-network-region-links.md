---
title: Skype for Business Server でネットワーク地域リンクを作成する
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Skype for Business Server の通話受付管理でエンタープライズ VoIPネットワーク地域リンクを作成または変更します。
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822467"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Skype for Business Server でネットワーク地域リンクを作成する
 
Skype for Business Server の通話受付管理でエンタープライズ VoIPネットワーク地域リンクを作成または変更します。 
  
ネットワーク内の地域は、物理的な WAN 接続でリンクされています。 ネットワーク地域リンクは、通話受付管理 (CAC) 用に構成された 2 つの地域間のリンクを作成し、これらの地域間の音声トラフィックとビデオ トラフィックの帯域幅制限を設定します。
  
トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。 「例: Skype for Business Server での通話受付管理の要件の収集」の地域リンクの帯域幅情報の表で説明するように、これらの各地域リンクは WAN 帯域幅によって [制限されます](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワーク地域リンクを作成するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
2. New-CsNetworkRegionLink コマンドレットを実行して、地域リンクを作成し、適切な帯域幅ポリシー プロファイルを適用します。 たとえば、以下を実行します。
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してネットワーク地域リンクを作成するには

1. Skype for Business Server コントロール パネルを開きます。
    
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
    
10. 他の地域についての設定を二間してステップ 4 ～ 9 を繰り返し、ご使用のトポロジのネットワーク地域リンクの作成を完了します。
    
## <a name="see-also"></a>関連項目

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
