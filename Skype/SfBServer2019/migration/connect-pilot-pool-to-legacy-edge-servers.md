---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。 従来のインストールで使用されているフェデレーションルートを使用するには、Skype for Business Server 2019 がこのルートを使用するように構成されている必要があります。
ms.openlocfilehash: 20aacda86c6c49b319859d6f1c175ce6258caddb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288629"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>パイロット プールのレガシ エッジ サーバーへの接続

Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。 従来のインストールで使用されているフェデレーションルートを使用するには、Skype for Business Server 2019 がこのルートを使用するように構成されている必要があります。 
  
Skype for Business Server 2019 サイトで従来の展開のディレクターとエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>トポロジビルダーを使用して従来のエッジプールを関連付けるには

1. トポロジビルダーを開きます。 
    
2. **Skype For Business Server**ノードのすぐ下にあるサイトを選びます。 
    
3. [**操作**] メニューの [**プロパティの編集**] をクリックします。
    
4. 左側のウィンドウで、[**フェデレーションルート**] を選びます。
    
5. [**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選択し、[レガシディレクター]、またはディレクターが表示されていない場合は従来のエッジサーバーを選択します。
  
6. [ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。 
    
7. [トポロジビルダー] の [Skype for Business Server 2019] ノードで、 **Standard edition Server**または**Enterprise Edition のフロントエンドプール**に移動し、プールを右クリックして、[**プロパティの編集**] をクリックします。
    
8. [**関連付け**] で [ **Edge プールを関連付ける (メディアコンポーネント)**] の横にあるチェックボックスをオンにします。 
    
9. リストから、従来のエッジサーバーを選択します。 
  
10. [ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。 
    
11. [**トポロジビルダー**] で、最上位のノードである [ **Skype for business Server**] を選びます。
    
12. [**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。
    
13. **発行ウィザード**が完了したら、[**完了**] をクリックします。
    

