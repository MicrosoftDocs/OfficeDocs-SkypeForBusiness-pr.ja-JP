---
title: XMPP ゲートウェイ アクセス ポリシーと証明書の構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づいて外部展開を定義します。 XMPP 構成を使用すると、ユーザーは次の方法で XMPP ドメイン ユーザーにアクセスできます。
ms.openlocfilehash: 31d3c2a4b4d16407a30eb755e8b18b3ddf1a1b31c342ed6ff3384bbcef3afbc6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296024"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP ゲートウェイ アクセス ポリシーと証明書の構成

XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づいて外部展開を定義します。 XMPP 構成を使用すると、ユーザーは次の方法で XMPP ドメイン ユーザーにアクセスできます。
  
- IM and Presence - ユーザー間のみ
    
- クライアントでの XMPP フェデレーション連絡先Skype for Businessする
    
XMPP フェデレーション パートナーをサポートするポリシーを構成する場合、ポリシーは XMPP フェデレーション ドメインのユーザーには適用されますが、セッション開始プロトコル (SIP) インスタント メッセージング (IM) サービス プロバイダーまたは SIP フェデレーション ドメインのユーザーには適用されません。 ユーザーが連絡先を追加して通信できる XMPP フェデレーション ドメインごとに XMPP フェデレーション パートナーを構成します。 ポリシーを設定したら、XMPP ゲートウェイ証明書を構成する必要があります。 
  
> [!NOTE]
> XMPP 機能は 2019 年Skype for Business Serverで廃止されましたが、従来のサーバーでは 2019 年と共存Skype for Business Serverできます。 レガシ サーバー (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway を既に展開し、ユーザーが従来の XMPP ゲートウェイを有効にするようにアクセス ポリシーを構成済みである必要があります。 詳細については [、「XMPP フェデレーションの移行」を参照してください](migrating-xmpp-federation.md)。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>従来の XMPP ゲートウェイでユーザーを有効にする外部アクセス ポリシーを構成する

1. 従来のコントロール パネルSkype for Business Server開きます。
    
2. 左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。
    
3. [**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。
    
4. 外部アクセス ユーザー ポリシーの名前を入力します。
    
5. 外部アクセス ユーザー ポリシーの説明を入力します。
    
6. [**フェデレーション ユーザーとの通信を有効にする**] を選択します。
    
7. [**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択します。
    
8. [**確定**] をクリックして、サイトまたはユーザー ポリシーへの変更を保存します。 
    

