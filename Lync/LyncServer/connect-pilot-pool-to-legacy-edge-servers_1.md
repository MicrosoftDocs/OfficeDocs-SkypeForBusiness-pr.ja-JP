---
title: パイロット プールのレガシ エッジ サーバーへの接続
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
ms.openlocfilehash: 09858b03c787af034790c94bcbf12ca6ea7ceecf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>パイロット プールのレガシ エッジ サーバーへの接続

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

Lync Server 2013 を展開した後、このサイトのフェデレーションルートは構成されていません。 Office Communications Server 2007 R2 で使用されているフェデレーションルートを使用するには、Lync Server 2013 がこのルートを使用するように構成されている必要があります。

Lync Server 2013 サイトで BackCompatSite のディレクターとエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>トポロジビルダーを使用して従来のエッジプールを関連付けるには

1.  トポロジビルダーでパイロットプールトポロジを開きます。

2.  Lync Server 2013 サイトを選びます。

3.  [**操作**] メニューの [**プロパティの編集**] をクリックします。

4.  [**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選択し、ディレクターが表示されていない場合は、Office Communications server 2007 R2 ディレクターか、Office Communications Server 2007 r2 エッジサーバーを選択します。
    
    ![[プロパティの編集] ダイアログ、[フェデレーションルート] ページ](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "[プロパティの編集] ダイアログ、[フェデレーションルート] ページ")  

5.  [ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。

6.  [トポロジビルダー] の [Lync Server 2013] ノードで、 **Standard edition Server**または**Enterprise Edition のフロントエンドプール**に移動し、プールを右クリックして、[**プロパティの編集**] をクリックします。

7.  [**関連付け**] で [ **Edge プールを関連付ける (メディアコンポーネント)**] の横にあるチェックボックスをオンにします。

8.  リストから、BackCompatSite のエッジサーバーインターフェイスを選択します。
    
    ![[プロパティの編集] ダイアログの [全般] ページ](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "[プロパティの編集] ダイアログの [全般] ページ")  

9.  [ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。

10. [**トポロジビルダー**] で、最上位のノードである**Lync Server**を選択します。

11. [**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。

12. **発行ウィザード**が完了したら、[**完了**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

