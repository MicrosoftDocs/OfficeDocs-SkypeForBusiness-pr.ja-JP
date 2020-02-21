---
title: パイロットプールを従来のエッジサーバーに接続する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48d2450d468ae6a28faef4c1fcacf577262c42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>パイロットプールを従来のエッジサーバーに接続する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Lync Server 2013 を展開した後に、このサイトのフェデレーションルートが構成されていません。 Office Communications Server 2007 R2 で使用されているフェデレーションルートを使用するためには、このルートを使用するように Lync Server 2013 を構成する必要があります。

Lync Server 2013 サイトが BackCompatSite のディレクターおよびエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>トポロジ ビルダーを使用してレガシ エッジ プールを関連付けるには

1.  トポロジビルダーでパイロットプールトポロジを開きます。

2.  Lync Server 2013 サイトを選択します。

3.  [**アクション**] メニューの [**プロパティの編集**] をクリックします。

4.  ディレクターが表示されていない場合は、[**サイトのフェデレーションルートの割り当て**] で、[ **SIP フェデレーションの有効化**] を選択してから、Office Communications server 2007 R2 Director または Office Communications Server 2007 r2 エッジサーバーを選択します。
    
    ![[プロパティの編集] ダイアログ、[フェデレーションルート] ページ](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "[プロパティの編集] ダイアログ、[フェデレーションルート] ページ")  

5.  [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。

6.  [トポロジビルダー] の [Lync Server 2013] ノードで、 **Standard Edition サーバー**または**Enterprise Edition フロントエンドプール**に移動して、プールを右クリックし、[**プロパティの編集**] をクリックします。

7.  [**関連付け**] で、[**エッジ プール (メディア コンポーネント用) を関連付ける**] の横のチェック ボックスをオンにします。

8.  リストから、BackCompatSite のエッジサーバーインターフェイスを選択します。
    
    ![[プロパティの編集] ダイアログの [全般] ページ](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "[プロパティの編集] ダイアログの [全般] ページ")  

9.  [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。

10. **トポロジ ビルダー**で、最上位ノードの **Lync Server** を選択します。

11. [**操作**] メニューで、[**トポロジの公開**]、[**次へ**] の順にクリックします。

12. **公開ウィザード**の実行が完了したら、[**完了**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

