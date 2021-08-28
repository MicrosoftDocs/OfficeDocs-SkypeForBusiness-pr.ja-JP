---
title: 仲介サーバーを常にバイパスSkype for Business Serverメディア バイパスを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: メディア バイパスを有効にして、常に仲介サーバーをバイパスSkype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 1158d397225c9a46650d6c8f8f1fb0c22555aeea
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597311"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスSkype for Business Serverメディア バイパスを構成する
 
メディア バイパスを有効にして、常に仲介サーバーをバイパスSkype for Business Server エンタープライズ VoIP。 
  
 このトピックの手順を使用してメディア バイパスのグローバル設定を構成する場合、Skype for Business エンドポイントとトランク接続でメディア バイパスを構成したピアとの間に良好な接続性があるという前提があります。
  
Skype for Business エンドポイントと仲介サーバーの各トランク接続がメディア バイパスに対して有効になっているすべてのピア間の接続が良好ではない場合は、メディア バイパスを使用するときにサイトと地域の情報を使用するグローバル メディア バイパス設定を構成する必要があります。 これにより、メディアが仲介サーバーをバイパスするか判定する際に、よりよく制御できます。 これを行うには、「Skype for Business Server でメディア[](use-site-and-region-information.md)バイパスグローバル設定を構成する」の手順を使用して、サイトと地域の情報を使用し、代わりにサブネットをネットワーク サイト[に関連付](deploy-network.md#BKMK_AssociateSubnets)ける。
  
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

