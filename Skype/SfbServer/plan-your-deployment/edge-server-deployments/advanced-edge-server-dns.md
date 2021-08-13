---
title: 高度なエッジ サーバーの展開を計画Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 単一のサーバー Skype for Business Server DNS または HLB を使用するサーバー プールを優先するかどうかに関するシナリオを確認します。
ms.openlocfilehash: 599cc1a779b0d62aa7870c07013e0766a9f8da1e4e5723e988b402b51a0c8f2c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320130"
---
# <a name="plan-advanced-edge-server-deployment-for-skype-for-business-server"></a>高度なエッジ サーバーの展開を計画Skype for Business Server
 
**概要:** 展開オプションのシナリオSkype for Business Server確認します。 単一のサーバーが必要な場合でも、DNS または HLB を使用するサーバー プールを優先する場合でも、このトピックは役立つ必要があります。
  
ドメイン ネーム システム (DNS) の計画に関しては、Skype for Business Serverが決定に影響を与える可能性があります。 組織のドメイン構造が既に設定されている場合は、続行する方法を確認する必要があります。 まず、以下のトピックから始めます。
  
- [サービスをSkype for Businessするクライアントのチュートリアル](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [スプリットブレイン DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [スプリットブレイン DNS を使用しない自動構成](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS 障害復旧](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS 負荷分散](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>サービスをSkype for Businessするクライアントのチュートリアル
<a name="WalkthroughOfSkype"> </a>

Skype for Businessクライアントは、以前の Skype for Business Serverバージョンの Lync クライアントと似ています。 このセクションでは、サーバーの場所プロセスの詳細を説明します。
  
1. lyncdiscoverinternal。\<domain\>
    
     *これは、内部 Web サービス上の自動検出サービスのホスト レコードです。* 
    
2. lyncdiscover。\<domain\>
    
     *これは、外部 Web サービス上の自動検出サービスのホスト レコードです。* 
    
3. _sipinternaltls._tcp。\<domain\>
    
     *これは、内部 TLS 接続の SRV レコードです。* 
    
4. _sip._tls。\<domain\>
    
     *これは、外部 TLS 接続の SRV レコードです。* 
    
5. sipinternal。\<domain\>
    
     *これは、フロント エンド プールまたはディレクターのホスト レコードで、内部ネットワークでのみ解決できます。* 
    
6. sip。\<domain\>
    
     *これは、フロント エンド プールまたはディレクターのホスト レコードで、内部ネットワークでのみ解決できます。* 
    
7. sipexternal。\<domain\>
    
     *これは、クライアントが外部の場合、Access Edge サービスのホスト レコードです。* 
    
自動検出サービスは、サービスの場所に優先する方法であり、他の方法はフォールバック メソッドとして常に優先されます。
  
> [!NOTE]
> SRV レコードを作成する場合は、DNS SRV レコードが作成されているのと同じドメイン内の DNS A (および IPv6 アドレス指定を使用している場合は AAAA) を指す必要があります。 たとえば、SRV レコードが contoso.com 内にある場合、A (および AAAA) レコードは、そのレコードが指定したレコードを fabrikam.com に含め fabrikam.com。 
  
それを行う傾向がある場合は、サービスを手動で検出するためにモバイル デバイスを設定できます。 これが必要な場合、各ユーザーは、プロトコルとパスを含む、内部および外部の自動検出サービス URI 全体を使用してモバイル デバイス設定を構成する必要があります。
  
- 外部アクセスの場合: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- 内部アクセスの場合: \<IntPoolFQDN\> https:// /AutoDiscover/AutoDiscover.svc/Root
    
手動検出ではなく自動検出を使用することをお勧めします。 ただし、トラブルシューティングやテストを行っている場合は、手動設定が非常に役立ちます。
  
## <a name="split-brain-dns"></a>スプリットブレイン DNS
<a name="SplitBrainDNS"> </a>

これは、同じ名前空間を持つ 2 つの DNS ゾーンがある DNS 構成です。 最初の DNS ゾーンは内部要求を処理し、2 番目の DNS ゾーンは外部要求を処理します。
  
企業がこれを行う理由 内部および外部で同じ名前空間を使用する必要がある場合がありますが、もちろん、これは多くの DNS SRV と A レコードが 1 つのゾーンまたは別の領域に固有であり、重複がある場合、これらのレコードに関連付けられている IP アドレスは一意になります。
  
これは、いくつかの課題を提示します。 最も重要なのは、スプリットブレイン DNS が Mobility **でサポート** されていない点です。 これは、LyncDiscover および LyncDiscoverInternal DNS レコード (LyncDiscover を外部 DNS サーバーで定義する必要があります。LyncDiscoverInternal は内部 DNS サーバーで定義する必要があります)。
  
ここでは、内部および外部領域の DNS レコードを一覧表示しますが、詳細な例については、「エッジ サーバー環境要件」セクションを参照してください。
  
### <a name="internal-dns"></a>内部 DNS

- 権限を持つ (たとえば) contoso.com DNS ゾーンが含まれる。
    
- この内部 contoso.com には、次の情報が含まれる。
    
  - フロントエンド プール、ディレクター プールまたはディレクター プール名、および組織のネットワーク内で Skype for Business Server を実行しているすべての内部サーバーの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード。
    
  - 境界ネットワーク内のエッジ サーバーごとに、エッジ内部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) Skype for Business Serverレコード。
    
  - 境界ネットワーク内の各リバース プロキシ サーバーの内部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード (リバース プロキシの管理ではオプション)。
    
  - DNS A と AAAA (IPv6 アドレス指定を使用している場合) と SRV レコードは、内部 Skype for Business Server クライアントの自動構成 (省略可能) に **使用します**。
    
  - DNS A および AAAA (IPv6 アドレス指定を使用している場合) または CNAME レコードを使用して、Skype for Business Server Web サービスの自動検出を行います (これはオプション **です**)。
    
- 境界ネットワークSkype for Business Server内部エッジ インターフェイスでは、この内部 DNS ゾーンを使用してクエリを解決 contoso.com。
    
- Skype for Business Server を実行しているすべてのサーバー、および企業ネットワークで Skype for Business Server を実行しているクライアントは、contoso.com へのクエリを解決するために内部 DNS サーバーをポイントするか、各エッジ サーバーの Host ファイルを使用し、次ホップ サーバー (特にディレクター またはディレクター プール VIP、フロントエンド プール VIP、または Standard Edition Standard Edition サーバー用) の A レコードと AAAA レコードを一覧表示します。
    
### <a name="external-dns"></a>外部 DNS

- 権限を持つ (たとえば) contoso.com DNS ゾーンが含まれる。
    
- この外部 contoso.com には、次の情報が含まれる。
    
  - DNS A と AAAA (IPv6 アドレス指定を使用している場合)、または CNAME レコードを使用して、Web サービスSkype for Business Server検出します。 これはモビリティで使用します。
    
  - 境界ネットワーク内の各 Skype for Business Server エッジ サーバーまたはハードウェア負荷分散 (HLB) VIP のエッジ外部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード。
    
  - DNS A と AAAA (IPv6 アドレス指定を使用している場合) と SRV レコードは、リバース プロキシ サーバーの外部インターフェイスまたは境界ネットワーク内の (リバース プロキシ サーバーのプールの VIP) です。
    
  - DNS A と AAAA (IPv6 アドレス指定を使用している場合) と SRV レコードは、クライアントSkype for Business Server構成 (省略 **可能**) です。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>スプリットブレイン DNS を使用しない自動構成
<a name="NoSplitBrainDNS"> </a>

スプリットブレイン DNS を使用しない場合、Skype for Business を実行しているクライアントの内部自動構成は、ここで示す回避策のいずれかを使用しない限り機能しません。 どうしてでしょうか? このSkype for Business Server、ユーザーの SIP URI が、自動構成用に指定されたフロントエンド プールのドメインと一致する必要があるためです。 これは以前のバージョンの Lync Server から変更されていない。
  
したがって、2 つの SIP ドメインが使用されている場合は、次の DNS SRV レコードが必要です。
  
- _sipinternaltls._tcp.contoso.com。 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *ユーザーが bob@contoso.com としてサインインすると、ユーザーの SIP ドメインがフロントエンド プール (contoso.com) のドメインと一致するので、このレコードは自動構成で機能します。* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *ユーザーが alice@fabrikam.com としてサインインすると、SIP ドメインがそのドメインのフロント エンド プールと一致するので、このレコードは 2 番目のドメインの自動構成で機能します。* 
    
この例をさらに詳しくは、次の方法では動作しません。
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *SIP ドメイン (tim@litwareinc.com litwareinc.com) がプール内のドメイン (fabrikam.com) と一致しないので、ユーザーが自動構成でサインインしても機能しません。* 
    
そのため、スプリットブレイン DNS のないクライアントに対する自動要件が必要Skype for Business、次のオプションがあります。
  
- **グループ ポリシー オブジェクト**
    
    グループ ポリシー オブジェクト (GPO) を使用して、正しいサーバー値を設定できます。
    
    > [!NOTE]
    > このオプションは自動構成を有効にしないが、手動構成を自動化します。 この方法を使用する場合、自動構成に関連付けられた SRV レコードは必要ありません。 
  
- **一致する内部領域**
    
    外部 DNS ゾーン (contoso.com など) に一致するゾーンを内部 DNS に作成し、自動構成に使用される Skype for Business Server プールに対応する DNS A (および IPv6 アドレス指定を使用している場合は AAAA) レコードを作成する必要があります。
    
    たとえば、pool01.contoso.net にユーザーが登録されているが、Skype for Business に bob@contoso.com としてサインインしている場合は、contoso.com という内部 DNS ゾーンを作成し、内部に pool01.contoso.com の DNS A (および IPv6 アドレス指定が使用されている場合は AAAA) レコードを作成する必要があります。
    
- **ピンポイントの内部ゾーン**
    
    内部 DNS でゾーン全体を作成する方法が選択できない場合は、自動構成に必要な SRV レコードに対応するピンポイント (専用) ゾーンを作成し、dnscmd.exe を使用してこれらのゾーンに設定できます。 Dnscmd.exeは、DNS ユーザー インターフェイスがピンポイント 領域の作成をサポートしないので、必須です。
    
    たとえば、SIP ドメインが contoso.com で、2 つのフロントエンド サーバーを含む pool01 というフロントエンド プールがある場合は、内部 DNS に次のピンポイント ゾーンと A レコードが必要になります。
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    環境内に 2 つ目の SIP ドメインがある場合があります。 その場合は、内部 DNS に次のピンポイント 領域と A レコードが必要になります。
    
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
> フロントエンド プールの FQDN が 2 回表示されますが、2 つの異なる IP アドレスが表示されます。 DNS 負荷分散が使用される理由です。 HLB を使用する場合、フロントエンド プール エントリは 1 つのみです。 
  
> [!NOTE]
> また、フロントエンド プールの FQDN 値は、contoso.com と fabrikam.com の間で変更されますが、IP アドレスは変わりません。 これは、いずれかの SIP ドメインからサインインしているユーザーが、自動構成に同じフロント エンド プールを使用する理由です。 
  
## <a name="dns-disaster-recovery"></a>DNS 障害復旧
<a name="DNSDR"> </a>

障害復旧 (DR) Skype for Business Serverフェールオーバー サイトに Web トラフィックをリダイレクトする DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用する必要があります。 障害復旧をサポートするために DNS レコードを設定すると、フロント エンド プール全体がダウンしても Web サービスを使用する機能が続行されます。 この DR 機能は、自動検出、会議、ダイヤルインの単純な URL をサポートします。
  
追加の DNS ホスト A (IPv6 を使用する場合は AAAA) レコードを定義および構成し、GeoDNS プロバイダーで Web サービスの内部および外部解決を行います。 次の詳細は、ペアプールが地理的に分散し、プロバイダーがサポートする GeoDNS がラウンドロビン **DNS** を持つか、または Pool1 をプライマリとして使用するように構成され、通信の損失や停電が発生した場合に Pool2 に失敗すると仮定します。
  
この表のすべての DNS レコードが例です。
  
|**GeoDNS レコード**|**プール レコード**|**CNAME レコード**|**DNS 設定 (1 つのオプションを選択)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com を Meet-int.geolb.contoso.com  <br/>   <br/> |プール間のラウンド ロビン  <br/> **OR** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com から Meet-ext.geolb.contoso.com  <br/>   <br/> |プール間のラウンド ロビン  <br/> **OR** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com を Meet-int.geolb.contoso.com   <br/>  <br/> |プール間のラウンド ロビン  <br/> **OR** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com から Meet-ext.geolb.contoso.com  <br/>  <br/> |プール間のラウンド ロビン  <br/> **OR** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com を Meet-int.geolb.contoso.com   <br/>   <br/> |プール間のラウンド ロビン  <br/> **OR** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com から Meet-ext.geolb.contoso.com  <br/>  <br/> |プール間のラウンド ロビン  <br/> **OR** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com を Meet-int.geolb.contoso.com   <br/>  <br/> |プール間のラウンド ロビン  <br/> **OR** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com から Meet-ext.geolb.contoso.com   <br/>  <br/> |プール間のラウンド ロビン  <br/> **OR** <br/> プライマリを使用し、障害が発生した場合はセカンダリに接続する  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 負荷分散
<a name="DNSLB"> </a>

DNS 負荷分散は通常、アプリケーション レベルで実装されます。 アプリケーション (たとえば、Skype for Business を実行しているクライアント) は、プール FQDN の DNS A および AAAA (IPv6 アドレス指定が使用されている場合) レコード クエリから返される IP アドレスの 1 つに接続して、プール内のサーバーへの接続を試行します。
  
たとえば、プール内に 3 つのフロントエンド サーバーがある場合、pool01.contoso.com が発生します。
  
- DNS のクエリSkype for Business実行しているクライアント pool01.contoso.com。 クエリは 3 つの IP アドレスを返し、次のように (ある順序で) キャッシュします。
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- クライアントは、IP アドレスの 1 つへの TCP 接続を確立します。 失敗した場合は、そのリストからキャッシュされている次の IP アドレスを試します。
    
- TCP 接続が成功した場合、クライアントは TLS をネゴシエートして、サーバー上のプライマリ レジストラー pool01.contoso.com。
    
- クライアントが正常に接続せずにすべてのキャッシュされたエントリを試みる場合、ユーザーは、サーバーを実行しているサーバーが現時点Skype for Business Server利用できないという通知を受け取ります。
    
> [!NOTE]
> DNS ベースの負荷分散は、DNS ラウンド ロビン (DNS RR) とは異なります。これは通常、プール内のサーバーに異なる順序の IP アドレスを与えるために DNS に依存して負荷分散を意味します。 通常、DNS RR は負荷分散を有効にしますが、フェールオーバーを有効にしません。 たとえば、DNS A (または IPv6 シナリオの AAAA) クエリによって返される 1 つの IP アドレスへの接続が失敗した場合、その接続は失敗します。 これにより、DNS ベースの負荷分散よりも DNS RR の信頼性が低くなされます。 DNS ベースの負荷分散を使用する必要がある場合は、DNS RR を DNS ベースの負荷分散と組み合わせて使用できます。 
  
DNS 負荷分散を使用して、次の処理を行います。
  
- サーバー間 SIP をエッジ サーバーに負荷分散します。
    
- 電話会議、応答グループ、通話パークなどのユニファイド コミュニケーション アプリケーション サービス (UCAS) アプリケーション自動応答負荷分散します。
    
- UCAS アプリケーションへの新しい接続 (ドレインとも呼ばれる) を防止します。
    
- クライアントとエッジ サーバー間のすべてのクライアント間トラフィックの負荷分散。
    
DNS 負荷分散は、次の場合に使用することはできません。
  
- フロントエンド サーバーまたはディレクターへのクライアントからサーバーへの Web トラフィック。
    
複数の DNS レコードがクエリによって返される場合に DNS SRV レコードがどのように選択されるのかについてもう少し詳しくは、Access Edge サービスは常に数値優先度が最も低いレコードを選択し、タイ ブレーカーが必要な場合は最も高い数値の重みを取得します。 これは、インターネット エンジニアリング タスク [フォースのドキュメントと一致しています](https://www.ietf.org/rfc/rfc2782.txt)。
  
たとえば、最初の DNS SRV レコードの重みが 20 で優先度が 40 で、2 番目の DNS SRV レコードの重みが 10 で優先度が 50 の場合、優先度が 40 より低いので、最初のレコードが選択されます。 優先度は常に最初に行き、クライアントが最初にターゲットとするホストです。 優先度が同じ 2 つのターゲットがある場合は、どうしますか。 
  
その場合、重量が考慮されます。 この状況では、選択される確率が高いほど、重みを大きくする必要があります。 DNS 管理者は、サーバーの選択が行えない場合は、重み 0 を使用する必要があります。 重みを 0 より大きいレコードが含まれている場合、重み 0 を持つレコードは選択される可能性が小さい。
  
では、同じ優先度と重みを持つ複数の DNS SRV レコードが返された場合は、どうなるでしょうか。 この状況では、Access Edge サービスは、最初に DNS サーバーから取得した SRV レコードを選択します。
  

