---
title: Skype for Business Server 2015 での通話受付管理の有効化
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: ビジネス サーバーのエンタープライズ VoIP には、Skype で通話受付制御を有効にします。
ms.openlocfilehash: 321b7838a2a818a9791b72e3851312006eb8dc7e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="enable-call-admission-control-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での通話受付管理の有効化
 
ビジネス サーバーのエンタープライズ VoIP には、Skype で通話受付制御を有効にします。 
  
通話受付管理展開のネットワーク設定を構成したら、帯域幅ポリシーを反映させるために CAC を有効にする必要があります。
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用して呼受付制御を有効にするには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. Set-CsNetworkConfiguration コマンドレットを実行して、ネットワークの CAC を有効にします。たとえば、以下を実行します。
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    ネットワークの CAC を無効にする場合は、次のように実行します。
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して呼受付制御を有効にするには

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. [**グローバル**] ナビゲーション ボタンをクリックします。
    
4. 一覧で [**グローバル**] をクリックし、[**編集**] メニューの [**詳細の表示**] をクリックします。
    
5. [**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにします。
    
    > [!NOTE]
    > 展開全体で通話受付管理を無効にする場合は、このチェック ボックスをオフにします。 
  
6. [**確定**] をクリックします。 
    
## <a name="see-also"></a>関連項目

#### 

[Get CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[セット CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[削除 CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)

