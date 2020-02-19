---
title: 'Lync Server 2013: DNS 負荷分散'
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
ms.openlocfilehash: 0d08c56e8b88f13a965f7ab24c8f497e01f10400
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Lync Server 2013 での DNS 負荷分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-01-15_

Lync Server は、DNS 負荷分散を有効にします。これにより、ネットワーク上の負荷分散の管理オーバーヘッドを大幅に削減できます。 DNS 負荷分散は、SIP トラフィックやメディアトラフィックなど、Lync Server に固有のネットワークトラフィックのバランスをとります。

DNS 負荷分散を展開すると、ハードウェアロードバランサーの管理オーバーヘッドが最小限に抑えられます。 さらに、SIP トラフィックの負荷分散装置の構成ミスに関する問題に対応するために、複雑なトラブルシューティングを行う必要がなくなります。 サーバーをオフラインにできるようにサーバー接続を禁止することもできます。 また、DNS 負荷分散を使用して、ハードウェア ロード バランサーの問題が基本的な通話のルーティングなどの SIP トラフィックの要素に影響しないようにすることもできます。

また、DNS 負荷分散を使用すると、すべての種類のトラフィックに対応するハードウェア ロード バランサーを使用していた場合よりもハードウェア ロード バランサーを低価格で購入できます。 Lync Server との相互運用性認定テストに合格したロードバランサーを使用する必要があります。 ロードバランサー相互運用性テストの詳細については、「」の「Lync Server [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)2010 ロードバランサーパートナー」を参照してください。

DNS 負荷分散は、フロント エンド プール、エッジ サーバー プール、ディレクター プール、およびスタンドアロンの仲介サーバー プールでサポートされます。

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>フロント エンド プールとディレクター プールの DNS 負荷分散

フロント エンド プールとディレクター プールの SIP トラフィックに DNS 負荷分散を使用できます。 DNS 負荷分散を展開している場合でも、クライアントとサーバー間の HTTPS トラフィックに対してのみ、これらのプールに引き続きハードウェア ロード バランサーを使用する必要があります。 ハードウェア ロード バランサーは、ポート 443 とポート 80 経由のクライアントからの HTTPS トラフィックに対して使用します。

これらのプール用のハードウェア ロード バランサーは引き続き必要ですが、そのセットアップと管理は主に HTTP トラフィックに対するものであり、ハードウェア ロード バランサーの管理者にはなじみのあるものです。

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 負荷分散およびサポートされる以前のクライアントとサーバー

DNS 負荷分散は、Lync Server 2013 または Lync Server 2010 を実行しているサーバー、および Lync 2013 および Lync 2010 クライアントに対してのみ、自動フェールオーバーをサポートします。 以前のバージョンのクライアントおよび Office Communications Server は、DNS 負荷分散を実行しているプールに接続できますが、DNS 負荷分散が参照する最初のサーバーに接続できない場合、プール内の別のサーバーにフェールオーバーすることはできません。.

また、Exchange UM を使用している場合は、少なくとも Exchange 2010 SP1 を使用して Lync Server DNS 負荷分散のサポートを受ける必要があります。 以前のバージョンの Exchange を使用している場合、次の Exchange UM シナリオでは、ユーザーはフェールオーバー機能を利用できません。

  - 電話でエンタープライズ VoIP ボイス メールを再生する

  - Exchange UM 自動応答から通話を転送する

他のすべての Exchange UM シナリオでは効果があります。

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>フロント エンド プールとディレクター プールへの DNS 負荷分散の展開

フロント エンド プールとディレクター プールに DNS 負荷分散を展開するには、FQDN と DNS レコードでいくつか追加の手順を実行する必要があります。

  - DNS 負荷分散を使用するプールに、次の 2 つの FQDN がある必要があります。まず、DNS 負荷分散で使用される通常のプールの FQDN (pool01.contoso.com など) で、プール内のサーバーの物理 IP に解決されます。次に、プールの Web サービスの別の FQDN (web01.contoso.com など) で、プールの仮想 IP アドレスに解決されます。
    
    トポロジビルダーで、プールの DNS 負荷分散を展開する場合は、プールの Web サービス用の追加の FQDN を作成するには、[**内部 Web サービスプールの fqdn を上書き**する] チェックボックスをオンにして、[**このプールの Web サービス url を指定**します] ページで FQDN を入力する必要があります。

  - DNS 負荷分散で使用される FQDN をサポートするには、プールの FQDN (pool01.contoso.com など) をプール内のすべてのサーバーの IP アドレス (192.168.1.1、192.168.1.2 など) に解決するように DNS をプロビジョニングする必要があります。現在展開されているサーバーの IP アドレスのみ含めるようにしてください。
    
    <div>
    

    > [!WARNING]  
    > フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。 たとえば、フロントエンドサーバーの外部 Web サービスの FQDN を<STRONG>pool01.contoso.com</STRONG>として定義した場合、別のフロントエンドプールまたはフロントエンドサーバーに<STRONG>pool01.contoso.com</STRONG>を使用することはできません。 ディレクターを展開している場合は、ディレクターまたはディレクタープールに対して定義されている外部 Web サービスの FQDN が、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーとも一意である必要があります。 内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>エッジ サーバー プールの DNS 負荷分散

エッジ サーバー プールに DNS 負荷分散を展開できます。 その場合、いくつかの考慮事項に注意する必要があります。

エッジ サーバーで DNS 負荷分散を使用する場合、次のシナリオではフェールオーバー機能を利用できません。

  - Lync Server 2010 より前にリリースされたバージョンの Office Communications Server を実行している組織とのフェデレーション。

  - パブリックインスタントメッセージング (IM) サービス AOLand Yahoo\!のユーザーとのインスタントメッセージ交換 (Google Talk などの xmpp ベースのプロバイダーおよびサーバーに加えて)。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>現時点では、Google Talk はサポートされている唯一の XMPP パートナーです。</P>
    > <LI>
    > <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P></LI></UL>

    
    </div>

これらのシナリオは、プール内のすべてのエッジ サーバーが実行されている限り有効ですが、いずれかのエッジ サーバーが利用できなくなると、これらのシナリオでそのエッジ サーバーに送信されるすべての要求は、別のエッジ サーバーにルーティングされずに失敗します。

Exchange UM を使用している場合は、少なくとも Exchange 2013 を使用して、エッジで Lync Server DNS 負荷分散のサポートを受ける必要があります。 以前のバージョンの Exchange を使用している場合、リモートユーザーは、これらの Exchange UM シナリオではフェールオーバー機能を利用できません。

  - 電話でエンタープライズ VoIP ボイス メールを再生する

  - Exchange UM 自動応答から通話を転送する

他のすべての Exchange UM シナリオでは効果があります。

内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>エッジ サーバー プールへの DNS 負荷分散の展開

エッジ サーバー プールの外部インターフェイスに DNS 負荷分散を展開するには、次の DNS エントリが必要です。

  - アクセスエッジサービスでは、プール内のサーバーごとに1つのエントリが必要です。 各エントリでは、アクセスエッジサービスの FQDN (sip.contoso.com など) を、プール内のいずれかのエッジサーバー上のアクセスエッジサービスの IP アドレスに解決する必要があります。

  - Web 会議エッジサービスでは、プール内のサーバーごとに1つのエントリが必要です。 各エントリでは、Web 会議エッジサービスの FQDN (webconf.contoso.com など) をプール内のいずれかのエッジサーバー上の Web 会議エッジサービスの IP アドレスに解決する必要があります。

  - 音声ビデオエッジサービスでは、プール内のサーバーごとに1つのエントリが必要です。 各エントリでは、オーディオ/ビデオエッジサービス (たとえば、av.contoso.com) の FQDN を、プール内のいずれかのエッジサーバーの音声ビデオエッジサービスの IP アドレスに解決する必要があります。

エッジ サーバー プールの内部インターフェイスに DNS ロード バランシングを展開するには、エッジ サーバー プールの内部 FQDN をプール内の各サーバーの IP アドレスに解決する 1 つの DNS A レコードを追加する必要があります。

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>仲介サーバー プールでの DNS 負荷分散の使用

スタンドアロンの仲介サーバー プールで、DNS 負荷分散を使用できます。すべての SIP トラフィックとメディア トラフィックは DNS 負荷分散によって調整されます。

仲介サーバー プールに DNS 負荷分散を展開するには、プールの FQDN (mediationpool1.contoso.com など) をプール内のすべてのサーバーの IP アドレス (192.168.1.1、192.168.1.2 など) に解決するように DNS をプロビジョニングする必要があります。

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>DNS 負荷分散を使用してサーバーへのトラフィックをブロックする

DNS 負荷分散を使用していて、特定のコンピューターへのトラフィックをブロックする必要がある場合は、IP アドレスエントリをプールの FQDN から削除するだけで十分ではありません。 コンピューターの DNS エントリも削除する必要があります。

サーバー間トラフィックの場合、Lync Server 2013 ではトポロジ対応の負荷分散が使用されることに注意してください。 サーバーは、中央管理ストアで公開されているトポロジを読み取り、トポロジ内のサーバーの Fqdn を取得し、そのトラフィックをサーバー間で自動的に分配します。 サーバーからサーバーへのトラフィックの受信をブロックするには、サーバーをトポロジから削除する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

