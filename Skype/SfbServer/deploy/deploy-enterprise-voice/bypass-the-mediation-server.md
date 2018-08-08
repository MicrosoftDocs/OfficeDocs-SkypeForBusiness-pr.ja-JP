---
title: Skype ビジネス サーバーを常に仲介サーバーをバイパスするためのメディア バイ パスを構成します。
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 常にビジネス サーバーのエンタープライズ VoIP の Skype に仲介サーバーをバイパスするのにはメディア バイ パスを有効にします。
ms.openlocfilehash: 518191dcf690650ebd614259e289f6cbf75ca8ce
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982609"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Skype ビジネス サーバーを常に仲介サーバーをバイパスするためのメディア バイ パスを構成します。
 
常にビジネス サーバーのエンタープライズ VoIP の Skype に仲介サーバーをバイパスするのにはメディア バイ パスを有効にします。 
  
 使用する場合は、メディアのグローバル設定を構成するには、このトピックの手順を省略、前提としてビジネス エンドポイントの Skype とトランク接続でメディア バイ パスを構成するすべてのピアとの間の適切な接続があること。
  
Skype ビジネス エンドポイントとのメディアのバイパスがそれぞれのトランク接続が有効になっている仲介サーバーへのすべてのピアとの間の適切な接続がない場合は、サイトと地域の情報を使用してグローバル メディア バイ パスの設定を構成する必要があります。用いたメディアをバイパスします。 これにより、メディアが仲介サーバーをバイパスするときを決定するときに詳細に制御できます。 これを行うには、[構成メディア ビジネス サーバーは、サイトと地域の情報を使用するの Skype のグローバル設定を使用しない](use-site-and-region-information.md)と、[ネットワーク サイトとサブネットを関連付ける](deploy-network.md#BKMK_AssociateSubnets)手順を代わりに使用します。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. リスト内の [**グローバル**] 構成をダブルクリックします。
    
4. [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。
    
5. [**常にバイパスする**] をクリックします。
    
6. [**確定**] をクリックします。
    
## <a name="see-also"></a>関連項目

[ビジネス用の Skype でメディアをバイパスするための計画します。](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[ビジネス サーバーの Skype でのメディア バイ パスを展開します。](deploy-media-bypass.md)

