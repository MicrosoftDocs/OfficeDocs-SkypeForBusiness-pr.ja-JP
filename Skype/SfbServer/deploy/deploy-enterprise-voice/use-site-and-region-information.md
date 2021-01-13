---
title: サイトおよび地域情報を使用するために Skype for Business Server のメディア バイパス グローバル設定を構成する
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: メディア バイパスを、Skype for Business Server の一部のサイトと地域でのみ使用エンタープライズ VoIP。
ms.openlocfilehash: 58fd4fca90029a8a5f4cd82c6a9616ae66e69cd0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830587"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>サイトおよび地域情報を使用するために Skype for Business Server のメディア バイパス グローバル設定を構成する
 
メディア バイパスを、Skype for Business Server の一部のサイトと地域でのみ使用エンタープライズ VoIP。 
  
 このトピックの手順を使用してメディア バイパスのグローバル設定を構成する場合、すべての Skype for Business エンドポイントと、トランク接続でメディア バイパスを構成したピア間の接続が良好ではないと想定されます。
  
> [!NOTE]
> ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。 
  
メディア バイパスが適切に動作するには、トポロジ ビルダーで定義されているサイトと、ネットワーク地域とネットワーク サイトを構成するときに定義されているサイト間の一貫性が必要です。 たとえば、トポロジ ビルダーで PSTN ゲートウェイのみを展開するように定義したブランチ サイトがある場合、ブランチ サイトのユーザーがブランチ サイトの PSTN ゲートウェイを介して PSTN 通話をルーティングできる エンタープライズ VoIP ポリシーを使用して、そのブランチ サイトを構成する必要があります。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>メディア バイパスのサイトおよび地域情報を構成するには

1. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. 表の [**グローバル**] 構成をダブルクリックします。
    
4. [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。
    
5. [**サイトと地域の構成を使用する**] をクリックします。
    
6. 必要に応じて、[**マップされていないサイトのバイパスを有効にする**] チェック ボックスをオンにします。
    
    > [!NOTE]
    > このチェック ボックスは、帯域幅制限のない同一地域に関連付けられた 1 つまたは複数の大規模なサイト (大規模なセントラル サイトなど) があり、帯域幅制限がある同一地域に関連付けられたいくつかのブランチ サイトもある場合のみオンにします。マップされていないサイトのバイパスを有効にすると、すべてのサイトに関連付けられたすべてのサブネットを指定する必要がなく、ブランチ サイトに関連付けられたサブネットのみを指定するため、構成が効率的になります。通話受付管理が有効な場合は、このチェック ボックスをオンにしないことをお勧めします。 
  
7. [**確定**] をクリックします。
    
次に、「サブネットをネットワーク サイトに関連付ける」の説明に従って、サブネット [をネットワーク サイトに追加します](deploy-network.md#BKMK_AssociateSubnets)。 すべてのサブネットをネットワーク サイトに関連付けると、メディア バイパスの展開は完了です。
> [!IMPORTANT]
> ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。 詳細については [、「Skype for Business でのネットワーク地域、サイト、サブネットの展開」を参照してください](deploy-network.md)。 
  
## <a name="see-also"></a>関連項目

[サブネットをネットワーク サイトに関連付ける](deploy-network.md#BKMK_AssociateSubnets)

