---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d12a67b0ba102fdacea66b6196bafe32d89c9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503104"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>パイロット プールのレガシ エッジ サーバーへの接続

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-29_

Lync Server 2013 を展開した後、サイトのフェデレーションルートを構成する必要があります。 Lync Server 2010 で使用されているフェデレーションルートを使用するためには、このルートを使用するように Lync Server 2013 を構成する必要があります。

Lync server 2013 サイトが Lync Server 2010 展開のディレクターおよびエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>トポロジ ビルダーを使用してレガシ エッジ プールを関連付けるには

1.  **トポロジ ビルダー**を開きます。

2.  **Lync Server** ノードの直下にあるサイトを選択します。

3.  [**操作**] メニューの [**プロパティの編集**] をクリックします。

4.  左ウィンドウで、[**フェデレーション ルート**] をクリックします。

5.  ディレクターが表示されていない場合は、[ **サイトのフェデレーションルートの割り当て**] で [ **SIP フェデレーションの有効化**] を選択し、[lync server 2010 director] または [Lync server 2010 エッジサーバー] を選択します。
    
    ![[プロパティの編集]、[フェデレーションルート] ページ](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "[プロパティの編集]、[フェデレーションルート] ページ")  

6.  [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。

7.  [トポロジビルダー] の [Lync Server 2013] ノードで、 **Standard Edition サーバー** または **Enterprise Edition フロントエンドプール**に移動して、プールを右クリックし、[ **プロパティの編集**] をクリックします。

8.  [**関連付け**] で、[**エッジ プール (メディア コンポーネント用) を関連付ける**] の横のチェック ボックスをオンにします。

9.  一覧から、レガシ エッジ サーバーを選択します。
    
    ![従来のエッジを選択する [プロパティの編集] ダイアログ](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "従来のエッジを選択する [プロパティの編集] ダイアログ")  

10. [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。

11. **トポロジ ビルダー**で、最上位ノードの **Lync Server** を選択します。

12. [**操作**] メニューで、[**トポロジの公開**]、[**次へ**] の順にクリックします。

13. **公開ウィザード**の実行が完了したら、[**完了**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

