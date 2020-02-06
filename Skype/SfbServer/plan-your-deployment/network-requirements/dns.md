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
ms.openlocfilehash: 52984c0813fb96c78ff5a1581c0722a691501ccb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802127"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Skype for Business Server の DNS 要件

**概要:** Skype for Business Server を実装する前に、このトピックの DNS の考慮事項を確認してください。

この記事では、組織の社内ネットワークにおける Skype for Business Server 展開の DNS 計画についてのみ説明します。 Skype for Business Online の場合は、「Office 365 の Url と IP アドレスの[https://aka.ms/o365ips](https://aka.ms/o365ips)範囲」を参照してください。

ドメインネームサービス (DNS) サーバーは、ホスト名 (www など<span></span> ) をマップします。(<span></span>10.10.10.10 など) IP アドレスに対して、contoso は web サーバーと思われます。 これにより、クライアントおよび相互依存のサーバー同士が、ネットワーク上で通信することができます。 Skype for Business Server 2015 の実装をセットアップするときには、新しいサーバー名 (通常、ユーザーが実行する役割を反映) のマッピングが、割り当てられている IP アドレスと一致するようにする必要があります。

これは少し困難に思えるかもしれませんが、計画を立てるための大きな取り組みは、 [Skype For Business Server 2015 計画ツール](https://www.microsoft.com/en-us/download/details.aspx?id=50357)を使って行うことができます。 使用する予定の機能についてウィザードの質問を完了した後は、定義した各サイトについて、エッジ管理者レポートで DNS レポートを表示して、そこに記載されている情報を使って DNS レコードを作成できます。 使用される名前と IP アドレスの多くを調整することもできます。詳細については、「 [DNS レポートを確認](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)する」を参照してください。 Edge 管理者レポートを Excel スプレッドシートにエクスポートして、DNS レポートはファイル内のワークシートの1つとしてエクスポートできることに注意してください。 このツールには、 [Skype For Business Server 2019 から廃止](../../../SfBServer2019/deprecated.md)された機能が含まれていますが、これらの機能が選択されていない場合は、最初のプランを作成するために使用することができます。

「 [Skype For Business server の dns レコードを作成](../../deploy/install/create-dns-records.md)する」と「skype For business server のトポロジを構築する」で説明されているように新しい実装をインストールすると、Windows Server 2016 またはサードパーティの dns パッケージに組み込まれている dns 機能を使用することができます。そのため、この記事では、具体的な説明ではなく、この ここでは、必要なものを詳しく説明しています。また、その必要性を満たすためには、決定する必要があります。

経験豊富な Skype for Business、Lync、Office Communications Suite 管理者は、次の表を参考にしてください。 表の内容が分かりにくい場合は、後のセクションや記事で次のような概念が明快に説明されています。

## <a name="summary-tables"></a>要約表
<a name="BK_Summary"> </a>

次の表は、Skype for Business Server がユーザーにサービスを提供するために使用する DNS レコードを示しています。 一部のオプションは、特定の機能をサポートするためだけに必要であり、これらの機能が必要でない場合はスキップできます。 内部アクセスに必要な DNS レコードは1つ目のテーブルにあり、内部および外部アクセスを可能にする展開では、両方のテーブルからのレコードが必要です。

**内部 DNS マッピング**

|レコードの種類|値|解決先|用途|必須|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |フロントエンドプール FQDN  <br/> *FE-プール。<span> </span>contoso<span></span>.com*   |フロントエンドプールサーバーの IP アドレス  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |フロントエンド プールの DNS 負荷分散。 フロントエンド プールの名前を IP アドレスのセットにマップします。  <br/> [フロントエンド プールとディレクター プールへの DNS 負荷分散の展開](load-balancing.md#BK_FE_Dir)を参照してください  |Y   |
|A/AAAA   | プールまたはスタンドアロンサーバーの各フロントエンドサーバーまたは標準エディションサーバーの FQDN <br/>  *FE01.<span> </span>contoso。<span> </span>com FE02。<span> </span>contoso<span></span>FE03。<span> </span>contoso<span></span>.com*   |各サーバーの対応する IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |IP アドレスのサーバー名をマップします。   |Y   |
|A/AAAA   |エンタープライズ プールの内部 Web サービスでの FQDN の上書き  <br/> *Web-int-13<span></span><span></span>*   |フロントエンドサーバーの内部 Web サービス向けの HLB VIP  <br/> *192.168.21.120*   |Skype for Business Web App のダウンロードなど、クライアントからサーバーへの web トラフィックを有効にするために必要です。 モバイル クライアントでも必要です。   |Y   |
|A/AAAA   |エンタープライズ プールの外部 Web サービスでの FQDN の上書き  <br/> *<span>Web また</span><span></span>は .com*   |フロントエンドサーバーの外部 Web サービス向けの HLB VIP  <br/>*68.123.56.90*   |Skype for Business Web App のダウンロードなど、クライアントからサーバーへの web トラフィックを有効にするために必要です。 モバイル クライアントが DNS を内部的に解決する場合に必要です。 DMZ リバース プロキシ IP または内部 IP に解決することができます。   ||
|A/AAAA   | バックエンドサーバーの SQL Server FQDN <br/> *SQL1.<span> </span>contoso<span></span>.com*   |サーバー IP アドレス  <br/> *192.168.11.90*   |フロントエンドプールで作業しているバックエンド SQL server のサーバー名を IP アドレスにマップします。   ||
|A/AAAA   |バックエンドサーバーミラー SQL Server FQDN  <br/> *SQL2.<span> </span>contoso<span></span>.com*   |サーバー IP アドレス  <br/> *192.168.11.91*   |フロントエンドプールを使用して、バックエンドの SQL ミラーサーバーのサーバー名を IP アドレスにマップします。   ||
|A/AAAA   |ディレクタープールの FQDN  <br/>**注:** スタンドアロンのディレクターサーバーを使用する場合は該当しません <br/> *DirPool。<span> </span>contoso<span></span>.com*   |ディレクタープールの IP アドレス  <br/> DNS LB から*192.168.21.132、192.168.21.133、192.168.21.134*   |ディレクタープールサーバーの DNS 負荷分散。 ディレクタープールのプール名を IP アドレスにマップします。「[フロントエンドプールとディレクタープールでの DNS の負荷分散の展開](load-balancing.md#BK_FE_Dir)」を参照してください。 <br/> ディレクターはユーザーを認証することができる、オプションです。   ||
|A/AAAA   |ディレクター FQDN   |各ディレクターサーバーのサーバー IP アドレス   |ディレクターのプール名を IP アドレスにマップします。「[フロントエンドプールとディレクタープールでの DNS の負荷分散の展開](load-balancing.md#BK_FE_Dir)」を参照してください。  ||
|A/AAAA   |仲介サーバープール FQDN   |プール IP アドレス   |仲介サーバー ロールはオプションです。 仲介サーバーによって提供されるサービスを、フロント エンド サーバーまたはプールに対して併置することができます。 「[仲介サーバープールでの DNS ロードバランシングの使用」を](load-balancing.md#BK_Mediation)参照してください。  ||
|A/AAAA   |仲介サーバーの FQDN   |サーバー IP アドレス   |仲介サーバーによって提供されるサービスを、フロント エンド サーバーまたはプールに対して併置することができます。 「[仲介サーバープールでの DNS ロードバランシングの使用」を](load-balancing.md#BK_Mediation)参照してください。  ||
|A/AAAA   |常設チャットサーバー FQDN   |常設チャットサーバーの IP アドレス   |常設チャット サーバーは、常設チャット機能のために必要ですが、それ以外の場合はオプションです。   ||
|A/AAAA   |lyncdiscoverinternal.* \<sipdomain\>* <br/> lyncdiscoverinternal.* <span> </span>contoso<span></span>.com*   |HLB フロントエンドプール VIP またはディレクター IP  <br/>  192.168.21.121  |内部自動検出 Service1。モビリティのサポートに必要です。 内部 DNS を使ってモバイルデバイスを解決する場合は、外部 IP または DMZ VIP を参照する必要があります。  <br/> Web サービスの場合、HTTPS は DNS を利用できないため、フロントエンドプールに HLB が必要です。 フロントエンドプールまたはディレクタープールの場合、これは HLB VIP、または Standard edition サーバーまたはスタンドアロンディレクターサーバーの標準 IP に解決されます。   |Y   |
|CNAME   |lyncdiscoverinternal.* \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso<span></span>.com*   |HLB FE プールの FQDN またはディレクターの FQDN  <br/> Web-int-13<span></span><span></span>   |内部自動検出 Service1 <br/> 必要に応じて、これを A レコードではなく CNAME として実装することができます。   ||
|A/AAAA   |フェデレーション.* \<sipdomain\>* <br/> フェデレーション.* <span> </span>contoso<span></span>.com*  |フロントエンドプールサーバーの IP アドレス (または各ディレクター IP アドレス)  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |自動構成のために必要です。「 [Skype For business クライアントのチュートリアル](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)」を参照してください。 <br/> 内部ネットワーク上のフロントエンドプールサーバーまたはディレクターサーバーを指すレコードまたはレコード、またはクライアントが外部の場合はアクセスエッジサービス   |&#x2777;  |
|A/AAAA   |ucupdates-r2。* \<sipdomain\>* <br/> ucupdates-r2。* <span> </span>contoso<span></span>.com*  |HLB FE プール VIP またはディレクター プール HLB VIP、または SE/ディレクター サーバー IP  <br/>  192.168.21.121  |このレコードの展開はオプション &#x2778;  ||
|SRV   |\_sipinternaltls.\_tcp。* \<sipdomain\> * <br/>ポート5061 <br/>\_sipinternaltls.\_tcp。* <span> </span>contoso<span></span>.com* <br/>ポート5061  |フロントエンドプール FQDN  <br/>*FE-プール。<span> </span>contoso<span></span>.com*  |サインインについてのクライアントの要求を認証およびリダイレクトするフロントエンド サーバー/プールまたは SE サーバー/プールに対する内部ユーザーの自動サインイン 1 を有効にします。  |&#x2777; |
|A/AAAA |sipinternal.* \<sipdomain\>* <br/>sipinternal.<span> </span> *contoso<span></span>.com*  |フロントエンドプール FQDN  <br/>_FE-プール。<span> </span>contoso<span></span>.com_  |内部ユーザーアクセス &#x2776;  |&#x2777;  |
|SRV   | \_ntp.\_udp。* \<sipdomain\> * <br/> \_ntp.\_udp。<span> </span> *contoso<span></span>.com*  |タイム サーバーの FQDN  <br/> north-america.pool.ntp.org   |Lync Phone Edition デバイスに必要な NTP ソース   |これは、デスクトップハンドセットをサポートするために必要です。   |
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span> </span> *contoso<span></span>.com*  | Access Edge サービス FQDN <br/> EdgePool-int-13<span></span>*<span></span>*  |IOS または Windows Phone のモバイル クライアントが存在する各 SIP ドメインに対して、1 つの SRV レコードを作成します。   |モバイル クライアントのサポートの場合   |
|A/AAAA   |管理 URL  <br/>*Web-int-13<span></span><span></span>*  |HLB FE プール VIP  <br/> 192.168.21.121   |Skype for Business Server コントロールパネルの「[簡単な url](dns.md#BK_Simple) 」をご覧ください。  ||
|A/AAAA   |会議 URL  <br/>*Web-int-13<span></span><span></span>*  |HLB FE プール VIP  <br/> 192.168.21.121   |オンライン会議, 「[単純な url](dns.md#BK_Simple) 」をご覧ください。  ||
|A/AAAA   |ダイヤルイン URL  <br/>*Web-int-13<span></span><span></span>*  |HLB FE プール VIP  <br/> 192.168.21.121   |ダイヤルイン会議。[簡易 URL](dns.md#BK_Simple) を参照してください。  ||
|A/AAAA   |内部 Web サービスの FQDN  <br/>*Web-int-13<span></span><span></span>*  |HLB FE プール VIP  <br/> 192.168.21.121   |Skype for business Web App で使用される skype for Business Web サービス   ||
|A/AAAA   |Office Web Apps サーバープールの FQDN  <br/> Outlook.<span> </span>contoso<span></span>.com   | Office Web Apps サーバープール VIP アドレス <br/> 192.168.1.5   |Office Web Apps サーバープールの FQDN を定義します   ||
|A/AAAA   |  内部 Web の FQDN <br/> Web-int-13<span></span><span></span>   | フロントエンドプール VIP アドレス <br/> 192.168.21.121   |Skype for Business Web App で使用される内部 Web FQDN を定義します  <br/> このプールで DNS 負荷分散を使用する場合は、フロントエンド プールと内部 Web ファームで同じ FQDN を使用することはできません。   ||

クライアントがフロントエンドサーバーまたはフロントエンドプールを検出し、ユーザーとして認証されてサインインするために使用される &#x2776;。 詳細については、「 [Skype For business クライアントでサービスを検索する](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)」をご覧ください。

&#x2777; Lync 2013 の前のレガシクライアントとデスクトップハンドセットをサポートするためだけに必要です。

統合通信デバイスが有効になっている状況で、ユーザーがデバイスにログインしたことがない場合は、A レコードを使うと、デバイスでデバイス更新 Web サービスをホストしているサーバーを検出し、更新プログラムを取得することができます。 &#x2778; そうしないと、デバイスは、ユーザーが初めてログインしたときに、インバンドプロビジョニングでサーバー情報を取得します。

次のダイアグラムでは、内部および外部 DNS レコードの両方を含んでいる場合の例と、周囲のテーブル内に数多くのレコードを示しています。

**パブリック IPv4 アドレスを使用したエッジ ネットワーク ダイアグラム**

![DNS ネットワーク ダイアグラムの例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**境界ネットワークの DNS マッピング (内部および外部インターフェイスの両方) **

|レコードの種類|値|解決先|用途|必須|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |内部エッジプールの FQDN  <br/>*EdgePool-int-13<span></span><span></span>*  |内部向けエッジプール IP アドレス  <br/> 172.25.33.10, 172.25.33.11   |統合エッジ プールの内部インターフェイスの IP アドレス   |Y   |
|A/AAAA   |エッジサーバーの FQDN  <br/>*短所-1。<span> </span>contoso<span></span>.com*  |エッジプールのサーバーの内部接続サーバー IP  <br/> 172.25.33.10   |プール内の各サーバーについてレコードを作成するサーバー FQDN がプール内の内部サーバーノード IP を指していることを確認します。「microsoft [Edge Server プールの DNS 負荷分散](load-balancing.md#BK_Edge)」を参照してください。   |Y   |
|A/AAAA   |Access Edge サービスプールの FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |Access Edge サービスプールの外部 IP アドレス  <br/> 131.107.16.10, 131.107.16.11   |アクセスエッジサービスは、送受信セッション開始プロトコル (SIP) トラフィックの単一の信頼できる接続ポイントを提供します。   |Y   |
|A/AAAA   |Web 会議エッジサービスプールの FQDN  <br/>*Webcon1.<span> </span>contoso<span></span>.com*  |Web 会議エッジサービスの外部 IP アドレス  <br/> 131.107.16.90, 131.107.16.91   |Web 会議エッジサービスを使うと、外部ユーザーは、社内の Skype for Business Server 環境でホストされている会議に参加することができます。   |Y   |
|A/AAAA   |*av-ドメイン\> \<* プールの FQDN <br/>*AV1.<span> </span>contoso<span></span>.com*  |音声ビデオ エッジ外部 IP アドレス  <br/> 131.107.16.170, 131.107.16.171   |A/V Edge サービスにより、オーディオ、ビデオ、アプリケーション共有、ファイル転送を外部ユーザーが利用できるようになります。   |Y   |
|CNAME   |フェデレーション.* \<sipdomain\>* <br/> フェデレーション.* <span> </span>contoso<span></span>.com*  |外部アクセス エッジ プールの FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |エッジサーバープールを検索します。 [サービスの検索については、「Skype For business クライアントのチュートリアル」を](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)参照してください。  |Y   |
|SRV   |\_フェデレーション.\_tls。* \<sipdomain\> * <br/>\_フェデレーション.\_tls。<span> </span> *contoso<span></span>.com*  |外部アクセスエッジ FQDN  <br/>_Access1.<span> </span>contoso<span></span>.com_  |外部ユーザー アクセスのために使用されます。 [サービスの検索については、「Skype For business クライアントのチュートリアル」を](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)参照してください。  |Y   |
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span> </span> *contoso<span></span>.com*  |外部アクセスエッジ FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |フェデレーションとパブリック IM 接続で使用されます   |&#x2776;  |
|SRV   |\_xmpp-サーバー。\_tcp。*<sipdomain\> * <br/>\_xmpp-サーバー。\_tcp。* <span> </span>contoso<span></span>.com*  |外部アクセスエッジ FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |XMPP プロキシサービスは、構成済みの XMPP フェデレーションパートナーとの間で、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) のメッセージを受け取り、送信します。   |フェデレーションの展開のために必要です。それ以外の場合はオプションです  <br/> Skype for Business Server 2019 では利用できません。|
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。* <span> </span>contoso<span></span>.com*  |外部アクセスエッジ FQDN  <br/>*Access1.<span> </span>contoso<span></span>.com*  |プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、SIP ドメインごとに1つの SRV レコードを作成します。 &#x2778;  ||
|A/AAAA   |外部フロントエンドプール web サービス FQDN  <br/>*<span>Web また</span><span></span>は .com*  |リバースプロキシパブリック IP アドレス、フロントエンドプールの外部 Web サービス VIP へのプロキシ &#x2776; <br/> 131.107.155.1 プロキシから192.168.21.120   |Skype for Business Web App で使用されるフロントエンドプールの外部インターフェイス   |Y   |
|A/AAAA/CNAME   |lyncdiscover.* \<sipdomain\>* <br/> lyncdiscover.* <span> </span>contoso<span></span>.com*  |リバースプロキシパブリック IP アドレスは、ディレクタープールがある場合は、外部 Web サービス VIP に解決されます。ディレクタープールを持っている場合は、フロントエンドプールに対しても、ディレクター &#x2777; を持っていない場合はそれが対象となります。 <br/> 131.107.155.1 プロキシから192.168.21.120   | モバイル、Skype for Business Web App、および scheduler Web アプリでも使用されるクライアントの自動検出の外部レコード (リバースプロキシサーバーで解決) <br/> プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync モバイルクライアントを含む SIP ドメインごとに SRV レコードを1つ作成します。 3  |Y   |
|A/AAAA   |即時.* \<sipdomain\>* <br/> 即時.* <span> </span>contoso<span></span>.com*  |リバースプロキシパブリック IP アドレスは、フロントエンドプールの外部 Web インターフェイスに解決されます。  <br/> 131.107.155.1 プロキシから192.168.21.120   |Skype for Business Web サービスへのプロキシ  <br/> [簡易 URL](dns.md#BK_Simple) を参照してください  |Y   |
|A/AAAA   |*\<sipdomain\>* <br/> ダイヤルイン (*<span></span>コントソ<span></span>)*  |リバースプロキシのパブリック IP アドレス、フロントエンドプールの外部 Web インターフェイスへのプロキシ  <br/> 131.107.155.1 プロキシから192.168.21.120   |Skype for Business Web サービスへのプロキシ  <br/> [簡易 URL](dns.md#BK_Simple) を参照してください  |Y   |
|A/AAAA   |Office Web Apps サーバープールの FQDN  <br/> Outlook.<span> </span>contoso<span></span>.com   | リバースプロキシパブリック IP アドレス、Office Web Apps サーバーの外部 Web インターフェイスへのプロキシ <br/> 131.107.155.1 は 192.168.1.5 にプロキシ   | Office Web Apps サーバープール VIP アドレス <br/> 192.168.1.5   |Office Web Apps サーバープールの FQDN を定義します   |

フェデレーションの展開に必要な &#x2776;、それ以外の場合は省略可能です。

クライアントがフロントエンドサーバーまたはフロントエンドプールを検出し、ユーザーとして認証されてサインインするために使用される &#x2777;。

&#x2778; この要件は、Apple または Microsoft ベースのモバイルデバイス上のクライアントにのみ適用されます。 Android および Nokia Symbian デバイスでは、プッシュ通知は使用されません。

 エッジサーバーと境界ネットワークの詳細については、「Edge server [DNS の計画](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)の内容」を参照してください。

> [!IMPORTANT]
> Skype for Business Server は IPv6 アドレスの使用をサポートしています。 詳細については、[Plan for IPv6 in Skype for Business](ipv6.md)を参照してください。

> [!IMPORTANT]
> FQDN の詳細については、[DNS basics](basics.md)を参照してください。 

**脳 DNS** 
 <a name="BK_split"> </a>の分割

スプリット ブレイン DNSは、2 つの DNS ゾーンが同じ名前空間に存在する DNS 構成です。 表内で述べられているように、一方の DNS ゾーンは内部要求のみ、他方の DNS ゾーンは外部要求のみを処理します。 詳細については、[スプリットブレイン DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS) を参照してください。

## <a name="hybrid-considerations"></a>ハイブリッドの考慮事項
<a name="BK_Hybrid"> </a>

一部のユーザーがオンラインであり、一部がオンプレミスの場合は、「ハイブリッド接続の計画」「 [Skype For business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」を参照してください。 Skype for Business Server 2015 の場合は、DNS を通常どおりに構成し、DNS レコードを追加する必要があります。

また、「Office 365 の Url と IP アドレスの範囲」を参照[https://aka.ms/o365ips](https://aka.ms/o365ips)して、ユーザーが必要なオンラインリソースにアクセスできることを確認する必要があります。

## <a name="simple-urls"></a>簡易 URL
<a name="BK_Simple"> </a>

URL (Uniform Resource Locator) は、Web リソースに対する参照として、そのコンピューター ネットワーク上の場所と、それを取得するために使用されるプロトコルを指定します。

Skype for Business Server は、3つの "シンプルな" Url を使用してサービスにアクセスすることをサポートしています。

- **会議**は、サイト内のすべての会議のベース URL として使用されます。 単純な "URL" の例は https:<span></span>//<span></span>会議です。<span> </span>contoso<span></span>。 特定の会議の URL が https:<span></span>//<span></span>会議になっている可能性があります。<span> </span>contoso<span></span>. .com/_username_/7322994

    会議の簡易 URL により、会議に参加するためのリンクが覚えやすいものになり、通知も簡単に行えます。

- [**ダイヤル**イン] は、ダイヤルイン会議の設定 web ページへのアクセスを有効にします。 このページには、会議のダイヤルイン番号が表示されます。このページには、利用可能な言語、割り当てられている会議情報 (スケジュールされていない会議)、会議中の DTMF コントロールが表示され、個人識別番号の管理がサポートされています (PIN) および割り当てられた会議情報。 ダイヤルインの簡易 URL は、会議にダイヤルインするユーザーが必要な電話番号と PIN 情報にアクセスできるように、すべての会議出席依頼に含まれています。 ダイヤルインの簡易 URL の例は、https://<span></span>のダイヤルインです。<span> </span>contoso<span></span>。

- **管理者**が Skype For Business Server コントロールパネルにすばやくアクセスできるようにします。 組織のファイアウォール内の任意のコンピューターから、管理者は、ブラウザーに管理者の簡易 URL を入力して、[Skype for Business Server] コントロールパネルを開くことができます。 管理者の簡易 URL は、組織の内部にあります。 管理者の簡易 URL の例は、<span></span>https://管理者です。<span> </span>contoso<span></span>。

簡単な Url について詳しくは、「 [Skype For Business Server の単純な url の DNS の要件](simple-urls.md)」をご覧ください。

## <a name="dns-by-server-role"></a>サーバー ロール別の DNS
<a name="BK_Servers"> </a>

これらのプールおよびサーバーの名前を自由に設定することができます。ただし、システム内での機能を反映した、覚えやすい名前にすることをお勧めします。

### <a name="dns-records-for-individual-servers-or-pools"></a>個別サーバーまたはプールの DNS レコード

これらの一般的なレコード要件は、Skype for Business で使用されるサーバーの役割に適用されます。 プールは、ロード バランサーを通してサーバーに向けられるクライアントの要求を処理するために連動する同じサービスを実行しているサーバーの集まりです。 詳細については、[Load balancing requirements for Skype for Business](load-balancing.md)を参照してください。

**サーバー/プールの役割の DNS レコード要件 (DNS の負荷分散の前提となります)**

|展開シナリオ|DNS 要件|
|:-----|:-----|
|1つのサーバー:  <br/> 常設チャット、監督、仲介サーバー、フロントエンドサーバー   |内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。  <br/> ServerRole.<span></span>コントソ<span></span>10.10.10.0   |
|生産  <br/> 常設チャット、監督、エッジサーバー、仲介サーバー、フロントエンド   |内部の A レコード。プール内の各サーバーノードの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。  <br/>**例** <br/> ServerRole01.<span></span>コントソ<span></span>10.10.10.1  <br/> ServerRole02.<span></span>コントソ<span></span>10.10.10.2  <br/> 複数の内部 A レコード。プールの完全修飾ドメイン名 (FQDN) を、プール内のサーバーノードの IP アドレスに解決します。  <br/>**例** <br/> ServerPool。<span></span>コントソ<span></span>10.10.10.1  <br/> ServerPool。<span></span>コントソ<span></span>10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Edge Server 固有の DNS トピック

 エッジサーバーの展開を計画するには、 [skype For Business server 2015 のエッジサーバー展開の計画](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)と、次のセクションを含む[Skype for business server 2015 向けの ADVANCED edge server DNS 計画](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)を確認します。

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


