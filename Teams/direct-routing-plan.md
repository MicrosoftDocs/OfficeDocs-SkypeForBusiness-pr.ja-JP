---
title: ダイレクト ルーティングを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: システム ダイレクト ルーティングMicrosoft 電話、サポートされている顧客が提供するセッション ボーダー コントローラー (SBC) をシステムに接続する方法Microsoft 電話します。
ms.openlocfilehash: 90ed1fe51c3b6e3ee6c498fd586e54a05ab533e3
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130286"
---
# <a name="plan-direct-routing"></a>ダイレクト ルーティングを計画する

> [!Tip]
> ダイレクト ルーティングの利点、その計画方法、およびそれをデプロイする方法については、次の[セッションをMicrosoft Teams](https://aka.ms/teams-direct-routing)

Microsoft 電話システムダイレクト ルーティングを使用すると、サポートされている顧客提供のセッション ボーダー コントローラー (SBC) をシステムにMicrosoft 電話できます。  たとえば、この機能を使用すると、次の図に示すように、Microsoft Teams クライアントとのオンプレミスのパブリック 交換電話網 (PSTN) 接続を構成できます。 

![オンプレミス PSTN 接続の構成を示す図](media/PlanDirectRouting1-PSTNwithTeams.png "クライアントとのオンプレミス PSTN 接続Microsoft Teams構成")

  > [!NOTE]
  > Skype for Businessまた、オンラインでは顧客が提供する SBC をペアリングできますが、これには、SBC と Microsoft Cloud の間に、オンプレミスの Skype for Business Server デプロイまたはクラウド コネクタと呼ばれる特別なエディションの Skype for Business が必要です。 このシナリオは、ハイブリッド音声と呼ばれる。 これに対し、ダイレクト ルーティングでは、サポートされている SBC と Microsoft Cloud 間の直接接続が可能です。

> [!Important]
> Cloud Connector Edition は、2021 年 7 月 31 日にオンライン版と共Skype for Business廃止されます。 組織がネットワーク にアップグレードTeams、ダイレクト ルーティングを使用してオンプレミスのテレフォニー ネットワークをネットワークにTeams[する方法について説明します](direct-routing-landing-page.md)。 

ダイレクト ルーティングを使用すると、SBC をほぼすべてのテレフォニー トランクに接続したり、サードパーティの PSTN 機器と相互接続することができます。 ダイレクト ルーティングを使用すると、次の操作を行います。 

- システムを使用して、事実上すべての PSTN トランクMicrosoft 電話使用します。 
- サードパーティのプライベートブランチ交換 (PBX)、アナログ デバイス、およびシステムなどの顧客所有のテレフォニー機器間の相互運用性Microsoft 電話構成します。

Microsoft では、通話プランなどのクラウド音声ソリューションも提供しています。 ただし、次の場合は、ハイブリッド音声ソリューションが組織に最適な場合があります。 

- Microsoft 通話プランは、お客様の国ではご利用になられません。 
- 組織では、サードパーティのアナログ デバイス、コール センターなどへの接続が必要です。 
- 組織には、PSTN キャリアとの既存の契約があります。

ダイレクト ルーティングでは、Microsoft 通話プランの追加ライセンスを持つユーザーもサポートされます。 詳細については、[電話システムと通話プラン](calling-plan-landing-page.md)に関する記事をご覧ください。 

ダイレクト ルーティングでは、ユーザーがスケジュールされた会議に参加すると、ダイヤルイン番号が Microsoft 電話会議サービスによって提供されます。適切なライセンスが必要です。  ダイヤルアウト時に、Microsoft 電話会議サービスはオンライン通話機能を使用して呼び出しを行います。適切なライセンスが必要です。 (ユーザーが Microsoft 電話会議ライセンスを持ってない場合は、ダイレクト ルーティングを通じて通話がルーティングされます。詳細については、「オンライン会議[とオンライン会議」を参照Teams。](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
ダイレクト ルーティングのデプロイを計画する方法は、実装を成功する上で重要です。 この記事では、インフラストラクチャとライセンスの要件について説明し、SBC 接続に関する情報を提供します。 

- [インフラストラクチャの要件](#infrastructure-requirements)
- [ライセンスと他の要件](#licensing-and-other-requirements)
- [SBC ドメイン名](#sbc-domain-names)
- [SBC のパブリック信頼された証明書](#public-trusted-certificate-for-the-sbc)
- [SIP シグナリング: FQDN](#sip-signaling-fqdns)
- [SIP シグナリング: ポート](#sip-signaling-ports)
- [メディア トラフィック: ポート範囲](#media-traffic-port-ranges)
- [サポートされているセッション ボーダー コントローラー (SPC)](#supported-session-border-controllers-sbcs)

ダイレクト ルーティングの構成の詳細については、「ダイレクト ルーティングの構成」 [を参照してください](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
ダイレクト ルーティングをデプロイするためにサポートされている SPC、ドメイン、その他のネットワーク接続要件のインフラストラクチャ要件を次の表に示します。  

|インフラストラクチャの要件|次の情報が必要です。|
|:--- |:--- |
|セッション ボーダー コントローラー (SBC)|サポートされている SBC。 詳細については、「サポートされている [SPC」を参照してください](#supported-session-border-controllers-sbcs)。|
|SBC に接続されているテレフォニー トランク|SBC に接続されている 1 つ以上のテレフォニー トランク。 一方の端では、SBC はダイレクト ルーティングをMicrosoft 電話システムに接続します。 SBC は、PBX、アナログ テレフォニー アダプターなどのサード パーティのテレフォニー エンティティにも接続できます。 SBC に接続されている PSTN 接続オプションは動作します。 (SBC への PSTN トランクの構成については、SBC ベンダーまたはトランク プロバイダーを参照してください)。|
|Microsoft 365またはOffice 365組織|ユーザー Microsoft 365をOffice 365、SBC への構成と接続をホームMicrosoft Teamsする組織または組織。|
|ユーザー レジストラー|ユーザーは、ユーザーがユーザーまたはMicrosoft 365にOffice 365。<br/>会社に Microsoft 365 または Office 365 へのハイブリッド接続を備えるオンプレミスの Skype for Business または Lync 環境がある場合、オンプレミスのユーザーに対して Teams で音声を有効にすることはできません。<br/><br/>ユーザーのレジストラーを確認するには、Online PowerShell コマンドレットSkype for Businessを使用します。<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>コマンドレットの出力には、次の情報が表示されます。<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|ドメイン|組織または組織に追加された 1 つ以上Microsoft 365ドメインOffice 365。<br/><br/>テナント用に自動的に作成される \* 既定のドメイン .onmicrosoft.com は使用できないことに注意してください。<br/><br/>ドメインを表示するには、Online PowerShell コマンドレットSkype for Businessを使用できます。<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>ドメインと組織または組織のMicrosoft 365詳細Office 365ドメインに関する FAQ[を参照してください](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC のパブリック IP アドレス|SBC への接続に使用できるパブリック IP アドレス。 SBC の種類に基づいて、SBC は NAT を使用できます。|
|SBC の完全修飾ドメイン名 (FQDN)|SBC の FQDN で、FQDN のドメイン部分が、組織または組織に登録されているMicrosoft 365ドメインOffice 365します。 詳細については [、「SBC ドメイン名」を参照してください](#sbc-domain-names)。|
|SBC のパブリック DNS エントリ |SBC FQDN をパブリック IP アドレスにマッピングするパブリック DNS エントリ。 |
|SBC のパブリック信頼された証明書 |ダイレクト ルーティングとのすべての通信に使用する SBC の証明書。 詳細については [、「SBC のパブリック信頼された証明書」を参照してください](#public-trusted-certificate-for-the-sbc)。|
|ダイレクト ルーティングの接続ポイント |ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。<br/><br/>`sip.pstnhub.microsoft.com` – グローバル FQDN、最初に試す必要があります。<br/>`sip2.pstnhub.microsoft.com` セカンダリ FQDN は、地理的に 2 番目の優先度のリージョンにマップされます。<br/>`sip3.pstnhub.microsoft.com` – 第 3 の FQDN、地理的に 3 番目の優先リージョンにマップされます。<br/><br/>構成要件の詳細については [、「SIP シグナリング: FQDN」を参照してください](#sip-signaling-fqdns)。|
|ダイレクト ルーティング メディアのファイアウォール IP アドレスとポート |SBC は、クラウド内の次のサービスに通信します。<br/><br/>シグナリングを処理する SIP プロキシ<br/>メディア プロセッサ: メディアを処理します 。Media Bypass がオンの場合を除く<br/><br/>これら 2 つのサービスには、このドキュメントで後述する Microsoft Cloud の個別の IP アドレスがあります。<br/><br/>詳細については、URL と[IP アドレス範囲Microsoft Teamsの](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)セクション[を参照してください](/office365/enterprise/urls-and-ip-address-ranges)。 |
|メディア トランスポート プロファイル|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
ファイアウォールの IP アドレスとポート (Microsoft Teams) |詳細については、「URL と [IP アドレス範囲」を参照してください](/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>ライセンスと他の要件 

ダイレクト ルーティングのユーザーには、次のライセンスが割り当てられている必要Microsoft 365またはOffice 365。 

- Microsoft 電話[システム] を選択します。 
- Microsoft Teamsに含Skype for Businessプラン 2 を選択します。
- Microsoft 電話会議 (ライセンスが必要な場合の具体的な例については、以下のノートと段落をお読みください)。

> [!NOTE]
> Skype for Businessプランを含むライセンス契約から削除する必要はありません。 
> 
> [!IMPORTANT]
> GCC高ユーザーと DoD ユーザーは、G5 に含まれる電話会議のライセンスを無効にし、ダイレクト ルーティングが完全に構成されるまで電話会議を有効にするまで待機する必要があります。 ユーザーは、電話会議のライセンスを有効にする前に、ダイヤルインの電話番号とダイヤル パッドを構成する必要があります。 詳細[については、「高レベルと DoD のGCCルーティング](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md)を使用した電話会議」を参照してください。


> [!IMPORTANT]
>  外部参加者をスケジュールされた会議に追加する場合は、ダイヤルアウトするか、ダイヤルイン番号を指定して、電話会議のライセンスが必要です。
> [GCC DoD] の場合は、G5 ユーザーに電話会議ライセンスを割り当てない。  G3 ユーザーの場合、ダイレクト ルーティングが完全に構成され、ユーザーがダイヤル パッドを使用するまで、電話会議ライセンスを割り当てない。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>アドホック通話のエスカレーションと電話会議のライセンス

ユーザー Teams PSTN への 1 対 1 Teamsを開始するか、TeamsをTeamsに PSTN 参加者を追加できます。 このシナリオは、アドホック会議と呼ばれる。 呼び出しが受け取るパスは、呼び出しをエスカレートするユーザーに Microsoft 電話会議ライセンスが割り当てられているかどうかによって異なります。

- 通話をTeamsユーザーに Microsoft 電話会議ライセンスが割り当てられている場合、そのエスカレーションは Microsoft 電話会議サービスを通じて行います。 既存の呼び出しに招待されたリモート PSTN 参加者は、着信呼び出しに関する通知を受け取り、エスカレーションを開始した Teams ユーザーに割り当てられている Microsoft ブリッジの数を確認します。
- 通話をエスカTeamsするユーザーに Microsoft 電話会議ライセンスが割り当てられていない場合、そのエスカレーションは、ダイレクト ルーティング インターフェイスに接続されたセッション ボーダー コントローラーを介して行います。 呼び出しに招待されたリモート PSTN 参加者は、着信呼び出しに関する通知を受け取り、エスカレーションを開始したユーザー Teams番号を表示します。 エスカレーションに使用される特定の SBC は、ユーザーのルーティング ポリシーによって定義されます。 


さらに、次の情報を確認する必要があります。
 
- CsOnlineVoiceRoutingPolicy がユーザーに割り当てられます。 
- プライベート呼び出しを許可するは、テナント レベルで有効Microsoft Teams。 

ダイレクト ルーティングでは、Microsoft 通話プランのライセンスを取得しているユーザーもサポートされます。 Microsoft 電話プランを呼び出すシステムでは、ダイレクト ルーティング インターフェイスを使用して一部の呼び出しをルーティングできます。 ただし、ユーザーの電話番号はオンラインで取得するか、Microsoft に移植する必要があります。  

同じユーザーの通話プランとダイレクト ルーティング接続の混在はオプションですが、便利です (たとえば、ユーザーに Microsoft 通話プランが割り当てられているが、SBC を使用して一部の呼び出しをルーティングする場合など)。 最も一般的なシナリオの 1 つは、サード パーティ製 PBX の呼び出しです。  サード パーティ PBX では、その PBX に接続されている電話への呼び出しを除くすべての通話は、Microsoft 通話プランを使用してルーティングされますが、サード パーティ製 PBX に接続されている電話への通話は SBC に送信されるため、PSTN ではなくエンタープライズ ネットワーク内にとどまっています。 

ライセンスの詳細については、「電話システムの詳細」および「プラン オプション[Officeを](https://products.office.com/compare-all-microsoft-office-products?tab=2)[参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。 

ライセンスの詳細については電話システムのライセンスMicrosoft Teams[を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。 

## <a name="supported-end-points"></a>サポートされているエンド ポイント 

エンド ポイントとして使用できます。

- すべてのTeamsクライアント。 
- 共通領域の電話。 「[共有領域のライセンスを設定する電話」をMicrosoft Teams。](./set-up-common-area-phones.md) ダイレクト ルーティングを使用して共通領域を設定するときに、通話プラン ライセンス電話必要ない点に注意してください。
- Skype for Business 3PIP 電話を使用します。 詳細[についてはSkype for Business電話 (3PIP)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)のサポートに関するページをMicrosoft Teams


## <a name="sbc-domain-names"></a>SBC ドメイン名

SBC ドメイン名は、テナントのドメインに登録されている名前の 1 つからである必要があります。 SBC の \* FQDN 名 onmicrosoft.com .onmicrosoft.com テナントを使用することはできません。

次の表は、テナントに登録されている DNS 名の例、SBC の FQDN として名前を使用できるかどうか、および有効な FQDN 名の例を示しています。

|DNS 名|SBC FQDN に使用できます|FQDN 名の例|
|:--- |:--- |:--- |
contoso.com|はい|**有効な名前:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|いいえ|SBC 名 onmicrosoft.com *.onmicrosoft.com ドメインの使用はサポートされていません

新しいドメイン名を使用するとします。 たとえば、テナントにドメイン contoso.com が登録されている場合、テナントを使用 sbc1.sip.contoso.com。 SBC と名前を組み合 sbc1.sip.contoso.com、テナントのドメインにドメイン名 sip.contoso.com 登録する必要があります。 ドメイン名を登録する前に SBC と sbc1.sip.contoso.com をペアリングすると、「このテナント用に構成されていないので、"sbc1.sip.contoso.com" ドメインを使用できません」 というエラーが表示されます。
ドメイン名を追加した後、UPN を使用してユーザーを作成し、user@sip.contoso.com ライセンスを割りTeams必要があります。 ドメイン名がテナントのドメインに追加され、新しい名前を持つユーザーが作成され、ライセンスがユーザーに割り当てられた後、ドメイン名を完全にプロビジョニングするには、最大で 24 時間かかる場合があります。 

1 つのテナントに複数の SIP アドレス空間がある可能性があります。 たとえば、企業が SIP アドレス空間 contoso.com、2 つ目の SIP アドレス空間として fabrikam.com を使用している可能性があります。 一部のユーザーは、user@contoso.com アドレスを持ち、一部のユーザーはアドレスを持 user@fabrikam.com。 

SBC は 1 つの FQDN のみを必要とし、ペアのテナント内の任意のアドレス空間からユーザーにサービスを提供できます。 たとえば、sbc1.contoso.com という名前の SBC は、これらの SIP アドレス 空間が同じテナントに登録されている限り、アドレス user@contoso.com と user@fabrikam.com を持つユーザーの PSTN トラフィックを送受信できます。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC のパブリック信頼された証明書

Microsoft では、証明書署名要求 (CSR) を生成して SBC の証明書を要求をお勧めします。 SBC の CSR を生成する具体的な手順については、SBC ベンダーが提供する相互接続の手順またはドキュメントを参照してください。 

  > [!NOTE]
  > ほとんどの認証局 (CA) では、少なくとも 2048 のプライベート キー サイズが必要です。 CSR を生成する場合は、これを念頭に置いておきます。

証明書には、共通名 (CN) またはサブジェクト代替名 (SAN) フィールドとして SBC FQDN が必要です。 証明書は、中間プロバイダーからではなく、証明機関から直接発行する必要があります。

または、ダイレクト ルーティングでは CN または SAN のワイルドカードがサポートされ、ワイルドカードは標準の RFC HTTP Over TLS に準拠 [している必要があります](https://tools.ietf.org/html/rfc2818#section-3.1)。 たとえば、SBC FQDN contoso.com と一致する .sbc.contoso.com を使用しますが、この値と一致 \* sbc.test.contoso.com。

証明書は、次のいずれかのルート証明機関によって生成される必要があります。

- ア肯定トラスト
- AddTrust 外部 CA ルート
- Baltimore CyberTrust Root*
- Buypass
- サイバートラスト
- クラス 3 パブリック プライマリ証明機関
- Comodo Secure Root CA
- Deutsche Telekom 
- DigiCert グローバル ルート CA
- DigiCert High Assurance EV ルート CA
- お任せ
- GlobalSign
- お父さんを移動する
- GeoTrust
- Verisign, Inc. 
- SSL.com
- スターフィールド
- Symantec Enterprise Mobile Root for Microsoft 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis
- USERTrust RSA 証明機関
- 香港事後ルート CA 1,2,3
- Sectigo Root CA

GCCH および DoD Office 365直接ルーティングの場合、証明書は次のいずれかのルート証明機関によって生成される必要があります。
- DigiCert グローバル ルート CA
- DigiCert High Assurance EV ルート CA

> [!NOTE]
> *SBC の Teams 接続に対して相互 TLS (MTLS) のサポートが有効になっている場合は、Teams TLS コンテキストの SBC 信頼されたルート ストアに Baltimore CyberTrust ルート証明書をインストールする必要があります。 (これは、Microsoft サービス証明書がボルチモアルート証明書を使用しているためです。Baltimore ルート証明書をダウンロードするには、「暗号化[チェーンOffice 365を参照してください](/microsoft-365/compliance/encryption-office-365-certificate-chains)。

Microsoft は、顧客の要求に基づいて証明機関を追加する作業を行っています。 

## <a name="sip-signaling-fqdns"></a>SIP シグナリング: FQDN 

ダイレクト ルーティングは、次の環境で提供されます。
- Microsoft 365またはOffice 365
- Office 365 GCC
- Office 365 GCC高
- Office 365DoD

詳細については[、Office 365、](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)高値、DoD など、GCC米国GCC環境に関する情報を参照してください。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、およびOffice 365 GCC環境

ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN – 最初に試す必要があります。 SBC がこの名前を解決するための要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。 割り当ては、データセンターのパフォーマンス メトリックと SBC への地理的な近接性に基づいて行われます。 返される IP アドレスは、プライマリ FQDN に対応します。
- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に 2 番目の優先度のリージョンにマップされます。
- **sip3.pstnhub.microsoft.com** – ターシャリ FQDN – 地理的に 3 番目の優先順位のリージョンにマップされます。

次の 3 つの FQDN を順番に配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込まれ少なく、最初の FQDN を照会して割り当てられた SBC データセンターに最も近い)。
- 一時的な問題が発生しているデータセンターへの SBC からの接続が確立された場合は、フェールオーバーを提供します。 詳細については、以下の「 [フェールオーバー メカニズム」を参照](#failover-mechanism-for-sip-signaling) してください。  

FQDN (sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.com) は、次のいずれかの IP アドレスに解決されます。

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29
- 52.114.36.156 
- 52.114.32.169

これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN **sip-all.pstnhub.microsoft.com** すべての IP アドレスに解決されます。 

> [!IMPORTANT]
>  ダイレクト ルーティングの拡張Teamsサービスの改善の一環として、オーストラリアに Direct Routing インフラストラクチャの新しいインスタンスをデプロイしました。 これは、オーストラリアのお客様 (sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.com の 2 つの追加 IP アドレス (52.114.16.74 と 52.114.20.29) に反映されます。 これら 2 つの IP アドレス (52.114.16.74 と 52.114.20.29) を IP アクセス制御リスト (ACL) に追加し、ファイアウォール内のすべてのこれらの IP アドレスのポートを開いて、信号を送信するアドレス間の着信トラフィックを許可する必要があります。

### <a name="office-365-gcch-and-dod-environment"></a>Office 365GCCH および DoD 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。 DoD Office 365は米国のデータ センターにのみ存在しますが、セカンダリ FQDN とターシャリ FQDN はありません。

FQDN sip.pstnhub.dod.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。

- 52.127.64.33
- 52.127.68.34

これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高い環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 High 環境GCC米国のデータ センターにのみ存在します。セカンダリ FQDN とターシャリー FQDN はありません。

FQDN sip.pstnhub.gov.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。

- 52.127.88.59
- 52.127.92.64

これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。 ファイアウォールで DNS 名がサポートされている場合 **、FQDN** sip-all.pstnhub.gov.teams.microsoft.us すべての IP アドレスに解決されます。 この FQDN は、着信呼び出しの分類にフェデレーション FQDN として使用できます。

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

ダイレクト ルーティングが提供される環境Microsoft 365またはOffice 365ポートを使用する必要があります。
- Microsoft 365またはOffice 365
- Office 365 GCC
- Office 365 GCC高
- Office 365DoD

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP プロキシ|SBC|1024 – 65535|SBC で定義されている (Office 365 GCC High/DoD のみポート 5061 を使用する必要があります)|
SIP/TLS|SBC|SIP プロキシ|SBC で定義されている|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP シグナリングのフェールオーバー メカニズム

SBC では、DNS クエリを実行して問題を解決 sip.pstnhub.microsoft.com。 SBC の場所とデータセンターのパフォーマンス メトリックに基づいて、プライマリ データセンターが選択されます。 プライマリ データセンターで問題が発生した場合、SBC は sip2.pstnhub.microsoft.com を試します。これは 2 番目に割り当てられたデータセンターに解決され、まれに 2 つのリージョンのデータセンターが利用できない場合、SBC は、第 3 データセンター IP を提供する最後の FQDN (sip3.pstnhub.microsoft.com) を再試行します。

次の表は、プライマリ データセンター、セカンダリ データセンター、第 3 データセンター間の関係をまとめたものです。

|プライマリ データセンターが|EMEA|NOAM|アジア|
|:--- |:--- |:--- |:--- |
|セカンダリ データセンター (sip2.pstnhub.microsoft.com)|米国|EU|米国|
|3 次データセンター (sip3.pstnhub.microsoft.com)|アジア|アジア|EU|
|||||

## <a name="media-traffic-port-ranges"></a>メディア トラフィック: ポート範囲
メディア バイパスを使用せずにダイレクト ルーティングをデプロイする場合は、次の要件が適用されます。 メディア バイパスのファイアウォール要件については、「ダイレクト ルーティングを使用したメディア バイパス [の計画」を参照してください](./direct-routing-plan-media-bypass.md)。



メディア トラフィックは、Microsoft Cloud 内の別のサービスと間で流れます。 メディア トラフィックの IP アドレス範囲は次のとおりです。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、およびOffice 365 GCC環境

- 52.112.0.0/14 (52.112.0.1 から 52.115.255.254 の IP アドレス)。
- 52.120.0.0/14 (52.120.0.1 から 52.123.255.254 の IP アドレス)。

### <a name="office-365-dod-environment"></a>Office 365DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高い環境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>ポート範囲 (すべての環境に適用)
メディア プロセッサのポート範囲を次の表に示します。 

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|メディア プロセッサ|SBC|3478-3481 および 49152 – 53247|SBC で定義されている|
|UDP/SRTP|SBC|メディア プロセッサ|SBC で定義されている|3478-3481 および 49152 – 53247|

  > [!NOTE]
  > Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートをお勧めします。


## <a name="media-traffic-media-processors-geography"></a>メディア トラフィック: メディア プロセッサの地理

メディア トラフィックは、メディア プロセッサと呼ばれるコンポーネントを介して流れます。 メディア プロセッサは、SIP プロキシと同じデータセンターに配置されます。 また、メディア フローを最適化するための追加のメディア プロセッサがあります。 たとえば、現在、オーストラリアには SIP プロキシ コンポーネント (シンガポールまたは香港経由の SIP フロー) は含んでおかしくなっていますが、オーストラリアにはローカルにメディア プロセッサがあります。 ローカルでのメディア プロセッサの必要性は、オーストラリアからシンガポールや香港にトラフィックを長距離送信することで発生する待機時間によって決まる。 オーストラリアから香港またはシンガポールに流れるトラフィックの例の待ち時間は、SIP トラフィックの良好な通話品質を維持するために許容されるが、リアルタイムのメディア トラフィックでは許容されない。

メディア プロセッサの場所:

SIP プロキシコンポーネントとメディア プロセッサ コンポーネントの両方がデプロイされた場所:
- 米国 (米国西部と米国東部のデータセンターで 2 つ)
- ヨーロッパ (アムステルダムとダブリンのデータセンター)
- アジア (シンガポールと香港のデータセンター)

メディア プロセッサのみをデプロイする場所 (上記の最も近いデータセンターを介して SIP フロー):
- 日本 (JP 東と西のデータセンター)
- オーストラリア (AU 東および南東のデータセンター)




## <a name="media-traffic-codecs"></a>メディア トラフィック: コーデック

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC と Cloud Media Processor の間またはクライアントMicrosoft Teamsします。
メディア バイパス ケースと非バイパス ケースの両方に適用されます。

セッション ボーダー コントローラーとクラウド メディア プロセッサの間 (メディア バイパスなし) または Teams クライアントと SBC (メディア バイパスが有効な場合) の間の脚のダイレクト ルーティング インターフェイスでは、次のコーデックを使用できます。

- 非メディア バイパス (SBC からクラウド メディア プロセッサ): SILK、G.711、G.722、G.729
- メディア バイパス (SBC Teamsクライアント): SILK、G.711、G.722、G.729

セッション ボーダー コントローラーで特定のコーデックを強制的に使用するには、オファーから望ましくないコーデックを除外します。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>クライアントとクラウド Microsoft Teamsプロセッサの間の脚
メディア以外のバイパス ケースにのみ適用されます。 Media Bypass を使用すると、メディアはクライアントと SBC Teams直接流れます。

クラウド メディア プロセッサとクラウド クライアントの間Microsoft Teamsでは、SILK または G.722 が使用されます。 この脚のコーデックの選択は、複数のパラメーターを考慮した Microsoft アルゴリズムに基づいて選択されます。 


## <a name="supported-session-border-controllers-sbcs"></a>サポートされているセッション ボーダー コントローラー (SPC)

Microsoft では、ダイレクト ルーティングとペアリングする認定 SBC のみをサポートしています。 このエンタープライズ VoIPは企業にとって重要なので、Microsoft は選択した SBC で集中的なテストを実行し、SBC ベンダーと組み合わせて 2 つのシステムの互換性を確保します。 

検証済みのデバイスは、ダイレクト ルーティングの認定Teams一覧表示されます。 認定されたデバイスは、すべてのシナリオで動作する保証があります。 

サポートされている SPC の詳細については、「ダイレクト ルーティングの認定を受けたセッション ボーダー コントローラーの一覧」 [を参照してください](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
