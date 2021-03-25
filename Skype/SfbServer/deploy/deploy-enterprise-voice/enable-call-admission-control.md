---
title: Skype for Business Server で通話受付管理を有効にする
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Skype for Business Server の通話受付管理を有効エンタープライズ VoIP。
ms.openlocfilehash: 2b8096a9223250cec88e57e68fdc201f5591fd92
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109863"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Skype for Business Server で通話受付管理を有効にする
 
Skype for Business Server の通話受付管理を有効エンタープライズ VoIP。 
  
通話受付管理展開のネットワーク設定を構成したら、帯域幅ポリシーを反映させるために CAC を有効にする必要があります。
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して通話受付管理を有効にするには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. Set-CsNetworkConfiguration コマンドレットを実行して、ネットワークの CAC を有効にします。たとえば、以下を実行します。
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    ネットワークの CAC を無効にする場合は、次のように実行します。
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して通話受付管理を有効にするには

1. Skype for Business Server コントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. [**グローバル**] ナビゲーション ボタンをクリックします。
    
4. 一覧で [**グローバル**] をクリックし、[**編集**] メニューの [**詳細の表示**] をクリックします。
    
5. [**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにします。
    
    > [!NOTE]
    > 展開全体で通話受付管理を無効にする場合は、このチェック ボックスをオフにします。 
  
6. [**確定**] をクリックします。 
    
## <a name="see-also"></a>関連項目

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)