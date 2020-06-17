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
localization_priority: Normal
description: Skype for Business Server 2019 を共存状態で展開する前に、従来のサービスが構成され、起動していることを確認する必要があります。 Skype for Business Server 2019 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。 従来の XMPP 展開を使用して、Microsoft Skype for Business Server 2019 XMPP を共存状態に展開する前に、従来の XMPP サービスが構成されて起動していることを確認し、従来の XMPP 構成がサポートしているフェデレーションパートナーを特定する必要があります。
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751679"
---
# <a name="verify-the-legacy-environment"></a>従来の環境を確認する

Skype for Business Server 2019 を共存状態で展開する前に、従来のサービスが構成され、起動していることを確認する必要があります。 Skype for Business Server 2019 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。 レガシ XMPP 展開を使用して、Microsoft Skype for Business Server 2019 XMPP を共存状態に展開する前に、従来の xmpp サービスが構成および開始されていることを確認し、従来の XMPP 構成がサポートしているフェデレーションパートナーを特定する必要があります。 従来の展開を確認するには、次のことが伴います。
  
- 従来のサービスが開始されていることを確認する
    
- トポロジとユーザーの確認
    
- フェデレーションとエッジサーバーの設定の確認
    
- XMPP サービスとフェデレーションパートナーを確認する
    
## <a name="verify-that-legacy-services-are-started"></a>従来のサービスが開始されていることを確認する

1. 従来のフロントエンドサーバーから、管理ツール \ サービスアプレットに移動します。
    
2. 次のサービスがフロントエンド サーバーで実行されていることを確認します。
    
     ![フロントエンドサーバーで実行されているサービスの一覧](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルで従来のトポロジを確認する

1. RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。
    
2. Skype for Business Server コントロールパネルを開きます。
    
3. [**トポロジ**] クリックします。 従来の展開に含まれるさまざまなサーバーが表示されていることを確認します。
    
     ![コントロールパネルのトポロジページ](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルで従来のユーザーを確認する

1. Skype for Business Server コントロールパネルを開きます。
    
2. [**ユーザー**] を選択し、[**検索**] をクリックします。
    
3. [**レジストラープール**] 列が、表示されている各ユーザーのレガシプールを指していることを確認します。 
    
     ![ユーザーを一覧表示するコントロールパネル](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>従来のエッジとフェデレーションの設定を確認する

1. トポロジ ビルダーを開始します。
    
2. [**既存の展開からトポロジをダウンロードする**] をクリックします。
    
3. ファイル名を選択し、redmond.tbxml ファイルの種類が既定のトポロジを保存します。
    
4. [従来のインストール] ノードを展開して、展開に含まれるさまざまなサーバーの役割を確認します。
    
5. サイトノードを選択し、[**サイトのフェデレーションルートの割り当て**] の値が設定されていることを確認します。 
    
     ![トポロジビルダー、サイトのフェデレーションルート](../media/migration_lyncserver_w14_federation.jpg)
  
6. Standard Edition サーバーまたは Enterprise Edition フロントエンドプールを選択します。 エッジプールが、 **association**の下にあるメディアに対して構成されているかどうかを確認します。 
    
     ![トポロジビルダー、サーバーとプールが表示されている](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. エッジプールを選択し、次ホッププールを次**ホップの選択範囲**より下に構成するかどうかを指定します。
    
     ![トポロジビルダー、次ホップの選択](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>レガシ XMPP フェデレーションパートナーの構成を確認する

1. レガシ XMPP サーバから、管理ツール\サービス アプレットに移動します。
    
2. Office Communications Server XMPP Gateway サービスが開始されていることを確認します。 
    
     ![Office Communications Server XMPP ゲートウェイサービス](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

