---
title: 通話受付管理を有効Skype for Business Server
ms.reviewer: null
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
ms.custom: null
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 通話受付管理を有効にするには、Skype for Business Server エンタープライズ VoIP。
---

# <a name="enable-call-admission-control-in-skype-for-business-server"></a>通話受付管理を有効Skype for Business Server
 
通話受付管理を有効にするには、Skype for Business Server エンタープライズ VoIP。 
  
通話受付管理展開のネットワーク設定を構成したら、帯域幅ポリシーを反映させるために CAC を有効にする必要があります。
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して通話受付管理Skype for Business Serverするには

1. 管理シェルをSkype for Business Serverする **: [スタート**] をクリックし、[すべてのプログラム] をクリックし、[**2015** 年Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. Set-CsNetworkConfiguration コマンドレットを実行して、ネットワークの CAC を有効にします。たとえば、以下を実行します。
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    ネットワークの CAC を無効にする場合は、次のように実行します。
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して通話受付Skype for Business Serverするには

1. [コントロール Skype for Business Server] を開きます。
    
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