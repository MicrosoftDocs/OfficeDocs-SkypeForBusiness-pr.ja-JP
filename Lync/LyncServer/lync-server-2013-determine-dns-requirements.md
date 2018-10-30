---
title: 'Lync Server 2013: DNS の要件を確認する'
TOCTitle: DNS の要件を確認する
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48272899
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の DNS の要件を確認する

 

_**トピックの最終更新日:** 2016-12-08_

次のフロー チャートを使用してドメイン ネーム システム (DNS) の要件を判断します。Lync Server 2013 の累積した更新プログラム: 2013 年 2 月での変更は、適宜、示しています。


> [!IMPORTANT]
> Microsoft Lync Server 2013 は IPv6 アドレスの使用をサポートしています。IPv6 アドレスを使用するには、IPv6 DNS のサポートも提供し、DNS ホスト AAAA (「クアッド A」として知られる) レコードを構成する必要があります。IPv4 と IPv6 の両方を使用する展開では、IPv4 のホスト A レコードおよび IPv6 のホスト AAAA の両方を維持するのが最善です。展開が完全に IPv6 に移行した場合でも、外部ユーザーが依然として IPv4 を使用しているときには IPv4 DNS ホスト レコードが必要になることもあります。



**DNS 要件の判断フロー チャート**

![DNS 要件のフロー チャート](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "DNS 要件のフロー チャート")


> [!IMPORTANT]
> 既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく、ホスト名です。 トポロジ ビルダーは、ホスト名ではなく、FQDN を使用します。そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、 <STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。Unicode 文字およびアンダースコアは使用しないでください。一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。詳細については、「<A href="lync-server-2013-configure-dns-host-records.md">Lync Server 2013 での DNS ホスト レコードの構成</A>」を参照してください。



## Lync クライアントがサービスを見つける方法

Microsoft Lync 2010、 Lync 2013、および Lync Mobile では、似た方法で、クライアントが Lync Server 2013 内のサービスを見つけてアクセスします。顕著な例外は、別のサービス特定プロセスを使用する Lync Windows ストア アプリです。このセクションは、クライアントがサービスを見つける方法の、2 つのシナリオについて詳しく説明します。まず一連の SRV と A ホスト レコードを使用する従来の方法、次に、自動検出サービス レコードのみを使用する方法を説明します。デスクトップ クライアントへの累積した更新プログラムにより、 Lync Server 2010 から DNS 特定プロセスが変更されています。すべてのクライアントで、正常なクエリが返されるまで、または、可能な DNS レコードのリストを調べ尽くして、最終的なエラーがクライアントに返されるまで、DNS クエリ プロセスが継続されます。

Lync Windows ストア アプリを **除く**すべてのクライアント。DNS 参照中に、SRV レコードのクエリは実行され、次の順序でクライアントに返されます。

1.  lyncdiscoverinternal.*\<domain\>*   内部 Web サービス上の自動検出サービスの (ホスト) レコード

2.  lyncdiscover.*\<domain\>*      外部 Web サービス上の自動検出サービスの (ホスト) レコード

3.  \_sipinternaltls.\_tcp.*\<domain\>*   内部 TLS 接続用の SRV (サービス ロケーター) レコード

4.  \_sipinternal.\_tcp.*\<domain\>*   内部 TCP 接続用の SRV (サービス ロケーター) レコード (TCP が許可されている場合のみ実行)

5.  \_sip.\_tls.*\<domain\>*   外部 TLS 接続用の SRV (サービス ロケーター) レコード

6.  sipinternal.*\<domain\>*   フロント エンド プールまたは ディレクターの (ホスト) レコード、内部ネットワークでのみ解決可能

7.  sip.*\<domain\>*   内部ネットワークで、フロント エンド プールまたはディレクター、あるいはクライアントが外部のとき アクセス エッジ サービスの (ホスト) レコード

8.  sipexternal.*\<domain\>*   クライアントが外部のとき アクセス エッジ サービスの (ホスト) レコード

Lync Windows ストア アプリは 2 つのレコードを使用するため、完全に過程が異なります。

1.  lyncdiscoverinternal.*\<domain\>*   内部 Web サービス上の自動検出サービスの (ホスト) レコード

2.  lyncdiscover.*\<domain\>*   外部 Web サービス上の自動検出サービスの (ホスト) レコード

その他のレコード種類へのフォールバックはありません。

以前のクライアントと比較して、新しいクライアントで使用される方法の違いは、自動検出サービスがすべてのサービスを見つける推奨の方法になっているということです。

接続に成功すると、自動検出サービスは、Mobility Service (IIS 内のサービス用に作成された仮想ディレクトリでは Mcx として認識されます)、 Microsoft Lync Web App、および Web スケジューラの URL を含め、ユーザーのホーム プール用のすべての Web サービス URL を返します。ただし、Mobility Service の内部 URL と Mobility Service の外部 URL は共に Web サービスの外部 FQDN に関連付けられます。したがって、モバイル デバイスがネットワークの内部または外部のどちらにあるかどうかに関係なく、デバイスは、常に、リバース プロキシ経由で Mobility Service に外部から接続します。

Lync Server 2013 の累積した更新プログラム: 2013 年 2 月が既にインストールされている場合、自動検出サービスは、内部/UCWA、外部/UCWA、および UCWA への参照も返します。これらの項目は、統合コミュニケーション Web API (UCWA) Web コンポーネントを参照します。現在、UCWA 項目のみが使用され、Web コンポーネントの URL への参照を示します。UCWA は、 Lync 2010 Mobile クライアントによって使用される Mcx Mobility Service ではなく、 Lync 2013 モバイル クライアントによって使用されます。

> [!NOTE]
> SRV レコードを作成する場合は、DNS SRV レコードが作成されている同じドメインの DNS A および AAAA (IPv6 アドレスを使用している場合) レコードを指す必要があります。たとえば、SRV レコードが contoso.com にある場合、A および AAAA (IPv6 アドレスを使用している場合) レコードが指す先は fabrikam.com 以外である必要があります。



> [!TIP]
> 既定の構成では、すべてのモバイル クライアントのトラフィックは外部サイトを通過するように設定されます。要件の必要性に応じて、設定を変更し内部 URL のみを返すようにできます。この構成では、ユーザーは、企業ネットワークの内側にいる場合にのみ、モバイル デバイスで Lync モバイル アプリケーションを使用できます。この構成を定義するには、 <STRONG>Set-CsMcxConfiguration</STRONG> コマンドレットを実行します。



> [!NOTE]
> モバイル アプリケーションは、他の Lync Server 2013 サービス (アドレス帳サービスなど) にも接続できますが、Mobility Service に対する内部のモバイル アプリケーション Web 要求に限っては、外部 Web FQDN に送信されます。他のサービス要求 (アドレス帳要求など) では、この構成は必要ありません。


モバイル デバイスでは、サービスの手動検出もサポートされます。この場合、次のように、プロトコルおよびパスを含む、自動検出サービスの完全な内部 URL および外部 URL を使用して、各ユーザーがモバイル デバイスの設定を構成する必要があります。

  - https:// *\<ExtPoolFQDN\>* /Autodiscover/autodiscoverservice.svc/Root for external access

  - https:// *\<IntPoolFQDN\>* /AutoDiscover/AutoDiscover.svc/Root for internal access

手動検出ではなく自動検出を使用することをお勧めします。ただし、モバイル デバイスの接続の問題についてトラブルシューティングを行うには、手動設定の使用が役に立ちます。

## Lync Server によるスプリットブレイン DNS の構成

スプリットブレイン DNS は、スプリット DNS または水平分割 DNS などと呼ばれることがあります。簡単に説明すると、スプリットブレイン DNS とは、2 つの DNS ゾーンが同じ名前空間に存在する DNS 構成です (一方の DNS ゾーンは内部要求のみ、他方の DNS ゾーンは外部要求のみを処理します)。ただし、内部 DNS に含まれる DNS SRV および A レコードの多くは、外部 DNS には含まれず、逆の場合も同様です。内部 DNS と外部 DNS の両方に同じ DNS レコードが存在する場合 (www.contoso.com など)、返される IP アドレスは、クエリが開始された場所によって異なります。


> [!IMPORTANT]
> 現時点では、モビリティ、具体的には LyncDiscover および LyncDiscoverInternal DNS レコードでは、スプリットブレイン DNS がサポートされていません。LyncDiscover は外部 DNS サーバーで定義し、LyncDiscoverInternal は内部 DNS サーバーで定義する必要があります。



これらのトピックでは、スプリットブレイン DNS という用語を使用します。

スプリットブレイン DNS を構成する場合、次の内部ゾーンと外部ゾーンには、各ゾーンで必要な DNS レコードの種類の概要が含まれます。詳細については、「[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

**内部 DNS**

  - contoso.com という信頼できる DNS ゾーンを含みます。

  - 内部の contoso.com ゾーンの内容
    
      - 内部 Lync Server 2013 クライアントの自動構成用の DNS A および AAAA (IPv6 アドレスを使用している場合) レコードと SRV レコード (オプション)。
    
      - Lync Server 2013 Web サービスの自動検出用の DNS A および AAAA (IPv6 アドレスを使用している場合) レコードまたは CNAME レコード (オプション)。
    
      - フロントエンド プール名、ディレクター、ディレクター プール名、および企業ネットワーク内で Lync Server 2013 を実行するすべての内部サーバーの DNS A および AAAA (IPv6 アドレスを使用している場合) レコード。
    
      - 境界ネットワークの各 Lync Server 2013 エッジ サーバーのエッジ内部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) レコード。
    
      - 境界ネットワークの各リバース プロキシ サーバーの内部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) レコード (リバース プロキシの管理の場合はオプション)。
    
      - 境界ネットワークのすべての Lync Server 2013エッジ サーバーの内部エッジ インターフェイスは、内部 DNS ゾーンを使用して contoso.com のクエリを解決します。
    
      - 企業ネットワーク内の、 Lync Server 2013 を実行するサーバーと Lync 2013 を実行するクライアントはすべて、contoso.com へのクエリを解決するために内部 DNS サーバーを参照するか、各エッジ サーバーの HOSTS ファイルを使用して、次ホップ サーバーの A レコードを、特にディレクターまたはディレクターの VIP、フロントエンド プールの VIP、または Standard Edition サーバーの A および AAAA (IPv6 アドレスを使用している場合) レコードをリストします。

**外部 DNS**

  - contoso.com という信頼できる DNS ゾーンを含みます。

  - 外部の contoso.com ゾーンの内容
    
      - Lync Server 2013 クライアントの自動構成用の DNS A および AAAA (IPv6 アドレスを使用している場合) レコードと SRV レコード (オプション)
    
      - モビリティで使用する Lync Server 2013 Web サービスの自動検出用の DNS A および AAAA (IPv6 アドレスを使用している場合) レコードまたは CNAME レコード。
    
      - 各 Lync Server 2013 エッジ サーバーのエッジ外部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) レコードと SRV レコード、または境界ネットワーク内のロード バランサー機器の仮想 IP (VIP)。
    
      - リバース プロキシ サーバーの外部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) レコード、または境界ネットワークのリバース プロキシ サーバーの VIP。

## スプリットブレイン DNS なしの自動構成

スプリットブレイン DNS を使用する場合、使用されている各 SIP ドメインの \_sipinternaltls.\_tcp SRV レコードが内部 DNS ゾーンに含められていれば、内部からサインインする Lync Server 2013 ユーザーは自動構成を利用できます。ただし、スプリットブレイン DNS を使用しない場合、後ほど説明する解決法の 1 つを実装しない限り、 Lync を実行するクライアントの内部での自動構成は機能しません。 Lync Server 2013 では、ユーザーの SIP URI が、自動構成用に指定されたフロントエンド プールのドメインと一致する必要があるためです。これは、 Communicator の旧バージョンの場合でも同様です。

たとえば、使用されている SIP ドメインが 2 つある場合、次の DNS サービス (SRV) レコードが必要です。

  - ユーザーが bob@contoso.com としてサインインした場合、次の SRV レコードは、ユーザーの SIP ドメイン (contoso.com) が自動構成用に指定されたフロントエンド プールのドメインと一致するため、自動構成が機能します。
    
     \_sipinternaltls.\_tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - ユーザーが alice@fabrikam.com としてサインインした場合、次の SRV レコードは、2 つ目の SIP ドメインの自動構成について機能します。
    
     \_sipinternaltls.\_tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

これに対して、ユーザーが tim@litwareinc.com としてサインインした場合、次の SRV レコードは、クライアントの SIP ドメイン (litwareinc.com) がプールのドメイン (fabrikam.com) と一致しないため、自動構成が機能しません。

 \_sipinternaltls.\_tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Lync を実行するクライアントについて自動構成が必要な場合は、次のオプションのいずれかを選択します。

  - **グループ ポリシー オブジェクト**   グループ ポリシー オブジェクト (GPO) を使用して、適切なサーバーの値を設定します。
    
    > [!NOTE]
    > このオプションは自動構成を有効にしませんが、手動構成のプロセスを自動化するので、この方法を使用した場合、自動構成に関連付ける SRV レコードは必要ありません。


  - **内部ゾーンの一致**   外部 DNS ゾーン (contoso.com など) と一致するゾーンを内部 DNS に作成し、自動構成に使用する Lync Server 2013 のプールに対応する DNS A および AAAA (IPv6 アドレスを使用している場合) レコードを作成します。たとえば、pool01.contoso.net に所属するユーザーが Lync に bob@contoso.com としてサインインする場合、contoso.com という内部 DNS ゾーンを作成し、その中に pool01.contoso.com の DNS A および AAAA (IPv6 アドレスを使用している場合) レコードを作成します。

  - **ピンポイントの内部ゾーン**   内部 DNS にゾーン全体を作成することができない場合は、自動構成に必要な SRV レコードに対応するピンポイント (つまり専用) のゾーンを作成し、dnscmd.exe を使用してこれらのゾーンを設定できます。dnscmd.exe が必要なのは、DNS のユーザー インターフェイスでは、ピンポイントのゾーン作成がサポートされていないからです。たとえば、SIP ドメインが contoso.com で、2 つのフロントエンド サーバーが含まれる pool01 というフロントエンド プールがある場合、次のピンポイントのゾーンと A レコードが内部 DNS に必要です。
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    現在の環境に 2 つ目の SIP ドメイン (fabrikam.com など) がある場合は、次のピンポイントのゾーンと A レコードが内部 DNS に必要です。
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

> [!NOTE]
> フロントエンド プールの FQDN は 2 つ表示されますが、これには 2 つの異なる IP アドレスが対応しています。これは DNS 負荷分散が使用されているためですが、ハードウェア ロード バランサーが使用される場合は、フロントエンド プールのエントリが 1 つのみになります。また、フロントエンド プールの FQDN 値は contoso.com の例と fabrikam.com の例で異なりますが、IP アドレスは同じです。これは、いずれの SIP ドメインからサインインするユーザーも、自動構成に同じフロントエンド プールを使用するためです。


詳細については、DMTF のブログ記事「Communicator Automatic Configuration and Split-Brain DNS」( <http://go.microsoft.com/fwlink/?linkid=200707>) を参照してください。

> [!NOTE]
> 各ブログの内容と URL は、将来予告なしに変更されることがあります。


## 障害復旧のためのドメイン ネーム システム (DNS) の構成

Lync Server 2013 の Web トラフィックを障害復旧およびフェールオーバーのサイトにリダイレクトするように DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用する必要があります。障害復旧をサポートする Web 用の DNS レコードをセットアップできるので、 フロント エンド プール全体がダウンした場合でも、Web サービスを使用する機能を引き続き利用できます。この障害復旧機能では、自動検出 (Lyncdiscover URL)、会議、およびダイヤルインの簡易 URL をサポートします。

GeoDNS プロバイダーにおける Web サービスの内部および外部の解決のために、追加の DNS ホスト (A、IPv6 を使用する場合は AAAA) レコードを定義および構成します。以下の詳細情報は、プールがペアになっていて、地理的に離れており、(通信が失われたり、ハードウェア障害が発生した場合に備えて、ラウンド ロビン DNS に対応している、または Pool1 をプライマリとして使用し、Pool2 にフェールオーバーするように構成している) プロバイダーで GeoDNS がサポートされていることを前提としています。


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
<th>プール レコード (例)</th>
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
<p>プライマリを使用し、障害時はセカンダリに接続</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Meet.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Meet.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害時はセカンダリに接続</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Dialin.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Dialin.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害時はセカンダリに接続</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Dialin.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Dialin.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害時はセカンダリに接続</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Lyncdiscoverinternal.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Lyncdiscoverinternal.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害時はセカンダリに接続</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Lyncdiscover.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Lyncdiscover.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害時はセカンダリに接続</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Scheduler.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Scheduler.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害時はセカンダリに接続</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>エイリアス Scheduler.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</p>
<p>エイリアス Scheduler.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</p></td>
<td><p>プール間のラウンド ロビン</p>
<p>プライマリを使用し、障害時はセカンダリに接続</p></td>
</tr>
</tbody>
</table>


## DNS 負荷分散

DNS 負荷分散は一般的に、アプリケーション レベルで実装されます。アプリケーション ( Lync を実行するクライアントなど) は、プールの完全修飾ドメイン名 (FQDN) に対する DNS A および AAAA (IPv6 アドレスを使用している場合) レコード クエリから返される IP アドレスの 1 つに接続することで、プール内のサーバーへの接続を試みます。

たとえば、pool01.contoso.com という名前のプールに 3 つのフロントエンド サーバーがある場合、次のようになります。

  - Lync を実行するクライアントは DNS に対して pool01.contoso.com についてクエリを実行します。このクエリは 3 つの IP アドレスを返し、それらを次のようにキャッシュに格納します (この順序になるとは限りません)。
    
    pool01.contoso.com      192.168.10.90
    
    pool01.contoso.com      192.168.10.91
    
    pool01.contoso.com      192.168.10.92

  - 次に、クライアントは IP アドレスの 1 つに対して伝送制御プロトコル (TCP) 接続を確立しようとします。それが失敗した場合は、キャッシュ内の次の IP アドレスで試します。

  - TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com のプライマリ レジストラーに接続します。

  - クライアントが正常な接続を確立できないまま、キャッシュされているすべての項目を試行すると、その時点で利用できる Lync Server 2013 を実行しているサーバーがないことがユーザーに通知されます。

> [!NOTE]
> DNS ベースの負荷分散は、一般的に、DNS を利用してプール内のサーバーに対応する IP アドレスを別の順序で提供させて負荷分散を行うことを指す DNS ラウンド ロビン (DNS RR) と異なります。一般的に、DNS RR は負荷分散のみが可能で、フェールオーバー機能は提供されません。たとえば、DNS A および AAAA (IPv6 アドレスを使用している場合) クエリで返された 1 つの IP アドレスに対する接続が失敗した場合、その接続は失敗します。したがって、DNS ラウンド ロビン自体は DNS ベースの負荷分散より信頼性が劣ります。DNS ラウンド ロビンは、DNS 負荷分散と共に使用することができます。


DNS 負荷分散は次のような状況で使用されます。

  - サーバー間の SIP からエッジ サーバーへの負荷分散

  - 会議自動アテンダント、応答グループ、コール パークなどの統合コミュニケーション アプリケーション サービス (UCAS) アプリケーションの負荷分散

  - UCAS アプリケーションへの新規接続 (別名 "ドレイン") の禁止

  - クライアントとエッジ サーバー間における、クライアントとサーバー間のすべてのトラフィックのロード バランシング

DNS 負荷分散は次のような状況では使用できません。

  - ディレクターまたはフロントエンド サーバーへのクライアントとサーバー間の Web トラフィック

DNS 負荷分散とフェデレーション トラフィック

DNS SRV クエリで複数の DNS レコードが返された場合、アクセス エッジ サービスは、優先度の数値が最も小さく、重みの数値が最も大きい DNS SRV レコードを選択します。インターネット技術標準化委員会ドキュメント "A DNS RR for specifying the location of services (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> は、複数の DNS SRV レコードが定義されている場合、優先度がまず使用され、次に重み付けに基づくことを指定しています。たとえば、DNS SRV レコード A が重み付け 20 と優先度 40 を持っており、DNS SRV レコード B が重み付け 10 と優先度 50 を持っているとします。この場合、優先度 40 を持つ DNS SRV レコード A が選択されます。DNS SRV レコード選択では以下のルールが適用されます。

  - 最初に優先度が検討されます。クライアントは、それが到達することができる、最も数値の小さい優先度を持つ DNS SRV レコードによって定義されたターゲットホストに通信しなくてはなりません。同じ優先度を持つターゲットには、重み付けフィールドによって定義された順序で接続が試みられる必要があります。

  - 重み付けフィールドは、同じ優先度の項目に対する相対的な重み付けを指定します。選択される可能性に比例して、より大きな重み付けを与える必要があります。サーバー選択が行われないとき、DNS 管理者は重み付け 0 を使用する必要があります。0 より大きい重み付けを持つレコードが存在するとき、重み付け 0 のレコードが選択される可能性は非常に小さくなります。

同じ優先度と重みを持つ複数の DNS SRV レコードが返された場合、アクセス エッジ サービスは、DNS サーバーから最初に受け取った SRV レコードを選択します。

