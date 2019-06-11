---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc42c645548ea9bad072da5f18643271a9eceeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>パイロット プールのレガシ エッジ サーバーへの接続

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-29_

Lync Server 2013 を展開した後、サイトのフェデレーションルートを構成する必要があります。 Lync Server 2010 で使用されているフェデレーションルートを使用するには、Lync Server 2013 がこのルートを使用するように構成されている必要があります。

Lync server 2013 サイトで Lync Server 2010 展開のディレクターとエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>トポロジビルダーを使用して従来のエッジプールを関連付けるには

1.  **トポロジビルダー**を開きます。

2.  **Lync Server**ノードのすぐ下にあるサイトを選びます。

3.  [**操作**] メニューの [**プロパティの編集**] をクリックします。

4.  左側のウィンドウで、[**フェデレーションルート**] を選びます。

5.  [**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選び、lync server 2010 ディレクター、またはディレクターが表示されていない場合は Lync server 2010 エッジサーバーを選びます。
    
    ![[プロパティの編集]、[フェデレーションルート] ページ](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "[プロパティの編集]、[フェデレーションルート] ページ")  

6.  [ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。

7.  [トポロジビルダー] の [Lync Server 2013] ノードで、 **Standard edition Server**または**Enterprise Edition のフロントエンドプール**に移動し、プールを右クリックして、[**プロパティの編集**] をクリックします。

8.  [**関連付け**] で [ **Edge プールを関連付ける (メディアコンポーネント)**] の横にあるチェックボックスをオンにします。

9.  リストから、従来のエッジサーバーを選択します。
    
    [![プロパティの編集] ダイアログ、[旧端] の選択][(images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "プロパティの編集] ダイアログ、[旧端] の選択")  

10. [ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。

11. [**トポロジビルダー**] で、最上位のノードである**Lync Server**を選択します。

12. [**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。

13. **発行ウィザード**が完了したら、[**完了**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

