---
title: サーバーの DNS 要件Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: このトピックの DNS に関する考慮事項を確認してから、このトピックをSkype for Business Server。'
ms.openlocfilehash: 9f9e06de1f90659308dfb07f66fdac98c24a330e031beac7c7531655120d49d1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289705"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>サーバーの DNS 要件Skype for Business Server

**概要:** このトピックの DNS に関する考慮事項を確認してから、Skype for Business Server。

この記事では、組織のオンプレミス ネットワークSkype for Business Server展開に関する DNS 計画についてのみ説明します。 オンラインSkype for Businessは、 で 「Office 365 URL と IP アドレス範囲」を参照してください [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) 。

ドメイン ネーム サービス (DNS) サーバーはホスト名 (www など) をマップします。 <span></span>contoso .com(おそらく Web サーバー) から <span></span> IP アドレス (10.10.10.10 など)。 クライアントと相互依存サーバーがネットワーク上で相互に通信するのに役立ちます。 Skype for Business Server 2015 の実装をセットアップする場合は、新しいサーバー名のマッピング (通常は役割を反映) が、割り当てられている IP アドレスと一致するようにする必要があります。

これは最初は少し気が重いように見えるかもしれないが、これを計画する重い持ち上げは[、2015](https://www.microsoft.com/download/details.aspx?id=50357)年の計画ツールを使用Skype for Business Server実行できます。 使用する予定の機能に関するウィザードの質問を確認したら、定義するサイトごとにエッジ管理レポート内で DNS レポートを表示し、ここに示す情報を使用して DNS レコードを作成できます。 使用する名前と IP アドレスの多くを調整することもできます。詳細については、「DNS レポートを確認 [する」を参照してください](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 エッジ管理レポートを別のスプレッドシートにエクスポートExcel、DNS レポートはファイル内のワークシートの 1 つになる場合に備えておきます。 このツール Skype for Business Serverには[、2019 年 2019](../../../SfBServer2019/deprecated.md)年から廃止された機能が含まれていますが、これらの機能が選択されていない場合でも、初期計画の作成に使用できます。

[「Skype for Business Server](../../deploy/install/create-dns-records.md)用 DNS レコードの作成」の説明に従って新しい実装をインストールし、Skype for Business Server のトポロジを構築する場合、Windows Server 2016 に組み込まれる DNS 機能またはサードパーティの DNS パッケージを使用することを選択できると認識しています。 必要な情報と、そのニーズを満たす方法について詳しく説明します。

コミュニケーション スイートSkype for Business Lync、および Office経験豊富な管理者は、次の表が役に立つ可能性があります。 テーブルがわかりにくい場合は、以降のセクションまたは記事で、次の概念に光が当たっています。

## <a name="summary-tables"></a>概要テーブル
<a name="BK_Summary"> </a>

次の表に、ユーザーにサービスSkype for Business Server使用する DNS レコードを示します。 一部の機能は、特定の機能をサポートするためにのみ必要であり、これらの機能が必要ない場合はスキップできます。 内部アクセスにのみ必要な DNS レコードは最初の表に含まれています。内部アクセスと外部アクセスを許可する展開では、両方のテーブルのレコードが必要になります。

**内部 DNS マッピング**

|レコードの種類|値|解決先|用途|必須|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |フロントエンド プールの FQDN  <br/> *FE-pool。 <span></span>contoso <span></span> .com*   |フロントエンド プール サーバーの IP アドレス  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |フロントエンド プールの DNS 負荷分散。 マッププール名を一連の IP アドレスに設定します。  <br/> 「 [フロントエンド プールとディレクター プールでの DNS 負荷分散の展開」を参照してください。](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | プール内の各フロントエンド サーバーまたはStandard Editionサーバーの FQDN、またはスタンドアロン サーバー <br/>  *FE01。 <span></span>contoso. <span></span>com FE02. <span></span>contoso <span></span> .com FE03. <span></span>contoso <span></span> .com*   |各サーバーの対応する IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |マップサーバー名を IP アドレスに設定します。   |Y   |
|A/AAAA   |Enterpriseプール内部 Web サービスの FQDN の上書き  <br/> *Web-int。 <span></span>contoso <span></span> .com*   |フロント エンド サーバー内部 Web サービスの HLB VIP  <br/> *192.168.21.120*   |クライアントからサーバーへの Web トラフィックを有効にするには、サーバーのダウンロードなど、Skype for Business Web アプリ。 モバイル クライアントにも必要です。   |Y   |
|A/AAAA   |Enterpriseプール外部 Web サービスの FQDN の上書き  <br/> *Web-ext。 <span></span>contoso <span></span> .com*   |フロント エンド サーバー外部 Web サービスの HLB VIP  <br/>*68.123.56.90*   |クライアントからサーバーへの Web トラフィックを有効にするには、サーバーのダウンロードなど、Skype for Business Web アプリ。 モバイル クライアントが DNS を内部的に解決する場合に必要です。 DMZ リバース プロキシ IP またはインターネット IP に解決できます。   ||
|A/AAAA   | バック エンド サーバー SQL FQDN <br/> *SQL1。 <span></span>contoso <span></span> .com*   |サーバー IP アドレス  <br/> *192.168.11.90*   |マッププールを操作するSQLエンド サーバーのサーバー名を IP アドレスに変更する   ||
|A/AAAA   |バック エンド サーバー ミラー SQL FQDN  <br/> *SQL2。 <span></span>contoso <span></span> .com*   |サーバー IP アドレス  <br/> *192.168.11.91*   |マッププールを操作するバック エンド SQLサーバーのサーバー名を IP アドレスに変更する   ||
|A/AAAA   |ディレクター プールの FQDN  <br/>**注:** スタンドアロン ディレクター サーバーを使用する場合は適用されません <br/> *DirPool。 <span></span>contoso <span></span> .com*   |ディレクター プールの IP アドレス  <br/> DNS LB to *192.168.21.132, 192.168.21.133, 192.168.21.134*   |ディレクター プール サーバーの DNS 負荷分散。 マッププールのプール名を IP アドレスに設定する方法については、「フロント エンド プールとディレクター プールでの DNS 負荷分散の[展開」を参照してください。](load-balancing.md#BK_FE_Dir) <br/> ディレクターはユーザーを認証できます。オプションです。   ||
|A/AAAA   |ディレクター FQDN   |各ディレクター サーバーのサーバー IP アドレス   |マップのプール名を IP アドレスに設定する方法については、「フロント エンド プールとディレクター プールでの DNS 負荷分散の展開」を[参照してください。](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |仲介サーバー プールの FQDN   |プール IP アドレス   |仲介サーバーの役割はオプションです。 仲介サーバーによって提供されるサービスをフロントエンド サーバーまたはプールに共同で検索できます。 「 [仲介サーバー プールでの DNS 負荷分散の使用」を参照してください。](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |仲介サーバーの FQDN   |サーバー IP アドレス   |仲介サーバーによって提供されるサービスをフロントエンド サーバーまたはプールに共同で検索できます。 「 [仲介サーバー プールでの DNS 負荷分散の使用」を参照してください。](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |常設チャット サーバーの FQDN   |常設チャット サーバーの IP アドレス   |常設チャット機能には常設チャット サーバーが必要であり、それ以外の場合はオプションです。   ||
|A/AAAA   |lyncdiscoverinternal。*\<sipdomain\>* <br/> lyncdiscoverinternal。*<span></span> contoso <span></span> .com*   |HLB フロントエンド プール VIP またはディレクター IP  <br/>  192.168.21.121  |モビリティサポートに必要な内部自動検出サービス 1。 モバイル デバイスの解決に内部 DNS を使用する場合は、外部 IP または DMZ VIP をポイントする必要があります。  <br/> Web サービスの場合、HTTPS では DNS を活用できないので、フロントエンド プールで HLB が必要です。 フロントエンド プールまたはディレクター プールの場合、HLB VIP または Standard Edition サーバーまたはスタンドアロン ディレクター サーバーの通常の IP に解決されます。   |Y   |
|CNAME   |lyncdiscoverinternal。*\<sipdomain\>* <br/> lyncdiscoverinternal。 *<span></span>contoso <span></span> .com*   |HLB FE プール FQDN またはディレクター FQDN  <br/> Web-int。 <span></span>contoso <span></span> .com   |内部自動検出サービス 1 <br/> 必要に応じて、A レコードの代わりに CNAME として実装できます。   ||
|A/AAAA   |sip。*\<sipdomain\>* <br/> sip。*<span></span> contoso <span></span> .com*  |フロントエンド プール サーバーの IP アドレス (または各ディレクター IP アドレス)  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |自動構成に必要な場合は、「[サービスを検索するクライアントSkype for Businessチュートリアル」を参照してください。](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> 内部ネットワーク上のフロントエンド プール サーバーまたはディレクター サーバー、またはクライアントが外部であるときに Access Edge サービスを指すレコードまたはレコード   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2.*<span></span> contoso <span></span> .com*  |HLB FE プール VIP またはディレクター プール HLB VIP 、または Standard Edition/ディレクター サーバー IP  <br/>  192.168.21.121  |このレコードの展開はオプション&#x2778;  ||
|SRV   |\_sipinternaltls. \_tcp。*\<sipdomain\>* <br/>ポート 5061 <br/>\_sipinternaltls. \_tcp。*<span></span> contoso <span></span> .com* <br/>ポート 5061  |フロントエンド プールの FQDN  <br/>*FE-Pool。 <span></span>contoso <span></span> .com*  |サインインのクライアント要求を認証およびリダイレクトするフロントエンド サーバー/プールまたは Standard Edition サーバー/プールへの内部ユーザー自動サインイン 1 を有効にします。  |&#x2777; |
|A/AAAA |sipinternal。*\<sipdomain\>* <br/>sipinternal。 <span></span>*contoso <span></span> .com*  |フロントエンド プールの FQDN  <br/>_FE-Pool。 <span></span>contoso <span></span> .com_  |内部ユーザー アクセス &#x2776;  |&#x2777;  |
|SRV   | \_ntp。 \_udp。*\<sipdomain\>* <br/> \_ntp。 \_udp。 <span></span>*contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync 電話 Edition デバイスに必要な NTP ソース   |これは、デスクトップハンドセットをサポートするために必要です。   |
|SRV   |\_sipfederationtls。 \_tcp。*\<sipdomain\>* <br/>\_sipfederationtls。 \_tcp。 <span></span>*contoso <span></span> .com*  | Access Edge service FQDN <br/> EdgePool-int。 <span></span>*contoso <span></span> .com*  |IOS または電話モバイル クライアントを持つ SIP ドメインごとに 1 つの SRV レコードWindows作成します。   |モバイル クライアントのサポート   |
|A/AAAA   |管理者 URL  <br/>*Web-int。 <span></span>contoso <span></span> .com*  |HLB FE プール VIP  <br/> 192.168.21.121   |Skype for Business Server[コントロール パネル] の「[簡易 URL」を参照してください。](dns.md#BK_Simple)  ||
|A/AAAA   |meet URL  <br/>*Web-int。 <span></span>contoso <span></span> .com*  |HLB FE プール VIP  <br/> 192.168.21.121   |オンライン会議については、「 [簡易 URL」を参照してください。](dns.md#BK_Simple)  ||
|A/AAAA   |ダイヤルイン URL  <br/>*Web-int。 <span></span>contoso <span></span> .com*  |HLB FE プール VIP  <br/> 192.168.21.121   |ダイヤルイン会議については、「簡易 [URL」を参照してください。](dns.md#BK_Simple)  ||
|A/AAAA   |内部 Web サービスの FQDN  <br/>*Web-int。 <span></span>contoso <span></span> .com*  |HLB FE プール VIP  <br/> 192.168.21.121   |Skype for Businessユーザーが使用する Web サービスSkype for Business Web アプリ   ||
|A/AAAA   |OfficeWeb Apps サーバー プール FQDN  <br/> OWA。 <span></span>contoso <span></span> .com   | OfficeWeb Apps Server プールの VIP アドレス <br/> 192.168.1.5   |Web Apps サーバー Office FQDN を定義します。   ||
|A/AAAA   | 内部 Web FQDN <br/> Web-int。 <span></span>contoso <span></span> .com   | フロントエンド プールの VIP アドレス <br/> 192.168.21.121   |ユーザーが使用する内部 Web FQDN をSkype for Business Web アプリ  <br/> このプールで DNS 負荷分散を使用している場合、フロントエンド プールと内部 Web ファームに同じ FQDN を設定することはできません。   ||

&#x2776;クライアントがフロントエンド サーバーまたはフロントエンド プールを検出し、ユーザーとして認証およびサインインするために使用します。 詳細については、「サービスを検索[するクライアントSkype for Businessチュートリアル」を参照してください](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)。

&#x2777; これは、Lync 2013 より前の従来のクライアントとデスクトップハンドセットをサポートする場合にのみ必要です。

&#x2778; ユニファイド コミュニケーション デバイスがオンになっているが、ユーザーがデバイスにログインしたことがない状況では、A レコードを使用すると、デバイスは Device Update Web サービスをホストしているサーバーを検出し、更新プログラムを取得できます。 この方法を実行しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてサーバー情報を取得します。

次の図は、内部 DNS レコードと外部 DNS レコードの両方、および周囲の表に示す多くのレコードを含む例を示しています。

**パブリック IPv4 アドレスを使用したエッジ ネットワークダイアグラム**

![DNS ネットワーク図の例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**境界ネットワーク DNS マッピング (内部インターフェイスと外部インターフェイスの両方)**

|レコードの種類|値|解決先|用途|必須|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |内部エッジ プールの FQDN  <br/>*EdgePool-int。 <span></span>contoso <span></span> .com*  |内部向けエッジ プール IP アドレス  <br/> 172.25.33.10, 172.25.33.11   |統合エッジ プールの内部インターフェイス IP アドレス   |Y   |
|A/AAAA   |エッジ サーバーの FQDN  <br/>*Cons-1. <span></span>contoso <span></span> .com*  |エッジ プール内のサーバーの内部向けサーバー IP  <br/> 172.25.33.10   |プール内の内部サーバー ノード IP を指すサーバー FQDN を使用して、プール内の各サーバーのレコードを作成します。「エッジ サーバー プールでの DNS 負荷分散」を [参照してください](load-balancing.md#BK_Edge)。   |Y   |
|A/AAAA   |Access Edge service Pool FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |Access Edge Service Pool 外部 IP アドレス  <br/> 131.107.16.10, 131.107.16.11   |アクセス エッジ サービスは、セッション開始プロトコル (SIP) の送受信トラフィック用の、信頼される単一の接続ポイントです。   |Y   |
|A/AAAA   |Web 会議エッジ サービス プール FQDN  <br/>*Webcon1。 <span></span>contoso <span></span> .com*  |Web 会議エッジ サービスの外部 IP アドレス  <br/> 131.107.16.90, 131.107.16.91   |Web 会議エッジ サービスを使用すると、外部ユーザーは内部会議環境でホストされている会議にSkype for Business Serverできます。   |Y   |
|A/AAAA   |*av.\<sip-domain\>* プールの FQDN <br/>*AV1。 <span></span>contoso <span></span> .com*  |A/V エッジの外部 IP アドレス  <br/> 131.107.16.170, 131.107.16.171   |音声ビデオ エッジ サービスは、オーディオ、ビデオ、アプリケーション共有、およびファイル転送を外部ユーザーが利用できます。   |Y   |
|CNAME   |sip。*\<sipdomain\>* <br/> sip。*<span></span> contoso <span></span> .com*  |外部アクセス エッジ プールの FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |エッジ サーバー プールを検索します。 「[サービスを検索するSkype for Businessのチュートリアル」を参照してください。](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sip。 \_tls。*\<sipdomain\>* <br/>\_sip。 \_tls。 <span></span>*contoso <span></span> .com*  |外部アクセス エッジ FQDN  <br/>_Access1。 <span></span>contoso <span></span> .com_  |外部ユーザー アクセスに使用されます。 「[サービスを検索するSkype for Businessのチュートリアル」を参照してください。](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls。 \_tcp。*\<sipdomain\>* <br/>\_sipfederationtls。 \_tcp。 <span></span>*contoso <span></span> .com*  |外部アクセス エッジ FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |フェデレーションとパブリック IM 接続に使用される   |&#x2776;  |
|SRV   |\_xmpp-server。 \_tcp。*<sipdomain \>* <br/>\_xmpp-server。 \_tcp。*<span></span> contoso <span></span> .com*  |外部アクセス エッジ FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |XMPP プロキシ サービスは、構成済みの XMPP フェデレーション パートナーとの間で、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) メッセージを受け入れて送信します。   |Y、フェデレーションを展開する場合、それ以外の場合は省略可能  <br/> 2019 年Skype for Business Server使用できません。|
|SRV   |\_sipfederationtls。 \_tcp。*\<sipdomain\>* <br/>\_sipfederationtls。 \_tcp。*<span></span> contoso <span></span> .com*  |外部アクセス エッジ FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、SIP ドメインごとに 1 つの SRV レコードを作成します。 &#x2778;  ||
|A/AAAA   |外部フロントエンド プール Web サービス FQDN  <br/>*Web-ext。 <span></span>contoso <span></span> .com*  |リバース プロキシパブリック IP アドレス、フロントエンド プールの外部 Web サービス VIP へのプロキシ&#x2776; <br/> 131.107.155.1 プロキシから 192.168.21.120   |ユーザーが使用するフロントエンド プールの外部インターフェイスSkype for Business Web アプリ   |Y   |
|A/AAAA/CNAME   |lyncdiscover。*\<sipdomain\>* <br/> lyncdiscover。*<span></span> contoso <span></span> .com*  |リバース プロキシのパブリック IP アドレスを取得し、ディレクター プールの外部 Web サービス VIP に解決します (ディレクター プールがある場合、またはディレクター サーバーがインストールされていない場合はフロント エンド プール&#x2777; <br/> 131.107.155.1 プロキシから 192.168.21.120   | リバース プロキシ サーバーによって解決された、Mobility、Skype for Business Web アプリ、スケジューラ Web アプリでも使用されるクライアント自動検出の外部レコード <br/> プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync Mobile クライアントを持つ SIP ドメインごとに 1 つの SRV レコードを作成します。 3  |Y   |
|A/AAAA   |を満たします。*\<sipdomain\>* <br/> を満たします。*<span></span> contoso <span></span> .com*  |リバース プロキシパブリック IP アドレス、フロントエンド プールの外部 Web インターフェイスに解決される  <br/> 131.107.155.1 プロキシから 192.168.21.120   |Web サービスSkype for Businessプロキシ  <br/> 「簡易 [URL」を参照してください。](dns.md#BK_Simple)  |Y   |
|A/AAAA   |ダイヤルイン。*\<sipdomain\>* <br/> ダイヤルイン。*<span></span> contoso <span></span> .com*  |リバース プロキシパブリック IP アドレス、フロントエンド プールの外部 Web インターフェイスへのプロキシ  <br/> 131.107.155.1 プロキシから 192.168.21.120   |Web サービスSkype for Businessプロキシ  <br/> 「簡易 [URL」を参照してください。](dns.md#BK_Simple)  |Y   |
|A/AAAA   |OfficeWeb Apps サーバー プール FQDN  <br/> OWA。 <span></span>contoso <span></span> .com   | リバース プロキシパブリック IP アドレス、Web Apps Server の外部 Web インターフェイスOfficeプロキシ <br/> 131.107.155.1 プロキシから 192.168.1.5   | OfficeWeb Apps Server プールの VIP アドレス <br/> 192.168.1.5   |Web Apps サーバー Office FQDN を定義します。   |

&#x2776;フェデレーションを展開する場合は必須です。それ以外の場合は省略可能です。

&#x2777;クライアントがフロントエンド サーバーまたはフロントエンド プールを検出し、ユーザーとして認証およびサインインするために使用します。

&#x2778;この要件は、Apple または Microsoft ベースのモバイル デバイス上のクライアントにのみ適用されます。 Android デバイスと Nokia Symbian デバイスでは、プッシュ通知は使用されません。

 エッジ サーバーと境界ネットワークの詳細については、「エッジ サーバーの DNS 計画 [コンテンツ」を参照](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) してください。

> [!IMPORTANT]
> Skype for Business Server IPv6 アドレス指定の使用をサポートしています。 詳細[については、「Plan for IPv6 in Skype for Business」](ipv6.md)を参照してください。

> [!IMPORTANT]
> FQDN の詳細については、「DNS の基本 [」を参照してください](basics.md)。

**スプリット ブレイン DNS** 
<a name="BK_split"></a>

スプリット ブレイン DNS は、同じ名前空間を持つ 2 つの DNS ゾーンを持つ DNS 構成です。 最初の DNS ゾーンは内部要求を処理しますが、2 番目の DNS ゾーンは、これらの表に記載されている外部要求を処理します。 詳細については、「スプリットブレイン [DNS」を参照してください](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)。

## <a name="hybrid-considerations"></a>ハイブリッドに関する考慮事項
<a name="BK_Hybrid"> </a>

一部のユーザーをオンラインにし、一部のユーザーをオンプレミスに持ち込む予定の場合は、「ハイブリッド接続計画」の記事「Skype for Business [2019」を参照](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)してください。 2015 年に DNS を通常通り構成し、Skype for Business Server DNS レコードを追加する必要があります。

ユーザーが必要とするオンライン リソースにアクセスOffice 365確認するには、「URL と IP アドレスの範囲を変更する」も [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) 参照してください。

## <a name="simple-urls"></a>簡易 URL
<a name="BK_Simple"> </a>

Uniform Resource Locator (URL) は、コンピューター ネットワーク上の場所と取得に使用されるプロトコルを指定する Web リソースへの参照です。

Skype for Business Serverサービスにアクセスするために、次の 3 つの "単純な" URL を使用できます。

- **Meet** は、サイト内のすべての会議の基本 URL として使用されます。 Meet 単純な URL の例は https: <span></span> // <span></span> meet です。 <span></span>contoso <span></span> .com。 特定の会議の URL は https: <span></span> // <span></span> meet である可能性があります。 <span></span>contoso <span></span> .com/_username_/7322994.

    会議の簡単な URL を使用すると、会議に参加するためのリンクを簡単に理解し、簡単にコミュニケーションできます。

- **ダイヤルインを使用すると**、Web ページからダイヤルイン会議設定アクセスできます。 このページには、使用可能な言語、割り当てられた会議情報 (スケジュールする必要ない会議用)、および会議内 DTMF コントロールを含む会議ダイヤルイン番号が表示され、個人識別番号 (PIN) と割り当てられた会議情報の管理がサポートされます。 ダイヤルイン簡易 URL は、すべての会議出席依頼に含まれているので、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。 ダイヤルインの単純な URL の例は、https:// <span></span> です。 <span></span>contoso <span></span> .com。

- **管理者** は、コントロール パネルへのクイック Skype for Business Serverを有効にします。 組織のファイアウォール内の任意のコンピューターから、管理者はブラウザーに管理者簡易 URL を入力して Skype for Business Server コントロール パネルを開きます。 簡単な管理 URL は、組織内部の URL です。 管理者の簡易 URL の例は、管理者 https:// <span></span> です。 <span></span>contoso <span></span> .com。

単純な URL については、詳細については、「DNS 要件」を参照してください。詳細については[、Skype for Business Server。](simple-urls.md)

## <a name="dns-by-server-role"></a>サーバーの役割別 DNS
<a name="BK_Servers"> </a>

これらのプールとサーバーの名前は必要に合って設定できますが、思い出深いものにし、その機能をシステムに反映することができます。

### <a name="dns-records-for-individual-servers-or-pools"></a>個々のサーバーまたはプールの DNS レコード

これらの一般的なレコード要件は、ユーザーが使用するサーバーの役割にSkype for Business。 プールは、ロード バランサー経由でクライアント要求を処理するために一緒に動作する同じサービスを実行する一連のサーバーです。 詳細[については、「負荷分散の要件」をSkype for Business](load-balancing.md)参照してください。

**DNS レコード サーバー/プールの役割の要件 (DNS 負荷分散を推定)**

|展開シナリオ|DNS 要件|
|:-----|:-----|
|1 つのサーバー:  <br/> 常設チャット、ディレクター、仲介サーバー、フロントエンド サーバー   |サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。  <br/> ServerRole。 <span></span>contoso <span></span> .com 10.10.10.0   |
|プール:  <br/> 常設チャット、ディレクター、エッジ サーバー、仲介サーバー、フロントエンド   |プール内の各サーバー ノードの完全修飾ドメイン名 (FQDN) を IP アドレスに解決する内部 A レコード。  <br/>**例** <br/> ServerRole01。 <span></span>contoso <span></span> .com 10.10.10.1  <br/> ServerRole02。 <span></span>contoso <span></span> .com 10.10.10.2  <br/> 複数の内部 プールの完全修飾ドメイン名 (FQDN) をプール内のサーバー ノードの IP アドレスに解決するレコード。  <br/>**例** <br/> ServerPool。 <span></span>contoso <span></span> .com 10.10.10.1  <br/> ServerPool。 <span></span>contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>エッジ サーバー固有の DNS トピック

 エッジ サーバーの展開を計画するには[、「Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)でのエッジ サーバー展開の計画」および「Skype for Business Server [2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)の Advanced Edge Server DNS 計画」を参照してください。このセクションでは、次のセクションを参照してください。

- [DNS 障害復旧](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS 負荷分散](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [スプリットブレイン DNS を使用しない自動構成](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [スプリットブレイン DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [サービスをSkype for Businessするクライアントのチュートリアル](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)