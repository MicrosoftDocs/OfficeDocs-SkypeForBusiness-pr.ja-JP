---
title: 'Lync Server 2013: DNS の負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Lync Server 2013 での DNS の負荷分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-01-15_

Lync Server を使用すると、DNS の負荷分散が有効になり、ネットワークでの負荷分散の管理オーバーヘッドが大幅に削減されます。 DNS ロードバランシングは、SIP トラフィックやメディアトラフィックなど、Lync Server に固有のネットワークトラフィックのバランスを行います。

DNS の負荷分散を展開すると、組織のハードウェアロードバランサーの管理オーバーヘッドが最小化されます。 さらに、SIP トラフィックのロードバランサーの誤りに関連する問題の複雑なトラブルシューティングも行われなくなります。 サーバー接続を禁止して、サーバーをオフラインにすることもできます。 また、DNS の負荷分散により、ハードウェアロードバランサーの問題が、基本的な通話ルーティングなどの SIP トラフィックの要素に影響を与えることはありません。

DNS 負荷分散を使用している場合は、すべての種類のトラフィックにハードウェアロードバランサーを使用した場合よりも低コストのハードウェアロードバランサーを購入できる場合があります。 ロードバランサーを使用して、Lync Server で相互運用性の認定テストに合格している必要があります。 ロードバランサーの相互運用性テストの詳細については、の「Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)ロードバランサーパートナー」を参照してください。

DNS の負荷分散は、フロントエンドプール、エッジサーバープール、ディレクタープール、スタンドアロンの仲介サーバープールでサポートされています。

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>フロントエンドプールとディレクタープールの DNS ロードバランシング

フロントエンドプールおよびディレクタープールの SIP トラフィックには、DNS の負荷分散を使用できます。 DNS ロードバランシングが展開されている場合でも、これらのプールにはハードウェアロードバランサーを使用する必要があります。ただし、クライアントとサーバーの HTTPS トラフィックに対してのみ使用できます。 ハードウェアロードバランサーは、ポート443および80経由のクライアントからの HTTPS トラフィックに使用されます。

ただし、これらのプールについては、ハードウェアロードバランサーが必要ですが、これらのセットアップと管理は主に HTTPS トラフィック用であり、ハードウェアロードバランサーの管理者は使い慣れています。

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS の負荷分散と、古いクライアントとサーバーのサポート

DNS の負荷分散は、Lync Server 2013 または Lync Server 2010、および Lync 2013 および Lync 2010 クライアントを実行しているサーバーに対してのみ、自動フェールオーバーをサポートします。 以前のバージョンのクライアントと Office Communications Server でも、DNS 負荷分散を実行しているプールに接続できますが、DNS ロードバランシングで参照される最初のサーバーに接続できない場合は、プール内の別のサーバーにフェールオーバーすることはできません。.

さらに、Exchange UM を使用している場合は、少なくとも Exchange 2010 SP1 を使用して、Lync Server DNS の負荷分散のサポートを受ける必要があります。 以前のバージョンの Exchange を使用している場合、ユーザーには次の Exchange UM シナリオのフェールオーバー機能はありません。

  - スマートフォンでのエンタープライズボイスボイスメールの再生

  - Exchange UM 自動応答からの着信の転送

その他のすべての Exchange UM シナリオは適切に動作します。

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>フロントエンドプールとディレクタープールで DNS の負荷分散を展開する

フロントエンドプールとディレクタープールで DNS の負荷分散を展開するには、Fqdn と DNS レコードでいくつかの追加の手順を実行する必要があります。

  - DNS 負荷分散を使用するプールには、DNS 負荷分散によって使用される標準プール FQDN (pool01.contoso.com など) と、プール内のサーバーの物理 Ip アドレス、さらにプールの Web サービス用の別の FQDN が含まれている必要があります。web01.contoso.com)。プールの仮想 IP アドレスに解決されます。
    
    トポロジビルダーでプールの負荷分散を展開する場合は、プールの Web サービスの追加 FQDN を作成するには、[**内部 Web サービスプールの fqdn を上書き**する] チェックボックスをオンにして、[**このプールの Web サービス url を指定**してください] ページで fqdn を入力する必要があります。

  - DNS の負荷分散で使用される FQDN をサポートするには、DNS をプロビジョニングしてプールの FQDN (pool01.contoso.com など) を、プール内のすべてのサーバーの IP アドレス (たとえば、192.168.1.1、192.168.1.2 など) に解決する必要があります。 現在展開されているサーバーの IP アドレスのみを含める必要があります。
    
    <div>
    

    > [!WARNING]  
    > 複数のフロントエンドプールまたはフロントエンドサーバーがある場合は、外部 Web サービスの FQDN が一意である必要があります。 たとえば、フロントエンドサーバーの外部 Web サービス FQDN を<STRONG>pool01.contoso.com</STRONG>として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して<STRONG>pool01.contoso.com</STRONG>を使用することはできません。 ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーから一意である必要があります。 自己定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>エッジサーバープールでの DNS の負荷分散

エッジサーバープールで DNS の負荷分散を展開できます。 その場合は、いくつかの考慮事項に注意する必要があります。

エッジサーバーで DNS の負荷分散を使用すると、次のシナリオでフェールオーバー機能が失われます。

  - Lync Server 2010 より前にリリースされたバージョンの Office Communications Server を実行している組織とのフェデレーション。

  - パブリックインスタントメッセージング (IM) サービス AOLand Yahoo\!のユーザーとのインスタントメッセージ交換 (Google Talk などの xmpp ベースのプロバイダーとサーバー)。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google Talk は現在サポートされている XMPP パートナーのみです。</P>
    > <LI>
    > <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P></LI></UL>

    
    </div>

これらのシナリオは、プール内のすべてのエッジサーバーが稼働していても動作しますが、1つのエッジサーバーが利用できない場合は、他のエッジサーバーにルーティングする代わりに、これらのシナリオに対する要求はすべて失敗します。

Exchange UM を使用している場合は、少なくとも Exchange 2013 を使用して、microsoft Lync Server DNS の負荷分散を Edge でサポートする必要があります。 以前のバージョンの Exchange を使用している場合、リモートユーザーには次の Exchange UM シナリオのフェールオーバー機能はありません。

  - スマートフォンでのエンタープライズボイスボイスメールの再生

  - Exchange UM 自動応答からの着信の転送

その他のすべての Exchange UM シナリオは適切に動作します。

内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。 1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>エッジサーバープールへの DNS 負荷分散の展開

エッジサーバープールの外部インターフェイスに DNS の負荷分散を展開するには、次の DNS エントリが必要です。

  - アクセスエッジサービスの場合、プール内の各サーバーに1つのエントリが必要です。 各エントリは、アクセスエッジサービスの FQDN (sip.contoso.com など) を、プール内のいずれかのエッジサーバー上のアクセスエッジサービスの IP アドレスに解決する必要があります。

  - Web 会議エッジサービスの場合、プール内の各サーバーに1つのエントリが必要です。 各エントリは、Web 会議エッジサービスの FQDN (webconf.contoso.com など) を、プール内のいずれかのエッジサーバー上の Web 会議エッジサービスの IP アドレスに解決する必要があります。

  - オーディオ/ビデオエッジサービスの場合、プール内の各サーバーに1つのエントリが必要です。 各エントリは、オーディオ/ビデオエッジサービス (たとえば、av.contoso.com) の FQDN を、プール内のいずれかのエッジサーバー上の A/V Edge サービスの IP アドレスに解決する必要があります。

エッジサーバープールの内部インターフェイスで DNS の負荷分散を展開するには、1つの DNS A レコードを追加する必要があります。これにより、エッジサーバープールの内部 FQDN がプール内の各サーバーの IP アドレスに解決されます。

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>仲介サーバープールでの DNS ロードバランシングの使用

DNS の負荷分散は、スタンドアロンの仲介サーバープールで使うことができます。 SIP とメディアのトラフィックはすべて DNS の負荷分散によって均等化されます。

DNS 負荷分散を仲介サーバープールに展開するには、DNS をプロビジョニングしてプールの FQDN (たとえば、mediationpool1.contoso.com) を、プール内のすべてのサーバーの IP アドレス (たとえば、192.168.1.1、192.168.1.2 など) に解決する必要があります。

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>DNS 負荷分散を使用してサーバーへのトラフィックをブロックする

DNS 負荷分散を使用していて、特定のコンピューターへのトラフィックを遮断する必要がある場合は、プールの FQDN から IP アドレス エントリを削除するだけでは十分ではありません。コンピューターの DNS エントリも削除する必要があります。

サーバー間のトラフィックについては、Lync Server 2013 はトポロジに対応した負荷分散を使用していることに注意してください。 サーバーは、中央管理ストアで公開されているトポロジを読み取り、トポロジ内のサーバーの Fqdn を取得し、サーバー間でトラフィックを自動的に分散します。 サーバーがサーバー間トラフィックを受信することをブロックするには、トポロジからサーバーを削除する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

