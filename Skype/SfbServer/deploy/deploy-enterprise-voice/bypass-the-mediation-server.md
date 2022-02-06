---
title: 仲介サーバーを常にバイパスSkype for Business Serverメディア バイパスを構成する
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: メディア バイパスを有効にして、常に仲介サーバーをバイパスSkype for Business Server エンタープライズ VoIP。
---

# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスSkype for Business Serverメディア バイパスを構成する
 
メディア バイパスを有効にして、常に仲介サーバーをバイパスSkype for Business Server エンタープライズ VoIP。 
  
 このトピックの手順を使用してメディア バイパスのグローバル設定を構成する場合、Skype for Business エンドポイントとトランク接続でメディア バイパスを構成したピアとの間に良好な接続性があるという前提があります。
  
Skype for Business エンドポイントと仲介サーバーの各トランク接続がメディア バイパスに対して有効になっているすべてのピア間の接続が良好ではない場合は、メディア バイパスを使用するときにサイトと地域の情報を使用するグローバル メディア バイパス設定を構成する必要があります。 これにより、メディアが仲介サーバーをバイパスするか判定する際に、よりよく制御できます。 これを行うには、「Skype for Business Server でメディア バイパスグローバル設定を構成する」の手順を使用して、サイト[と地域](use-site-and-region-information.md)の情報を使用し、代わりにサブネットをネットワーク サイト[に](deploy-network.md#BKMK_AssociateSubnets)関連付ける。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには

1. [コントロール Skype for Business Server] を開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. リスト内の [**グローバル**] 構成をダブルクリックします。
    
4. [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。
    
5. [**常にバイパスする**] をクリックします。
    
6. [**確定**] をクリックします。
    
## <a name="see-also"></a>関連項目

[ネットワークでメディア バイパスを計画Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[メディア バイパスを展開Skype for Business Server](deploy-media-bypass.md)

