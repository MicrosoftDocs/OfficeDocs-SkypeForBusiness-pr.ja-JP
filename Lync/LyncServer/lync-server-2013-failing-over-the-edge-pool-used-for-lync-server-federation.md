---
title: 'Lync Server 2013: Lync Server フェデレーションに使用するエッジプールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f884f9e2ee822e99ebb17bd4b17717d1e147bf95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Lync Server 2013 での Lync Server フェデレーションに使用するエッジプールのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

Lync Server のフェデレーションが構成されているエッジ プールがダウンした場合、フェデレーションを動作させるには、別のエッジ プールを使用するようにフェデレーションを変更する必要があります。

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Lync Server のフェデレーションに使用するエッジ プールのフェールオーバー

1.  フロントエンド サーバーでトポロジ ビルダーを開きます。[**エッジ プール**] を展開し、現在フェデレーションに構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックして、[**プロパティの編集**] を選択します。

2.  [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオフにします。[**OK**] をクリックします。

3.  [**エッジ プール**] を展開し、フェデレーションに使用するエッジ サーバーまたはエッジ サーバー プールを右クリックして、[**プロパティの編集**] を選択します。

4.  [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオンにします。[**OK**] を選択します。

5.  [**アクション**] をクリックし、[**トポロジ**]、[**公開**] の順に選択します。[**トポロジの公開**] で入力を求められたら、[**次へ**] をクリックします。公開の終了後、[**完了**] をクリックします。

6.  エッジ サーバーで、Lync Server 展開ウィザードを開きます。[**Lync Server システムのインストールまたは更新**]、[**Lync Server コンポーネントのセットアップまたは削除**] の順にクリックします。[**再実行**] をクリックします。

7.  [Lync Server コンポーネントのセットアップ] で、[**次へ**] をクリックします。概要画面に、実行されたアクションが表示されます。展開が完了したら、[**ログの表示**] をクリックして、参照できるログ ファイルを表示します。[**完了**] をクリックして、展開を完了します。
    
    失敗したエッジ プールを含むサイトにまだ稼動中のフロントエンド サーバーがある場合は、まだ稼動中のリモート サイトのエッジ プールを使用するように、これらのフロントエンド プールの Web 会議サービスおよび音声ビデオ会議サービスを更新する必要があります。 詳細については、「 [Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Lync server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Lync Server 2013 でのエッジサーバーの障害復旧](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

