---
title: 常に仲介サーバーをバイパスするサーバー 2015 のビジネス用の Skype でのメディア バイ パスを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 常にビジネス サーバーのエンタープライズ VoIP の Skype に仲介サーバーをバイパスするのにはメディア バイ パスを有効にします。
ms.openlocfilehash: 5a7ca70b6f060c9d6a5399934fb784c9247e95fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a>常に仲介サーバーをバイパスするサーバー 2015 のビジネス用の Skype でのメディア バイ パスを構成します。
 
常にビジネス サーバーのエンタープライズ VoIP の Skype に仲介サーバーをバイパスするのにはメディア バイ パスを有効にします。 
  
 使用する場合は、メディアのグローバル設定を構成するには、このトピックの手順を省略、前提としてビジネス エンドポイントの Skype とトランク接続でメディア バイ パスを構成するすべてのピアとの間の適切な接続があること。
  
Skype ビジネス エンドポイントとのメディアのバイパスがそれぞれのトランク接続が有効になっている仲介サーバーへのすべてのピアとの間の適切な接続がない場合は、サイトと地域の情報を使用してグローバル メディア バイ パスの設定を構成する必要があります。用いたメディアをバイパスします。 これにより、メディアが仲介サーバーをバイパスするときを決定するときに詳細に制御できます。 これを行うには、[メディアの構成は、サイトと地域の情報を使用してサーバー 2015 のビジネス用の Skype のグローバル設定をバイパス](use-site-and-region-information.md)し、[ネットワーク サイトとサブネットを関連付ける](deploy-network.md#BKMK_AssociateSubnets)手順を代わりに使用します。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. リスト内の [**グローバル**] 構成をダブルクリックします。
    
4. [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。
    
5. [**常にバイパスする**] をクリックします。
    
6. [**確定**] をクリックします。
    
## <a name="see-also"></a>関連項目

#### 

[ビジネス 2015年の Skype でのメディア バイ パスの計画します。](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[ビジネス サーバー 2015 に Skype でのメディア バイ パスを展開します。](deploy-media-bypass.md)

