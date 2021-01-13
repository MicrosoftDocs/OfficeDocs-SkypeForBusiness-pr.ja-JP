---
title: Skype for Business Server でメディア バイパスを構成して、常に仲介サーバーをバイパスする
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: メディア バイパスを有効にして、Skype for Business Server の仲介サーバーを常にバイパスエンタープライズ VoIP。
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804217"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Skype for Business Server でメディア バイパスを構成して、常に仲介サーバーをバイパスする
 
メディア バイパスを有効にして、Skype for Business Server の仲介サーバーを常にバイパスエンタープライズ VoIP。 
  
 このトピックの手順を使用してメディア バイパスのグローバル設定を構成する場合、Skype for Business エンドポイントとトランク接続でメディア バイパスを構成したピア間の接続が良好な場合が前提です。
  
Skype for Business エンドポイントと、それぞれのトランク接続でメディア バイパスが有効になっている仲介サーバーへのすべてのピア間の接続が良好ではない場合は、メディア バイパスを使用するときにサイトおよび地域情報を使用するグローバル メディア バイパス設定を構成する必要があります。 これにより、メディアが仲介サーバーをバイパスするか判定する際に、よりよく制御できます。 これを行うには [、「Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and Associate a subnet with a network [site](deploy-network.md#BKMK_AssociateSubnets) instead」の手順を使用します。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには

1. Skype for Business Server コントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. リスト内の [**グローバル**] 構成をダブルクリックします。
    
4. [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。
    
5. [**常にバイパスする**] をクリックします。
    
6. [**確定**] をクリックします。
    
## <a name="see-also"></a>関連項目

[Skype for Business でのメディア バイパスの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Skype for Business Server でのメディア バイパスの展開](deploy-media-bypass.md)

