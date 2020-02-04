---
title: 'Lync Server 2013: DNS の要件を確認する'
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
ms.openlocfilehash: fd8c1c95c3b8ba3671735447f098eca9173111ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>Lync Server 2013 の DNS の要件を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

次のフローチャートを使用して、ドメインネームシステム (DNS) の要件を確認します。 Lync Server 2013 の累積更新プログラムの変更点については、2013年2月に、それらが適用される場所を示しています。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 では、IPv6 アドレスの使用がサポートされています。 IPv6 アドレスを使用するには、IPv6 DNS のサポートも提供し、DNS host AAAA ("クアッドコア" と呼ばれます) レコードを構成する必要があります。 IPv4 と IPv6 の両方が使用されている展開では、IPv4 のホスト A レコードと IPv6 用の host AAAA の両方を構成および管理することをお勧めします。 展開が IPv6 に完全に移行されている場合でも、外部ユーザーが IPv4 を使用している場合は IPv4 DNS ホストレコードが必要になることがあります。



</div>

**DNS 要件フローチャートを決定する**

![175782ace363e4-08 a8-912f2-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ace363e4-08 a8-912f2-8991bf152970")

<div>


> [!IMPORTANT]  
> 既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく、ホスト名です。 トポロジビルダーでは、ホスト名ではなく Fqdn を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で DNS サフィックスを構成する必要があります。 Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。 詳細については、「 <A href="lync-server-2013-configure-dns-host-records.md">Lync Server 2013 の DNS ホストレコードを構成する</A>」を参照してください。



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Lync クライアントがサービスを見つける方法

Microsoft Lync 2010、Lync 2013、Lync Mobile は、クライアントが Lync Server 2013 でサービスを検索してアクセスする方法に似ています。 重要な例外として、別のサービスの場所のプロセスを使用する Lync Windows ストアアプリがあります。 このセクションでは、自動検出サービスレコードのみを使用して、クライアントがサービスを見つける方法、一連の SRV とホストレコードを使用する従来の方法について、2つのシナリオについて説明します。 デスクトップクライアントの累積更新プログラムによって、DNS の位置情報のプロセスが Lync Server 2010 から変更されるすべてのクライアントについて、DNS クエリのプロセスは、成功したクエリが返されるか、または可能な DNS レコードの一覧がなくなって、最終的なエラーが返されるまで、クライアント。

DNS 参照時に Lync Windows ストアアプリを**除く**すべてのクライアントで、SRV レコードが照会され、次の順序でクライアントに返されます。

1.  lyncdiscoverinternal.\<内部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード

2.  lyncdiscover.\<外部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード

3.  \_sipinternaltls.\_tcp。\<内部\> TLS 接続のドメイン SRV (サービスロケーター) レコード

4.  \_sipinternal.\_tcp。\<内部\> tcp 接続のドメイン SRV (サービスロケーター) レコード (TCP が許可されている場合にのみ実行)

5.  \_フェデレーション.\_tls。\<外部\> TLS 接続のドメイン SRV (サービスロケーター) レコード

6.  sipinternal.\<フロント\>エンドプールまたはディレクターのドメイン A (ホスト) レコード。内部ネットワークでのみ解決可能

7.  フェデレーション.\<内部\>ネットワーク上のフロントエンドプールまたはディレクターのドメイン A (ホスト) レコード、またはクライアントが外部の場合はアクセスエッジサービス

8.  sipexternal.\<クライアント\>が外部の場合のアクセスエッジサービスのドメイン A (ホスト) レコード

Lync Windows ストアアプリでは、次の2つのレコードが使用されるため、そのプロセスが完全に変更されます。

1.  lyncdiscoverinternal.\<内部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード

2.  lyncdiscover.\<外部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード

他のレコードの種類にフォールバックすることはできません。

古いクライアントと比較した場合の新しいクライアントで使用されるメソッドの違いは、自動検出サービスがすべてのサービスを見つけるために推奨される方法です。

接続に成功すると、自動検出サービスは、ユーザーのホームプールのすべての Web サービスの Url (IIS のサービス用に作成された仮想ディレクトリによる Mcx と呼ばれます)、Microsoft Lync Web App、Web scheduler Url などを返します。 ただし、内部のモビリティーサービス URL と外部モビリティーサービスの URL は両方とも、外部 Web サービスの FQDN と関連付けられています。 そのため、モバイルデバイスがネットワークの内部と外部のどちらであるかに関係なく、デバイスは常にリバースプロキシ経由で外部のモビリティサービスに接続します。

Lync Server 2013 の累積更新プログラム (2013 年2月) がインストールされている場合、自動検出サービスは、内部/UCWA、外部/UCWA、UCWA への参照も返します。 これらのエントリは、ユニファイドコミュニケーション Web API (UCWA) web コンポーネントを参照します。 現時点では、エントリ "UCWA" のみが使われ、web コンポーネントの URL への参照が提供されています。 UCWA は、Lync 2010 モバイルクライアントで使用される Mcx Mobility サービスではなく、Lync 2013 モバイルクライアントによって使用されます。

<div>


> [!NOTE]  
> SRV レコードを作成する場合は、dns SRV レコードが作成された同じドメインで DNS A と AAAA (IPv6 アドレス指定を使用している場合) を参照している必要があることに注意することが重要です。 たとえば、SRV レコードが contoso.com にある場合、A と AAAA (IPv6 アドレス指定を使用している場合) レコードは、fabrikam.com ではできません。



</div>

<div>


> [!TIP]  
> 既定の構成では、すべてのモバイルクライアントトラフィックが外部サイト経由で転送されます。 必要に応じて、内部 URL のみを返すように設定を変更できます。 この構成では、ユーザーは、企業ネットワーク内にいる場合にのみ、モバイルデバイスで Lync モバイルアプリケーションを使うことができます。 この構成を定義するには、 <STRONG>Set-CsMcxConfiguration</STRONG>コマンドレットを使います。



</div>

<div>


> [!NOTE]  
> モバイルアプリケーションは、アドレス帳サービスなどの他の Lync Server 2013 サービスに接続することもできますが、内部のモバイルアプリケーション web 要求は、Mobility Service の場合にのみ外部 web FQDN に送信されます。 アドレス帳要求などの他のサービス要求では、この構成は必要ありません。



</div>

モバイルデバイスでは、サービスの手動での検出がサポートしています。 この場合、各ユーザーは、次のように、完全な内部および外部の自動検出サービスの Uri を使用して、モバイルデバイスの設定を構成する必要があります。

  - 外部\<アクセス用の\>Https://extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root

  - 内部\<アクセス用の\>Https://intpoolfqdn/AutoDiscover/AutoDiscover.svc/Root

手動検出ではなく、自動検出を使用することをお勧めします。 ただし、手動の設定は、モバイルデバイスの接続問題のトラブルシューティングに役立ちます。

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Lync Server でのスプリットブレイン DNS の構成

スプリットブレイン dns は、複数の名前によって認識されます。たとえば、分割 DNS や分割ホライズン DNS などです。 単に、同じ名前空間を持ち、1つの DNS ゾーンサービスの内部専用要求と、他の DNS ゾーンサービスの外部専用要求を持つ2つの DNS ゾーンがある DNS 構成について説明します。 ただし、内部 DNS に含まれる DNS SRV と A レコードの多くは、外部 DNS には含まれておらず、逆も同様です。 内部と外部の両方の DNS (たとえば、www.contoso.com) に同じ DNS レコードが存在する場合、返される IP アドレスは、クエリが開始された場所 (内部または外部) によって異なります。

<div>


> [!IMPORTANT]  
> 現時点では、モビリティ、特に LyncDiscover と LyncDiscoverInternal の DNS レコードについては、スプリットブレイン DNS はサポートされていません。 LyncDiscover は外部 DNS サーバーで定義され、LyncDiscoverInternal は内部 DNS サーバーで定義されている必要があります。



</div>

これらのトピックでは、「split ブレインという用語を使用します。

分割ブレイン DNS を構成している場合、次の内部と外部のゾーンには、各ゾーンで必要な DNS レコードの種類の概要が含まれています。 詳細については、「 [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

**内部 DNS:**

  - 権限のある contoso.com という名前の DNS ゾーンが含まれています。

  - 内部 contoso.com ゾーンには、次の内容が含まれます。
    
      - DNS A と AAAA (IPv6 アドレスを使用している場合)、および内部の Lync Server 2013 クライアント用の SRV レコード (オプション)
    
      - Lync Server 2013 Web サービスを自動検出するための DNS A と AAAA (IPv6 アドレスを使用している場合) または CNAME レコード (オプション)
    
      - フロントエンドプール名、監督またはディレクターのプール名、および企業ネットワーク内の Lync Server 2013 を実行しているすべての内部サーバーについて、DNS A および AAAA (IPv6 アドレス指定を使用している場合)
    
      - DNS A and AAAA (IPv6 アドレス指定を使用している場合) 境界ネットワークの各 Lync Server 2013 のエッジサーバーの Edge 内部インターフェイスのレコード
    
      - DNS A and AAAA (IPv6 アドレス指定を使用している場合) 境界ネットワーク内の各リバースプロキシサーバーの内部インターフェイスのレコード (リバースプロキシの場合はオプション)
    
      - すべての Lync Server 2013 Edge Server 境界ネットワーク内の内部境界インターフェイスは、contoso.com へのクエリを解決するために内部 DNS ゾーンを使用します。
    
      - 企業ネットワークの lync 2013 を実行しているすべての2013サーバーは、contoso.com に対してクエリを解決するための内部 DNS サーバー、または各エッジサーバー上の HOSTS ファイルの使用をポイントします (IPv6 アドレス指定を使用している場合)次ホップサーバー、具体的にはディレクターまたはディレクター VIP、フロントエンドプール VIP、または Standard Edition サーバー

**外部 DNS:**

  - 権限のある contoso.com という名前の DNS ゾーンが含まれています。

  - 外部 contoso.com ゾーンには、次の内容が含まれます。
    
      - DNS A と AAAA (IPv6 アドレス指定を使用している場合)、および Lync Server 2013 クライアントの自動構成の SRV レコード (オプション)
    
      - DNS A および AAAA (IPv6 アドレスを使用している場合) または CNAME レコードを使って、モビリティで使用するために Lync Server 2013 Web サービスを自動的に検出する
    
      - 境界ネットワークの各 Lync Server 2013、エッジサーバー、またはハードウェアロードバランサー仮想 IP (VIP) のエッジ外部インターフェイス用の DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード
    
      - DNS A and AAAA (IPv6 アドレス指定を使用している場合)、境界ネットワーク内のリバースプロキシサーバーのプールに対するリバースプロキシサーバーまたは VIP の外部インターフェイスのレコード

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>スプリットブレイン DNS なしの自動構成

内部の DNS ゾーンに\_sipinternaltls が含まれている場合は、スプリットブレイン DNS を使用して、内部でサインインしている Lync Server 2013 ユーザーは自動構成を利用できます。\_使用中の各 SIP ドメインの tcp SRV レコード。 ただし、スプリットブレイン DNS を使っていない場合は、このセクションの後半で説明する回避策のいずれかが実装されていない限り、Lync を実行しているクライアントの内部自動構成は機能しません。 これは、Lync Server 2013 では、自動構成用に指定されたフロントエンドプールのドメインと一致するようにユーザーの SIP URI が必要であるためです。 これは、以前のバージョンの Communicator の場合にも当てはまります。

たとえば、2つの SIP ドメインが使用されている場合、次の DNS サービス (SRV) レコードが必要になります。

  - ユーザーが bob@contoso.com としてサインインした場合、ユーザーの SIP ドメイン (contoso.com) が自動構成のフロントエンドプールのドメインと一致するため、次の SRV レコードが自動構成で動作します。
    
     \_sipinternaltls.\_tcp.contoso.com。 86400 IN SRV 0 0 5061 pool01.contoso.com

  - ユーザーが alice@fabrikam.com としてサインインした場合、次の DNS SRV レコードは、2つ目の SIP ドメインの自動構成に使用できます。
    
     \_sipinternaltls.\_tcp.fabrikam.com。 86400 IN SRV 0 0 5061 pool01.fabrikam.com

比較のために、ユーザーが tim@litwareinc.com としてサインインした場合、次の DNS SRV レコードは、プールが存在するドメイン (fabrikam.com) と一致しないため、自動構成では動作しません。

 \_sipinternaltls.\_tcp.litwareinc.com。 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Lync を実行しているクライアントで自動構成が必要な場合は、次のいずれかのオプションを選択します。

  - **グループポリシー**   オブジェクトでは、グループポリシーオブジェクト (gpo) を使って正しいサーバー値を入力します。
    
    <div>
    

    > [!NOTE]  
    > このオプションでは、自動構成は有効ではありませんが、手動構成のプロセスを自動化するため、この方法を使う場合、自動構成に関連付けられている SRV レコードは必要ありません。

    
    </div>

  - **一致する内部ゾーン**   外部 dns ゾーンと一致する内部 dns (contoso.com など) に、自動構成で使用される Lync Server 2013 プールに対応する dns a および AAAA を作成します (IPv6 アドレス指定を使用している場合)。 たとえば、ユーザーが pool01.contoso.net をホームにしていて、bob@contoso.com として Lync にサインインしている場合は、pool01.contoso.com の DNS A と AAAA (IPv6 アドレスが使用される場合) レコードを作成します。

  - **ピンポイント内部ゾーン**   内部 DNS でゾーン全体を作成する場合は、自動構成に必要な SRV レコードに対応するピンポイント (専用) ゾーンを作成して、それらのゾーンについては、「nuget.exe」を使用して設定できます。 DNS ユーザーインターフェイスでは、ピンポイントゾーンの作成がサポートされていないため、Dnscmd が必要です。 たとえば、SIP ドメインが contoso.com で、2つのフロントエンドサーバーを含む pool01 というフロントエンドプールがある場合、次のピンポイントゾーンと内部 DNS 内のレコードが必要です。
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    環境に2つ目の SIP ドメイン (たとえば、fabrikam.com) が含まれている場合は、次のピンポイントゾーンと内部 DNS 内のレコードが必要です。
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> フロントエンドプールの FQDN は2回表示されますが、2つの異なる IP アドレスがあります。 これは、DNS の負荷分散が使用されるためですが、ハードウェアの負荷分散が使用されている場合は、1つのフロントエンドプールエントリしかありません。 また、contoso.com の例と fabrikam.com の例では、フロントエンドプールの FQDN 値が変更されますが、IP アドレスは変わりません。 これは、ユーザーがいずれかの SIP ドメインからサインインしているため、自動構成で同じフロントエンドプールを使用しているためです。



</div>

詳細については、DMTF のブログ記事「Communicator の自動構成とスプリットブレイン DNS (英語[http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707))」を参照してください。

<div>


> [!NOTE]  
> 各ブログの内容と URL は、将来予告なしに変更されることがあります。



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>障害回復のためにドメインネームシステム (DNS) を構成する

Lync Server 2013 Web トラフィックを災害回復とフェールオーバーサイトにリダイレクトするように DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用している必要があります。 Web 用の DNS レコードを設定して、フロントエンドプール全体が停止している場合でも、Web サービスを使う機能が継続されるようにすることができます。 この障害回復機能は、自動検出 (Lyncdiscover URL)、会議、ダイヤルインの単純な Url をサポートしています。

GeoDNS プロバイダーの Web サービスの内部および外部の解決に、追加の DNS ホスト (IPv6 を使用する場合は A と AAAA) レコードを定義して構成します。 次の情報は、ラウンドロビン DNS を使用してプロバイダーがサポートしているペアリングプール、地理的に分散した GeoDNS、または Pool1 をプライマリとして使用するように構成されている場合、または通信の損失またはハードウェアの障害が発生した場合に、Pool2 にフェールオーバーすることを前提とします。


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
<th>DNS 設定 (オプションを 1 つ選択する)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Meet.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Meet.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Meet.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Meet.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Dialin.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Dialin.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Dialin.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Dialin.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Lyncdiscoverinternal.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Lyncdiscoverinternal.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Lyncdiscover.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Lyncdiscover.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Scheduler.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Scheduler.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Scheduler.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Scheduler.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害が発生した場合はセカンダリに接続する</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS Load Balancing

DNS の負荷分散は、通常、アプリケーションレベルで実装されます。 アプリケーション (たとえば、Lync を実行しているクライアント) は、プールの完全修飾ドメイン名 (FQDN) に対する DNS A と AAAA (IPv6 アドレスが使用されている場合) から返される IP アドレスのいずれかに接続して、プール内のサーバーに接続しようとします。

たとえば、pool01.contoso.com という名前のプールに3台のフロントエンドサーバーがある場合は、次のような処理が行われます。

  - Lync を実行しているクライアントは、pool01.contoso.com に対して DNS を照会します。 このクエリでは、3つの IP アドレスが返され、次のようにキャッシュされます (この順序で行う必要はありません)。
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - クライアントは、いずれかの IP アドレスへの伝送制御プロトコル (TCP) 接続を確立しようとします。 この問題が発生した場合、クライアントはキャッシュ内の次の IP アドレスを試します。

  - TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com のプライマリ レジストラーに接続します。

  - クライアントがすべてのキャッシュエントリを正常に接続していない場合、ユーザーには Lync Server 2013 を実行しているサーバーが現時点で利用できないことが通知されます。

<div>


> [!NOTE]  
> DNS ベースの負荷分散は、通常は dns に依存して、プール内のサーバーに対応する異なる順序の IP アドレスを提供することによって、負荷分散を意味します。 通常、DNS RR では、読み込みの配布のみが可能ですが、フェールオーバーは有効になりません。 たとえば、DNS A と AAAA によって返される1つの IP アドレスへの接続 (IPv6 アドレスを使っている場合) クエリが失敗すると、接続は失敗します。 したがって、DNS によるラウンドロビンは、DNS ベースの負荷分散よりも信頼性が低くなります。 Dns ラウンドロビンと DNS の負荷分散を併用できます。



</div>

DNS の負荷分散は、次の場合に使用されます。

  - エッジサーバーへのサーバー間 SIP の負荷分散

  - 会議の自動応答、返信グループ、コールパークなどの統合コミュニケーションアプリケーションサービス (UCAS) アプリケーションのロードバランシング

  - アプリケーション ("ドレイン" とも呼ばれます) としての新しい接続の無効化

  - クライアントとエッジサーバー間のすべてのクライアント間トラフィックの負荷分散

DNS の負荷分散は、次の用途では使用できません。

  - ディレクターまたはフロントエンドサーバーへのクライアント対サーバー web トラフィック

DNS の負荷分散とフェデレーショントラフィック:

DNS SRV クエリによって複数の DNS レコードが返される場合、アクセスエッジサービスは常に、最も低い数値の優先度と最大の数値の重みで DNS SRV レコードを選びます。 インターネットエンジニアリングタスクは、"サービスの場所を指定するための DNS RR" を強制します<http://www.ietf.org/rfc/rfc2782.txt> 。複数の DNS SRV レコードが定義されている場合は、priority が最初に使用され、次に重みが使われることを指定します。 たとえば、DNS SRV レコード A の配点は20で、優先度は40で、DNS SRV レコード B の重みは10で、もう1つは50の優先順位です。 優先順位40の DNS SRV レコード A が選択されます。 DNS SRV レコードの選択には、次のルールが適用されます。

  - 優先度は最初に考慮されます。 クライアントは、DNS SRV レコードによって定義されたターゲットホストに連絡して、到達可能な最も低い優先順位を持つ必要があります。 同じ優先順位のターゲットは、[加重] フィールドで定義された順序で試す必要があります。

  - [加重] フィールドでは、同じ優先度のエントリの相対的な重みを指定します。 重みを大きくすると、より高い確率で選択されます。 サーバーが選択されていない場合、DNS 管理者はウエイト0を使用する必要があります。 加重値が0より大きいレコードが存在する場合、重み付けが0のレコードは、非常に少ない確率で選択される可能性があります。

優先度が同じ複数の DNS SRV レコードが返される場合、アクセスエッジサービスによって、DNS サーバーから最初に受信された SRV レコードが選択されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

