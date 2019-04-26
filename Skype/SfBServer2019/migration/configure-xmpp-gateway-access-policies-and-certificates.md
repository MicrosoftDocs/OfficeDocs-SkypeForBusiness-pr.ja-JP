---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: XMPP フェデレーションでは、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) に基づいて、外部の配置を定義します。 XMPP は、の構成には、XMPP ドメイン ユーザーへのユーザー アクセスができます。
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238662"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成

XMPP フェデレーションでは、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) に基づいて、外部の配置を定義します。 XMPP は、の構成には、XMPP ドメイン ユーザーへのユーザー アクセスができます。
  
- IM とプレゼンスのユーザのみ
    
- 作成の XMPP フェデレーションのクライアントのビジネスの Skype の連絡先
    
構成するときは、XMPP をサポートするためのポリシーはフェデレーション パートナーしますが、XMPP のフェデレーション ドメインのユーザーにポリシーを適用しないセッション開始プロトコル (SIP) のユーザーがインスタント メッセージング (IM) サービスのプロバイダー、または SIP フェデレーション ドメイン。 XMPP フェデレーション ドメインごと、ユーザーが連絡先を追加するとの通信を許可するために、XMPP フェデレーション パートナーを構成するとします。 場所のポリシーが表示されたら、XMPP ゲートウェイ証明書を構成する必要があります。 
  
> [!NOTE]
> XMPP の機能は、ビジネス サーバー 2019、Skype では非推奨ですが、ビジネス サーバー 2019 の Skype との共存のレガシー サーバーで継続することができます。 レガシ サーバーを既に展開しているかどうかを確認 (ビジネス サーバー 2015 の Skype と Lync Server 2013) XMPP ゲートウェイでは、従来の XMPP ゲートウェイに対してユーザーを有効にするアクセス ポリシーを構成し、。 詳細については、 [XMPP フェデレーションの移行](migrating-xmpp-federation.md)を参照してください。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>従来の XMPP ゲートウェイの外部アクセス ポリシーを有効にするユーザーを構成します。

1. ビジネス サーバーのコントロール パネルの従来の Skype を開きます。
    
2. 左側のナビゲーション ・ バーで [**フェデレーションと外部アクセス**、および**外部アクセス ポリシー**] をクリックします。
    
3. [**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。
    
4. 外部アクセスのユーザー ポリシーの名前を入力します。
    
5. 外部アクセスのユーザー ポリシーの説明を提供します。
    
6. **フェデレーション ユーザーとの通信を有効にする**を選択します。
    
7. **XMPP と通信を有効にするフェデレーション ユーザー**を選択します。
    
8. **コミット**をサイトまたはユーザーのポリシーに変更を保存する] をクリックします。 
    

