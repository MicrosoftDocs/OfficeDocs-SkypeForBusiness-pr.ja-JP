---
title: パイロット プールのレガシ エッジ サーバーへの接続
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
description: Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。 従来のインストールで使用されているフェデレーションルートを使用するためには、このルートを使用するように Skype for Business Server 2019 を構成する必要があります。
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753927"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>パイロット プールのレガシ エッジ サーバーへの接続

Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。 従来のインストールで使用されているフェデレーションルートを使用するためには、このルートを使用するように Skype for Business Server 2019 を構成する必要があります。 
  
Skype for Business Server 2019 サイトが従来の展開のディレクターおよびエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>トポロジ ビルダーを使用してレガシ エッジ プールを関連付けるには

1. トポロジ ビルダーを開きます。 
    
2. [ **Skype For Business Server** ] ノードのすぐ下にあるサイトを選択します。 
    
3. [**操作**] メニューの [**プロパティの編集**] をクリックします。
    
4. 左ウィンドウで、[**フェデレーション ルート**] をクリックします。
    
5. [**サイトのフェデレーションルートの割り当て**] で、[ **SIP フェデレーションの有効化**] を選択してから、従来のディレクター、またはディレクターが表示されていない場合は従来のエッジサーバーを選択します。
  
6. [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。 
    
7. [トポロジビルダー] の [Skype for Business Server 2019] ノードで、 **Standard Edition サーバー**または**Enterprise Edition フロントエンドプール**に移動して、プールを右クリックし、[**プロパティの編集**] をクリックします。
    
8. [**関連付け**] で、[**エッジ プール (メディア コンポーネント用) を関連付ける**] の横のチェック ボックスをオンにします。 
    
9. 一覧から、レガシ エッジ サーバーを選択します。 
  
10. [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。 
    
11. [**トポロジビルダー**] で、最上位ノードの [ **Skype for business Server**] を選択します。
    
12. [**操作**] メニューで、[**トポロジの公開**]、[**次へ**] の順にクリックします。
    
13. **公開ウィザード**の実行が完了したら、[**完了**] をクリックします。
    

