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
ms.localizationpriority: medium
description: 2019 Skype for Business Server後、サイトのフェデレーション ルートを構成する必要があります。 従来のインストールで使用されているフェデレーション ルートを使用するには、このルートを使用するように Skype for Business Server 2019 を構成する必要があります。
ms.openlocfilehash: a5f5da34300d993f59d4de5e2eb0b47cc58eff0e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607464"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>パイロット プールのレガシ エッジ サーバーへの接続

2019 Skype for Business Server後、サイトのフェデレーション ルートを構成する必要があります。 従来のインストールで使用されているフェデレーション ルートを使用するには、このルートを使用するように Skype for Business Server 2019 を構成する必要があります。 
  
従来の展開Skype for Business Server 2019 サイトでディレクターとエッジ サーバーを使用するには、トポロジ ビルダーを使用してレガシ エッジ プールを関連付ける必要があります。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>トポロジ ビルダーを使用してレガシ エッジ プールを関連付けるには

1. トポロジ ビルダーを開きます。 
    
2. サイトを選択します。このサイトは、**このノードの** Skype for Business Serverします。 
    
3. [**操作**] メニューの [**プロパティの編集**] をクリックします。
    
4. 左ウィンドウで、[**フェデレーション ルート**] をクリックします。
    
5. [ **サイトフェデレーション ルートの割り当** て] で **、[SIP** フェデレーションを有効にする] を選択し、レガシ ディレクターを選択するか、ディレクターが一覧に表示されない場合は従来のエッジ サーバーを選択します。
  
6. [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。 
    
7. トポロジ ビルダーの Skype for Business Server 2019 ノードの下で **、Standard Edition** サーバーまたは **Enterprise Edition** フロントエンド プールに移動し、プールを右クリックし、[プロパティの編集] をクリック **します**。
    
8. [**関連付け**] で、[**エッジ プール (メディア コンポーネント用) を関連付ける**] の横のチェック ボックスをオンにします。 
    
9. 一覧から、レガシ エッジ サーバーを選択します。 
  
10. [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。 
    
11. トポロジ **ビルダーで、** 最も上位のノードを選択し、[Skype for Business Server]**をクリックします**。
    
12. [**操作**] メニューで、[**トポロジの公開**]、[**次へ**] の順にクリックします。
    
13. **公開ウィザード** の実行が完了したら、[**完了**] をクリックします。
    

