---
title: ビジネス サーバーの Skype で帯域幅ポリシー プロファイルの作成します。
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
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 作成または、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用する帯域幅ポリシーを変更します。
ms.openlocfilehash: ddc74ad5327651225bb6f0e78f83d8248c290806
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986444"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>ビジネス サーバーの Skype で帯域幅ポリシー プロファイルの作成します。 
 
作成または、Skype でのエンタープライズ VoIP 通話受付制御がビジネスのサーバーに使用する帯域幅ポリシーを変更します。 
  
帯域幅ポリシーは、リアルタイムのオーディオおよびビデオのモダリティについて、帯域幅使用量の制限を定義します。 帯域幅ポリシーは、tobandwidth が適用されているポリシー プロファイルは、呼受付制御の複数のネットワーク サイトに適用することができます。
  
ガイドラインについて、どのような帯域幅を制限する必要があります、CAC の展開の設定は、[ビジネス サーバーの Skype で通話受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)を参照してください。
  
次の手順で作成されるポリシーの例は、オーディオ トラフィック全体、個々のオーディオ セッション、ビデオ トラフィック全体、および個々のビデオ セッションに制限を設定します。たとえば、5Mb_Link の帯域幅のポリシーのプロファイルは次の制限値を設定します。 
  
- オーディオ リミット: 2,000 kbps
    
- オーディオ セッション リミット: 200 kbps
    
- ビデオ リミット: 1,400 kbps
    
- ビデオ セッション リミット: 700 kbps
    
> [!NOTE]
> オーディオ セッション リミットの最小値は 40 kbps です。 ビデオ セッション リミットの最小値は 100 kbps です。 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用して帯域幅ポリシーのプロファイルを作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 作成する帯域幅ポリシーのプロファイルごとに、New-CsNetworkBandwidthPolicyProfile コマンドレットを実行します。たとえば、以下を実行します。
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、帯域幅ポリシーのプロファイルを作成するには

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
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
    
12. トポロジの帯域幅ポリシーのプロファイル作成を完了するには、他の帯域幅ポリシーのプロファイルの設定値を使用してステップ 4 ～ 11 を繰り返します。
    
## <a name="see-also"></a>関連項目

[新しい-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[セット CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[削除 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)