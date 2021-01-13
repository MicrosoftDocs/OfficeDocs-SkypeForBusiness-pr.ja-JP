---
title: Skype for Business Server の高度なエッジ サーバー DNS の計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '概要: Skype for Business Server 展開オプションのシナリオを確認します。 単一サーバーを使用する場合も、DNS または HLB を使用するサーバー プールを使用する場合も、このトピックで説明します。'
ms.openlocfilehash: 5a41baac30f3bf6a1e20ae34db009dae0cec40af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825327"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Skype for Business Server の高度なエッジ サーバー DNS の計画
 
**概要:** Skype for Business Server 展開オプションのシナリオを確認します。 単一サーバーを使用する場合でも、DNS または HLB を使用するサーバー プールを使用する場合でも、このトピックは役立ちます。
  
Skype for Business Server のドメイン ネーム システム (DNS) の計画に関しては、決定に影響を与える可能性がある多くの要因があります。 組織のドメイン構造が既に設定されている場合は、手順を確認する必要があります。 まず、以下のトピックを参照してください。
  
- [Skype for Business クライアント検索サービスのチュートリアル](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [スプリットブレイン DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [スプリットブレイン DNS を使用しない自動構成](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS 障害復旧](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS 負荷分散](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Skype for Business クライアント検索サービスのチュートリアル
<a name="WalkthroughOfSkype"> </a>

Skype for Business クライアントは、Skype for Business Server でサービスを検索してアクセスする方法について、以前のバージョンの Lync クライアントに似ています。 このセクションでは、サーバーの場所の処理について詳しい説明を示します。
  
1. lyncdiscoverinternal。\<domain\>
    
     *これは、内部 Web サービス上の自動検出サービスの A ホスト レコードです。* 
    
2. lyncdiscover。\<domain\>
    
     *これは、外部 Web サービス上の自動検出サービスのホスト レコードです。* 
    
3. _sipinternaltls._tcp。\<domain\>
    
     *これは、内部 TLS 接続の SRV レコードです。* 
    
4. _sip._tls。\<domain\>
    
     *これは、外部 TLS 接続の SRV レコードです。* 
    
5. sipinternal。\<domain\>
    
     *これはフロント エンド プールまたはディレクターの A ホスト レコードで、内部ネットワーク上でのみ解決できます。* 
    
6. sip.\<domain\>
    
     *これはフロント エンド プールまたはディレクターの A ホスト レコードで、内部ネットワーク上でのみ解決できます。* 
    
7. sipexternal。\<domain\>
    
     *クライアントが外部の場合、これはアクセス エッジ サービスの A ホスト レコードです。* 
    
自動検出サービスは常に優先され、サービスの場所の推奨される方法であり、他の方法はフォールバック方法です。
  
> [!NOTE]
> SRV レコードを作成する場合、DNS SRV レコードが作成されているのと同じドメイン内の DNS A (および IPv6 アドレスを使用している場合は AAAA) をポイントする必要がある点に注意してください。 たとえば、SRV レコードが contoso.com にある場合、そのレコードがポイントしている A (および AAAA) レコードは、fabrikam.com。 
  
これを行う必要がある場合は、サービスを手動で検出するためにモバイル デバイスを設定できます。 これが必要な場合、各ユーザーは、プロトコルとパスを含む、内部および外部の完全な自動検出サービス URI を使用して、次のようにモバイル デバイス設定を構成する必要があります。
  
- 外部アクセスの場合: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- 内部アクセスの場合: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
手動検出ではなく、自動検出を使用することをお勧めします。 ただし、トラブルシューティングやテストを行う場合は、手動設定が非常に役立ちます。
  
## <a name="split-brain-dns"></a>スプリットブレイン DNS
<a name="SplitBrainDNS"> </a>

これは、同じ名前空間を持つ 2 つの DNS ゾーンがある DNS 構成です。 最初の DNS ゾーンは内部要求を処理し、2 番目の DNS ゾーンは外部要求を処理します。
  
企業がこれを行う理由 内部と外部で同じ名前空間を使用する必要がある場合がありますが、もちろん、これにより、多くの DNS SRV レコードと A レコードが 1 つのゾーンまたは別のゾーンに固有のものになります。重複がある場合、これらのレコードに関連付けられた IP アドレスは一意になります。
  
これはいくつかの課題を示しています。 最も重要なのは、スプリットブレイン DNS が Mobility **でサポートされていない** 点です。 これは、LyncDiscover と LyncDiscoverInternal DNS レコード (LyncDiscover は外部 DNS サーバーで定義する必要があるのに対し、LyncDiscoverInternal は内部 DNS サーバーで定義する必要がある) ためです。
  
ここでは、内部ゾーンと外部ゾーンの DNS レコードを一覧表示しますが、詳細な例については、「エッジ サーバーの環境要件」セクションを参照してください。
  
### <a name="internal-dns"></a>内部 DNS

- 権限がある (たとえば) contoso.com DNS ゾーンが含まれている。
    
- この内部contoso.com次の情報が含まれる。
    
  - フロント エンド プール、ディレクター プールまたはディレクター プール名、および組織のネットワーク内で Skype for Business Server を実行しているすべての内部サーバーの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード。
    
  - 境界ネットワーク内の各 Skype for Business Server エッジ サーバーのエッジ内部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード。
    
  - 境界ネットワーク内の各リバース プロキシ サーバーの内部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード (リバース プロキシの管理にはオプション)。
    
  - 内部 Skype for Business Server クライアントの自動構成用の DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード **(オプション)。**
    
  - DNS A および AAAA (IPv6 アドレス指定を使用している場合) または CNAME レコードを使用して、Skype for Business Server Web サービスの自動検出を行います (**オプション)。**
    
- 境界ネットワーク内のすべての Skype for Business Server 内部エッジ インターフェイスは、この内部 DNS ゾーンを使用してクエリを解決contoso.com。
    
- Skype for Business Server を実行しているすべてのサーバー、および企業ネットワークで Skype for Business Server を実行しているクライアントは、contoso.com へのクエリを解決するために内部 DNS サーバーをポイントするか、各エッジ サーバーのホスト ファイルを使用して次ホップ サーバー (特にディレクターまたはディレクター プールの VIP 用) の A および AAAA (IPv6 アドレス指定を使用している場合) レコードを一覧表示します。、フロントエンド プールの VIP、または Standard Edition サーバー)。
    
### <a name="external-dns"></a>外部 DNS

- 権限がある (たとえば) contoso.com DNS ゾーンが含まれている。
    
- この外部contoso.com次の情報が含まれる。
    
  - Skype for Business Server Web サービスの自動検出用の DNS A および AAAA (IPv6 アドレス指定を使用している場合)、または CNAME レコード。 これはモビリティで使用するために使用されます。
    
  - 境界ネットワーク内の各 Skype for Business Server エッジ サーバーまたはハードウェア負荷分散 (HLB) VIP のエッジ外部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード。
    
  - 境界ネットワーク内のリバース プロキシ サーバーの外部インターフェイスまたは (リバース プロキシ サーバーのプールの VIP) の DNS A および AAAA (IPv6 アドレスを使用している場合) および SRV レコード。
    
  - Skype for Business Server クライアントの自動構成の DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード ( **オプション** )。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>スプリットブレイン DNS を使用しない自動構成
<a name="NoSplitBrainDNS"> </a>

スプリットブレイン DNS を使用しない場合は、ここに示す回避策のいずれかを使用しない限り、Skype for Business を実行しているクライアントの内部自動構成は機能しません。 どうしてでしょうか? Skype for Business Server では、自動構成用に指定されたフロントエンド プールのドメインと一致するユーザーの SIP URI が必要です。 これは、以前のバージョンの Lync Server から変更されていない。
  
したがって、2 つの SIP ドメインが使用されている場合は、次の DNS SRV レコードが必要です。
  
- _sipinternaltls._tcp.contoso.com。 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *ユーザーが bob@contoso.com としてサインインした場合、ユーザーの SIP ドメインがフロントエンド プール (contoso.com) のドメインと一致する場合、このレコードは自動構成で機能します。* 
    
- _sipinternaltls._tcp.fabrikam.com。 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *ユーザーが alice@fabrikam.com としてサインインすると、SIP ドメインがドメインのフロント エンド プールと一致する場合も、このレコードは 2 番目のドメインの自動構成で機能します。* 
    
この例をさらに詳しくは、次の方法では動作しません。
  
- _sipinternaltls._tcp.litwareinc.com。 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *SIP ドメイン litwareinc.com (tim@litwareinc.com) がプール内のドメイン (fabrikam.com) と一致しないので、ユーザーが tim@litwareinc.com としてサインインしても自動構成は機能しません。* 
    
これで、スプリットブレイン DNS を使用しない Skype for Business クライアントの自動要件が必要な場合は、次のオプションを使用できます。
  
- **グループ ポリシー オブジェクト**
    
    グループ ポリシー オブジェクト (GPO) を使用して、正しいサーバー値を設定できます。
    
    > [!NOTE]
    > このオプションは自動構成を有効にしないが、手動構成を自動化する。 この方法を使用する場合、自動構成に関連付けられている SRV レコードは必要ありません。 
  
- **内部ゾーンの一致**
    
    外部 DNS ゾーン (contoso.com など) に一致するゾーンを内部 DNS に作成し、自動構成に使用される Skype for Business Server プールに対応する DNS A (および IPv6 アドレス指定を使用している場合は AAAA) レコードを作成する必要があります。
    
    たとえば、ユーザーが pool01.contoso.net にホームとしていて、Skype for Business に bob@contoso.com としてサインインしている場合は、contoso.com という内部 DNS ゾーンを作成し、その内部に pool01.contoso.com の DNS A (および IPv6 アドレス指定が使用されている場合は AAAA) レコードを作成する必要があります。
    
- **ピンポイントの内部ゾーン**
    
    内部 DNS でゾーン全体を作成するオプションではない場合は、自動構成に必要な SRV レコードに対応するピンポイント (専用) ゾーンを作成し、dnscmd.exe を使用してこれらのゾーンにデータを設定できます。 Dnscmd.exe DNS ユーザー インターフェイスはピンポイント ゾーンの作成をサポートしないので、この設定は必須です。
    
    たとえば、SIP ドメインが contoso.com で、pool01 というフロントエンド プールに 2 つのフロントエンド サーバーが含まれている場合、内部 DNS には次のピンポイント ゾーンと A レコードが必要です。
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    環境内に 2 番目の SIP ドメインがある場合があります。 その場合は、内部 DNS に次のピンポイント ゾーンと A レコードが必要になります。
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> フロントエンド プールの FQDN が 2 回表示されますが、2 つの異なる IP アドレスが表示されます。 これは、DNS 負荷分散が使用されているからです。 HLB を使用する場合、フロントエンド プール エントリは 1 つのみです。 
  
> [!NOTE]
> また、フロントエンド プールの FQDN の値は、contoso.com と fabrikam.comの間で変化しますが、IP アドレスは変わりません。 これは、いずれかの SIP ドメインからサインインしているユーザーが、自動構成に同じフロントエンド プールを使用するからです。 
  
## <a name="dns-disaster-recovery"></a>DNS 障害復旧
<a name="DNSDR"> </a>

Skype for Business Server Web トラフィックを障害復旧 (DR) およびフェールオーバー サイトにリダイレクトする DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用する必要があります。 障害復旧をサポートする DNS レコードを設定して、1 つのフロントエンド プール全体がダウンしても Web サービスを使用する機能を続行できます。 この DR 機能は、自動検出、会議、ダイヤルインの簡易 URL をサポートします。
  
追加の DNS ホスト A (IPv6 を使用する場合は AAAA) レコードを定義して構成し、GeoDNS プロバイダーで Web サービスの内部および外部の解決を行います。 次の詳細は、ペアのプールが地理的に分散し、プロバイダーがサポートする GeoDNS がラウンドロビン **DNS** を持っているか、Pool1 をプライマリとして使用するように構成され、通信損失や停電が発生した場合に Pool2 に障害が発生した場合に Pool2 に障害が発生したと想定しています。
  
この表に示す DNS レコードはすべて例です。
  
|**GeoDNS レコード**|**プール レコード**|**CNAME レコード**|**DNS 設定 (1 つのオプションを選択)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.comエイリアスをPool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.comエイリアスをPool2InternalWebFQDN.contoso.com  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.comエイリアスをPool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.comエイリアスを使用してPool2ExternalWebFQDN.contoso.com  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.comエイリアスを指定Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.comエイリアスを指定Pool2InternalWebFQDN.contoso.com  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.comエイリアスを指定Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.comエイリアスをPool2ExternalWebFQDN.contoso.com  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.comエイリアスをPool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.comエイリアスをPool2InternalWebFQDN.contoso.com  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.comエイリアスをPool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.comエイリアスを設定Pool2ExternalWebFQDN.contoso.com  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.comエイリアスをPool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.comエイリアスを追加Pool2InternalWebFQDN.contoso.com  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.comにエイリアスをPool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.comエイリアスをPool2ExternalWebFQDN.contoso.com  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 負荷分散
<a name="DNSLB"> </a>

DNS 負荷分散は、通常、アプリケーション レベルで実装されます。 アプリケーション (Skype for Business を実行しているクライアントなど) は、プール FQDN の DNS A および AAAA (IPv6 アドレスが使用されている場合) レコード クエリから返された IP アドレスの 1 つに接続して、プール内のサーバーへの接続を試行します。
  
たとえば、pool01.contoso.com という名前のプールに 3 つのフロントエンド サーバーがある場合、次のようになります。
  
- Skype for Business を実行しているクライアントは、DNS にクエリをpool01.contoso.com。 クエリは 3 つの IP アドレスを返し、次のようにキャッシュします (順序は次のとおりです)。
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- クライアントは、IP アドレスの 1 つへの TCP 接続を確立します。 失敗した場合は、そのリストからキャッシュされている次の IP アドレスを試します。
    
- TCP 接続が成功すると、クライアントは TLS をネゴシエートして、サーバー上のプライマリ レジストラー pool01.contoso.com。
    
- クライアントが接続に成功せずにすべてのキャッシュされたエントリを試みる場合、ユーザーは、現時点では Skype for Business Server を実行しているサーバーが利用できないという通知を受け取ります。
    
> [!NOTE]
> DNS ベースの負荷分散は、DNS ラウンド ロビン (DNS RR) とは異なります。これは、通常、DNS に依存してプール内のサーバーに異なる順序の IP アドレスを与える負荷分散を指します。 通常、DNS RR は負荷分散を有効にしますが、フェールオーバーを有効にしません。 たとえば、DNS A (または IPv6 シナリオの AAAA) クエリによって返された 1 つの IP アドレスへの接続が失敗した場合、その接続は失敗します。 これにより、DNS RR の信頼性が DNS ベースの負荷分散よりも低くします。 必要に応じて、DNS RR を DNS ベースの負荷分散と組み合わせて使用できます。 
  
DNS 負荷分散を使用して、次の処理を行います。
  
- サーバー間 SIP をエッジ サーバーに負荷分散します。
    
- 会議サービス、応答グループ、コール パークなど、統合コミュニケーション 自動応答 (UCAS) アプリケーションの負荷分散。
    
- UCAS アプリケーションへの新しい接続を防止する (ドレインとも呼ばれる)。
    
- クライアントとエッジ サーバー間のすべてのクライアント間トラフィックの負荷分散。
    
次の場合に DNS 負荷分散を使用することはできません。
  
- フロントエンド サーバーまたはディレクターへのクライアントからサーバーへの Web トラフィック。
    
クエリによって複数の DNS レコードが返された場合に DNS SRV レコードがどのように選択されるのかについてもう少し詳しい情報を得る場合、アクセス エッジ サービスは常に数値の優先順位が最も低いレコードを選択し、タイ ブレーカーが必要な場合は数値ウェイトが最も高くなります。 これは、インターネットエンジニアリングタスク [フォースのドキュメントと一致しています](https://www.ietf.org/rfc/rfc2782.txt)。
  
たとえば、最初の DNS SRV レコードの重み付け値が 20、優先順位が 40 で、2 番目の DNS SRV レコードの重み付けが 10 で優先順位が 50 の場合、優先順位が 40 より低いので、最初のレコードが選択されます。 優先度は常に最初に行き、クライアントが最初にターゲットとするホストです。 同じ優先度を持つターゲットが 2 つある場合は、どうなるでしょうか。 
  
その場合は、重みを考慮します。 この状況では、より大きな重みを選択する可能性が高い必要があります。 DNS 管理者は、実行するサーバーが選択されていない場合は、重み 0 を使用する必要があります。 重み付けが 0 より大きいレコードが存在する場合、重み付け 0 のレコードが選択される可能性は非常に小さいです。
  
では、同じ優先度と重みを持つ複数の DNS SRV レコードが返された場合は、どうなるでしょうか。 この場合、アクセス エッジ サービスは、最初に DNS サーバーから取得した SRV レコードを選択します。
  

