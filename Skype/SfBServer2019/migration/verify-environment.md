---
title: 従来の環境を確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 を共存状態で展開する前に、従来のサービスが構成されて開始されていることを確認する必要があります。 Skype for Business Server 2019 パイロットプールを展開する前に、従来の環境に存在する主要サービスと機能を特定することが重要です。 従来の XMPP 展開を使用して、Microsoft Skype for Business Server 2019 XMPP を共存状態で展開する前に、以前の XMPP サービスが構成されて開始されていることを確認し、レガシ XMPP 構成のフェデレーションパートナーを特定する必要があります。サポート.
ms.openlocfilehash: 4c648dbbadeca50c12eb6047958ef63066ed7a3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243776"
---
# <a name="verify-the-legacy-environment"></a>従来の環境を確認する

Skype for Business Server 2019 を共存状態で展開する前に、従来のサービスが構成されて開始されていることを確認する必要があります。 Skype for Business Server 2019 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。 従来の XMPP 展開を使用して、Microsoft Skype for Business Server 2019 XMPP を共存状態で展開する前に、従来の XMPP サービスが構成されて開始されていることを確認し、レガシ XMPP のフェデレーションパートナーを特定する必要があります。構成がサポートされています。 従来の展開を確認することには、次のものがあります。
  
- 従来のサービスが開始されていることを確認する
    
- トポロジとユーザーの確認
    
- フェデレーションとエッジサーバーの設定を確認する
    
- XMPP サービスおよびフェデレーションパートナーを確認する
    
## <a name="verify-that-legacy-services-are-started"></a>従来のサービスが開始されていることを確認する

1. 従来のフロントエンドサーバーから、[管理] の [サービス] アプレットに移動します。
    
2. フロントエンドサーバーで次のサービスが実行されていることを確認します。
    
     ![フロントエンドサーバーで実行されているサービスの一覧](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルで従来のトポロジを確認する

1. RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。
    
2. Skype for Business Server コントロールパネルを開きます。
    
3. [**トポロジ**] を選びます。 レガシ展開のさまざまなサーバーが一覧に表示されていることを確認します。
    
     ![コントロールパネルのトポロジーページ](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルで従来のユーザーを確認する

1. Skype for Business Server コントロールパネルを開きます。
    
2. [**ユーザー**] を選択し、[**検索**] をクリックします。
    
3. **レジストラー pool**列が、表示されている各ユーザーのレガシープールをポイントしていることを確認します。 
    
     ![コントロールパネルのユーザの一覧](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>従来のエッジとフェデレーションの設定を確認する

1. トポロジビルダーを起動します。
    
2. [**既存の展開からトポロジをダウンロード**] を選択します。
    
3. ファイル名を選択し、tbxml ファイルの種類が設定されたトポロジを保存します。
    
4. 展開内のさまざまなサーバーの役割を表示するために、[従来のインストール] ノードを展開します。
    
5. サイトノードを選択し、[**サイトフェデレーションルートの割り当て**] の値が設定されていることを確認します。 
    
     ![トポロジビルダー、サイトフェデレーションルート](../media/migration_lyncserver_w14_federation.jpg)
  
6. Standard Edition Server または Enterprise Edition のフロントエンドプールを選択します。 **アソシエーション**の下にあるメディアにエッジプールが構成されているかどうかを確認します。 
    
     ![サーバーとプールを表示するトポロジビルダー](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. エッジプールを選択して、次ホッププールが**次ホップの選択**の下に構成されているかどうかを確認します。
    
     ![トポロジビルダー、次ホップの選択](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>従来の XMPP フェデレーションパートナーの構成を確認する

1. 従来の XMPP サーバーから、[管理] の [サービス] アプレットに移動します。
    
2. Office Communications Server XMPP ゲートウェイサービスが開始されていることを確認します。 
    
     ![Office Communications Server XMPP ゲートウェイサービス](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

