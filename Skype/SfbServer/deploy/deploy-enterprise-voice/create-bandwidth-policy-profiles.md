---
title: 帯域幅ポリシー プロファイルを作成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 帯域幅ポリシーを作成または変更します。このポリシーは、エンタープライズ VoIPの通話受付管理でSkype for Business Server。
ms.openlocfilehash: d1c7391abb535f3d7309809adea5b66a28087c75
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841909"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>帯域幅ポリシー プロファイルを作成Skype for Business Server 
 
帯域幅ポリシーを作成または変更します。このポリシーは、エンタープライズ VoIPの通話受付管理でSkype for Business Server。 
  
帯域幅ポリシーは、リアルタイムのオーディオおよびビデオのモダリティについて、帯域幅使用量の制限を定義します。 帯域幅ポリシーはbandwidth ポリシー プロファイルに適用され、通話受付管理のために複数のネットワーク サイトに適用できます。
  
CAC 展開で設定する帯域幅制限のガイドラインについては、「通話受付管理の計画」を参照[Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
次の手順で作成されるポリシーの例は、オーディオ トラフィック全体、個々のオーディオ セッション、ビデオ トラフィック全体、および個々のビデオ セッションに制限を設けます。 たとえば、5Mb_Link の帯域幅のポリシーのプロファイルは次の制限値を設定します。 
  
- オーディオ リミット: 2,000 kbps
    
- オーディオ セッション リミット: 200 kbps
    
- ビデオ リミット: 1,400 kbps
    
- ビデオ セッション リミット: 700 kbps
    
> [!NOTE]
> オーディオ セッション リミットの最小値は 40 kbps です。 ビデオ セッション リミットの最小値は 100 kbps です。 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して帯域幅ポリシー プロファイルをSkype for Business Serverするには

1. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 作成する帯域幅ポリシーのプロファイルごとに、New-CsNetworkBandwidthPolicyProfile コマンドレットを実行します。たとえば、以下を実行します。
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して帯域幅ポリシー プロファイルをSkype for Business Serverするには

1. [コントロール Skype for Business Server] を開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. [**ポリシーのプロファイル**] ナビゲーション ボタンをクリックします。
    
4. [**新規**] をクリックします。
    
5. [**新しいポリシーのプロファイル**] ページで、[**名前**] をクリックし、帯域幅ポリシー プロファイルの名前を入力します。
    
6. [**オーディオ リミット**] をクリックし、すべてのオーディオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。
    
7. [**オーディオ セッション リミット**] をクリックし、個々のオーディオ セッションに対して許可する最大値 (kbps) を入力します。
    
8. [**ビデオ リミット**] をクリックし、すべてのビデオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。
    
9. [**ビデオ セッション リミット**] をクリックし、個々のビデオ セッションに対して許可する最大値 (kbps) を入力します。
    
10. 必要に応じて、[**説明**] をクリックし、この帯域幅ポリシーのプロファイルを説明する追加情報を入力します。
    
11. [**確定**] をクリックします。
    
12. トポロジの帯域幅ポリシーのプロファイル作成を完了するには、ステップ 4 ～ 11 を繰り返して、他の帯域幅ポリシーのプロファイルを設定します。
    
## <a name="see-also"></a>関連項目

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)