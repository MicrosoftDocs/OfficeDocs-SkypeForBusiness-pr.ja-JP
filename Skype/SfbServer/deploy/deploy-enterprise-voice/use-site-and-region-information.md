---
title: サイトと地域の情報を使用するために、Skype for Business Server でメディアを無視するグローバル設定を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Skype for Business Server Enterprise Voice で特定のサイトと地域に対してのみ使用するようにメディアバイパスを構成します。
ms.openlocfilehash: 3bfb3dca6e53316d5c1de71abad976ae9223c787
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240045"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>サイトと地域の情報を使用するために、Skype for Business Server でメディアを無視するグローバル設定を構成する
 
Skype for Business Server Enterprise Voice で特定のサイトと地域に対してのみ使用するようにメディアバイパスを構成します。 
  
 このトピックの手順を使用してメディアのバイパスのグローバル設定を構成する場合、すべての Skype for Business エンドポイントと、トランク接続でメディアをバイパスするように構成したピアとの間の接続が良好でないことを前提としています。
  
> [!NOTE]
> ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。 
  
メディアのバイパスが正常に動作するためには、トポロジビルダーで定義されているサイトと、ネットワーク領域とネットワークサイトを構成するときに定義されているサイトの間で一貫性が保たれている必要があります。 たとえば、PSTN ゲートウェイのみが展開されていることを示すために、トポロジビルダーで定義したブランチサイトがある場合、そのブランチサイトは、ブランチサイトユーザーが pstn 経由でルーティングする PSTN 通話を使用できるようにするエンタープライズ Voip ポリシーを使って構成する必要があります。ブランチサイトのゲートウェイ。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>メディア バイパスのサイトおよび地域情報を構成するには

1. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. 表の [**グローバル**] 構成をダブルクリックします。
    
4. [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。
    
5. [**サイトと地域の構成を使用する**] をクリックします。
    
6. 必要に応じて、[**マップされていないサイトのバイパスを有効にする**] チェック ボックスをオンにします。
    
    > [!NOTE]
    > このチェック ボックスは、帯域幅制限のない同一地域に関連付けられた 1 つまたは複数の大規模なサイト (大規模なセントラル サイトなど) があり、帯域幅制限がある同一地域に関連付けられたいくつかのブランチ サイトもある場合のみオンにします。マップされていないサイトのバイパスを有効にすると、すべてのサイトに関連付けられたすべてのサブネットを指定する必要がなく、ブランチ サイトに関連付けられたサブネットのみを指定するため、構成が効率的になります。通話受付管理が有効な場合は、このチェック ボックスをオンにしないことをお勧めします。 
  
7. [**確定**] をクリックします。
    
次に、「[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)」の説明に従ってネットワーク サイトにサブネットを追加します。すべてのサブネットをネットワーク サイトに関連付けたら、メディア バイパスの展開は完了です。
> [!IMPORTANT]
> ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。 詳細については、「 [Skype For business でネットワークのリージョン、サイト、サブネットを展開](deploy-network.md)する」を参照してください。 
  
## <a name="see-also"></a>関連項目

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

