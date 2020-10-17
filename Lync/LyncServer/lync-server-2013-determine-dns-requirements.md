---
title: 'Lync Server 2013: DNS の要件を決定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d00f86eb437f673e83e2ea2e610ad9b35dbea082
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522604"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a>Lync Server 2013 の DNS 要件を決定する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

次のフローチャートを使用して、ドメインネームシステム (DNS) の要件を決定します。 Lync Server 2013 2013 の累積的な更新プログラムの変更点については、該当する場所について説明します。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 は、IPv6 アドレスの使用をサポートしています。 IPv6 アドレスを使用するには、IPv6 DNS のサポートを提供し、DNS ホスト AAAA ("クワッド-A") レコードを構成する必要もあります。 IPv4 と IPv6 の両方が使用されている展開では、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA の両方を構成して管理することをお勧めします。 展開が完全に IPv6 に移行している場合でも、外部ユーザーが依然として IPv4 を使用している場合は、IPv4 DNS ホストレコードが必要になることがあります。



</div>

**DNS 要件の判断フローチャート**

![175782ace363e4-08、912f2-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ace363e4-08、912f2-8991bf152970")

<div>


> [!IMPORTANT]  
> 既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく、ホスト名です。 トポロジビルダーでは、ホスト名ではなく Fqdn を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。 Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。 詳細については、「 <A href="lync-server-2013-configure-dns-host-records.md">CONFIGURE DNS Host records For Lync Server 2013</A> 」を参照してください。



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Lync クライアントがサービスを検索する方法

Microsoft Lync 2010、Lync 2013、Lync Mobile は、クライアントが Lync Server 2013 でサービスを検索してアクセスする方法に似ています。 注目すべき例外として、異なるサービスの場所のプロセスを使用する Lync Windows ストアアプリがあります。 このセクションでは、クライアントがサービスを検索する方法、最初に一連の SRV およびホストレコードを使用する従来の方法、さらには自動検出サービスレコードのみを使用して、2つのシナリオについて説明します。 デスクトップクライアントへの累積的な更新プログラムを適用すると、すべてのクライアントに対して Lync Server 2010 から DNS の場所のプロセスが変更されます。 DNS クエリプロセスは、クエリが正常に返されるか、または使用可能な DNS レコードの一覧が使い果たされるまで続行され、最終的なエラーがクライアントに返されます。

DNS 参照中に Lync Windows ストアアプリを **除く** すべてのクライアントについて、SRV レコードが照会され、次の順序でクライアントに返されます。

1.  lyncdiscoverinternal。 \<domain\>    内部 Web サービスの自動検出サービスの A (ホスト) レコード

2.  lyncdiscover。 \<domain\>    外部 Web サービス上の自動検出サービスの A (ホスト) レコード

3.  \_sipinternaltls。 \_tcp。 \<domain\>    内部 TLS 接続用の SRV (サービスロケーター) レコード

4.  \_sipinternal。 \_tcp。 \<domain\>    内部 TCP 接続の SRV (サービスロケーター) レコード (TCP が許可されている場合にのみ実行)

5.  \_sip。 \_tls。 \<domain\>    外部 TLS 接続用の SRV (サービスロケーター) レコード

6.  sipinternal。 \<domain\>    フロントエンドプールまたはディレクターの A (ホスト) レコード (内部ネットワーク上でのみ解決可能)

7.  sip。 \<domain\>    内部ネットワーク上のフロントエンドプールまたはディレクターの (ホスト) レコード、またはクライアントが外部にある場合はアクセスエッジサービス

8.  sipexternal。 \<domain\>    クライアントが外部にいる場合のアクセスエッジサービスの A (ホスト) レコード

Lync Windows ストアアプリは、2つのレコードを使用するので、プロセスが完全に変更されます。

1.  lyncdiscoverinternal。 \<domain\>    内部 Web サービスの自動検出サービスの A (ホスト) レコード

2.  lyncdiscover。 \<domain\>    外部 Web サービス上の自動検出サービスの A (ホスト) レコード

他のレコードの種類へのフォールバックはありません。

以前のクライアントと比較した新しいクライアントで使用される方法の違いは、自動検出サービスがすべてのサービスを特定するために推奨される方法です。

接続が成功すると、自動検出サービスはユーザーのホームプールのすべての Web サービス Url を返します。これには、Mobility Service (IIS のサービスに対して作成された仮想ディレクトリによる Mcx を使用)、Microsoft Lync Web App、Web スケジューラの Url が含まれます。 ただし、内部 Mobility Service URL と外部 Mobility Service URL の両方が外部 Web サービスの FQDN に関連付けられています。 そのため、モバイルデバイスがネットワークの内部と外部のどちらにあるかに関係なく、デバイスは常にリバースプロキシ経由でモビリティサービスに接続します。

Lync Server 2013 の累積的な更新プログラム (2 月 11 2013 日) がインストールされている場合、自動検出サービスは、Internal/UCWA、External/UCWA、UCWA への参照も返します。 これらのエントリは、統合コミュニケーション Web API (UCWA) web コンポーネントを参照します。 現時点では、エントリ UCWA のみが使用されており、web コンポーネントの URL への参照を提供しています。 UCWA は、lync 2010 モバイルクライアントで使用される Mcx Mobility Service ではなく、Lync 2013 モバイルクライアントによって使用されます。

<div>


> [!NOTE]  
> SRV レコードを作成する場合、DNS SRV レコードが作成されるのと同じドメインで DNS A および AAAA (IPv6 アドレスを使用している場合) レコードを参照する必要があることを覚えておくことが重要です。 たとえば、SRV レコードが contoso.com にある場合、A および AAAA (IPv6 アドレス指定を使用している場合) レコードは、fabrikam.com ではできません。



</div>

<div>


> [!TIP]  
> 既定の構成では、すべてのモバイルクライアントトラフィックを外部サイト経由で転送します。 要件に適している場合は、設定を変更して内部 URL のみを返すようにできます。 この構成では、ユーザーは企業ネットワークの内部にいる場合にのみ、モバイルデバイスで Lync mobile アプリケーションを使用できます。 この構成を定義するには、 <STRONG>Set-CsMcxConfiguration</STRONG> コマンドレットを使用します。



</div>

<div>


> [!NOTE]  
> モバイルアプリケーションは、アドレス帳サービスなどの他の Lync Server 2013 サービスに接続することもできますが、内部モバイルアプリケーション web 要求は、Mobility Service に対してのみ外部 web FQDN に送られます。 その他のサービス要求 (アドレス帳要求など) では、この構成は必要ありません。



</div>

モバイルデバイスは、サービスの手動検出をサポートしています。 この場合、各ユーザーは、次のように、完全な内部および外部の自動検出サービス Uri (プロトコルとパスを含む) でモバイルデバイスの設定を構成する必要があります。

  - \<ExtPoolFQDN\>外部アクセス用の Https:///autodiscover/autodiscoverservice.svc/root (

  - \<IntPoolFQDN\>内部アクセス用の Https:///AutoDiscover/AutoDiscover.svc/Root

手動検出ではなく、自動検出を使用することをお勧めします。 ただし、手動の設定は、モバイルデバイスの接続の問題のトラブルシューティングに役立ちます。

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Lync Server を使用して Split-Brain DNS を構成する

スプリットブレイン DNS は、分割 DNS またはスプリットホライズン DNS など、さまざまな名前で認識されます。 単純に、同じ名前空間を持つ2つの DNS ゾーンがあり、DNS ゾーンサービスの内部のみの要求、およびその他の DNS ゾーンサービスの外部専用要求がある DNS 構成について説明します。 ただし、内部 DNS に含まれる DNS SRV および A レコードの多くは、外部 DNS には含まれず、逆の場合も同様です。 内部および外部 DNS の両方に同じ DNS レコードが存在する場合 (たとえば、www.contoso.com)、返される IP アドレスは、クエリが開始された場所 (内部または外部) によって異なります。

<div>


> [!IMPORTANT]  
> Split-Brain 現時点では、LyncDiscover および LyncDiscoverInternal DNS レコードは、モビリティに対してはサポートされていません。 LyncDiscover は、外部 DNS サーバーで定義されている必要があり、LyncDiscoverInternal は内部 DNS サーバーで定義されている必要があります。



</div>

これらのトピックでは、スプリットブレイン DNS という用語が使用されます。

スプリットブレイン DNS を構成している場合は、次の内部および外部ゾーンに、各ゾーンで必要な DNS レコードの種類の概要が含まれています。 詳細については、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

**内部 DNS:**

  - 権限がある contoso.com という名前の DNS ゾーンが含まれています。

  - 内部 contoso.com ゾーンには、次のものが含まれます。
    
      - 内部 Lync Server 2013 クライアントの自動構成用の DNS A および AAAA (IPv6 アドレスを使用している場合) および SRV レコード (オプション)
    
      - Lync Server 2013 Web サービスの自動検出用の DNS A および AAAA (IPv6 アドレスを使用している場合) または CNAME レコード (オプション)
    
      - フロントエンドプール名、ディレクターまたはディレクターのプール名、および企業ネットワークで Lync Server 2013 を実行しているすべての内部サーバーの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード
    
      - 境界ネットワーク内の各 Lync Server 2013 のエッジ内部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) レコード
    
      - 境界ネットワーク内の各リバースプロキシサーバーの内部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) レコード (リバースプロキシの管理の場合はオプション)
    
      - 境界ネットワーク内のすべての Lync Server 2013 エッジサーバー内部エッジインターフェイスは、contoso.com へのクエリを解決するために内部 DNS ゾーンを使用します。
    
      - 企業ネットワーク内の Lync Server 2013 を実行2013しているすべてのサーバーは、contoso.com に対するクエリを解決するための内部 DNS サーバーを指しているか、各エッジサーバーで HOSTS ファイルを使用しています。また、各エッジサーバーで HOSTS ファイルを使用します。、または Standard Edition サーバー

**外部 DNS:**

  - 権限がある contoso.com という名前の DNS ゾーンが含まれています。

  - 外部 contoso.com ゾーンには、次のものが含まれます。
    
      - Lync Server 2013 クライアントの自動構成用の DNS A および AAAA (IPv6 アドレスを使用している場合) および SRV レコード (オプション)
    
      - モビリティで使用する Lync Server 2013 Web サービスの自動検出用の DNS A および AAAA (IPv6 アドレスを使用している場合) または CNAME レコード
    
      - 境界ネットワーク内の各 Lync Server 2013、エッジサーバーまたはハードウェアロードバランサー仮想 IP (VIP) のエッジ外部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) および SRV レコード
    
      - 境界ネットワーク内のリバースプロキシサーバーの外部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合)、または VIP の外部インターフェイスのレコード

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Split-Brain DNS を使用しない自動構成

内部 DNS ゾーンに sipinternaltls が含まれている場合は、スプリットブレイン DNS を使用して内部にサインインする Lync Server 2013 ユーザーが自動構成を利用できます \_ 。 \_使用中の各 SIP ドメインの tcp SRV レコード。 ただし、スプリットブレイン DNS を使用しない場合は、このセクションで後述する回避策のいずれかが実装されていなければ、Lync を実行しているクライアントの内部自動構成は機能しません。 これは、Lync Server 2013 では、ユーザーの SIP URI が自動構成用に指定されたフロントエンドプールのドメインと一致する必要があるためです。 これは、以前のバージョンの Communicator の場合と同じです。

たとえば、2つの SIP ドメインが使用されている場合、次の DNS サービス (SRV) レコードが必要になります。

  - ユーザーが bob@contoso.com としてサインインすると、ユーザーの SIP ドメイン (contoso.com) が自動構成フロントエンドプールのドメインと一致するため、次の SRV レコードが自動構成に対して機能します。
    
     \_sipinternaltls。 \_tcp.contoso.com。 SRV 0 0 5061 pool01.contoso.com の86400

  - ユーザーが alice@fabrikam.com としてサインインしている場合、次の DNS SRV レコードは、2番目の SIP ドメインの自動構成に使用できます。
    
     \_sipinternaltls。 \_tcp.fabrikam.com。 SRV 0 0 5061 pool01.fabrikam.com の86400

比較のために、ユーザーが tim@litwareinc.com としてサインインする場合、次の DNS SRV レコードは自動構成では機能しません。クライアントの SIP ドメイン (litwareinc.com) は、プールが存在するドメイン (fabrikam.com) と一致しないためです。

 \_sipinternaltls。 \_tcp.litwareinc.com。 SRV 0 0 5061 pool01.fabrikam.com の86400

Lync を実行しているクライアントに対して自動構成が必要な場合は、次のいずれかのオプションを選択します。

  - **グループポリシーオブジェクト**    グループポリシーオブジェクト (Gpo) を使用して、適切なサーバーの値を設定します。
    
    <div>
    

    > [!NOTE]  
    > このオプションは自動構成を有効にしませんが、手動構成のプロセスを自動化するので、この方法を使用した場合、自動構成に関連付けられている SRV レコードは必要ありません。

    
    </div>

  - **内部ゾーン**     の一致内部 DNS で、外部 DNS ゾーンに一致するゾーンを作成し (たとえば、contoso.com)、自動構成に使用される Lync Server 2013 プールに対応する DNS A および AAAA (IPv6 アドレスを使用している場合) を作成します。 たとえば、ユーザーが pool01.contoso.net に所属しているが、bob@contoso.com として Lync にサインインしている場合は、pool01.contoso.com の DNS A および AAAA (IPv6 アドレスを使用する場合) レコードを作成します。

  - **ピンポイントの内部ゾーン**    内部 DNS でゾーン全体を作成するのではなく、自動構成に必要な SRV レコードに対応する pin ポイント (つまり専用) の領域を作成し、それらの領域に dnscmd.exe を使用して設定することができます。 DNS ユーザーインターフェイスがピンポイントゾーンの作成をサポートしていないため、Dnscmd.exe が必要です。 たとえば、SIP ドメインが contoso.com、2台のフロントエンドサーバーを含む pool01 というフロントエンドプールがある場合は、次のピンポイントゾーンと内部 DNS 内のレコードが必要です。
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    環境に2番目の SIP ドメイン (たとえば、fabrikam.com) が含まれている場合は、次のピンポイントゾーンと内部 DNS 内のレコードが必要です。
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> フロントエンドプールの FQDN は2回表示されますが、2つの異なる IP アドレスがあります。 これは、DNS 負荷分散が使用されているためですが、ハードウェア負荷分散が使用されている場合は、フロントエンドプールのエントリが1つだけになります。 また、フロントエンドプールの FQDN 値は contoso.com の例と fabrikam.com の例で異なりますが、IP アドレスは同じままです。 これは、ユーザーがどちらかの SIP ドメインからサインインし、自動構成に同じフロントエンドプールを使用するためです。



</div>

詳細については、「DMTF のブログ記事、「Communicator Automatic Configuration and Split-Brain DNS,」 () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) 。

<div>


> [!NOTE]  
> 各ブログのコンテンツおよびその URL は予告なしに変更されることがあります。



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>障害復旧のためのドメインネームシステム (DNS) の構成

Lync Server 2013 Web トラフィックを障害回復およびフェールオーバーサイトにリダイレクトするように DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用している必要があります。 障害復旧をサポートするために Web 用の DNS レコードをセットアップすることができます。これにより、フロントエンドプール全体がダウンした場合でも、Web サービスを使用する機能が続行されます。 この障害復旧機能は、自動検出 (Lyncdiscover URL)、会議、およびダイヤルインの簡易 Url をサポートします。

GeoDNS プロバイダーの Web サービスの内部および外部の解決に、追加の DNS ホスト (A および AAAA を使用している場合は AAAA) レコードを定義して構成します。 次の詳細は、ラウンドロビン DNS を使用してプロバイダーがサポートしているペアプール、地理的に分散されている、および GeoDNS を想定しているか、または Pool1 をプライマリとして使用するように構成するか、または通信の損失やハードウェアの障害が発生した場合に Pool2 にフェールオーバーします。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>GeoDNS レコード (例)</th>
<th>プールレコード (例)</th>
<th>CNAME レコード (例)</th>
<th>DNS 設定 (1 つのオプションを選択)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com alias から Pool1InternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com alias から Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>プール間のラウンドロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com alias から Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com alias から Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>プール間のラウンドロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com alias から Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com alias から Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>プール間のラウンドロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com alias から Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com alias から Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>プール間のラウンドロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com alias から Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com alias から Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>プール間のラウンドロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com alias から Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com alias から Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>プール間のラウンドロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com alias から Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com alias から Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>プール間のラウンドロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com alias から Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com alias から Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>プール間のラウンドロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS 負荷分散

DNS 負荷分散は、通常、アプリケーションレベルで実装されます。 アプリケーション (たとえば、Lync を実行しているクライアント) は、プールの完全修飾ドメイン名 (FQDN) の DNS A および AAAA (IPv6 アドレスが使用されている場合) レコードクエリから返された IP アドレスの1つに接続して、プール内のサーバーへの接続を試行します。

たとえば、pool01.contoso.com という名前のプールに3つのフロントエンドサーバーがある場合、次の処理が行われます。

  - Pool01.contoso.com の Lync クエリ DNS を実行しているクライアント。 このクエリは3つの IP アドレスを返し、次のようにキャッシュします (この順序では必ずしも同じではありません)。
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - クライアントは、IP アドレスの1つに対して伝送制御プロトコル (TCP) 接続を確立しようとします。 失敗した場合、クライアントはキャッシュ内の次の IP アドレスを試行します。

  - TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com 上のプライマリレジストラーに接続します。

  - 接続が正常に行われなかったすべてのエントリをクライアントが試行すると、その時点で Lync Server 2013 を実行しているサーバーが利用できないことがユーザーに通知されます。

<div>


> [!NOTE]  
> Dns ベースの負荷分散は、通常、dns に依存して、プール内のサーバーに対応する異なる順序で IP アドレスを提供することによって負荷分散を参照する dns ラウンドロビン (DNS RR) とは異なります。 通常、DNS RR は負荷分散のみを有効にしますが、フェールオーバーを有効にしません。 たとえば、DNS A および AAAA (IPv6 アドレス指定を使用している場合) によって返された1つの IP アドレスへの接続が失敗すると、接続は失敗します。 そのため、DNS ラウンドロビン自体は、DNS ベースの負荷分散よりも信頼性が低くなります。 Dns ラウンドロビンを DNS 負荷分散と組み合わせて使用することができます。



</div>

DNS 負荷分散は次のように使用されます。

  - エッジサーバーへのサーバー間 SIP の負荷分散

  - 会議の自動応答、応答グループ、コールパークなどの統合コミュニケーションアプリケーションサービス (UCAS) アプリケーションの負荷分散

  - アプリケーション ("ドレイン" とも呼ばれる) として UCAS の新しい接続を禁止する

  - クライアントとエッジサーバー間のクライアントとサーバー間のすべてのトラフィックの負荷分散

DNS 負荷分散は、次のような場合には使用できません。

  - ディレクターまたはフロントエンドサーバーへのクライアントからサーバーへの web トラフィック

DNS 負荷分散とフェデレーショントラフィック:

DNS SRV クエリによって複数の DNS レコードが返される場合、アクセスエッジサービスは常に、最も低い数値の優先度と最大の数値を持つ DNS SRV レコードを選択します。 「サービスの場所を指定するための DNS RR」というインターネット技術標準化のタスク強制ドキュメント。 <http://www.ietf.org/rfc/rfc2782.txt> 複数の DNS srv レコードが定義されている場合、優先度が最初に使用され、次に重みが設定されることを指定します。 たとえば、DNS SRV レコード A の重みは20で、優先度は40、DNS SRV レコード B の重みは10、優先度は50です。 優先度40の DNS SRV レコード A が選択されます。 DNS SRV レコードの選択には、次のルールが適用されます。

  - 優先度が最初に考慮されます。 クライアントは、DNS SRV レコードによって定義されているターゲットホストに、到達可能な最小番号の優先度を持つ接続を試みる必要があります。 同じ優先度を持つターゲットは、weight フィールドで定義された順序で試行する必要があります。

  - [重み] フィールドには、同じ優先度を持つエントリの相対的な重みを指定します。 重みが大きいほど、選択される可能性が高くなります。 DNS 管理者は、サーバーが選択されていない場合はウエイト0を使用する必要があります。 0より大きい加重値を持つレコードが存在する場合、重み付けが0のレコードは、選択される可能性が非常に低くなります。

優先度と重みが同じ複数の DNS SRV レコードが返された場合、アクセスエッジサービスは最初に DNS サーバーから受信した SRV レコードを選択します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

