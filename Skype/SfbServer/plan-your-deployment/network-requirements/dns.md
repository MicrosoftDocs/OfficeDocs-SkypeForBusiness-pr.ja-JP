---
title: Skype のビジネス サーバー用の DNS の要件
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: '概要: は、Skype をビジネスのサーバーを実装する前にここでは DNS の考慮事項を確認します。'
ms.openlocfilehash: 8f47d7de61521c3908a8094bb7c6c866a55c4842
ms.sourcegitcommit: 81b38b389bfe3acd1aa13ce61c221b7b368c0e2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2018
ms.locfileid: "27382855"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Skype のビジネス サーバー用の DNS の要件

**の概要:** Skype をビジネスのサーバーを実装する前にここでは DNS の考慮事項を確認します。

DNS Skype のビジネス サーバー展開計画組織の設置型のネットワークでのみ解説します。 ビジネス オンラインの Skype を参照してください「Office 365 の Url と IP アドレスの範囲」で[https://aka.ms/o365ips](https://aka.ms/o365ips)です。

ドメイン ネーム サービス (DNS) サーバーのホスト名をマップする (www のようにします<span></span>。contoso<span></span>.com、おそらく web サーバー) の IP アドレス (10.10.10.10) などにします。 これにより、クライアントおよび相互依存のサーバー同士が、ネットワーク上で通信することができます。 ビジネス サーバー 2015 の Skype の実装を設定するときは、(通常、説明的役割を反映する)、新しいサーバー名のマッピングに割り当てられている IP アドレスに一致するかどうかを確認する必要があります。

これを計画するため、複雑な処理を実行することができます最初は困難なビットこれと思われるかもしれませんが、 [Skype](https://www.microsoft.com/en-us/download/details.aspx?id=50357)を使用します。 どの機能を使用する予定があるかについてのウィザードの質問に回答し終えたら、各サイトについてエッジ管理レポート内で表示できる DNS レポートを定義して、そこで DNS レコードを作成するために一覧表示された情報を使用します。 使用される多くの名前と IP アドレスに対して調整を行うこともできます。詳細については、[DNS レポートの確認](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)を参照してください。 エッジ管理レポートは、Excel スプレッドシートにエクスポートすることができますが、DNS レポートはそのファイル内のワークシートの 1 つであることに留意してください。 このツールでは、[ビジネス サーバー 2019 の Skype から非推奨](../../../SfBServer2019/deprecated.md)機能が含まれていますが、まだできますこれらの機能が選択されていない場合、初期の計画を作成するには

[Skype ビジネス サーバー用のレコードを DNS の作成](../../deploy/install/create-dns-records.md)で説明するよう、新しい実装をインストールして、Skype のビジネス サーバーのトポロジを構築、認識しているときは、Windows Server に組み込まれている DNS 機能を使用することもできます。2016 またはサード パーティ製 DNS パッケージ、スクリプトを紹介する、ディスカッションここで特定するのではなく、一般的なようです。 何が必要であるかについては詳細に示されていますので、それらの必要性をどのように満たすかについてはユーザー自身が決定することになります。

ビジネス、Lync では、および通信のスイートを Office の管理者の経験豊富な Skype はおそらく次の表は、役に立ちます。 表の内容が分かりにくい場合は、後のセクションや記事で次のような概念が明快に説明されています。

## <a name="summary-tables"></a>要約表
<a name="BK_Summary"> </a>

次の表は、ユーザーにサービスを提供するビジネスのサーバー用の Skype を使用して DNS レコードを表示します。 一部のレコードは特定の機能をサポートするためのみに必要とされるためオプションとなり、それらの機能が要求されない場合はスキップされます。 内部アクセスのみで必要な DNS レコードは、最初の表にあります。内部および外部のアクセスを許可する展開では、両方の表にあるレコードが必要となります。

**内部 DNS マッピング**

|レコードの種類|値|解決先|用途|必須|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |フロント エンド プールの FQDN  <br/> *FE のプールです。<span> </span>contoso<span></span>.com*   |フロント エンド プール サーバーの IP アドレス  <br/>  DNS LB *192.168.21.122 192.168.21.123 192.168.21.124*   |フロントエンド プールの DNS 負荷分散。 フロントエンド プールの名前を IP アドレスのセットにマップします。 <br/> [フロントエンド プールとディレクター プールへの DNS 負荷分散の展開](load-balancing.md#BK_FE_Dir)を参照してください  |Y   |
|A/AAAA   | プール内の各フロント エンド サーバーまたは Standard Edition サーバーまたはスタンドアロン サーバーの FQDN <br/>  *FE01。<span> </span>contoso。<span> </span>com FE02。<span> </span>contoso<span></span>.com FE03。<span> </span>contoso<span></span>.com*   |各サーバーの対応する IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |IP アドレスのサーバー名をマップします。   |Y   |
|A/AAAA   |エンタープライズ プールの内部 Web サービスでの FQDN の上書き  <br/> *Web 整数<span></span>contoso<span></span>.com*   |フロント エンド サーバーの内部の Web サービス用の HLB の VIP  <br/> *192.168.21.120*   |クライアントは、Skype のビジネス Web アプリケーションのダウンロードなど、サーバーの web トラフィックを有効にする場合に必要です。 モバイル クライアントでも必要です。   |Y   |
|A/AAAA   |エンタープライズ プールの外部 Web サービスでの FQDN の上書き  <br/> *Web 内線<span></span>contoso<span></span>.com*   |フロント エンド サーバーの外部の Web サービス用の HLB の VIP  <br/>*68.123.56.90*   |クライアントは、Skype のビジネス Web アプリケーションのダウンロードなど、サーバーの web トラフィックを有効にする場合に必要です。 モバイル クライアントが DNS を内部的に解決する場合に必要です。 DMZ リバース プロキシ IP または内部 IP に解決することができます。   ||
|A/AAAA   | バック エンド サーバーの SQL サーバーの FQDN <br/> *SQL1。<span> </span>contoso<span></span>.com*   |サーバー IP アドレス  <br/> *192.168.11.90*   |フロント エンド プールの IP アドレスを使用するバックエンド SQL サーバーのサーバー名をマッピングします。   ||
|A/AAAA   |バック エンド サーバーのミラーの SQL サーバーの FQDN  <br/> *SQL2。<span> </span>contoso<span></span>.com*   |サーバー IP アドレス  <br/> *192.168.11.91*   |フロント エンド プールの IP アドレスを使用するバック エンド SQL のミラー ・ サーバのサーバ名をマップします。   ||
|A/AAAA   |ディレクター プールの FQDN  <br/>**注:** スタンドアロン ディレクター サーバーを使用する場合は適用されません。 <br/> *DirPool。<span> </span>contoso<span></span>.com*   |ディレクター プールの IP アドレス  <br/> *192.168.21.132、192.168.21.133* 、192.168.21.134 の DNS LB   |ディレクター プール サーバーの DNS 負荷分散。 プールの名前を IP アドレスでは、ディレクター プールのマップは、[フロント エンド プールとディレクター プールに DNS 負荷分散を展開する](load-balancing.md#BK_FE_Dir)を参照してください。 <br/> ディレクターはユーザーを認証することができる、オプションです。   ||
|A/AAAA   |ディレクターの FQDN   |ダイレクタの各サーバーのサーバーの IP アドレス   |プールの名前を IP アドレスでは、ダイレクタのマップは、[フロント エンド プールとディレクター プールに DNS 負荷分散を展開する](load-balancing.md#BK_FE_Dir)を参照してください。  ||
|A/AAAA   |仲介サーバー プールの FQDN   |プール IP アドレス   |仲介サーバー ロールはオプションです。 仲介サーバーによって提供されるサービスを、フロント エンド サーバーまたはプールに対して併置することができます。 [仲介サーバー プールの DNS のロードバランシングを使用する](load-balancing.md#BK_Mediation)を参照してください。  ||
|A/AAAA   |仲介サーバーの FQDN   |サーバー IP アドレス   |仲介サーバーによって提供されるサービスを、フロント エンド サーバーまたはプールに対して併置することができます。 [仲介サーバー プールの DNS のロードバランシングを使用する](load-balancing.md#BK_Mediation)を参照してください。  ||
|A/AAAA   |永続的なチャット サーバーの FQDN   |永続的なチャット サーバーの IP アドレス   |常設チャット サーバーは、常設チャット機能のために必要ですが、それ以外の場合はオプションです。   ||
|A/AAAA   |lyncdiscoverinternal。* \<sipdomain\>* <br/> lyncdiscoverinternal。* <span> </span>contoso<span></span>.com*   |VIP の HLB のフロント エンド プールまたはディレクターの IP  <br/>  192.168.21.121  |内部自動検出サービス 1、モビリティのサポートに必要な。 モバイル デバイスを解決するのには、内部 DNS を使用する場合は、外部 ip アドレス、または DMZ の VIP をポイントする必要があります。  <br/> Web サービスに HTTPS は、DNS を利用できないとフロント エンド プールの HLB が必要です。 フロント エンド プールまたはディレクター プールがこれにする必要がありますが、HLB の VIP、または Standard edition サーバーまたはスタンドアロンのディレクター サーバーの通常の IP を解決します。   |Y   |
|CNAME   |lyncdiscoverinternal。* \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso<span></span>.com*   |HLB FE プールの FQDN またはディレクターの FQDN  <br/> Web 整数<span></span>contoso<span></span>.com   |内部の自動検出サービス 1 <br/> 必要に応じて、これを A レコードではなく CNAME として実装することができます。   ||
|A/AAAA   |sip。* \<sipdomain\>* <br/> sip。* <span> </span>contoso<span></span>.com*  |フロント エンド プールのサーバーの IP アドレス (または、各ダイレクタの IP アドレス)  <br/>  DNS LB *192.168.21.122 192.168.21.123 192.168.21.124*   |自動構成が必要には、[チュートリアルの Skype クライアントのビジネスのサービスを検索する](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)を参照してください。 <br/> 外部にあるクライアントとフロント エンド プールのサーバーまたは社内のネットワークでは、アクセス エッジ サービス上のディレクター サーバーをポイントするレコード   |& #x 2777 です。  |
|A/AAAA   |ucupdates と r2 です。* \<sipdomain\>* <br/> ucupdates と r2 です。* <span> </span>contoso<span></span>.com*  |HLB FE プール VIP またはディレクター プール HLB VIP、または SE/ディレクター サーバー IP  <br/>  192.168.21.121  |オプションは、このレコードを展開する & #x 2778 です。  ||
|SRV   |\_sipinternaltls。\_tcp です。* \<sipdomain\> * <br/>ポート 5061 <br/>\_sipinternaltls。\_tcp です。* <span> </span>contoso<span></span>.com* <br/>ポート 5061  |フロント エンド プールの FQDN  <br/>*FE のプールです。<span> </span>contoso<span></span>.com*  |サインインについてのクライアントの要求を認証およびリダイレクトするフロントエンド サーバー/プールまたは SE サーバー/プールに対する内部ユーザーの自動サインイン 1 を有効にします。    |& #x 2777 です。 |
|A/AAAA |sipinternal。* \<sipdomain\>* <br/>sipinternal。<span> </span> *contoso<span></span>.com*  |フロント エンド プールの FQDN  <br/>_FE のプールです。<span> </span>contoso<span></span>.com_  |内部ユーザーのアクセス & #x 2776。  |& #x 2777 です。  |
|SRV   | \_ntp。\_udp です。* \<sipdomain\> * <br/> \_ntp。\_udp です。<span> </span> *contoso<span></span>.com*  |タイム サーバーの FQDN  <br/> north-america.pool.ntp.org   |Lync の電話のエディションのデバイスに必要な NTP ソース   |これがデスクトップの電話機をサポートするために必要です。   |
|SRV   |\_sipfederationtls。\_tcp です。* \<sipdomain\> * <br/>\_sipfederationtls。\_tcp です。<span> </span> *contoso<span></span>.com*  | アクセス エッジ サービスの FQDN <br/> EdgePool 整数<span></span>*contoso<span></span>.com*  |IOS または Windows Phone のモバイル クライアントが存在する各 SIP ドメインに対して、1 つの SRV レコードを作成します。   |モバイル クライアントのサポートの場合   |
|A/AAAA   |管理 URL  <br/>*Web 整数<span></span>contoso<span></span>.com*  |HLB FE プール VIP  <br/> 192.168.21.121   |Skype ビジネス サーバーのコントロール パネルは、[単純な Url](dns.md#BK_Simple)を参照してください。  ||
|A/AAAA   |会議 URL  <br/>*Web 整数<span></span>contoso<span></span>.com*  |HLB FE プール VIP  <br/> 192.168.21.121   |オンライン会議は、[単純な Url](dns.md#BK_Simple)を参照してください。  ||
|A/AAAA   |ダイヤルイン URL  <br/>*Web 整数<span></span>contoso<span></span>.com*  |HLB FE プール VIP  <br/> 192.168.21.121   |ダイヤルイン会議、[単純な Url](dns.md#BK_Simple)を参照してください。  ||
|A/AAAA   |内部 Web サービスの FQDN  <br/>*Web 整数<span></span>contoso<span></span>.com*  |HLB FE プール VIP  <br/> 192.168.21.121   |Skype ビジネス Web アプリケーションのために使用するビジネス Web サービスの Skype   ||
|A/AAAA   |Office Web アプリケーション サーバー プールの FQDN  <br/> OWA。<span> </span>contoso<span></span>.com   | Office Web アプリケーション サーバー プールの VIP アドレス <br/> 192.168.1.5   |Office Web アプリケーション サーバー プールの FQDN を定義します。   ||
|A/AAAA   |  内部 Web の FQDN <br/> Web 整数<span></span>contoso<span></span>.com   | フロント エンド プールの VIP アドレス <br/> 192.168.21.121   |Skype ビジネス Web アプリケーションのために使用する内部 Web FQDN を定義します。  <br/> このプールで DNS 負荷分散を使用する場合は、フロントエンド プールと内部 Web ファームで同じ FQDN を使用することはできません。   ||

& #x 2776。フロント エンド サーバーまたはフロント エンド プールを検出し、認証およびユーザーとしてサインインするのには、クライアントによって使用されます。 これの詳細については、[チュートリアルの Skype クライアントのビジネスのサービスを検索するの](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)には。

& #x 2777 です。これは、Lync 2013、およびデスクトップの電話機の前にレガシ クライアントをサポートするためにのみ必要です。

& #x 2778 です。統合コミュニケーション デバイスがオンですが、デバイスに、ユーザーがログオンしない場合では、A レコードは、デバイス更新 Web サービスをホストするサーバーを検出し、更新プログラムを入手するのにはデバイスを使用できます。 この方法を使用しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてサーバー情報を取得します。

次のダイアグラムでは、内部および外部 DNS レコードの両方を含んでいる場合の例と、周囲のテーブル内に数多くのレコードを示しています。

**パブリック IPv4 アドレスを使用したエッジ ネットワーク ダイアグラム**

![DNS ネットワーク ダイアグラムの例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**境界ネットワークの DNS マッピング (内部および外部インターフェイスの両方) **

|レコードの種類|値|解決先|用途|必須|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |内部エッジ プールの FQDN  <br/>*EdgePool 整数<span></span>contoso<span></span>.com*  |内部に接続するエッジ プールの IP アドレス  <br/> 172.25.33.10、172.25.33.11   |統合エッジ プールの内部インターフェイスの IP アドレス   |Y   |
|A/AAAA   |エッジ サーバーの FQDN  <br/>*短所-1。<span> </span>contoso<span></span>.com*  |エッジ プール内のサーバーの内部に接続するサーバーの ip アドレス  <br/> 172.25.33.10   |レコードを作成するサーバーの FQDN をプール内のサーバーごとに、プール内の内部サーバー ノードの IP を指す参照してください[にエッジ サーバー プールの DNS 負荷分散](load-balancing.md#BK_Edge)します。   |Y   |
|A/AAAA   |アクセス エッジ サービス プールの FQDN  <br/>*Access1。<span> </span>contoso<span></span>.com*  |アクセス エッジ サービス プールの外部 IP アドレス  <br/> 131.107.16.10、131.107.16.11   |アクセス エッジ サービスは、セッション開始プロトコル (SIP) トラフィックの送信と受信の両方に単一の信頼された接続ポイントを提供します。   |Y   |
|A/AAAA   |Web 会議エッジ サービス プールの FQDN  <br/>*Webcon1。<span> </span>contoso<span></span>.com*  |Web 会議エッジ サービスの外部 IP アドレスします。  <br/> 131.107.16.90、131.107.16.91   |Web 会議エッジ サービス、外部、内部の Skype ビジネス サーバー環境でホストされている会議に参加できます。   |Y   |
|A/AAAA   |*av.\<sip ドメイン\>* プールの FQDN <br/>*AV1。<span> </span>contoso<span></span>.com*  |音声ビデオ エッジ外部 IP アドレス  <br/> 131.107.16.170、131.107.16.171   |A とは、音声ビデオ エッジ サービスでは、オーディオ、ビデオ、アプリケーション共有、およびファイルは、外部で使用できるユーザーを転送します。   |Y   |
|CNAME   |sip。* \<sipdomain\>* <br/> sip。* <span> </span>contoso<span></span>.com*  |外部アクセス エッジ プールの FQDN  <br/>*Access1。<span> </span>contoso<span></span>.com*  |エッジ サーバー プールを検索します。 [チュートリアルの Skype クライアントのビジネスのサービスを検索する](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)を参照してください。  |Y   |
|SRV   |\_sip。\_tls です。* \<sipdomain\> * <br/>\_sip。\_tls です。<span> </span> *contoso<span></span>.com*  |FQDN の外部アクセス エッジ  <br/>_Access1。<span> </span>contoso<span></span>.com_  |外部ユーザー アクセスのために使用されます。 [チュートリアルの Skype クライアントのビジネスのサービスを検索する](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)を参照してください。  |Y   |
|SRV   |\_sipfederationtls。\_tcp です。* \<sipdomain\> * <br/>\_sipfederationtls。\_tcp です。<span> </span> *contoso<span></span>.com*  |FQDN の外部アクセス エッジ  <br/>*Access1。<span> </span>contoso<span></span>.com*  |フェデレーションとパブリック IM 接続で使用されます   |& #x 2776。  |
|SRV   |\_xmpp サーバーです。\_tcp です。*<sipdomain\> * <br/>\_xmpp サーバーです。\_tcp です。* <span> </span>contoso<span></span>.com*  |FQDN の外部アクセス エッジ  <br/>*Access1。<span> </span>contoso<span></span>.com*  |XMPP プロキシ サービスを受け入れるし、構成された XMPP フェデレーション パートナーとの間に、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) メッセージを送信します。   |フェデレーションの展開のために必要です。それ以外の場合はオプションです  <br/> ビジネス サーバー 2019 の Skype では使用できません。|
|SRV   |\_sipfederationtls。\_tcp です。* \<sipdomain\> * <br/>\_sipfederationtls。\_tcp です。* <span> </span>contoso<span></span>.com*  |FQDN の外部アクセス エッジ  <br/>*Access1。<span> </span>contoso<span></span>.com*  |プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、SIP ドメインごとに 1 つの SRV レコードを作成します。 & #x 2778 です。  ||
|A/AAAA   |フロント エンド プールの外部の web サービスの FQDN  <br/>*Web 内線<span></span>contoso<span></span>.com*  |リバース プロキシのパブリック IP アドレス、プロキシの外部 Web サービス用の VIP、フロント エンド プール & #x 2776。 <br/> 131.107.155.1 プロキシ 192.168.21.120   |フロント エンド プールの外部インターフェイスが Skype ビジネス Web アプリケーションの使用   |Y   |
|A/AAAA/CNAME   |lyncdiscover。* \<sipdomain\>* <br/> lyncdiscover。* <span> </span>contoso<span></span>.com*  |リバース プロキシのパブリック IP アドレスをディレクター プールの外部 Web サービスの VIP に解決を持っている場合、またはフロント エンド プールの場合ディレクター & #x 2777; する必要はありません。 <br/> 131.107.155.1 プロキシ 192.168.21.120   | リバース プロキシ サーバーによってクライアントの外部のレコード移動性、ビジネスの Web アプリケーション、およびスケジューラ Web アプリケーションでは、Skype で使用しても、自動検出の解決 <br/> 、プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync のモバイル クライアントが存在する SIP ドメインごとに 1 つの SRV レコードを作成します。 3  |Y   |
|A/AAAA   |対応します。* \<sipdomain\>* <br/> 対応します。* <span> </span>contoso<span></span>.com*  |リバース プロキシのパブリック IP アドレス、フロント エンド プールの外部 Web インターフェイスへの解決  <br/> 131.107.155.1 プロキシ 192.168.21.120   |Skype ビジネス Web サービスのプロキシ  <br/> [単純な Url](dns.md#BK_Simple)を参照してください。  |Y   |
|A/AAAA   |ダイヤル部分は*\<sipdomain\>* <br/> ダイヤル部分は*<span></span>contoso<span></span>.com*  |プロキシのパブリック IP アドレスを逆にフロント エンド プールの外部 Web インターフェイスへのプロキシ  <br/> 131.107.155.1 プロキシ 192.168.21.120   |Skype ビジネス Web サービスのプロキシ  <br/> [単純な Url](dns.md#BK_Simple)を参照してください。  |Y   |
|A/AAAA   |Office Web アプリケーション サーバー プールの FQDN  <br/> OWA。<span> </span>contoso<span></span>.com   | リバース プロキシのパブリック IP アドレス、オフィスの Web アプリケーション サーバーの外部の Web インターフェイスのプロキシ <br/> 131.107.155.1 は 192.168.1.5 にプロキシ   | Office Web アプリケーション サーバー プールの VIP アドレス <br/> 192.168.1.5   |Office Web アプリケーション サーバー プールの FQDN を定義します。   |

& #x 2776。フェデレーションでは、それ以外はオプションの展開に必要です。

& #x 2777 です。フロント エンド サーバーまたはフロント エンド プールを検出し、認証およびユーザーとしてサインインするのには、クライアントによって使用されます。

& #x 2778 です。この要件は、Apple のクライアントにのみ適用されます。 または、Microsoft ベースのモバイル デバイスです。 Android および Nokia Symbian デバイスはプッシュ通知を使用しません。

 エッジ トランスポート サーバーおよび境界ネットワークの詳細については、エッジ サーバーの[DNS の計画](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)の内容を参照してください。

> [!IMPORTANT]
> Skype ビジネス サーバーの IPv6 アドレスの使用をサポートします。 詳細については、[Plan for IPv6 in Skype for Business](ipv6.md)を参照してください。

> [!IMPORTANT]
> FQDN の詳細については、[DNS basics](basics.md)を参照してください。 

**スプリット ・ ブレイン DNS** 
 <a name="BK_split"> </a>

スプリット ブレイン DNSは、2 つの DNS ゾーンが同じ名前空間に存在する DNS 構成です。 表内で述べられているように、一方の DNS ゾーンは内部要求のみ、他方の DNS ゾーンは外部要求のみを処理します。 詳細については、[スプリットブレイン DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS) を参照してください。

## <a name="hybrid-considerations"></a>ハイブリッドの考慮事項
<a name="BK_Hybrid"> </a>

計画する場合は、一部のユーザーがオンライン ホームし、いくつかの上にホームが設置されている型は、[ビジネス サーバー 2019 の Skype](../../../SfBServer2019/hybrid/plan-hybrid-connectivity.md)の記事を計画するハイブリッド接続を参照してください。 ビジネス サーバー 2015 の Skype の通常の方法で DNS を構成し、またその他の DNS レコードを追加する必要があります。

ある「Office 365 の Url と IP アドレスの範囲」を参照することもする必要があります[https://aka.ms/o365ips](https://aka.ms/o365ips)ユーザーが必要なオンライン リソースへアクセスを持つことを確認します。

## <a name="simple-urls"></a>簡易 URL 
<a name="BK_Simple"> </a>

URL (Uniform Resource Locator) は、Web リソースに対する参照として、そのコンピューター ネットワーク上の場所と、それを取得するために使用されるプロトコルを指定します。 

ビジネス サーバーの Skype では、サービスにアクセスするのには「単純」の 3 つの Url を使用してサポートしています。

- **会議 ** URL は、サイト内のすべての会議のベース URL として使用されます。 対応の簡単な URL の例としては、https:<span></span>//<span></span>に対応します。<span> </span>contoso<span></span>. com です。 特定の会議の URL が https をする可能性があります:<span></span>//<span></span>に対応します。<span> </span>contoso<span></span>.com//7322994 である_ユーザー名_。

    会議の簡易 URL により、会議に参加するためのリンクが覚えやすいものになり、通知も簡単に行えます。

- **ダイヤルイン ** URL を使用すると、[ダイヤルイン会議の設定] Web ページにアクセスできます。 このページには、使用可能な言語、割り当て済み会議情報 (すなわち、スケジュールされる必要がない会議用)、および会議内 DTMF コントロールと組み合わされた会議のダイヤルイン番号が表示されます。また、暗証番号 (PIN) および割り当て済みの会議情報の管理をサポートします。 ダイヤルインの簡易 URL は、すべての会議への招待に含まれるため、会議にダイヤルインするユーザーは、必要な電話番号および PIN 情報にアクセスできます。 ダイヤルの簡単な URL の例としては、https://<span></span>ダイヤルインします。<span> </span>contoso<span></span>. com です。

- **管理者**は、業務サーバーのコントロール パネルの Skype へのすばやいアクセスを使用できます。 組織のファイアウォール内の任意のコンピューターから管理者が開くことができます、Skype ビジネス サーバーのコントロール パネルの管理の簡単な URL をブラウザーに入力することによって。 管理の簡易 URL は、組織内部の URL です。 管理の簡単な URL の例としては、https://<span></span>管理者<span> </span>contoso<span></span>. com です。

Url の単純な[ビジネス サーバーの Skype での簡単な Url の DNS 要件](simple-urls.md)の詳細については後ほど説明します。

## <a name="dns-by-server-role"></a>サーバー ロール別の DNS
<a name="BK_Servers"> </a>

これらのプールおよびサーバーの名前を自由に設定することができます。ただし、システム内での機能を反映した、覚えやすい名前にすることをお勧めします。

### <a name="dns-records-for-individual-servers-or-pools"></a>個別サーバーまたはプールの DNS レコード

これらのレコードの一般的な要件は、ビジネスのため、Skype で使用されるサーバーの役割に適用されます。 プールは、ロード バランサーを通してサーバーに向けられるクライアントの要求を処理するために連動する同じサービスを実行しているサーバーの集まりです。 詳細については、[Load balancing requirements for Skype for Business](load-balancing.md)を参照してください。

**サーバー/プールのロールでの DNS レコードの要件 (DNS 負荷分散を想定)**

|展開シナリオ|DNS 要件|
|:-----|:-----|
|1 台のサーバー:  <br/> 常設チャット、ディレクター、仲介サーバー、フロント エンド サーバー   |サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。  <br/> ServerRole。<span> </span>contoso<span></span>.com 10.10.10.0   |
|プール:  <br/> 常設チャット、ディレクター、エッジ サーバー、仲介サーバー、フロント エンド    |プール内の各サーバー ノードの完全修飾ドメイン名 (FQDN) を、その IP アドレスに解決する内部 A レコード。  <br/>**例** <br/> ServerRole01。<span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerRole02。<span> </span>contoso<span></span>.com 10.10.10.2  <br/> プールの完全修飾ドメイン名 (FQDN) を、プールのサーバー ノードの IP アドレスに解決する複数の内部 A レコード。  <br/>**例** <br/> ServerPool。<span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerPool。<span> </span>contoso<span></span>.com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>エッジ サーバー固有の DNS に関するトピック

 エッジ サーバーの展開を計画するには、「[ビジネス サーバー 2015 の Skype でエッジ サーバーの展開の計画](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)、および[エッジ サーバーの高度な DNS 計画ビジネス サーバー 2015 の Skype](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)は以下のセクションでの使用」を参照してください。

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [スプリットブレイン DNS なしの自動構成](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [スプリット ブレイン DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


