---
title: Skype for Business Server の DNS 要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: '概要: Skype for Business Server を実装する前に、このトピックの DNS の考慮事項を確認してください。'
ms.openlocfilehash: 33c5e18c6bc8d5a29b0e4a6fa447fbde02028556
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982812"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Skype for Business Server の DNS 要件

**概要:** Skype for Business Server を実装する前に、このトピックの DNS の考慮事項を確認してください。

この記事では、組織のオンプレミスネットワーク上の Skype for Business Server 展開の DNS 計画についてのみ取り上げます。 Skype for Business Online の場合は、「Office 365 の Url と IP アドレスの[https://aka.ms/o365ips](https://aka.ms/o365ips)範囲」を参照してください。

ドメインネームサービス (DNS) サーバーは、ホスト名 (www など<span></span> ) をマップします。IP<span></span>アドレス (10.10.10.10 など) に対して、contoso .com が web サーバーであると思われます。 これにより、クライアントと相互依存するサーバーがネットワーク上で相互に通信できるようになります。 Skype for Business Server 2015 の実装をセットアップする場合は、新しいサーバー名 (通常、ユーザーが実行する役割を反映) のマッピングが、割り当てられている IP アドレスと一致していることを確認する必要があります。

これは最初は少し困難に思えるかもしれませんが、これを計画するには、 [Skype For Business Server 2015 計画ツール](https://www.microsoft.com/download/details.aspx?id=50357)を使用して行うことができます。 使用する予定の機能に関するウィザードの質問について説明した後、定義した各サイトに対してエッジ管理レポート内で DNS レポートを表示し、そこに記載されている情報を使用して DNS レコードを作成することができます。 また、使用する名前と IP アドレスの多くを調整することもできます。詳細については、「 [Review THE DNS Report](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)」を参照してください。 エッジ管理レポートは、Excel スプレッドシートにエクスポートすることができ、DNS レポートはファイル内のワークシートの1つになることに注意してください。 このツールには、 [Skype For Business Server 2019 から非推奨](../../../SfBServer2019/deprecated.md)になった機能が含まれていますが、これらの機能が選択されていない場合は、初期プランを作成するために引き続き使用できます。

「 [Skype for Business server の dns レコードを作成](../../deploy/install/create-dns-records.md)する」および「skype For business server のトポロジを構築する」の説明に従って新しい実装をインストールする場合、Windows Server 2016 またはサードパーティの dns パッケージに組み込まれた dns 機能を使用することを選択できるので、この記事では、具体的にはなく、この記事に記載されている 必要なものを詳細に説明しています。また、そのニーズを満たす方法を決定することをお勧めします。

熟練した Skype for Business、Lync、および Office Communications Suite 管理者は、次の表を参考にしてください。 表が混乱している場合は、後のセクションや記事では、次の概念についていくつかの点について説明します。

## <a name="summary-tables"></a>サマリーテーブル
<a name="BK_Summary"> </a>

次の表に、Skype for Business Server がユーザーにサービスを提供するために使用する DNS レコードを示します。 一部の機能は特定の機能をサポートするためにのみ必要であり、それらの機能を必要としない場合は省略できます。 内部アクセスのみに必要な DNS レコードは最初のテーブルにあり、内部および外部アクセスを許可する展開では、両方のテーブルのレコードが必要になります。

**内部 DNS マッピング**

|レコードの種類|値|解決先|用途|必須|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |フロントエンドプールの FQDN  <br/> *FE プール。<span> </span>contoso<span></span>.com*   |フロントエンドプールサーバーの IP アドレス  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |フロントエンドプールの DNS 負荷分散。 フロントエンドプール名を一連の IP アドレスにマップします。  <br/> 「[フロントエンドプールとディレクタープールで DNS 負荷分散を展開](load-balancing.md#BK_FE_Dir)する」を参照してください。  |Y   |
|A/AAAA   | プール内の各フロントエンドサーバーまたは Standard Edition サーバー、またはスタンドアロンサーバーの FQDN <br/>  *FE01.<span> </span>contoso。<span> </span>com FE02。<span> </span>CONTOSO<span></span>.com FE03<span> </span>contoso<span></span>.com*   |各サーバーの対応する IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |サーバー名を IP アドレスにマップします。   |Y   |
|A/AAAA   |エンタープライズプール内部 Web サービスの上書き FQDN  <br/> *Web-int-13<span></span><span></span>*   |フロントエンドサーバーの内部 Web サービスの HLB VIP  <br/> *192.168.21.120*   |Skype for Business Web App のダウンロードなど、クライアントからサーバーへの web トラフィックを有効にするために必要です。 モバイルクライアントにも必要です。   |Y   |
|A/AAAA   |エンタープライズプールの外部 Web サービスの上書き FQDN  <br/> *Web 外部<span></span><span></span>-.com*   |フロントエンドサーバーの外部 Web サービスの HLB VIP  <br/>*68.123.56.90*   |Skype for Business Web App のダウンロードなど、クライアントからサーバーへの web トラフィックを有効にするために必要です。 モバイルクライアントが内部で DNS を解決する場合に必要です。 DMZ のリバースプロキシ IP またはインターネット IP に解決できます。   ||
|A/AAAA   | バックエンドサーバーの SQL Server の FQDN <br/> *SQL1.<span> </span>contoso<span></span>.com*   |サーバー IP アドレス  <br/> *192.168.11.90*   |フロントエンドプールを使用して作業しているバックエンド SQL server のサーバー名を、その IP アドレスにマップします。   ||
|A/AAAA   |バックエンドサーバーミラーの SQL Server の FQDN  <br/> *: Sql2.<span> </span>contoso<span></span>.com*   |サーバー IP アドレス  <br/> *192.168.11.91*   |フロントエンドプールを使用するバックエンド SQL ミラーサーバーのサーバー名を、その IP アドレスにマップします。   ||
|A/AAAA   |ディレクタープールの FQDN  <br/>**注:** スタンドアロンのディレクターサーバーを使用している場合は該当しない <br/> *DirPool。<span> </span>contoso<span></span>.com*   |ディレクタープールの IP アドレス  <br/> DNS LB to*で先, 192.168.21.133, 192.168.21.134*   |ディレクタープールサーバーの DNS 負荷分散。 ディレクタープールのプール名を IP アドレスにマップするには、「[フロントエンドプールとディレクタープールで DNS 負荷分散を展開](load-balancing.md#BK_FE_Dir)する」を参照してください。 <br/> ディレクターは、ユーザーを認証でき、オプションです。   ||
|A/AAAA   |ディレクター FQDN   |各ディレクターサーバーのサーバー IP アドレス   |ディレクターのプール名を IP アドレスにマップするには、「[フロントエンドプールとディレクタープールに DNS 負荷分散を展開](load-balancing.md#BK_FE_Dir)する」を参照してください。  ||
|A/AAAA   |仲介サーバープールの FQDN   |プール IP アドレス   |仲介サーバーの役割はオプションです。 仲介サーバーによって提供されるサービスを、フロントエンドサーバーまたはプールに併置することができます。 「[仲介サーバープールで DNS 負荷分散を使用する」を](load-balancing.md#BK_Mediation)参照してください。  ||
|A/AAAA   |仲介サーバーの FQDN   |サーバー IP アドレス   |仲介サーバーによって提供されるサービスを、フロントエンドサーバーまたはプールに併置することができます。 「[仲介サーバープールで DNS 負荷分散を使用する」を](load-balancing.md#BK_Mediation)参照してください。  ||
|A/AAAA   |常設チャットサーバーの FQDN   |常設チャットサーバーの IP アドレス   |常設チャットサーバーは、常設チャットの機能に必要ですが、それ以外の場合はオプションです。   ||
|A/AAAA   |lyncdiscoverinternal.* \<microsoft.rtc.management.xds.sipdomain\>* <br/> lyncdiscoverinternal.* <span> </span>contoso<span></span>.com*   |HLB フロントエンドプール VIP またはディレクター IP  <br/>  192.168.21.121  |内部自動検出 Service1。モビリティのサポートに必要です。 内部 DNS を使用してモバイルデバイスを解決する場合は、外部 IP または DMZ VIP をポイントする必要があります。  <br/> Web サービスでは、フロントエンドプールでは、HTTPS が DNS を利用できないため、HLB を必要とします。 フロントエンドプールまたはディレクタープールの場合、これは HLB VIP、または Standard edition サーバーまたはスタンドアロンディレクターサーバーの正規の IP に解決されます。   |Y   |
|CNAME   |lyncdiscoverinternal.* \<microsoft.rtc.management.xds.sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso<span></span>.com*   |HLB FE プールの FQDN またはディレクターの FQDN  <br/> Web-int-13<span></span><span></span>   |内部自動検出 Service1 <br/> 必要に応じて、これを A レコードではなく CNAME として実装することができます。   ||
|A/AAAA   |sip.* \<microsoft.rtc.management.xds.sipdomain\>* <br/> sip.* <span> </span>contoso<span></span>.com*  |フロントエンドプールサーバーの IP アドレス (または各ディレクターの IP アドレス)  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |自動構成では必須。「 [Skype For business クライアントのウォークスルーサービスの検索](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)」を参照してください。 <br/> 内部ネットワーク上のフロントエンドプールサーバーまたはディレクターサーバー、またはクライアントが外部にある場合はアクセスエッジサービスを指すレコードまたはレコード   |&#x2777;  |
|A/AAAA   |ucupdates-r2。* \<microsoft.rtc.management.xds.sipdomain\>* <br/> ucupdates-r2。* <span> </span>contoso<span></span>.com*  |HLB FE プール VIP またはディレクタープール HLB VIP、または SE/ディレクターサーバー IP  <br/>  192.168.21.121  |このレコードの展開はオプション &#x2778;  ||
|SRV   |\_sipinternaltls.\_tcp。* \<microsoft.rtc.management.xds.sipdomain\> * <br/>ポート5061 <br/>\_sipinternaltls.\_tcp。* <span> </span>contoso<span></span>.com* <br/>ポート5061  |フロントエンドプールの FQDN  <br/>*FE プール。<span> </span>contoso<span></span>.com*  |サインインのためのクライアント要求を認証およびリダイレクトするフロントエンドサーバー/プールまたは SE サーバー/プールに対する内部ユーザーの自動サインイン1を有効にします。  |&#x2777; |
|A/AAAA |sipinternal.* \<microsoft.rtc.management.xds.sipdomain\>* <br/>sipinternal.<span> </span> *contoso<span></span>.com*  |フロントエンドプールの FQDN  <br/>_FE プール。<span> </span>contoso<span></span>.com_  |内部ユーザーアクセス &#x2776;  |&#x2777;  |
|SRV   | \_ntp.\_udp。* \<microsoft.rtc.management.xds.sipdomain\> * <br/> \_ntp.\_udp。<span> </span> *contoso<span></span>.com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync Phone Edition デバイスに必要な NTP ソース   |これは、デスクトップハンドセットをサポートするために必要です。   |
|SRV   |\_sipfederationtls.\_tcp。* \<microsoft.rtc.management.xds.sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span> </span> *contoso<span></span>.com*  | アクセスエッジサービスの FQDN <br/> EdgePool-int-13<span></span>*<span></span>*  |IOS または Windows phone モバイルクライアントがある SIP ドメインごとに1つの SRV レコードを作成します。   |モバイルクライアントのサポート   |
|A/AAAA   |管理 URL  <br/>*Web-int-13<span></span><span></span>*  |HLB FE プール VIP  <br/> 192.168.21.121   |Skype for Business Server コントロールパネル、「 [Simple URLs](dns.md#BK_Simple) 」を参照  ||
|A/AAAA   |会議 URL  <br/>*Web-int-13<span></span><span></span>*  |HLB FE プール VIP  <br/> 192.168.21.121   |オンライン会議。「 [Simple URLs](dns.md#BK_Simple) 」を参照  ||
|A/AAAA   |ダイヤルイン URL  <br/>*Web-int-13<span></span><span></span>*  |HLB FE プール VIP  <br/> 192.168.21.121   |ダイヤルイン会議 ([簡易 url](dns.md#BK_Simple)を参照)  ||
|A/AAAA   |内部 Web サービスの FQDN  <br/>*Web-int-13<span></span><span></span>*  |HLB FE プール VIP  <br/> 192.168.21.121   |Skype for business Web App で使用されている skype for Business Web サービス   ||
|A/AAAA   |Office Web Apps サーバープールの FQDN  <br/> OWA.<span> </span>contoso<span></span>.com   | Office Web Apps サーバープール VIP アドレス <br/> 192.168.1.5   |Office Web Apps サーバープールの FQDN を定義します。   ||
|A/AAAA   | 内部 Web FQDN <br/> Web-int-13<span></span><span></span>   | フロントエンドプールの VIP アドレス <br/> 192.168.21.121   |Skype for Business Web App で使用される内部 Web FQDN を定義します。  <br/> このプールで DNS 負荷分散を使用している場合は、フロントエンドプールと内部 web ファームの FQDN を同じにすることはできません。   ||

クライアントによって使用され、フロントエンドサーバーまたはフロントエンドプールを検出し、ユーザーとして認証およびサインインを行います。 &#x2776;。 詳細については、「 [Skype For business クライアントを使用したサービスの検索](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)」を参照してください。

&#x2777; これは、Lync 2013 および desktop ハンドセットよりも前にレガシクライアントをサポートするためにのみ必要です。

&#x2778; 統合コミュニケーションデバイスが有効になっているが、ユーザーがデバイスにログインしたことがない場合は、A レコードによってデバイス更新 Web サービスをホストしているサーバーを検出し、更新を取得することができます。 この方法を実行しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてサーバー情報を取得します。

次の図は、内部および外部の DNS レコードと、周囲のテーブルに表示されるレコードの多くを含む例を示しています。

**パブリック IPv4 アドレスを使用したエッジネットワーク図**

![DNS ネットワーク図の例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**境界ネットワークの DNS マッピング (内部インターフェイスと外部インターフェイスの両方)**

|レコードの種類|値|解決先|用途|必須|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |内部エッジプールの FQDN  <br/>*EdgePool-int-13<span></span><span></span>*  |内部接続エッジプールの IP アドレス  <br/> 172.25.33.10、172.25.33.11 が   |統合エッジプールの内部インターフェイスの IP アドレス   |Y   |
|A/AAAA   |エッジサーバーの FQDN  <br/>*-1。<span> </span>contoso<span></span>.com*  |エッジプール内のサーバーの内部接続サーバー IP  <br/> 172.25.33.10   |プール内の各サーバーのレコードを作成する。サーバーの FQDN がプール内の内部サーバーノード IP を指している場合は、「 [DNS 負荷分散のエッジサーバープール](load-balancing.md#BK_Edge)」を参照してください。   |Y   |
|A/AAAA   |アクセスエッジサービスプールの FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |アクセスエッジサービスプールの外部 IP アドレス  <br/> 131.107.16.10, 131.107.16.11   |アクセス エッジ サービスは、セッション開始プロトコル (SIP) の送受信トラフィック用の、信頼される単一の接続ポイントです。   |Y   |
|A/AAAA   |Web 会議エッジサービスプールの FQDN  <br/>*Webcon1.<span> </span>contoso<span></span>.com*  |Web 会議エッジサービスの外部 IP アドレス  <br/> 131.107.16.90, 131.107.16.91   |Web 会議エッジサービスを使用すると、外部ユーザーは、内部の Skype for Business Server 環境でホストされている会議に参加できます。   |Y   |
|A/AAAA   |*av-ドメイン\> \<* プールの FQDN <br/>*AV1.<span> </span>contoso<span></span>.com*  |音声ビデオエッジの外部 IP アドレス  <br/> 131.107.16.170, 131.107.16.171   |音声ビデオエッジサービスを使用すると、オーディオ、ビデオ、アプリケーション共有、およびファイル転送が外部ユーザーに対して使用可能になります。   |Y   |
|CNAME   |sip.* \<microsoft.rtc.management.xds.sipdomain\>* <br/> sip.* <span> </span>contoso<span></span>.com*  |外部アクセスエッジプールの FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |エッジサーバープールを検索します。 [サービスの検索の詳細については、「Skype For business クライアントのチュートリアル」を](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)ご覧ください。  |Y   |
|SRV   |\_sip.\_tls。* \<microsoft.rtc.management.xds.sipdomain\> * <br/>\_sip.\_tls。<span> </span> *contoso<span></span>.com*  |外部アクセスエッジの FQDN  <br/>_Access1.<span> </span>contoso<span></span>.com_  |外部ユーザーアクセスに使用されます。 [サービスの検索の詳細については、「Skype For business クライアントのチュートリアル」を](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)ご覧ください。  |Y   |
|SRV   |\_sipfederationtls.\_tcp。* \<microsoft.rtc.management.xds.sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span> </span> *contoso<span></span>.com*  |外部アクセスエッジの FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |フェデレーションとパブリック IM 接続に使用   |&#x2776;  |
|SRV   |\_xmpp-サーバー。\_tcp。*<microsoft.rtc.management.xds.sipdomain\> * <br/>\_xmpp-サーバー。\_tcp。* <span> </span>contoso<span></span>.com*  |外部アクセスエッジの FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |XMPP プロキシサービスは、構成された XMPP フェデレーションパートナーとの間で、拡張可能な messaging およびプレゼンスプロトコル (XMPP) メッセージを送受信します。   |フェデレーションを展開する場合は Y、省略可能な場合はオプション  <br/> Skype for Business Server 2019 では使用できません。|
|SRV   |\_sipfederationtls.\_tcp。* \<microsoft.rtc.management.xds.sipdomain\> * <br/>\_sipfederationtls.\_tcp。* <span> </span>contoso<span></span>.com*  |外部アクセスエッジの FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、SIP ドメインごとに1つの SRV レコードを作成します。 &#x2778;  ||
|A/AAAA   |外部フロントエンドプール web サービスの FQDN  <br/>*Web 外部<span></span><span></span>-.com*  |リバースプロキシのパブリック IP アドレス、フロントエンドプールの外部 Web サービス VIP へのプロキシ &#x2776; <br/> 131.107.155.1 プロキシから192.168.21.120   |Skype for Business Web App で使用されるフロントエンドプールの外部インターフェイス   |Y   |
|A/AAAA/CNAME   |lyncdiscover.* \<microsoft.rtc.management.xds.sipdomain\>* <br/> lyncdiscover.* <span> </span>contoso<span></span>.com*  |リバースプロキシのパブリック IP アドレス。ディレクタープールの外部 Web サービス VIP、またはディレクターを持っていない場合はフロントエンドプールに対して解決され &#x2777; <br/> 131.107.155.1 プロキシから192.168.21.120   | クライアント自動検出の外部レコード。モビリティ、Skype for Business Web App、およびスケジューラ Web アプリでも使用され、リバースプロキシサーバーによって解決されます。 <br/> プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync Mobile クライアントが存在する各 SIP ドメインに対して1つの SRV レコードを作成します。 3   |Y   |
|A/AAAA   |満たせ.* \<microsoft.rtc.management.xds.sipdomain\>* <br/> 満たせ.* <span> </span>contoso<span></span>.com*  |リバースプロキシのパブリック IP アドレス。フロントエンドプールの外部 Web インターフェイスに解決されます。  <br/> 131.107.155.1 プロキシから192.168.21.120   |Skype for business Web サービスへのプロキシ  <br/> [簡易 url](dns.md#BK_Simple)を参照  |Y   |
|A/AAAA   |ダイヤルイン*\<microsoft.rtc.management.xds.sipdomain\>* <br/> ダイヤルイン*<span></span><span></span>.com*  |リバースプロキシのパブリック IP アドレス、フロントエンドプールの外部 Web インターフェイスへのプロキシ  <br/> 131.107.155.1 プロキシから192.168.21.120   |Skype for business Web サービスへのプロキシ  <br/> [簡易 url](dns.md#BK_Simple)を参照  |Y   |
|A/AAAA   |Office Web Apps サーバープールの FQDN  <br/> OWA.<span> </span>contoso<span></span>.com   | リバースプロキシのパブリック IP アドレス、Office Web Apps サーバーの外部 Web インターフェイスへのプロキシ <br/> 131.107.155.1 プロキシから192.168.1.5   | Office Web Apps サーバープール VIP アドレス <br/> 192.168.1.5   |Office Web Apps サーバープールの FQDN を定義します。   |

&#x2776; は、フェデレーションを展開するために必要です。それ以外の場合はオプションです。

クライアントによって使用され、フロントエンドサーバーまたはフロントエンドプールを検出し、ユーザーとして認証およびサインインを行います。 &#x2777;。

&#x2778; この要件は、Apple または Microsoft ベースのモバイルデバイス上のクライアントにのみ適用されます。 Android および Nokia Symbian デバイスでは、プッシュ通知は使用されません。

 エッジサーバーと境界ネットワークの詳細については、「エッジサーバーの[DNS 計画](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)のコンテンツ」を参照してください。

> [!IMPORTANT]
> Skype for Business Server は、IPv6 アドレスの使用をサポートしています。 詳細については、「 [Skype For business で IPv6 を計画](ipv6.md)する」を参照してください。

> [!IMPORTANT]
> Fqdn の詳細については、「 [DNS の基礎](basics.md)」を参照してください。

**スプリットブレイン DNS** 
 <a name="BK_split"> </a>

スプリットブレイン DNS は、同じ名前空間を持つ2つの DNS ゾーンがある DNS 構成です。 最初の DNS ゾーンは内部要求を処理し、2番目の DNS ゾーンは外部要求を処理します。これらの表に記載されています。 詳細については[、「スプリットブレイン DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)」を参照してください。

## <a name="hybrid-considerations"></a>ハイブリッドの考慮事項
<a name="BK_Hybrid"> </a>

一部のユーザーをオンラインにして、一部のオンプレミスをホームにする場合は、「 [Skype For business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」のハイブリッド接続の計画に関する記事を参照してください。 Skype for Business Server 2015 の場合は DNS を通常として構成し、さらに DNS レコードを追加する必要があります。

また、「Office 365 の Url と IP アドレスの範囲」を参照[https://aka.ms/o365ips](https://aka.ms/o365ips)して、ユーザーが必要とするオンラインリソースにアクセスできることを確認する必要があります。

## <a name="simple-urls"></a>簡易 URL
<a name="BK_Simple"> </a>

URL (Uniform Resource Locator) は、web リソースへの参照で、コンピューターネットワーク上の場所と、それを取得するために使用されるプロトコルを指定します。

Skype for Business Server は、3つの "単純な" Url を使用してサービスにアクセスすることをサポートしています。

- **Meet**は、サイト内のすべての電話会議のベース URL として使用されます。 簡単な会議 URL の例として、<span></span>//<span></span>https: meet があります。<span> </span>contoso<span></span>.com。 特定の会議の URL が https:<span></span>//<span></span>meet である場合があります。<span> </span>contoso<span></span>.com/_username_/7322994。

    会議への簡単な URL を使用すると、会議に参加するためのリンクを簡単に理解し、簡単に伝えることができます。

- **ダイヤル**インは、ダイヤルイン会議設定 web ページにアクセスできるようにします。 このページには、使用可能な言語で会議のダイヤルイン番号、割り当てられている会議情報 (スケジュールする必要がない会議の場合)、および会議中の DTMF コントロールを表示し、個人識別番号の管理をサポートしています (PIN) と割り当てられている会議情報。 ダイヤルインの簡易 URL は、すべての会議出席依頼に含まれているため、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。 ダイヤルインの簡易 URL の例としては<span></span>、Https://のダイヤルインがあります。<span> </span>contoso<span></span>.com。

- **管理者**は、Skype For Business Server コントロールパネルにすばやくアクセスできます。 管理者は、組織のファイアウォール内の任意のコンピューターから、管理者の簡易 URL をブラウザーに入力して、Skype for Business Server コントロールパネルを開くことができます。 簡単な管理 URL は、組織内部の URL です。 管理の簡易 URL の例として<span></span>は、https://admin があります。<span> </span>contoso<span></span>.com。

簡易 Url の詳細については、「 [Skype For Business Server の簡易 url の DNS 要件](simple-urls.md)」を参照してください。

## <a name="dns-by-server-role"></a>サーバーの役割による DNS
<a name="BK_Servers"> </a>

これらのプールおよびサーバーの名前を必要に応じて設定することができますが、システム内の機能をわかりやすくするために、これらのプールとサーバーを記憶するようにします。

### <a name="dns-records-for-individual-servers-or-pools"></a>個別のサーバーまたはプールの DNS レコード

これらの一般的なレコード要件は、Skype for Business で使用されるすべてのサーバーの役割に適用されます。 プールとは、同じサービスを実行していて、ロードバランサーを経由して送信されたクライアント要求を処理するサーバーの集合です。 詳細については、「 [Skype For business の負荷分散の要件](load-balancing.md)」を参照してください。

**サーバー/プールの役割の DNS レコード要件 (DNS 負荷分散を前提としています)**

|展開シナリオ|DNS 要件|
|:-----|:-----|
|1つのサーバー:  <br/> 常設チャット、ディレクター、仲介サーバー、フロントエンドサーバー   |サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。  <br/> ServerRole.<span> </span>contoso<span></span>.com 10.10.10.0   |
|Pool  <br/> 常設チャット、ディレクター、エッジサーバー、仲介サーバー、フロントエンド   |プール内の各サーバーノードの完全修飾ドメイン名 (FQDN) を、その IP アドレスに解決する内部 A レコード。  <br/>**例** <br/> ServerRole01.<span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerRole02.<span> </span>contoso<span></span>.com 10.10.10.2  <br/> プールの完全修飾ドメイン名 (FQDN) を、プール内のサーバーノードの IP アドレスに解決する複数の内部 A レコード。  <br/>**例** <br/> ServerPool。<span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerPool。<span> </span>contoso<span></span>.com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>エッジサーバー固有の DNS トピック

 エッジサーバーの展開を計画するには、「 [skype For Business server 2015 でのエッジサーバーの展開の計画](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)」および[「skype For business 2015 Server での高度なエッジサーバーの DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)の計画」 (次のセクションを参照) を参照してください。

- [DNS の障害復旧](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS 負荷分散](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [スプリットブレイン DNS なしの自動構成](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [スプリットブレイン DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [サービスを特定するための Skype for Business クライアントのチュートリアル](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


