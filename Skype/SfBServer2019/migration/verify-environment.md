---
title: 従来の環境を確認する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 2019 Skype for Business Server共存状態で展開する前に、従来のサービスが構成および開始されていることを確認する必要があります。 2019 パイロット プールを展開する前に、従来の環境に存在する主要なサービスと機能をSkype for Business Server重要です。 従来の XMPP 展開との共存状態で Microsoft Skype for Business Server 2019 XMPP を展開する前に、従来の XMPP サービスが構成および開始されていることを確認し、従来の XMPP 構成がサポートしているフェデレーション パートナーを特定する必要があります。
ms.openlocfilehash: c81686f77d42f855f61699d3f141ffcaa463bc9a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586241"
---
# <a name="verify-the-legacy-environment"></a>従来の環境を確認する

2019 Skype for Business Server共存状態で展開する前に、従来のサービスが構成および開始されていることを確認する必要があります。 2019 パイロット プールを展開する前に、従来の環境に存在する主要なサービスSkype for Business Server重要です。 従来の XMPP 展開との共存状態で Microsoft Skype for Business Server 2019 XMPP を展開する前に、従来の XMPP サービスが構成および開始されていることを確認し、従来の XMPP 構成がサポートしているフェデレーション パートナーを特定する必要があります。 従来の展開を確認するには、次の手順が必要です。
  
- レガシ サービスが開始されたのを確認する
    
- トポロジとユーザーの確認
    
- フェデレーションとエッジ サーバーの設定の確認
    
- XMPP サービスとフェデレーション パートナーの確認
    
## <a name="verify-that-legacy-services-are-started"></a>レガシ サービスが開始されたのを確認する

1. 従来のフロント エンド サーバーから、[管理ツール\サービス] アプレットに移動します。
    
2. 次のサービスがフロントエンド サーバーで実行されていることを確認します。
    
     ![フロント エンド サーバーで実行されているサービスの一覧](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>[コントロール パネル] で従来のトポロジSkype for Business Server確認する

1. RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。
    
2. [コントロール パネルSkype for Business Server開きます。
    
3. [**トポロジ**] クリックします。 従来の展開のさまざまなサーバーが一覧に表示されるのを確認します。
    
     ![コントロール パネルのトポロジ ページ](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>[コントロール パネル] で従来Skype for Business Serverを確認する

1. [コントロール パネルSkype for Business Server開きます。
    
2. [ユーザー **] を選択** し、[検索] **をクリックします**。
    
3. [レジストラー プール **] 列が、** 一覧に表示されている各ユーザーのレガシ プールをポイントしている点を確認します。 
    
     ![ユーザーを一覧するコントロール パネル](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>従来のエッジとフェデレーションの設定を確認する

1. トポロジ ビルダーを開始します。
    
2. [**既存の展開からトポロジをダウンロードする**] をクリックします。
    
3. ファイル名を選択し、既定の .tbxml ファイルの種類を使用してトポロジを保存します。
    
4. 従来のインストール ノードを展開して、展開のさまざまなサーバーの役割を表示します。
    
5. サイト ノードを選択し、サイトフェデレーション ルート割り当ての値が **設定** されているのを確認します。 
    
     ![トポロジ ビルダー、サイト フェデレーション ルート](../media/migration_lyncserver_w14_federation.jpg)
  
6. [サーバー] Standard Editionまたはフロントエンド Enterprise Editionを選択します。 [関連付け] の下のメディアにエッジ プールが構成 **されているかどうかを確認します**。 
    
     ![サーバーとプールを表示するトポロジ ビルダー](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. エッジ プールを選択し、次ホップ プールが [次ホップの選択] の下に構成 **されているかどうかを識別します**。
    
     ![トポロジ ビルダー、次ホップの選択](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>従来の XMPP フェデレーション パートナーの構成を確認する

1. レガシ XMPP サーバから、管理ツール\サービス アプレットに移動します。
    
2. Office Communications Server XMPP Gateway サービスが開始されていることを確認します。 
    
     ![OfficeCommunications Server XMPP Gateway Service](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

