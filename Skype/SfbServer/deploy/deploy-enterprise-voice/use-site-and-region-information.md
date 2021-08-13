---
title: サイトと地域の情報を使用Skype for Business Serverメディア バイパスのグローバル設定を構成する
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
description: 特定のサイトと地域でのみ使用するメディア バイパスを構成Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 38fa42374b4b5dd8c8f304de04c9beeb59f2635d955b2e9ee5afb1fb16de7789
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322339"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>サイトと地域の情報を使用Skype for Business Serverメディア バイパスのグローバル設定を構成する
 
特定のサイトと地域でのみ使用するメディア バイパスを構成Skype for Business Server エンタープライズ VoIP。 
  
 このトピックの手順を使用してメディア バイパスのグローバル設定を構成する場合は、すべての Skype for Business エンドポイントとトランク接続でメディア バイパスを構成したピアとの間に良好な接続が確立されていないという前提があります。
  
> [!NOTE]
> ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。 
  
メディア バイパスが適切に機能するには、トポロジ ビルダーで定義されているサイトと、ネットワーク領域とネットワーク サイトを構成するときに定義されているサイトの間に一貫性が必要です。 たとえば、トポロジ ビルダーで PSTN ゲートウェイのみを展開するように定義したブランチ サイトがある場合、ブランチ サイトユーザーがブランチ サイトの PSTN ゲートウェイを介して PSTN 通話をルーティングできる エンタープライズ VoIP ポリシーを使用してブランチ サイトを構成する必要があります。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>メディア バイパスのサイトおよび地域情報を構成するには

1. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。
    
3. 表の [**グローバル**] 構成をダブルクリックします。
    
4. [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。
    
5. [**サイトと地域の構成を使用する**] をクリックします。
    
6. 必要に応じて、[**マップされていないサイトのバイパスを有効にする**] チェック ボックスをオンにします。
    
    > [!NOTE]
    > このチェック ボックスは、帯域幅制限のない同一地域に関連付けられた 1 つまたは複数の大規模なサイト (大規模なセントラル サイトなど) があり、帯域幅制限がある同一地域に関連付けられたいくつかのブランチ サイトもある場合のみオンにします。マップされていないサイトのバイパスを有効にすると、すべてのサイトに関連付けられたすべてのサブネットを指定する必要がなく、ブランチ サイトに関連付けられたサブネットのみを指定するため、構成が効率的になります。通話受付管理が有効な場合は、このチェック ボックスをオンにしないことをお勧めします。 
  
7. [**確定**] をクリックします。
    
次に、「サブネットをネットワーク サイトに関連付ける」の説明に従って、サブネット [をネットワーク サイトに追加します](deploy-network.md#BKMK_AssociateSubnets)。 すべてのサブネットをネットワーク サイトに関連付けると、メディア バイパスの展開が完了します。
> [!IMPORTANT]
> ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。 詳細については、「ネットワーク領域[、サイト、](deploy-network.md)サブネットを展開する」を参照Skype for Business。 
  
## <a name="see-also"></a>関連項目

[サブネットをネットワーク サイトに関連付ける](deploy-network.md#BKMK_AssociateSubnets)

