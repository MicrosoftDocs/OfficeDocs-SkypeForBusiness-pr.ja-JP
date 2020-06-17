---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
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
description: XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づいて外部展開を定義します。 XMPP 構成を使用すると、ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753937"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成

XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づいて外部展開を定義します。 XMPP 構成を使用すると、ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。
  
- IM とプレゼンス-ユーザーからのみ
    
- Skype for Business クライアントでの XMPP フェデレーション連絡先の作成
    
XMPP フェデレーションパートナーのサポートのためのポリシーを構成する場合、ポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) インスタントメッセージング (IM) サービスプロバイダーまたは SIP フェデレーションドメインのユーザーには適用されません。 ユーザーが連絡先を追加して通信できるようにする XMPP フェデレーションドメインごとに XMPP フェデレーションパートナーを構成します。 ポリシーを設定したら、XMPP ゲートウェイ証明書を構成する必要があります。 
  
> [!NOTE]
> XMPP 機能は、Skype for Business Server 2019 では廃止されましたが、従来のサーバーで Skype for business Server 2019 と共存させることができます。 従来のサーバー (Skype for Business Server 2015/Lync Server 2013) XMPP ゲートウェイを既に展開していること、および従来の XMPP ゲートウェイをユーザーが使用できるようにアクセスポリシーを構成していることを確認してください。 詳細については、「 [XMPP フェデレーションを移行](migrating-xmpp-federation.md)する」を参照してください。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>従来の XMPP ゲートウェイでユーザーを有効にするための外部アクセスポリシーを構成する

1. 従来の Skype for Business Server コントロールパネルを開きます。
    
2. 左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。
    
3. [**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。
    
4. 外部アクセス ユーザー ポリシーの名前を入力します。
    
5. 外部アクセス ユーザー ポリシーの説明を入力します。
    
6. [**フェデレーション ユーザーとの通信を有効にする**] を選択します。
    
7. [**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択します。
    
8. [**確定**] をクリックして、サイトまたはユーザー ポリシーへの変更を保存します。 
    

