---
title: Skype for Business Server 向け Advanced Edge Server DNS の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '概要: Skype for Business Server 展開オプションのシナリオを確認します。 単一サーバーを使用したいと考えている場合も、DNS または HLB と共にサーバー プールを使用することを優先する場合も、このトピックは役に立ちます。'
ms.openlocfilehash: 098d25a23745c035813cfc5c0ea6d291999c3704
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803387"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Skype for Business Server 向け Advanced Edge Server DNS の計画
 
**概要:** Skype for Business Server 展開オプションのシナリオを確認します。 単一サーバーを使用したいと考えている場合も、DNS または HLB と共にサーバー プールを使用することを優先する場合も、このトピックは役に立ちます。
  
Skype for Business Server のドメインネームシステム (DNS) の計画については、多くの要因が考えられます。 組織のドメイン構造が既に確立されている場合は、どのように作業を進めるか確認するための考慮事項になる可能性があります。 最初に、以下に示すトピックについて説明します。
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype for Business クライアントは、以前のバージョンの Lync クライアントと似ていますが、Skype for Business Server でのサービスの検索とアクセス方法が含まれています。 ここではサーバー検索の詳細について説明します。
  
1. lyncdiscoverinternal.\<ドメイン\>
    
     *これは、内部 Web サービスを対象とした自動検出サービスの A ホスト レコードです。* 
    
2. lyncdiscover.\<ドメイン\>
    
     *これは、外部 Web サービスを対象とした自動検出サービスのホスト レコードです。* 
    
3. _sipinternaltls _tcp。\<ドメイン\>
    
     *これは、内部 TLS 接続用の SRV レコードです。* 
    
4. _sip _tls。\<ドメイン\>
    
     *これは、外部 TLS 接続用の SRV レコードです。* 
    
5. sipinternal.\<ドメイン\>
    
     *これは、内部ネットワーク上でのみ解決可能なフロントエンドプールまたはディレクターのホストレコードです。* 
    
6. フェデレーション.\<ドメイン\>
    
     *これは、内部ネットワーク上でのみ解決可能なフロントエンドプールまたはディレクターのホストレコードです。* 
    
7. sipexternal.\<ドメイン\>
    
     *これは、クライアントが外部の場合に、アクセスエッジサービスのホストレコードです。* 
    
常に自動検出サービスを使用することが望まれます。これはサービス検出に関して優先される方法であり、他の方法はフォールバックの方法です。
  
> [!NOTE]
> SRV レコードを作成する場合は、DNS SRV レコードを作成するのと同じドメインにある DNS の A レコード (および、IPv6 アドレスを使用している場合は AAAA レコード) を指す必要があります。たとえば、SRV レコードが contoso.com にある場合、A (および AAAA) レコードが fabrikam.com を指すことはできません。 
  
希望する場合は、サービスの手動検出に依存するようにモバイル デバイスを設定することもできます。この方法を採用しようとする場合は、各ユーザーが自らのモバイル デバイスで、次のようにプロトコルとパスを含め、内部と外部の完全な自動検出サービス URL を構成する必要があります。
  
- 外部アクセスの場合:\<Https://extpoolfqdn\>/Autodiscover/autodiscoverservice.svc/Root
    
- 内部アクセスの場合:\<Https://intpoolfqdn\>/AutoDiscover/AutoDiscover.svc/Root
    
手動検出ではなく、自動検出を使用することを強くお勧めします。ただし、トラブルシューティングやテストを実行する場合は、手動設定が非常に役に立つこともあります。
  
## <a name="split-brain-dns"></a>スプリットブレイン DNS
<a name="SplitBrainDNS"> </a>

これは、2 つの DNS ゾーンが同じ名前空間に存在する DNS 構成です。一方の DNS ゾーンは内部要求のみ、他方の DNS ゾーンは外部要求のみを処理します。
  
企業がこの構成を採用するのはなぜでしょうか。これは、内部と外部で同じ名前空間を使用する場合の要件になることがあります。もちろん、この構成を採用すると、DNS の多数の SRV レコードと A レコードが一方のゾーン内または他方のゾーン内で一意になることが求められる結果につながります。重複が存在する場合は、これらのレコードに関連付けられる IP アドレスは一意になります。
  
この構成を採用すると、いくつかの課題が発生します。 最も重要なことは、スプリットブレイン DNS はモビリティでサポートされて**いない**ことです。 これは、LyncDiscover と LyncDiscoverInternal の各 DNS レコードが原因です (LyncDiscover は外部 DNS サーバー上で、また LyncDiscoverInternal は内部 DNS サーバー上で定義する必要があります)。
  
ここでは、内部と外部のゾーンの DNS レコードについて説明しますが、「microsoft Edge Server の環境要件」セクションで詳しく説明します。
  
### <a name="internal-dns"></a>内部 DNS

- (たとえば) contoso.com という信頼できる DNS ゾーンが含まれています。
    
- 以下は、内部 contoso.com の内容です。
    
  - フロントエンドプール、ディレクタープールまたはディレクタープールの名前、および組織のネットワーク内で Skype for Business Server を実行しているすべての内部サーバーに対して、DNS A と AAAA (IPv6 アドレス指定を使用している場合)。
    
  - 境界ネットワーク内の各 Skype for Business Server Edge サーバーの Edge 内部インターフェイスの (IPv6 アドレス指定を使用している場合は) DNS A と AAAA。
    
  - DNS A と AAAA (IPv6 アドレス指定を使用している場合) 境界ネットワーク内の各リバースプロキシサーバーの内部インターフェイスのレコード (リバースプロキシを管理するための**オプション**)。
    
  - DNS A と AAAA (IPv6 アドレス指定を使用している場合)、および内部の Skype for Business Server クライアントの自動構成の SRV レコード (**オプション**)。
    
  - Skype for Business Server Web サービスを自動的に検出するための DNS A と AAAA (IPv6 アドレスを使用している場合) または CNAME レコード (**オプション**)。
    
- 境界ネットワーク内のすべての Skype for Business Server 内部エッジインターフェイスは、この内部 DNS ゾーンを使って、contoso.com へのクエリを解決します。
    
- Skype for Business Server を実行しているすべてのサーバー、および企業ネットワーク内の Skype for Business Server を実行しているクライアント、contoso.com へのクエリを解決するための内部 DNS サーバー、または各エッジサーバー上のホストファイルを使用している場合は、(使用している場合)IPv6 アドレス) 次ホップサーバーのレコード (特にディレクターまたはディレクタープール VIP、フロントエンドプール VIP、または Standard Edition server)。
    
### <a name="external-dns"></a>外部 DNS

- (たとえば) contoso.com という信頼できる DNS ゾーンが含まれています。
    
- 以下は、外部 contoso.com の内容です。
    
  - Skype for Business Server web サービスを自動的に検出するために、DNS A と AAAA (IPv6 アドレス指定を使用している場合)、または CNAME レコード。 これは、モビリティでの使用に適しています。
    
  - DNS A と AAAA (IPv6 アドレスを使用している場合)、および境界ネットワークでの各 Skype for Business Server Edge サーバーまたはハードウェア負荷分散 (HLB) VIP のエッジ外部インターフェイスの SRV レコード。
    
  - 境界ネットワークの DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード (リバースプロキシサーバーの外部インターフェイスまたはリバースプロキシサーバーのプール用 VIP)。
    
  - DNS A と AAAA (IPv6 アドレス指定を使用している場合)、および Skype for Business Server クライアント自動構成の SRV レコード (**オプション**)。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>スプリットブレイン DNS なしの自動構成
<a name="NoSplitBrainDNS"> </a>

スプリットブレイン DNS を使用していない場合は、次の回避策のいずれかを使用しない限り、Skype for Business を実行しているクライアントの内部自動構成は機能しません。 なぜでしょうか。 Skype for Business Server は、自動構成用に指定されたフロントエンドプールのドメインと一致するようにユーザーの SIP URI を要求するためです。 これは、以前のバージョンの Lync Server から変更されていません。
  
たとえば、使用されている SIP ドメインが 2 つある場合、次の DNS SRV レコードが必要です。
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *ユーザーが bob@contoso.com としてサインインした場合、ユーザーの SIP ドメインはフロントエンドプールのドメイン (contoso.com) と一致するため、このレコードは自動構成で動作します。* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *ユーザーが alice@fabrikam.com としてサインインした場合、SIP ドメインがそのドメインのフロントエンドプールと一致するため、このレコードは2番目のドメインの自動構成に使用できます。* 
    
ここまでの例を使用すると、次のレコードは機能しません。
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *tim@litwareinc.com としてサインインしたユーザーの場合は、自動構成は機能しません。このユーザーの SIP ドメイン (litwareinc.com) は、プール内のドメイン (fabrikam.com) と一致しないためです。* 
    
これで、スプリットブレイン DNS を使わずに Skype for Business クライアントの自動要件が必要な場合は、次のオプションがあります。
  
- **グループ ポリシー オブジェクト**
    
    グループ ポリシー オブジェクト (GPO) を使用して、適切なサーバーの値を設定できます。
    
    > [!NOTE]
    > このオプションを使用しても自動構成は有効になりませんが、手動構成が自動化されます。この方法を使用した場合、自動構成に関連付ける SRV レコードは必要ありません。 
  
- **内部ゾーンの一致**
    
    外部 DNS ゾーン (contoso.com など) に一致する内部 DNS のゾーンを作成して、自動で使用される Skype for Business Server プールに対応するレコードを作成する必要があります (IPv6 アドレスを使っている場合は、AAAA の場合)。構成.
    
    たとえば、ユーザーが pool01.contoso.net をホームにしていて、bob@contoso.com として Skype for Business にサインインしている場合、contoso.com という名前の内部 DNS ゾーンを作成し、その内部に pool01.contoso.com の DNS A (IPv6 アドレスを使用する場合は AAAA) レコードを作成する必要があります。
    
- **ピンポイントの内部ゾーン**
    
    内部 DNS 内にゾーン全体を作成することが適切なオプションではない場合は、自動構成で必要とされる複数の SRV レコードに対応するピンポイント (専用) ゾーンを作成し、dnscmd.exe を使用してそれらのゾーンを設定することができます。DNS ユーザー インターフェイスはピンポイント ゾーンの作成をサポートしていないため、Dnscmd.exe が必須です。
    
    たとえば、SIP ドメインが contoso.com で、2つのフロントエンドサーバーを含む pool01 というフロントエンドプールがある場合、次のピンポイントゾーンと内部 DNS 内のレコードが必要になります。
    
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
> フロントエンドプールの FQDN が2回表示されますが、2つの異なる IP アドレスがあります。 DNS 負荷分散を使用しているためです。 HLB を使っている場合は、1つのフロントエンドプールエントリしかありません。 
  
> [!NOTE]
> また、contoso.com と fabrikam.com の例では、フロントエンドプールの FQDN 値が変更されますが、IP アドレスは変わりません。 その理由は、いずれかの SIP ドメインからサインインしているユーザーが、自動構成で同じフロントエンドプールを使用しているためです。 
  
## <a name="dns-disaster-recovery"></a>DNS 障害復旧
<a name="DNSDR"> </a>

Skype for Business Server の web トラフィックを disaster recover (DR) とフェールオーバーサイトにリダイレクトするように DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用する必要があります。 障害回復をサポートするように DNS レコードを設定することができます。これにより、フロントエンドプール全体が停止した場合でも、web サービスを使う機能が続行されます。 この障害復旧機能では、自動検出、会議、およびダイヤルインの簡易 URL をサポートします。
  
You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider. The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.
  
この表の DNS レコードは、いずれも例です。
  
|**GeoDNS レコード**|**プール レコード**|**CNAME レコード**|**DNS 設定 (オプションを 1 つ選択する)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Meet-int.geolb.contoso.com  <br/>   <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Meet-ext.geolb.contoso.com  <br/>   <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Meet-int.geolb.contoso.com   <br/>  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Meet-ext.geolb.contoso.com  <br/>  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Meet-int.geolb.contoso.com   <br/>   <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Meet-ext.geolb.contoso.com  <br/>  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Meet-int.geolb.contoso.com   <br/>  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Meet-ext.geolb.contoso.com   <br/>  <br/> |プール間のラウンド ロビン  <br/> **または** <br/> プライマリを使用し、障害発生時はセカンダリに接続  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 負荷分散
<a name="DNSLB"> </a>

DNS 負荷分散は一般的に、アプリケーション レベルで実装されます。 このアプリケーション (たとえば、Skype for Business を実行しているクライアント) は、DNS A と AAAA から返された IP アドレスの1つ (IPv6 アドレスが使用されている場合) に接続して、プールの FQDN のレコードクエリを実行します。
  
たとえば、pool01.contoso.com という名前のプールに3台のフロントエンドサーバーがある場合は、次のようになります。
  
- Skype for Business の DNS クエリを実行しているクライアント pool01.contoso.com。 このクエリは 3 つの IP アドレスを返し、それらを次のようにキャッシュに格納します (順序は任意)。
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 次に、クライアントは IP アドレスの 1 つに対して TCP 接続を確立しようとします。それが失敗した場合は、一覧の中にキャッシュされている次の IP アドレスを試します。
    
- TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com のプライマリ レジストラーに接続します。
    
- クライアントがすべてのキャッシュエントリを正常に接続していない場合は、Skype for Business Server が実行されているサーバーが現在利用できないという通知がユーザーに表示されます。
    
> [!NOTE]
> DNS ベースの負荷分散は、一般的に、DNS を利用してプール内のサーバーの IP アドレスを別の順序で提供して負荷分散を行うことを指す DNS ラウンド ロビン (DNS RR) と異なります。一般的に、DNS RR は負荷分散が可能で、フェールオーバー機能を実現しません。たとえば、DNS A (または IPv6 のシナリオを使用している場合は AAAA) クエリで返された 1 つの IP アドレスに対する接続が失敗した場合、その接続は失敗します。したがって、DNS RR は DNS ベースの負荷分散より信頼性が劣りますが、上記の目的で、DNS 負荷分散と共に DNS RR を引き続き使用することができます。 
  
DNS 負荷分散の用途:
  
- サーバー間 SIP の負荷分散をエッジサーバーに対して行います。
    
- 会議自動アテンダント、応答グループ、コール パークなどの統合コミュニケーション アプリケーション サービス (UCAS) アプリケーションの負荷分散
    
- UCAS アプリケーションへの新規接続の禁止(ドレインとも呼ばれます)
    
- クライアントとエッジサーバー間のクライアント間トラフィックはすべて負荷分散されます。
    
DNS 負荷分散を使用できない用途:
  
- フロントエンドサーバーまたはディレクターへのクライアント対サーバー web トラフィック。
    
Mutiple DNS レコードがクエリによって返されたときの DNS SRV レコードの選択方法についてさらに詳しく理解するために、アクセスエッジサービスは常に最も低い数値の優先度を持つレコードを選びます。また、タイのブレーカーが必要な場合は、最も高い数値の重みにします。 これは、[インターネットエンジニアリングタスクのフォースに関するドキュメント](https://www.ietf.org/rfc/rfc2782.txt)と一貫性があります。
  
そのため、たとえば最初の DNS SRV レコードの重み付けが 20 で、優先順位が 40、また 2 番目の DNS SRV レコードの重み付けが 10 で、優先順位が 50 の場合は、優先順位が 40 である最初のレコードが選択されます。常に優先順位が最初に考慮され、クライアントが最初にターゲットにするホストになります。同じ優先順位を持つターゲットが 2 つ存在する場合はどうなるでしょうか。 
  
この場合は、重み付けが考慮されます。この状況では、重み付けが大きいほど、選択される確率が高くなります。サーバー選択を行わない場合は、DNS 管理者は重み付け 0 を使用する必要があります。0 より大きい重み付けを持つレコードが存在するとき、重み付け 0 のレコードが選択される可能性は非常に小さくなります。
  
同じ優先度と重み付けを持つ複数の DNS SRV レコードが返された場合は、どうなるでしょうか。 この場合、アクセスエッジサービスによって、DNS サーバーから取得した SRV レコードが最初に選択されます。
  

