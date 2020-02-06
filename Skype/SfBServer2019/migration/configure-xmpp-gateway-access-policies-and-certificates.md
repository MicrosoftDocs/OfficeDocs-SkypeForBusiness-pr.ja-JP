---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコル (XMPP) に基づいて外部展開を定義します。 XMPP の構成では、ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813765"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成

XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコル (XMPP) に基づいて外部展開を定義します。 XMPP の構成では、ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。
  
- IM とプレゼンス-相手からのみ
    
- Skype for Business クライアントでの XMPP フェデレーション連絡先の作成
    
XMPP フェデレーションパートナーのサポートのためにポリシーを構成すると、そのポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) のインスタントメッセージング (IM) サービスプロバイダー、または SIP フェデレーションドメインのユーザーには適用されません。 ユーザーが連絡先を追加して通信できるようにする、各 XMPP フェデレーションドメインに対して XMPP フェデレーションパートナーを構成します。 ポリシーが設定されたら、XMPP ゲートウェイ証明書を構成する必要があります。 
  
> [!NOTE]
> XMPP 機能は、Skype for Business Server 2019 では使われなくなりましたが、従来のサーバーでは引き続き、Skype for Business Server 2019 と共存させることができます。 以前のバージョンのレガシサーバー (Skype for Business Server 2015/Lync Server 2013) XMPP ゲートウェイを既に展開していることを確認して、従来の XMPP ゲートウェイのユーザーを有効にするためのアクセスポリシーを構成していることを確認します。 詳細については、「 [XMPP フェデレーションを移行](migrating-xmpp-federation.md)する」を参照してください。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>外部アクセスポリシーを構成して、レガシ XMPP ゲートウェイのユーザーを有効にする

1. 従来の Skype for Business Server コントロールパネルを開きます。
    
2. 左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。
    
3. [**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。
    
4. 外部アクセスのユーザーポリシーの名前を入力します。
    
5. 外部アクセスユーザーポリシーの説明を入力します。
    
6. [**フェデレーションユーザーとの通信を有効にする**] を選択します。
    
7. [ **XMPP フェデレーションユーザーとの通信を有効にする**] を選択します。
    
8. [**コミット**] をクリックして、サイトまたはユーザーポリシーの変更を保存します。 
    

