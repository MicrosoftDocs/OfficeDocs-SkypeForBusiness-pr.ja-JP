---
title: Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

フェデレーションをホストするために使用された、失敗したエッジプールをオンラインに戻した後、次の手順を実行して、Lync Server フェデレーションルートまたは XMPP フェデレーションルートをフェイルバックし、この復元されたエッジプールを再び使用します。

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>復元されたエッジプールへのフェデレーションのフェイルバック

1.  もう一度使用できるようになったエッジプールで、エッジサービスを開始します。

2.  復元されたエッジサーバーを使用するために Lync Server フェデレーションルートをフェイルバックする場合は、次の操作を行います。
    
      - フロントエンドサーバーで、[トポロジビルダー] を開きます。 [ **Edge プール**] を展開して、フェデレーション用に現在構成されているエッジサーバープールまたはエッジサーバープールを右クリックします。 [**プロパティの編集**] を選びます。
    
      - [**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] をオフにします。 **[OK]** をクリックします。
    
      - [ **Edge プール**] を展開し、もう一度フェデレーションに使用する元のエッジサーバープールまたはエッジサーバープールを右クリックします。 [**プロパティの編集**] を選びます。
    
      - [**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] を選択します。 **[OK]** をクリックします。
    
      - [**アクション**] をクリックし、[**トポロジ**] を選択し、[**発行**] を選択します。 **トポロジの発行**を求められたら、[**次へ**] をクリックします。 発行が完了したら、[**完了**] をクリックします。
    
      - エッジサーバーで、Lync Server 展開ウィザードを開きます。 [ **Lync Server System のインストールまたは更新**] をクリックし、[ **lync Server コンポーネントのセットアップまたは削除**] をクリックします。 [**実行] をもう一度**クリックします。
    
      - Lync Server コンポーネントのセットアップで、[**次へ**] をクリックします。 概要画面には、実行中の操作が表示されます。 展開が完了したら、[**ログの表示**] をクリックして、利用可能なログファイルを表示します。 [**完了**] をクリックして展開を完了します。

3.  復元されたエッジサーバーを使用するために XMPP フェデレーションルートをフェイルバックする場合は、次の操作を行います。
    
      - 次のコマンドレットを実行して、xmpp フェデレーションルートを Edge プールに再ポイントします。これにより、XMPP フェデレーションがホストされます (この例では EdgeServer1)。
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        この例では、Site1 は、XMPP フェデレーションルートをホストするエッジプールが含まれているサイトで、EdgeServer1.contoso.com はそのプールのエッジサーバーの FQDN です。
    
      - Xmpp フェデレーション用の DNS SRV レコードをまだ持っていない場合は、次の例のように、それを追加する必要があります。これは、現在 XMPP フェデレーションをホストしています。 この SRV レコードには、5269のポート値を指定する必要があります。
        
            _xmpp-server._tcp.contoso.com
    
      - 外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードを EdgeServer2.contoso.com に変更します。
    
      - XMPP フェデレーションをホストしている Edge プールのポート5269が外部で開かれていることを確認します。

4.  フロントエンドプールが、失敗して復元されたエッジプールが含まれているサイトでまだ実行されている場合は、これらのフロントエンドプールの Web 会議サービスと A/V 会議サービスを更新して、もう一度ローカルサイトでエッジプールを使用する必要があります。 詳細については、「 [Lync Server 2013 でフロントエンドプールに関連付けられているエッジプールを変更する](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。

5.  障害が発生したエッジプールと同じサイトのフロントエンドプールでもエラーが発生する場合は、CsPoolFailback を使ってフロントエンドプールをフェールバックすることができます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Lync Server フェデレーションに使用するエッジ プールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Lync Server 2013 でのエッジ サーバーの障害復旧](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

