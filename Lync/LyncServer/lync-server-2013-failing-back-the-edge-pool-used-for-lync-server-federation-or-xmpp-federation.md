---
title: Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック
description: Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137910d71de1d6177356e0b7bacbd6d17022d71d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567723"
---
# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Lync server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

フェデレーションをホストしていたエッジ プールが障害から復旧してオンライに戻ったら、その復旧されたエッジ プールが再び使用されるように、以下の手順を使って Lync Server フェデレーション ルート または XMPP フェデレーション ルート (あるいはこの両方) をフェールバックします。

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>復旧されたエッジ プールにフェデレーションをフェールバックする

1.  再び使用できるようになったエッジ プールで、エッジ サービスを開始します。

2.  復旧されたエッジ サーバーが使用されるように Lync Server フェデレーション ルートをフェールバックするには以下を行います。
    
      - フロントエンド サーバーでトポロジ ビルダーを開きます。[**エッジ プール**] を展開し、現在フェデレーション用に構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックします。[**プロパティの編集**] をクリックします。
    
      - [**プロパティの編集**] の [**全般**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をクリアします。[**OK**] をクリックします。
    
      - [**エッジ プール**] を展開し、フェデレーションに再び使用する元のエッジ サーバーまたはエッジ サーバー プールを右クリックします。[**プロパティの編集**] をクリックします。
    
      - [**プロパティの編集**] の [**全般**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] を選択します。[**OK **] をクリックします。
    
      - [**アクション**] をクリックし、[**トポロジ**]、[**公開**] の順に選択します。[**トポロジの公開**] で入力を求められたら、[**次へ**] をクリックします。公開の終了後、[**完了**] をクリックします。
    
      - エッジ サーバーで、Lync Server 展開ウィザードを開きます。[**Lync Server システムのインストールまたは更新**]、[**Lync Server コンポーネントのセットアップまたは削除**] の順にクリックします。[**再実行**] をクリックします。
    
      - [Lync Server コンポーネントのセットアップ] で、[**次へ**] をクリックします。概要画面に、実行されたアクションが表示されます。展開が完了したら、[**ログの表示**] をクリックして、参照できるログ ファイルを表示します。[**完了**] をクリックして、展開を完了します。

3.  復旧されたエッジ サーバーが使用されるように XMPP フェデレーション ルートをフェールバックするには以下を行います。
    
      - 以下のコマンドレットを実行して、XMPP フェデレーション ルートが、XMPP フェデレーションをホストするようになるエッジ プール (この例では、EdgeServer1) を再び指すようにします。
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        この例では、Site1 は XMPP フェデレーション ルートをホストするようになるエッジ プールを含むサイトです。EdgeServer1.contoso.com はそのプール内のエッジ サーバーの FQDN です。
    
      - XMPP フェデレーションをホストするようになるエッジ プールに解決される、XMPP フェデレーション用の DNS SRV レコードがまだない場合は、以下の例のようにそれを追加する必要があります。この SRV レコードはポート値が 5269 である必要があります。
        
            _xmpp-server._tcp.contoso.com
    
      - 外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードが EdgeServer2.contoso.com を指すように変更します。
    
      - XMPP フェデレーションをホストするようになるエッジ プールがポート 5269 を外部にオープンしていることを確認します。

4.  障害発生後に復旧されたエッジ プールを含むサイトで、フロントエンド プールが実行を続けていた場合は、それらのフロントエンド プール上の Web 会議サービスおよび音声ビデオ会議サービスを更新して、ローカル サイトのエッジ プールが再び使用されるようにしてください。 詳細については、「 [Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。

5.  停止したエッジ プールと同じサイトでフロントエンド プールも停止していた場合は、Invoke–CsPoolFailback を使ってフロントエンド プールをフェールバックできます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Lync Server フェデレーションに使用するエッジプールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Lync Server 2013 でのエッジサーバーの障害復旧](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

