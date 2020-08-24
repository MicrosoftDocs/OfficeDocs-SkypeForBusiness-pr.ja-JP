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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft Phone System DirectRouting でサポートされているサポートされている Session Border Controller (SBC) を Microsoft Phone System に接続する方法について説明します。
ms.openlocfilehash: bb711b72fb200ceec9d2c50c86f6f977436c9c02
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860808"
---
# <a name="plan-direct-routing"></a>ダイレクト ルーティングを計画する

> [!Tip]
> 次のステッションでは、直接ルーティングのメリット、その計画方法、および展開方法について [学習します。Microsoft Teams で直接ルーティングを行う](https://aka.ms/teams-direct-routing)

Microsoft Phone System ルーティングでは、サポートされている、顧客が提供するセッション ボーダー コントローラー (SBC) を Microsoft Phone System に接続できます。  たとえば、この機能を使用すると、次の図に示すように、Microsoft Teams クライアントとのオンプレミスの公開切り替え電話ネットワーク (PSTN) 接続を構成できます。 

![オンプレミス PSTN 接続の構成を示す図](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft Teams クライアントを使用したオンプレミス PSTN 接続の構成")

  > [!NOTE]
  > Skype for Business Online では、顧客が提供する SBC のペアリングもできますが、これには、SBC と Microsoft Cloud の間にオンプレミスの Skype for Business Server 展開またはクラウド コネクタと呼ぶ特別版の Skype for Business Server 展開またはクラウド Connector と呼ぶ特別なエディションの Skype for Business Server 展開が必要です。 このシナリオは、ハイブリッド音声とも知られます。 これに対して、直接ルーティングでは、サポートされている SBC と Microsoft Cloud 間の直接接続を使用できます。 

ダイレクト ルーティングを使用すると、ほぼすべてのテレフォニーのトランクまたはサードパーティの PSTN のコマンドとの間で SBC を接続することができます。 ルーティングを使用すると、次のことを行うことを行うための機能を使用できます。 

- Microsoft 電話システムで仮想的に PSTN トランクを使います。 
- サードパーティのプライベート ブランチ交換 (PBX)、アナログ デバイス、Microsoft 電話システムなどの顧客所有のテレフォニティ デバイス間で相互に対する相互体の設定を構成します。

Microsoft は、通話プランなどのクラウド内音声ソリューションも利用できます。 ただし、次の場合にハイブリッド音声ソリューションが最も有効な場合があります。 

- お使いの国では Microsoft 通話プランを利用できません。 
- 組織ではサードパーティのアナログ デバイスや通話センターなどに接続する必要があります。 
- 組織には PSTN キャリアとの既存の対を行うことになります。

直接ルーティングでは、Microsoft 通話プランの追加ライセンスを持つユーザーもサポートします。 詳細については、[電話システムと通話プラン](calling-plan-landing-page.md)に関する記事をご覧ください。 

ダイレクト ルーティングを使用すると、ユーザーがスケジュール済みの会議に参加すると、ダイヤルイン番号は Microsoft 電話会議サービスによって提供され、適切なライセンスが必要です。  ダイヤルアウトすると、Microsoft 電話会議サービスによってオンライン通話機能を使用して通話が発信されます。この機能には、適切なライセンスが必要です。 (ユーザーが Microsoft 電話会議ライセンスを持っていない場合は、直接ルーティングを介してルーティングします)。詳細については [、Teams でオンライン会議を参照してください](https://products.office.com/microsoft-teams/online-meeting-solutions)。 
 
直接ルーティングの展開を計画することは、実装を成功に導くうえでの主な展開です。 この記事では、インフラストラクチャとライセンスの要件について説明し、SBC 接続についての情報を提供します。 

- [インフラストラクチャの要件](#infrastructure-requirements)
- [ライセンスおよびその他の要件](#licensing-and-other-requirements)
- [SBC ドメイン名](#sbc-domain-names)
- [SBC のパブリック信頼された署名](#public-trusted-certificate-for-the-sbc)
- [SIP シグナリング:FQDN](#sip-signaling-fqdns)
- [SIP シグナリング:ポート](#sip-signaling-ports)
- [メディア トラフィック: ポート範囲](#media-traffic-port-ranges)
- [サポートされているセッション ボーダー コントローラー (SBC)](#supported-session-border-controllers-sbcs)

ルーティングの構成の詳細については、「Direct Routing を構成する [」を参照してください](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
ダイレクト ルーティングの展開に対応している SBC、ドメイン、およびその他のネットワーク接続要件のインフラストラクチャ要件は、次の表に示します。  

|インフラストラクチャの要件|次の情報が必要です|
|:--- |:--- |
|セッション ボーダー コントローラー (SBC)|サポートされている SBC。 詳細については、サポートされている [SBC を参照してください](#supported-session-border-controllers-sbcs)。|
|SBC に接続されているテレフェニックが切り捨てられます。|SBC に接続されている 1 つ以上のテレフェンスが切り捨てられます。 一終的に、SBC はダイレクト ルーティングを使用して Microsoft 電話システムに接続します。 また、SBC は、PBX、Analog Telephony Adapters などのサードパーティ テレフニ エンティエントに接続することもできます。 SBC に接続されている PSTN 接続オプションがすべて機能します。 (PSTN の構成が SBC にトランク付けされる場合は、SBC ベンダーまたはトランク プロバイダーを参照してください)。|
|Microsoft 365 または Office 365 組織|Microsoft Teams ユーザーの家Officeンで使用する Microsoft 365 または 365 組織、および SBC への接続。|
|ユーザー レジストラー|ユーザーは Microsoft 365 または Office 365 でOfficeである必要があります。<br/>会社に Microsoft 365 または Office 365 へのハイブリッド接続を使用するオンプレミスの Skype for Business または Lync 環境がある場合、ユーザー自宅オンプレミスの Teams で音声を有効にできません。<br/><br/>ユーザーのレジストラーを確認するには、次の Skype for Business Online PowerShell コマンドレットを使用します。<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>次のコードレットの出力が表示されます。<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|ドメイン|Microsoft 365 または 365 組織に追加された 1 つまたは複数の Officeドメイン。<br/><br/>テナント用に自動 \* 的に作成される既定のドメイン .onmicrosoft.com を使用することはできません。<br/><br/>ドメインを表示するには、次の Skype for Business Online PowerShell コマンドレットを使用できます。<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>ドメインおよび Microsoft 365 または Office 365 の組織の詳細については、ドメインに関するよく寄せられる [質問を参照してください](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC のパブリック IP アドレス|SBC への接続に使用できるパブリック IP アドレス。 SBC の種類に基づいて、SBC で NAT を使用できます。|
|SBC の完全認済みドメイン名 (FQDN)|FQDN のドメイン部分が Microsoft 365 または Office 365 組織の登録済みドメインのいずれかである SBC の FQDN。 詳細については [、SBC ドメイン名を参照してください](#sbc-domain-names)。|
|SBC のパブリック DNS エントリ |パブリック IP アドレスに SBC FQDN をマッピングするパブリック DNS エントリ。 |
|SBC のパブリック信頼された署名 |直接ルーティングとのすべての通信で使用する SBC 用の資料です。 詳細については [、SBC の公開信頼できる署名を参照してください](#public-trusted-certificate-for-the-sbc)。|
|ルーティングの接続ポイント |直接ルーティングの接続ポイントは、次の 3 つの FQDN です。<br/><br/>`sip.pstnhub.microsoft.com` – グローバル FQDN は最初に試行する必要があります。<br/>`sip2.pstnhub.microsoft.com` – 第 2 の FQDN。地理的には、2 番目の優先度領域にマップします。<br/>`sip3.pstnhub.microsoft.com` – テティアの FQDN。地理的には、3 番目の優先地域にマップされます。<br/><br/>構成要件については [、SIP 号化: FQDN を参照してください](#sip-signaling-fqdns)。|
|ファイアウォール IP アドレスとダイレクト ルーティング メディアのポート |SBC はクラウド内の次のサービスに通信します。<br/><br/>シグナリングを処理する SIP プロキシ<br/>メディア プロセッサ 。メディア バイパスがオンの場合を除くメディア プロセッサ<br/><br/>これら 2 つのサービスは、このドキュメントで後述した Microsoft Cloud で個別の IP アドレスを持っています。<br/><br/>詳細については、IP アドレスと IP アドレス [範囲の Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [セクションを参照してください](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 |
|メディアトランスポート プロファイル|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams メディアのファイアウォール IP アドレスとポート |詳細については [、IP アドレスと IP アドレスの範囲を参照してください](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>ライセンスおよびその他の要件 

直接ルーティングのユーザーには、Microsoft 365 または 365 ライセンスで次のライセンスが割り当てられ Officeている必要があります。 

- Microsoft 電話システム。 
- ライセンスに含まれている場合は、Microsoft Teams + Skype for Business プラン 2。
- Microsoft 電話会議 (ライセンスが必要な場合の具体的な例については、以下のメモと段落をお読みください)。

> [!NOTE]
> Skype for Business プランは、含まれているライセンスに関するいかのライセンスに関する一切のライセンスに関するもので削除しないでください。 


> [!IMPORTANT]
>  どちらかのダイヤルアウトするか、ダイヤルイン番号を指定して、会議に外部参加者を追加する場合は、電話会議ライセンスが必要です。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>アドホック通話のオプションと電話会議ライセンス

Teams ユーザーは、PSTN または Teams から PSTN または Teams 通話を利用して、PSTN 参加者を追加できます。 このシナリオは、アドホック会議と呼びます。 通話が行われるパスは、通話をエスカレーションするユーザーに Microsoft 電話会議ライセンスが割り当てられているかどうかによって異なります。

- 通話をエスカレートする Teams ユーザーに Microsoft 電話会議ライセンスが割り当てられている場合、エスカレーションは Microsoft 電話会議サービスを通じて行われます。 既存の通話に招待されるリモート PSTN の参加者は、着信通話についての通知を受け取り、エスカレーションを開始した Teams ユーザーに割り当てられた Microsoft Bridge の番号が表示されます。
- 通話をエスカレートする Teams ユーザーに Microsoft 電話会議ライセンスが割り当てられていない場合、エスカレーションは直接ルーティング インターフェイスに接続された Session Border Controller を通じて行われます。 通話に招待されたリモート PSTN の参加者は、着信通話に関する通知を受け取り、エスカレーションを開始した Teams ユーザーの数を確認します。 エスカレーションに使用される特定の SBC は、ユーザーのルーティング ポリシーによって定義されます。 


また、以下のことを確認する必要があります。
 
- CsOnlineVoiceRoutingPolicy がユーザーに割り当てられます。 
- プライベート通話は Microsoft Teams のテナント レベルで有効になります。 

直接ルーティングは、Microsoft 通話プランのライセンスを持つユーザーもサポートします。 通話プラン付きの Microsoft 電話システムでは、ダイレクト ルーティング インターフェイスを使用して一部の通話をルーティングできます。 ただし、ユーザーの電話番号はオンラインで入手するか、Microsoft に移行する必要があります。  

同じユーザーの通話プランとダイレクト ルーティング接続はオプションですが、便利な場合があります (たとえば、Microsoft 通話プランが割り当てられても、SBC を使用して通話をルーティングしたい場合など)。 最も一般的なシナリオの 1 つは、サードパーティ PBX への呼び出しです。  サードパーティの PBX では、その PBX に接続された電話を除くすべての通話は Microsoft 通話プランを使用してルーティングされますが、サードパーティ PBX に接続されている電話への通話は SBC にアクセスするので、PSTN は実用ネットワーク内に入れるため、PSTN は入手しません。 

電話システムのライセンスの詳細については[、「Office オプションとプランのオプションをOffice」](https://products.office.com/compare-all-microsoft-office-products?tab=2)[を参照してください](https://technet.microsoft.com/library/office-365-plan-options.aspx)。 

電話システムのライセンスの詳細については、Microsoft Teams の [アドオン ライセンスをご覧ください](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。 

## <a name="supported-end-points"></a>サポートされるエンドポイント 

エンドポイントとして使用できます。

- 任意の Teams クライアント。 
- 一般的なエリア Phone [「Microsoft Teams の共通領域の電話ライセンスをセットアップする」をご覧ください](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)。 ダイレクト ルーティングで共通の領域フォンを設定する場合は、通話プランのライセンスは必要ありません。
- Skype for Business 3PIP 電話。 [Microsoft Teams で Skype for Business 電話 (3PIP) のサポートを参照する](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC ドメイン名

SBC ドメイン名はテナントの Domains に登録されている名前の 1 つである必要があります。 \*SBC の FQDN 名には .onmicrosoft.com テナントを使用できない。

次の表は、テナントに登録されている DNS 名の例、その名前を SBC の FQDN として使用できるかどうか、有効な FQDN 名の例を示しています。

|DNS 名|SBC FQDN に使用できます|FQDN の名前の例|
|:--- |:--- |:--- |
contoso.com|はい|**有効な名前:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|いいえ|SBC 名に *.onmicrosoft.com ドメインを使用することはできません

新しいドメイン名を使うとします。 たとえば、テナントにはテナントにcontoso.comており、そのドメイン名をsbc1.sip.contoso.com。 SBC と名前をペアsbc1.sip.contoso.com、テナントのドメインsip.contoso.com登録する必要があります。 ドメイン名を登録する前に、sbc1.sip.contoso.com と SBC をペアリングしようとすると、"このテナントに構成されていない "sbc1.sip.contoso.com" ドメインが使用されません。
ドメイン名を追加した後は、UPN アカウントを使用してユーザーを作成して Teams user@sip.contoso.com割り当てる必要もあります。 テナントのドメインにドメイン名を追加した後、新しい名前を含むユーザーが作成され、ライセンスがユーザーに割り当てられてから、ライセンスがユーザーに割り当てられるまで、最大で 24 時間かかる場合があります。 

1 つのテナントに会社が複数の SIP アドレス空間を持つ場合があります。 たとえば、会社には SIP アドレス空間として contoso.comスペースとして、2 番目の SIP アドレス空間としてfabrikam.comを持つ場合があります。 一部のユーザーには、user@contoso.com アドレスがあり、一部のユーザーにアドレスuser@fabrikam.com。 

SBC では必要な FQDN のみが必要です。ペアリングされたテナントのアドレス空間からユーザーをサービスを使用できます。 たとえば、名前 sbc1.contoso.com と user@fabrikam.com のユーザーの PSTN トラフィックを受信および送信できるのが、これらの SIP アドレス空間が user@contoso.com同じテナントに登録されている場合は、その名前 sbc1.contoso.com がユーザーの PSTN トラフィックを受信および送信することができます。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC のパブリック信頼された署名

Microsoft では、証明書署名要求 (CSR) を生み、SBC に対する証明書を要求することをお勧めします。 SBC 用の CSR を生用に生用する方法については、SBC ベンダーが提供する間の接続手順またはドキュメントを参照してください。 

  > [!NOTE]
  > ほとんどの主要件 (CA) には、2048 年以上の主キー サイズが必要です。 CSR を生み出すときには、この作業を行う必要があります。

この場合、サブジェット フィールドには共通名 (CN) として SBC FQDN を用語にする必要があります。

または、直接ルーティングは SAN のワイルドカードをサポートし、ワイルドカードは [TLS を超える HTTP に一定する必要があります](https://tools.ietf.org/html/rfc2818#section-3.1)。 たとえば \* 、SAN の .contoso.com を使用します。SAN の場合は SBC FQDN sbc.contoso.com と一致しますが、sbc.test.contoso.com と一致しません。

次のルートの認明書のいずれかが作成される必要があります。

- AffirmTrust
- AddTrust External CA Root
- Baltimore CyberTrust Root*
- 購入
- Cybertrust
- Class 3 Public Primary Certification Authority
- Comodo Secure Root CA
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV ルート CA
- 信頼
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- 星型
- Microsoft のシマンテック Enterprise Mobile Root 
- SwissSign
- タイマーキング キャプチャ
- Trustwave
- TeliaSonera 
- T システム国際 GmbH (Deutsche Telekom)
- QuoVadis



> [!NOTE]
> * SBC 上の Teams 接続で MTLS (MTLS) のサポートが有効になっている場合は、Teams TLS コンテキストの SBC 信頼できるルート ストアに Baltimore CyberTrust Root Certificate をインストールする必要があります。 (これは、Microsoft サービスの認めが Baltimore ルート チケットを使用するためです)。Baltimore ルート チェー [ンをダウンロードするには、Office 365 Encryption チェーンを参照してください](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)。

Microsoft は、お客様からの要求に基づいて、追加の認認当者を追加できるように取り上げられます。 

## <a name="sip-signaling-fqdns"></a>SIP シグナリング:FQDN 

Direct Routing は、次の環境で利用できます。
- Microsoft 365 または Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

GCC [Office、GCC High、DoD などの、米](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 国のガバナンス環境の詳細については、こちらをご覧ください。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office および 365 GCC 環境

直接ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN – まず試行する必要があります。 SBC からこの名前を解決する要求が SBC から送信されると、Microsoft Azure DNS サーバーは SBC に割り当てられているプライマリ Azure データセンターをポイントしている IP アドレスを返します。 割り当ては、SBC に対するデータセンターのパフォーマンス メトリックとジオリンジェントに基づいています。 返される IP アドレスは、プライマリ FQDN に対応します。
- **sip2.pstnhub.microsoft.com** – 第 2 の FQDN – 地理的に 2 番目の優先度領域にマップします。
- **sip3.pstnhub.microsoft.com** テティア FQDN – 地理的に第 3 の優先度領域にマップします。

次の 3 つの FQDN を順序で配置する必要があります。

- 最適な操作性を提供する (最初の FQDN クエリによって割り当てられた SBC データセンターに最も負の数字を最もよく使用します)。
- 一時的な問題が発生しているデータセンターに SBC からの接続が設定された場合は、フェールオーバーを提供します。 詳細については、以下の [Failover メカニスムを](#failover-mechanism-for-sip-signaling) 参照してください。  

FQDN (ページ、sip.pstnhub.microsoft.com スsip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.com 1 は、次の IP アドレスのいずれかに解決されます。

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

受信および発行するアドレスの受信トラフィックをアドレスとの内部で許可するには、ファイアウォールでこれらのすべての IP アドレスのポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip-all.pstnhub.microsoft.comすべての IP アドレスに解決されます。 


### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

Direct ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.usー** バル FQDN。 Office 365 DoD 環境が米国のデータ センターにのみ存在するので、セカンダリとテクニカリの FQDN はありません。

FQDN sip.pstnhub.dod.teams.microsoft.us次の IP アドレスのいずれかに解決されます。

- 52.127.64.33
- 52.127.68.34

受信および発行するアドレスの受信トラフィックをアドレスとの内部で許可するには、ファイアウォールでこれらのすべての IP アドレスのポートを開く必要があります。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC の高い環境

Direct ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 GCC ハイ環境は米国のデータ センターにのみ存在するため、セカンダリとテクニカル FQDN はありません。

FQDN sip.pstnhub.gov.teams.microsoft.us次の IP アドレスのいずれかに解決されます。

- 52.127.88.59
- 52.127.92.64

受信および発行するアドレスの受信トラフィックをアドレスとの内部で許可するには、ファイアウォールでこれらのすべての IP アドレスのポートを開く必要があります。

## <a name="sip-signaling-ports"></a>SIP シグナリング:ポート

ダイレクト ルーティングが利用されている Microsoft 365 または Office 365 環境では、次のポートを使用する必要があります。
- Microsoft 365 または Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP プロキシ|SBC|1024 – 65535|SBC で定義 (Office 365 GCC 高/DoD のみを使用する必要があります)|
SIP/TLS|SBC|SIP プロキシ|SBC で定義される|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP シグナリングのフェールオーバー メカニスム

SBC によって、DNS クエリを作成して、この問題を解決sip.pstnhub.microsoft.com。 SBC の場所とデータセンターのパフォーマンス メトリックに基づいて、主データセンターの主なデータセンターが選択されます。 主なデータセンターで問題が発生した場合、SBC は sip2.pstnhub.microsoft.com、2 つ目に割り当てられたデータセンターに解決され、2 つの領域のデータセンターを利用できない場合は、SBC は最後に FQDN (sip3.pstnhub.microsoft.com) を再試行します。これは、Tertiary データセンター IP を提供する最後の FQDN (sip3.pstnhub.microsoft.com) が再試行されます。

次の表は、主キー、セカンダリ、およびテクニカル データセンター間のリレーションシップを示しています。

|主なデータセンターが|EMEA|NOAM|アジア|
|:--- |:--- |:--- |:--- |
|セカンダリ データセンター (sip2.pstnhub.microsoft.com)|米国|EU|米国|
|tertiary datacenter (sip3.pstnhub.microsoft.com)|アジア|アジア|EU|
|||||

## <a name="media-traffic-port-ranges"></a>メディア トラフィック: ポート範囲
メディア バイパスを使用せずにルーティングを展開する場合、以下の要件は適用されます。 メディア バイパスのファイアウォール要件については、直接ルーティングを使用してメディアを計画 [してください](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)。



メディア トラフィックは、Microsoft Cloud の別のサービスとの対対に行います。 メディア トラフィックの IP アドレス範囲は次のとおりです。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office および 365 GCC 環境

- 52.112.0.0/14 (52.112.0.1 から 52.115.255.254 の IP アドレス)
- 52.120.0.0/14 (52.120.0.1 から 52.123.255.254 の IP アドレス)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC の高い環境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>ポート レンジ (すべての環境に準じます)
メディア プロセッサの一部が次の表に示されています。 

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|メディア プロセッサ|SBC|3478-3481 および 49152 – 53247|SBC で定義される|
|UDP/SRTP|SBC|メディア プロセッサ|SBC で定義される|3478-3481 および 49152 – 53247|

  > [!NOTE]
  > Microsoft では、SBC の同時呼び出しあたり 2 つ以上のポートをお勧めします。


## <a name="media-traffic-media-processors-geography"></a>メディア トラフィック: メディア プロセッサの地理

メディア トラフィック フローはメディア プロセッサと呼びます。 メディア プロセッサは、SIP プロキシと同じデータセンター内に配置されます。 メディア フローを最適化するメディア プロセッサも用です。 たとえば、オーストラリア (Singapore または Hong Kong Kong Kong から SIP フロー) に SIP プロキシ コンポーネントが現在ありませんが、オーストラリアではローカルにメディア プロセッサがあります。 ローカルでメディア プロセッサのニーズは、たとえば、Australia から Singapore や Hong Kong Kong など、トラフィック長距離を送信することによって発生する遅延によって提供されます。 オーストラリアからハンガリーやシンガポールへのトラフィックの例では遅延時間がかかっていますが、SIP トラフィックに対して良い通話品質を保持することが可能ですが、リアルタイム メディア トラフィックに対しては良い通話品質を保持することが可能です。

メディア プロセッサの場所:

SIP プロキシとメディア プロセッサ コンポーネントの両方が展開されている場所:
- 米国 (米国および米国の 2 つ)
- Europe (Amsterdam と Dublin のデータセンター)
- アジア (シンガポールと英国のデータセンター)

メディア プロセッサのみが配置されている場所 (上に示した最もも新しいデータセンターを使用して SIP フロー) する場所:
- 日本 (日本とウェスト データセンター)
- Australia (AU East および Southest のデータセンター)




## <a name="media-traffic-codecs"></a>メディア トラフィック: コーデック

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC とクラウド メディア プロセッサまたは Microsoft Teams クライアントを切り替えます。
大文字と小文字以外のケースの両方に適用されます。

セッション ボーダー コントローラーとクラウド メディア プロセッサ間 (メディア バイパスを使用しない) の間の方向ルーティング インターフェイス、または Teams クライアントと SBC (メディア バイパスが有効な場合) は、次のコーデックを使用できます。

- メディア以外のバイパス (SBC からクラウド メディア プロセッサ): SILK、G.711、G.722、G.729
- メディア バイパス (SBC から Teams クライアントへの): SILK、G.711、G.722、G.729

Session Border コントローラーで特定のコーデックを使用するには、オファーからの不可のコーデックを除外します。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams クライアントとクラウド メディア プロセッサ間の切り替え
メディア以外のバイパスのみに適用されます。 メディア バイパスを使用すると、メディアは Teams クライアントと SBC の間で直接フローします。

クラウド メディア プロセッサと Microsoft Teams クライアント間の SILK または G.722 が使用されます。 このリーグの選択は、複数のパラメーターを考慮する Microsoft アルゴリズムに基づいています。 


## <a name="supported-session-border-controllers-sbcs"></a>サポートされているセッション ボーダー コントローラー (SBC)

マイクロソフトでは、直接ルーティングとペアリングするサーティファイド SBC のみサポートされています。 エンタープライズ VoIPは企業にとってとってとても無効であるため、Microsoft は選択した SBC で頻度の高いテストを実行し、SBC ベンダーと組み合わせて 2 つのシステムに互換性があることを確認します。 

検証済みのデバイスは、Teams の直接ルーティング用にサーティフェイスとして表示されます。 サーティファイド デバイスは、すべてのシナリオで動作する保保ストが保たれます。 

サポートされている SBC の詳細については、直接ルーティング用に認証された [Session Border コントローラーのリストを参照してください](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
