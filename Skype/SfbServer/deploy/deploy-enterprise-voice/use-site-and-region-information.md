---
title: ビジネス サーバーは、サイトと地域の情報を使用するの Skype でメディア バイ パスのグローバル設定を構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: ビジネス サーバーのエンタープライズ VoIP の特定のサイトと Skype 内の領域のみに使用するメディア バイ パスを構成します。
ms.openlocfilehash: 42f6e9406fdb3a33124c5cfb7abba638dd7fa4b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892273"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>ビジネス サーバーは、サイトと地域の情報を使用するの Skype でメディア バイ パスのグローバル設定を構成します。
 
ビジネス サーバーのエンタープライズ VoIP の特定のサイトと Skype 内の領域のみに使用するメディア バイ パスを構成します。 
  
 使用する場合は、メディアのグローバル設定を構成するには、このトピックの手順を省略が前提とする必要はありませんビジネス エンドポイントのすべての Skype とトランク接続でメディア バイ パスを構成するすべてのピア間の接続が良好です。
  
> [!NOTE]
> ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。 
  
メディアを使用するバイパスの正しく必要があります一貫性、サイト間トポロジ ビルダーで定義されていると、ネットワーク地域およびネットワーク サイトを構成すると定義されています。 などがあると、トポロジ ビルダーで定義したブランチ サイトがある場合、PSTN ゲートウェイのみを展開し、ブランチ サイトのユーザー、PSTN 通話を PSTN 経由でルーティングを有効にするエンタープライズ VoIP ポリシーを使用してそのブランチ サイトを構成する必要があります。ブランチ サイトのゲートウェイです。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>メディア バイパスのサイトおよび地域情報を構成するには

1. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
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
> ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。 詳細については、[ネットワークの領域を展開、サイトとサブネットでビジネス用の Skype](deploy-network.md)を参照してください。 
  
## <a name="see-also"></a>関連項目

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

