---
title: Skype for Business Server でメディアバイパスを構成して、常に仲介サーバーをバイパスする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: メディアバイパスを有効にして、Skype for Business Server Enterprise Voice の仲介サーバーを常にバイパスします。
ms.openlocfilehash: 0e45f8ede38411974f9433c17ccd0a0946b427ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275879"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Skype for Business Server でメディアバイパスを構成して、常に仲介サーバーをバイパスする
 
メディアバイパスを有効にして、Skype for Business Server Enterprise Voice の仲介サーバーを常にバイパスします。 
  
 このトピックの手順を使用してメディアバイパスのグローバル設定を構成する場合は、Skype for Business エンドポイントと、トランク接続でメディアをバイパスするように構成したすべてのピアとの間に接続性が良好であることを前提としています。
  
Skype for Business エンドポイントと、各トランク接続がメディアバイパスに対応している仲介サーバーへのすべてのピアとの接続が適切でない場合は、サイトと地域の情報を使用するようにグローバルメディアバイパス設定を構成する必要があります。メディアのバイパスを採用している場合。 これにより、メディアが仲介サーバーをバイパスするタイミングをより細かく制御できます。 これを行うには、「 [Skype For Business Server でのグローバル設定のメディアを無視する](use-site-and-region-information.md)」の手順に従って、サイトと地域の情報を使用し、[サブネットをネットワークサイトに関連付け](deploy-network.md#BKMK_AssociateSubnets)ます。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには

1. Skype for Business Server コントロールパネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. リスト内の [**グローバル**] 構成をダブルクリックします。
    
4. [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。
    
5. [**常にバイパスする**] をクリックします。
    
6. [**確定**] をクリックします。
    
## <a name="see-also"></a>関連項目

[Skype for Business でのメディアのバイパスの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Skype for Business Server でメディアバイパスを展開する](deploy-media-bypass.md)

