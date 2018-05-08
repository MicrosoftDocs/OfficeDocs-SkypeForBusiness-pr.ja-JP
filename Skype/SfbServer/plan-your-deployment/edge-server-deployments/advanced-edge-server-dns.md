---
title: 高度なエッジ サーバーの DNS を計画する Skype のビジネス サーバー 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '概要: は、Skype のビジネス サーバー 2015 展開オプションのシナリオを確認します。 単一サーバーを使用したいと考えている場合も、DNS または HLB と共にサーバー プールを使用することを優先する場合も、このトピックは役に立ちます。'
ms.openlocfilehash: 575bbacfa58f52197d50b335942909dc8748a965
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server-2015"></a>高度なエッジ サーバーの DNS を計画する Skype のビジネス サーバー 2015
 
**概要:** Skype for Business Server 2015 の展開オプションに関するシナリオを確認します。単一サーバーを使用したいと考えている場合も、DNS または HLB と共にサーバー プールを使用することを優先する場合も、このトピックは役に立ちます。
  
Skype のビジネス サーバー 2015 のドメイン ネーム システム (DNS) を計画する際に、たくさんの要因、意思決定に果たすことがあります。 組織のドメイン構造が既に確立されている場合は、どのように作業を進めるか確認するための考慮事項になる可能性があります。 最初に、以下に示すトピックについて説明します。
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

ビジネス クライアント用の Skype は、検索し、ビジネス サーバー 2015 の Skype のサービスへのアクセス方法での Lync クライアントの以前のバージョンに似ています。 ここではサーバー検索の詳細について説明します。
  
1. lyncdiscoverinternal。\<ドメイン\>
    
     *これは、内部 Web サービスを対象とした自動検出サービスの A ホスト レコードです。* 
    
2. lyncdiscover。\<ドメイン\>
    
     *これは、外部 Web サービスを対象とした自動検出サービスのホスト レコードです。* 
    
3. _sipinternaltls._tcp。\<ドメイン\>
    
     *これは、内部 TLS 接続用の SRV レコードです。* 
    
4. ゾーンに追加します。\<ドメイン\>
    
     *これは、外部 TLS 接続用の SRV レコードです。* 
    
5. sipinternal。\<ドメイン\>
    
     *これは、フロント エンド プールまたはディレクター、内部ネットワークでのみ名前解決の A ホスト レコードです。* 
    
6. sip。\<ドメイン\>
    
     *これは、フロント エンド プールまたはディレクター、内部ネットワークでのみ名前解決の A ホスト レコードです。* 
    
7. sipexternal。\<ドメイン\>
    
     *これは、クライアントが外部にある場合、アクセス エッジ サービスは、ホスト A レコードです。* 
    
常に自動検出サービスを使用することが望まれます。これはサービス検出に関して優先される方法であり、他の方法はフォールバックの方法です。
  
> [!NOTE]
> SRV レコードを作成する場合は、DNS SRV レコードを作成するのと同じドメインにある DNS の A レコード (および、IPv6 アドレスを使用している場合は AAAA レコード) を指す必要があります。たとえば、SRV レコードが contoso.com にある場合、A (および AAAA) レコードが fabrikam.com を指すことはできません。 
  
希望する場合は、サービスの手動検出に依存するようにモバイル デバイスを設定することもできます。この方法を採用しようとする場合は、各ユーザーが自らのモバイル デバイスで、次のようにプロトコルとパスを含め、内部と外部の完全な自動検出サービス URL を構成する必要があります。
  
- 外部アクセス用: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- 内部アクセス用: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
手動検出ではなく、自動検出を使用することを強くお勧めします。ただし、トラブルシューティングやテストを実行する場合は、手動設定が非常に役に立つこともあります。
  
## <a name="split-brain-dns"></a>スプリットブレイン DNS
<a name="SplitBrainDNS"> </a>

これは、2 つの DNS ゾーンが同じ名前空間に存在する DNS 構成です。一方の DNS ゾーンは内部要求のみ、他方の DNS ゾーンは外部要求のみを処理します。
  
企業がこの構成を採用するのはなぜでしょうか。これは、内部と外部で同じ名前空間を使用する場合の要件になることがあります。もちろん、この構成を採用すると、DNS の多数の SRV レコードと A レコードが一方のゾーン内または他方のゾーン内で一意になることが求められる結果につながります。重複が存在する場合は、これらのレコードに関連付けられる IP アドレスは一意になります。
  
この構成を採用すると、いくつかの課題が発生します。 最も重要なは、ブレイン DNS モビリティの**サポートされていない**のです。 これは、LyncDiscover と LyncDiscoverInternal の各 DNS レコードが原因です (LyncDiscover は外部 DNS サーバー上で、また LyncDiscoverInternal は内部 DNS サーバー上で定義する必要があります)。
  
ゾーンについては、内部および外部ここでは、DNS レコードをリストしますが、エッジ サーバーの環境の必要条件のセクションで詳細な例を見つけることができます。
  
### <a name="internal-dns"></a>内部 DNS

- (たとえば) contoso.com という信頼できる DNS ゾーンが含まれています。
    
- 以下は、内部 contoso.com の内容です。
    
  - DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合は、フロント エンド プール、ディレクター プールまたはディレクターのプール名、およびビジネス サーバー 2015 の Skype を実行して、組織のネットワーク内のすべての内部サーバーに記録されます。
    
  - DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、エッジの内部インターフェイスの各 Skype の記録ビジネス 2015 エッジ サーバーを境界ネットワーク内です。
    
  - (これは**省略可能な**リバース プロキシを管理するため) を境界ネットワーク内の各のリバース プロキシ サーバーの内部インターフェイスの DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合を記録します。
    
  - DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、(これは**省略可能**) ビジネス サーバー 2015 クライアントの自動構成の内部の Skype の SRV レコード。
    
  - DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、または (これは**省略可能**) ビジネス サーバー 2015 Web サービスの Skype の自動検出の CNAME レコード。
    
- ビジネス サーバー 2015 内部エッジのインタ フェースを境界ネットワーク内のすべての Skype は、contoso.com にクエリを解決するため、この内部 DNS ゾーンを使用します。
    
- ビジネス サーバー 2015 年およびビジネス サーバー 2015 の企業のネットワークでは、Skype を実行しているクライアントの Skype を実行しているすべてのサーバーは、contoso.com にクエリを解決するために内部の DNS サーバーをポイントまたは各エッジ サーバー] ボックスの一覧の A および AAAA のホスト ファイルを使用する場合IPv6 のアドレス指定を使用している) (具体的には、ディレクターまたはディレクター プールの VIP、フロント エンド プールの VIP、または Standard Edition サーバー) の次ホップのサーバーに記録します。
    
### <a name="external-dns"></a>外部 DNS

- (たとえば) contoso.com という信頼できる DNS ゾーンが含まれています。
    
- 以下は、外部 contoso.com の内容です。
    
  - DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合は、CNAME は、Skype のビジネス サーバー 2015 web サービス用の自動検出機能を記録します。 これは移動に使用します。
    
  - DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、エッジの外部インターフェイス ビジネス 2015 エッジ サーバーまたはハードウェアの負荷を各 Skype の SRV レコードは、境界ネットワーク内の (HLB) の VIP を分散しました。
    
  - (リバース プロキシ サーバーのプールの VIP)、またはリバース プロキシ サーバーの外部インターフェイスのネットワーク境界に DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、SRV が記録されます。
    
  - DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合や SRV レコード Skype のビジネス サーバー 2015 クライアントの自動構成が (**省略可能**) のです。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>スプリットブレイン DNS なしの自動構成
<a name="NoSplitBrainDNS"> </a>

ブレイン DNS を使用しない、あるここでの回避策のいずれかを使用している場合を除き、Skype のビジネスを実行しているクライアントの内部の自動構成は機能しません。 なぜでしょうか。 ビジネス サーバー 2015 の Skype では、ユーザーの SIP URI は、自動構成用に指定されたフロント エンド プールのドメインと一致する必要があります。 これは、Lync Server の以前のバージョンから変更されていません。
  
たとえば、使用されている SIP ドメインが 2 つある場合、次の DNS SRV レコードが必要です。
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Bob@contoso.com として、ユーザーがサインインしている場合このレコードはどおりに動作を自動的に構成、ユーザーの SIP ドメイン (contoso.com) のフロント エンド プールのドメインと一致します。* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Alice@fabrikam.com として、ユーザーがサインインしている場合は、SIP ドメインはそのドメイン内のフロント エンド プールを一致するためを自動的に構成の 2 つ目のドメインでは、もう一度このレコードが動作は。* 
    
ここまでの例を使用すると、次のレコードは機能しません。
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *tim@litwareinc.com としてサインインしたユーザーの場合は、自動構成は機能しません。このユーザーの SIP ドメイン (litwareinc.com) は、プール内のドメイン (fabrikam.com) と一致しないためです。* 
    
わかったところで、DNS の分散管理をビジネスのクライアントの Skype の自動要件が必要な場合は、これらのオプションがあります。
  
- **グループ ポリシー オブジェクト**
    
    グループ ポリシー オブジェクト (GPO) を使用して、適切なサーバーの値を設定できます。
    
    > [!NOTE]
    > このオプションを使用しても自動構成は有効になりませんが、手動構成が自動化されます。この方法を使用した場合、自動構成に関連付ける SRV レコードは必要ありません。 
  
- **内部ゾーンの一致**
    
    外部 DNS ゾーン (たとえば、contoso.com) に一致する内部 DNS にゾーンを作成し、DNS の A (および AAAA IPv6 のアドレス指定を使用する場合) を作成する必要がありますビジネス サーバー 2015 プールの自動使用の Skype に対応するレコード構成します。
    
    などがある場合、ユーザーが置かれている記号ですが、pool01.contoso.net、Skype に bob@contoso.com、ビジネスは、contoso.com と呼ばれる内部の DNS ゾーンを作成し、その中には、DNS の A (および AAAA 使用されている IPv6 アドレスの場合) を作成する必要がレコードpool01.contoso.com。
    
- **ピンポイントの内部ゾーン**
    
    内部 DNS 内にゾーン全体を作成することが適切なオプションではない場合は、自動構成で必要とされる複数の SRV レコードに対応するピンポイント (専用) ゾーンを作成し、dnscmd.exe を使用してそれらのゾーンを設定することができます。DNS ユーザー インターフェイスはピンポイント ゾーンの作成をサポートしていないため、Dnscmd.exe が必須です。
    
    などの場合は、SIP ドメインは、contoso.com を使用して 2 つのフロント エンド サーバーを含む pool01 と呼ばれるフロント エンド プール、する必要があります次のピン ・ ポイントのゾーン レコードおよび a レコード内部 DNS に。
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    環境内で 2 番目の SIP ドメインを用意することもできます。この場合は、内部 DNS 内で以下のピンポイント ゾーンと A レコードが必要になります。
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> フロント エンド プールを 2 回ですが、2 つの異なる IP アドレスと FQDN が表示されますが表示されます。 DNS 負荷分散を使用しているためです。 HLB が使用されている場合だけでしょう、1 つのフロント エンド プール エントリ。 
  
> [!NOTE]
> フロント エンド プールの FQDN の値を変更する、contoso.com と fabrikam.com の例との間も、IP アドレスは変わりません。 いずれかの SIP ドメインからサインインしているユーザーが自動構成に同じフロント エンド プールを使用するためです。 
  
## <a name="dns-disaster-recovery"></a>DNS 障害復旧
<a name="DNSDR"> </a>

障害回復 (DR) とフェイル オーバー ・ サイトに web トラフィックをビジネス サーバー 2015 の Skype をリダイレクトするように DNS を構成するには GeoDNS をサポートしているプロバイダーの DNS を使用する必要があります。 Web サービスを使用する機能は、全体のフロント エンド プールを 1 つがダウンした場合でもを続行するためは、災害リカバリをサポートするために DNS レコードを設定できます。 この障害復旧機能では、自動検出、会議、およびダイヤルインの簡易 URL をサポートします。
  
定義し、(AAAA IPv6 を使用する場合) は、GeoDNS プロバイダーで web サービスの内部および外部の解像度の記録その他の DNS ホストを構成します。 以下の詳細は、地理的に分散している、一対のプールを想定していて、ラウンド ロビン DNS **、または**プロバイダー**か**でサポートされている GeoDNS を持っている Pool1 をプライマリとして使用するように構成されて Pool2 に、通信の発生時にフェイル オーバー損失または電源障害が発生。
  
この表の DNS レコードは、いずれも例です。
  
|**GeoDNS レコード**|**プールのレコード**|**CNAME レコード**|**(1 つのオプションを選択します)、DNS の設定**|
|:-----|:-----|:-----|:-----|
|対応 int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |エイリアス Meet.contoso.com を Pool1InternalWebFQDN.contoso.com に指定  <br/> エイリアス Meet.contoso.com を Pool2InternalWebFQDN.contoso.com に指定  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|対応 ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |エイリアス Meet.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定  <br/> エイリアス Meet.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|ダイヤルイン int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |エイリアス Dialin.contoso.com を Pool1InternalWebFQDN.contoso.com に指定  <br/> エイリアス Dialin.contoso.com を Pool2InternalWebFQDN.contoso.com に指定  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|ダイヤルイン ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |エイリアス Dialin.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定  <br/> エイリアス Dialin.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Lyncdiscoverint int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |エイリアス Lyncdiscoverinternal.contoso.com を Pool1InternalWebFQDN.contoso.com に指定  <br/> エイリアス Lyncdiscoverinternal.contoso.com を Pool2InternalWebFQDN.contoso.com に指定  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Lyncdiscover ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |エイリアス Lyncdiscover.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定  <br/> エイリアス Lyncdiscover.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|スケジューラ int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |エイリアス Scheduler.contoso.com を Pool1InternalWebFQDN.contoso.com に指定  <br/> エイリアス Scheduler.contoso.com を Pool2InternalWebFQDN.contoso.com に指定  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|スケジューラ ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |エイリアス Scheduler.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定  <br/> エイリアス Scheduler.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 負荷分散
<a name="DNSLB"> </a>

DNS 負荷分散は一般的に、アプリケーション レベルで実装されます。 返される IP アドレスのいずれかに接続することによって、プール内のサーバーに接続しようとするアプリケーション (たとえば、クライアント ビジネスの Skype を実行している)、DNS の A および AAAA (IPv6 のアドレス指定が使用されます) の場合は、プールの FQDN についてのクエリを記録します。
  
たとえば、pool01.contoso.com をという名前のプールで 3 つのフロント エンド サーバーがある場合は、次が発生します。
  
- ビジネス用の Skype を実行しているクライアントは、pool01.contoso.com の DNS を照会します。クエリでは、3 つの IP アドレスが返され、次のように (順序) でキャッシュに保持します。
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 次に、クライアントは IP アドレスの 1 つに対して TCP 接続を確立しようとします。それが失敗した場合は、一覧の中にキャッシュされている次の IP アドレスを試します。
    
- TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com のプライマリ レジストラーに接続します。
    
- クライアントには、キャッシュされているすべてのエントリが正常に接続しなくてもしようとすると、ユーザーは、ビジネス サーバー 2015 の Skype を実行しているサーバーがある時点で通知を受け取ります。
    
> [!NOTE]
> DNS ベースの負荷分散は、一般的に、DNS を利用してプール内のサーバーの IP アドレスを別の順序で提供して負荷分散を行うことを指す DNS ラウンド ロビン (DNS RR) と異なります。一般的に、DNS RR は負荷分散が可能で、フェールオーバー機能を実現しません。たとえば、DNS A (または IPv6 のシナリオを使用している場合は AAAA) クエリで返された 1 つの IP アドレスに対する接続が失敗した場合、その接続は失敗します。したがって、DNS RR は DNS ベースの負荷分散より信頼性が劣りますが、上記の目的で、DNS 負荷分散と共に DNS RR を引き続き使用することができます。 
  
DNS 負荷分散の用途:
  
- 負荷は、サーバーからサーバー、エッジ サーバーに SIP を分散します。
    
- 会議自動アテンダント、応答グループ、コール パークなどの統合コミュニケーション アプリケーション サービス (UCAS) アプリケーションの負荷分散
    
- UCAS アプリケーションへの新規接続の禁止(ドレインとも呼ばれます)
    
- 負荷は、クライアントとエッジ サーバー間のすべてのクライアントからサーバーへのトラフィックを分散します。
    
DNS 負荷分散を使用できない用途:
  
- クライアントからサーバーへの web トラフィックは、フロント エンド サーバーまたはディレクター。
    
タイ ブレーカーの場合、複数の DNS レコードがアクセス エッジ サービスを常に、クエリによって返された優先度の低い数値のレコードを選択するときに、DNS SRV レコードを選択する方法で、もう少し詳細を移動するために必要な最大の数値の重量。 これは、[インターネット技術標準化委員会ドキュメント](https://www.ietf.org/rfc/rfc2782.txt)と一致します。
  
そのため、たとえば最初の DNS SRV レコードの重み付けが 20 で、優先順位が 40、また 2 番目の DNS SRV レコードの重み付けが 10 で、優先順位が 50 の場合は、優先順位が 40 である最初のレコードが選択されます。常に優先順位が最初に考慮され、クライアントが最初にターゲットにするホストになります。同じ優先順位を持つターゲットが 2 つ存在する場合はどうなるでしょうか。 
  
この場合は、重み付けが考慮されます。この状況では、重み付けが大きいほど、選択される確率が高くなります。サーバー選択を行わない場合は、DNS 管理者は重み付け 0 を使用する必要があります。0 より大きい重み付けを持つレコードが存在するとき、重み付け 0 のレコードが選択される可能性は非常に小さくなります。
  
同じ優先度と重み付けを持つ複数の DNS SRV レコードが返された場合は、どうなるでしょうか。 このような場合、アクセス エッジ サービスは、取得した DNS サーバーから最初の SRV レコードを選択します。
  

