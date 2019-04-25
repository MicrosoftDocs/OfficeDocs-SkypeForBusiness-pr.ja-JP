---
title: レガシー環境を確認します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 共存状態でのビジネス サーバー 2019 の Skype を導入する前に従来のサービスを構成および開始されたことを確認する必要があります。 重要なサービスと、Skype のビジネス サーバー 2019 パイロット プールを展開する前に、従来の環境に存在する機能を特定するのには重要です。 Microsoft Skype を展開する、従来の XMPP 展開との共存状態でのビジネス サーバー 2019 XMPP の前に従来の XMPP サービスを構成および開始を確認し、XMPP の従来の構成は、どちらのフェデレーション パートナーを識別する必要があります。サポートします。
ms.openlocfilehash: 0f9812efe966d72eba1eeead9d74780f2ba16661
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235115"
---
# <a name="verify-the-legacy-environment"></a>レガシー環境を確認します。

共存状態でのビジネス サーバー 2019 の Skype を導入する前に従来のサービスを構成および開始されたことを確認する必要があります。 重要なサービスと、Skype のビジネス サーバー 2019 パイロット プールを展開する前に、従来の環境に存在する機能を特定するのには重要です。 Microsoft Skype を展開する、従来の XMPP 展開との共存状態でのビジネス サーバー 2019 XMPP の前に従来の XMPP サービスを構成および開始することを確認し、フェデレーション パートナーの従来の XMPP の先を識別する必要があります。構成をサポートします。 以下が必要です、従来の展開を確認します。
  
- 従来のサービスが開始されているを確認します。
    
- トポロジとユーザーを確認します。
    
- フェデレーションおよびエッジ サーバーの設定を確認します。
    
- XMPP サービスとフェデレーション パートナーの確認
    
## <a name="verify-that-legacy-services-are-started"></a>従来のサービスが開始されていることを確認します。

1. 従来のフロント エンド サーバー、管理 Tools\Services のアプレットに移動します。
    
2. フロント エンド サーバー上で次のサービスが実行されていることを確認します。
    
     ![フロント エンド サーバーで実行されているサービスの一覧](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype で従来のトポロジを確認します。

1. RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。
    
2. Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. **トポロジ**を選択します。 従来配置内のさまざまなサーバーの一覧が表示されることを確認します。
    
     ![コントロール パネルのトポロジのページ](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype で従来のユーザーを確認します。

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. **ユーザー**を選択し、[**検索**] をクリックします。
    
3. **レジストラー プール**] 列が表示されている各ユーザーの従来のプールを指していることを確認します。 
    
     ![コントロール パネルのユーザーを一覧表示](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>従来のエッジとフェデレーションの設定を確認します。

1. トポロジ ビルダーを起動します。
    
2. **既存の展開からのトポロジのダウンロード**を選択します。
    
3. ファイルの名前を選択し、.tbxml ファイルの既定の種類のトポロジを保存します。
    
4. 展開におけるさまざまなサーバーの役割を明らかにするには、バージョンのインストール] ノードを展開します。
    
5. サイト] ノードを選択し、**サイトのフェデレーション ルートの割り当て**の値が設定されていることを確認します。 
    
     ![トポロジ ビルダーでは、サイトのフェデレーション ルート](../media/migration_lyncserver_w14_federation.jpg)
  
6. Standard Edition Server または Enterprise Edition フロント エンド プールを選択します。 メディア**関連**の下に、エッジ プールが構成されているかどうかを決定します。 
    
     ![サーバーとプールを表示するトポロジ ビルダー](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. エッジ プールを選択し、**次ホップの選択範囲**の下に次ホップ プールが構成されているかどうかを特定します。
    
     ![トポロジ ビルダーでは、次ホップの選択](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>従来の XMPP フェデレーション パートナーの構成を確認します。

1. 従来の XMPP サーバー管理用の Tools\Services のアプレットに移動します。
    
2. Office 通信サーバーの XMPP ゲートウェイ サービスが開始されていることを確認します。 
    
     ![Office 通信サーバー XMPP ゲートウェイ サービス](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

