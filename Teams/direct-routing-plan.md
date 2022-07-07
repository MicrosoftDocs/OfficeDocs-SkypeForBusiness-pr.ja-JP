---
title: ダイレクト ルーティングを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft Direct Routing を使用して、サポートされている顧客が提供するセッション ボーダー コントローラー (SBC) を電話システムに接続する方法について説明します。
ms.openlocfilehash: a5ccb8534ed8772124ae6e2506af81e5b63134d0
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682516"
---
# <a name="plan-direct-routing"></a>ダイレクト ルーティングを計画する

> [!Tip]
> ダイレクト ルーティングの利点、計画方法、展開方法については、次のセッションをご覧 [ください。Microsoft Teams でのダイレクト ルーティング](https://aka.ms/teams-direct-routing)

ダイレクト ルーティングを使用すると、サポートされている顧客が提供するセッション ボーダー コントローラー (SBC) を電話システムに接続できます。 この機能を使用すると、次の図に示すように、Microsoft Teams クライアントとのオンプレミスの公衆交換電話網 (PSTN) 接続を構成できます。 

![オンプレミス PSTN 接続の構成を示す図。](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft Teams クライアントとのオンプレミス PSTN 接続の構成")

  > [!NOTE]
  > Skype for Business Online では、お客様が指定した SBC をペアリングすることもできますが、これには、SBC と Microsoft Cloud の間にオンプレミスのSkype for Business Server展開または Cloud Connector と呼ばれる特別なエディションのSkype for Businessが必要です。 このシナリオはハイブリッド音声と呼ばれます。 これに対し、ダイレクト ルーティングでは、サポートされている SBC と Microsoft Cloud の間に直接接続できます。

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、 [直接ルーティング](direct-routing-landing-page.md)を使用してオンプレミステレフォニー ネットワークを Teams に接続する方法について説明します。 

ダイレクト ルーティングを使用すると、サード パーティの PSTN 機器を使用して、SBC をほぼすべてのテレフォニー トランクまたは相互接続に接続できます。 ダイレクト ルーティングを使用すると、次のことが可能になります。 

- 電話システムで実質的に任意の PSTN トランクを使用します。 

- サードパーティのプライベート ブランチエクスチェンジ (PBX)、アナログ デバイス、Teams など、顧客所有のテレフォニー機器間の相互運用性を構成します。

Microsoft では、通話プランなどのクラウド内のすべての音声ソリューションも提供しています。 ただし、次の場合は、組織にとってハイブリッド音声ソリューションが最適な場合があります。 

- Microsoft 通話プランは、お客様の国ではご利用いただけません。 

- 組織では、サード パーティ製のアナログ デバイス、コール センターなどへの接続が必要です。 

- 組織に PSTN 通信事業者との既存の契約があります。

ダイレクト ルーティングでは、Microsoft 通話プランの追加ライセンスを持つユーザーもサポートされます。 詳細については、[電話システムと通話プラン](calling-plan-landing-page.md)に関する記事をご覧ください。 

ダイレクト ルーティングでは、ユーザーがスケジュールされた会議に参加すると、ダイヤルイン番号が Microsoft 電話会議サービスによって提供されます。これには適切なライセンスが必要です。  ダイヤルアウトすると、Microsoft 電話会議サービスは、適切なライセンスが必要なオンライン通話機能を使用して通話を発信します。 (ユーザーが Microsoft 電話会議ライセンスを持っていない場合、通話はダイレクト ルーティング経由でルーティングされることに注意してください)。詳細については、「 [Teams を使用したオンライン会議](https://www.microsoft.com/en-us/microsoft-teams/online-meetings)」を参照してください。 
 
ダイレクト ルーティングの展開を計画することは、実装を成功させるために重要です。 この記事では、インフラストラクチャとライセンスの要件について説明し、SBC 接続に関する情報を提供します。 

- [インフラストラクチャの要件](#infrastructure-requirements)
- [ライセンスとその他の要件](#licensing-and-other-requirements)
- [SBC ドメイン名](#sbc-domain-names)
- [SBC のパブリック信頼された証明書](#public-trusted-certificate-for-the-sbc)
- [SIP シグナリング: FQDN](#sip-signaling-fqdns)
- [SIP シグナリング: ポート](#sip-signaling-ports)
- [メディア トラフィック: ポート範囲](#media-traffic-port-ranges)
- [サポートされているセッション ボーダー コントローラー (SBC)](#supported-session-border-controllers-sbcs)

ダイレクト ルーティングの構成の詳細については、「ダイレクト ルーティングの [構成」を](direct-routing-configure.md)参照してください。

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
ダイレクト ルーティングを展開するためにサポートされている SBC、ドメイン、およびその他のネットワーク接続要件のインフラストラクチャ要件を次の表に示します。  

|インフラストラクチャの要件|次のものが必要です|
|:--- |:--- |
|セッション ボーダー コントローラー (SBC)|サポートされている SBC。 詳細については、「 [サポートされている SBC」を参照してください](#supported-session-border-controllers-sbcs)。|
|SBC に接続されたテレフォニー トランク|SBC に接続されている 1 つ以上のテレフォニー トランク。 一方の側では、SBC は直接ルーティングを介して電話システムに接続します。 SBC は、PBX、アナログ テレフォニー アダプターなどのサード パーティ製テレフォニー エンティティに接続することもできます。 SBC に接続されているすべての PSTN 接続オプションが機能します。 (SBC への PSTN トランクの構成については、SBC ベンダーまたはトランク プロバイダーを参照してください)。|
|Microsoft 365 組織|Microsoft Teams ユーザーのホームに使用する Microsoft 365 組織と、SBC への構成と接続。|
|ユーザー レジストラー|ユーザーは Microsoft 365 に所属している必要があります。<br/>会社に、Microsoft 365 へのハイブリッド接続を備えたオンプレミスのSkype for Businessまたは Lync 環境がある場合、オンプレミスのユーザーに対して Teams で音声を有効にすることはできません。<br/><br/>ユーザーのレジストラーを確認するには、次のSkype for Business Online PowerShell コマンドレットを使用します。<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>コマンドレットの出力は次のように表示されます。<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|ドメイン|Microsoft 365 またはOffice 365組織に追加された 1 つ以上のドメイン。<br/><br/>テナント用に自動的に作成される既定のドメイン \*.onmicrosoft.com は使用できないことに注意してください。<br/><br/>ドメインを表示するには、次のSkype for Business Online PowerShell コマンドレットを使用します。<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>ドメインと Microsoft 365 またはOffice 365組織の詳細については、「[ドメインに関する FAQ」を](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)参照してください。|
|SBC のパブリック IP アドレス|SBC への接続に使用できるパブリック IP アドレス。 SBC の種類に基づいて、SBC は NAT を使用できます。|
|SBC の完全修飾ドメイン名 (FQDN)|SBC の FQDN。FQDN のドメイン部分は、Microsoft 365 またはOffice 365組織の登録済みドメインの 1 つです。 詳細については、「 [SBC ドメイン名](#sbc-domain-names)」を参照してください。|
|SBC のパブリック DNS エントリ |SBC FQDN をパブリック IP アドレスにマッピングするパブリック DNS エントリ。 |
|SBC のパブリック信頼された証明書 |ダイレクト ルーティングとのすべての通信に使用する SBC の証明書。 詳細については、「 [SBC のパブリック信頼された証明書」を](#public-trusted-certificate-for-the-sbc)参照してください。|
|ダイレクト ルーティングの接続ポイント |ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。<br/><br/>`sip.pstnhub.microsoft.com` – グローバル FQDN を最初に試す必要があります。<br/>`sip2.pstnhub.microsoft.com` セカンダリ FQDN。地理的に 2 番目の優先度リージョンにマップされます。<br/>`sip3.pstnhub.microsoft.com` – ターシャリ FQDN は、地理的に 3 番目の優先度リージョンにマップされます。<br/><br/>構成要件の詳細については、「 [SIP シグナリング: FQDN」を参照](#sip-signaling-fqdns)してください。|
|ダイレクト ルーティング メディアのファイアウォール IP アドレスとポート |SBC は、クラウド内の次のサービスと通信します。<br/><br/>シグナリングを処理する SIP プロキシ<br/>メディア を処理するメディア プロセッサ (Media Bypass がオンの場合を除く)<br/><br/>これら 2 つのサービスには、このドキュメントで後述する Microsoft Cloud の個別の IP アドレスがあります。<br/><br/>詳細については、[URL と IP アドレス範囲](/office365/enterprise/urls-and-ip-address-ranges)の [Microsoft Teams セクション](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を参照してください。 |
|メディア トランスポート プロファイル|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams メディアのファイアウォール IP アドレスとポート |詳細については、「 [URL と IP アドレス範囲」を](/office365/enterprise/urls-and-ip-address-ranges)参照してください。 |
|||

## <a name="licensing-and-other-requirements"></a>ライセンスとその他の要件 

ダイレクト ルーティングのユーザーには、Microsoft 365 で次のライセンスが割り当てられている必要があります。 

- Microsoft Phone System
- Microsoft Teams + Skype for Business プラン 2 (ライセンスに含まれる場合)
- Microsoft 電話会議 (このライセンスが必要な場合の具体的な例については、以下のノートと段落を参照してください)。

> [!NOTE]
> Skype for Businessプランが含まれているライセンス契約から削除しないでください。 
> 
> [!IMPORTANT]
> GCC High および DoD ユーザーは、G5 に含まれる電話会議ライセンスを無効にし、直接ルーティングが完全に構成されるまで電話会議を有効にするのを待つ必要があります。 ユーザーは、電話会議ライセンスを有効にする前に、ダイヤルイン電話番号が構成され、ダイヤル パッドが動作している必要があります。 詳細については、「 [GCC High と DoD のダイレクト ルーティングを使用した電話会議](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) 」を参照してください。


> [!IMPORTANT]
>  外部参加者をスケジュールされた会議に追加する場合は、ダイヤルアウトするか、ダイヤルイン番号を指定して、電話会議ライセンスが必要です。
> GCC High および DoD の場合は、G5 ユーザーに電話会議ライセンスを割り当てないでください。 G3 ユーザーの場合は、直接ルーティングが完全に構成され、ユーザーにダイヤル パッドが動作するまで、電話会議ライセンスを割り当てないでください。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>アドホック通話エスカレーションと電話会議ライセンス

Teams ユーザーは、1 対 1 の Teams 間 PSTN または Teams 間通話を開始し、PSTN 参加者を追加できます。 このシナリオは、アドホック会議と呼ばれます。 通話のパスは、通話をエスカレートするユーザーに Microsoft 電話会議ライセンスが割り当てられているかどうかによって異なります。

- **通話をエスカレートする Teams ユーザーに Microsoft 電話会議ライセンスが割り当てられている場合**、エスカレーションは Microsoft 電話会議サービスを通じて行われます。 既存の通話に招待されたリモート PSTN 参加者は、着信に関する通知を受け取り、エスカレーションを開始した Teams ユーザーに割り当てられた Microsoft ブリッジの番号を確認します。

- **通話をエスカレートする Teams ユーザーに Microsoft 電話会議ライセンスが割り当てられていない場合**、エスカレーションはダイレクト ルーティング インターフェイスに接続されたセッション ボーダー コントローラーを介して行われます。 通話に招待されたリモート PSTN 参加者は、着信通話に関する通知を受け取り、エスカレーションを開始した Teams ユーザーの数を確認します。 エスカレーションに使用される特定の SBC は、ユーザーのルーティング ポリシーによって定義されます。 

次のことを確認する必要があります。
 
- CsOnlineVoiceRoutingPolicy がユーザーに割り当てられます。 

- プライベート通話を許可するは、Microsoft Teams のテナント レベルで有効になっています。 

ダイレクト ルーティングでは、Microsoft 通話プランのライセンスを持つユーザーもサポートされます。 通話プランを使用した電話システムでは、ダイレクト ルーティング インターフェイスを使用して一部の通話をルーティングできます。 ただし、ユーザーの電話番号は、オンラインで取得するか、Microsoft に移植する必要があります。  

同じユーザーに対する通話プランとダイレクト ルーティング接続の混在は省略可能ですが、便利な場合があります。 たとえば、ユーザーに Microsoft 通話プランが割り当てられているが、SBC を使用して一部の呼び出しをルーティングする場合などです。 最も一般的なシナリオの 1 つは、サード パーティの PBX の呼び出しです。  サード パーティの PBX では、その PBX に接続されている電話への通話を除くすべての通話は Microsoft 通話プランを使用してルーティングされますが、サード パーティの PBX に接続されている電話への通話は SBC に送信されるため、PSTN ではなくエンタープライズ ネットワーク内にとどまります。 

電話システム ライセンスの詳細については、「Office と[プランのオプション](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)と [Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)[を最大限](https://products.office.com/compare-all-microsoft-office-products?tab=2)に活用する」を参照してください。 

## <a name="supported-end-points"></a>サポートされているエンドポイント 

エンドポイントとして使用できます。

- すべての Teams クライアント。 

- 共通領域の電話。 [Microsoft Teams 用の共通エリアフォンの設定に関するページを参照してください](./set-up-common-area-phones.md)。 ダイレクト ルーティングを使用して共通エリア電話を設定する場合、通話プラン ライセンスは必要ありません。

- Skype for Business 3PIP 電話。 [Microsoft Teams Skype for Business電話 (3PIP) のサポートに関するページを](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)参照してください


## <a name="sbc-domain-names"></a>SBC ドメイン名

SBC ドメイン名は、テナントのドメインに登録されている名前のいずれかから取得する必要があります。 SBC の FQDN 名に \*.onmicrosoft.com テナントを使用することはできません。

次の表は、テナントに登録されている DNS 名の例、名前を SBC の FQDN として使用できるかどうか、および有効な FQDN 名の例を示しています。

|DNS 名|SBC FQDN に使用できます|FQDN 名の例|
|:--- |:--- |:--- |
contoso.com|はい|**有効な名前:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|いいえ|*.onmicrosoft.com ドメインの使用は、SBC 名ではサポートされていません

新しいドメイン名を使用することを想定しています。 たとえば、テナントにドメイン名として contoso.com が登録されており、sbc1.sip.contoso.com を使用します。 SBC と名前 sbc1.sip.contoso.com をペアリングする前に、テナント内のドメインにドメイン名 sip.contoso.com を登録する必要があります。 ドメイン名を登録する前に SBC と sbc1.sip.contoso.com のペアリングを試みると、「このテナント用に構成されていないため、"sbc1.sip.contoso.com" ドメインを使用できません」というエラーが表示されます。
ドメイン名を追加した後、UPN user@sip.contoso.com を使用してユーザーを作成し、Teams ライセンスを割り当てる必要もあります。 ドメイン名がテナントのドメインに追加され、新しい名前を持つユーザーが作成され、ライセンスがユーザーに割り当てられた後、ドメイン名を完全にプロビジョニングするには、最大で 24 時間かかる場合があります。 

1 つのテナントに複数の SIP アドレス空間が存在する可能性があります。 たとえば、会社は SIP アドレス空間として contoso.com し、2 番目の SIP アドレス空間として fabrikam.com 可能性があります。 一部のユーザーはアドレス user@contoso.com を持ち、一部のユーザーはアドレス user@fabrikam.com を持っています。 

SBC には 1 つの FQDN のみが必要であり、ペアになっているテナント内の任意のアドレス空間からユーザーにサービスを提供できます。 たとえば、sbc1.contoso.com という名前の SBC は、これらの SIP アドレス空間が同じテナントに登録されている限り、user@contoso.com アドレスと user@fabrikam.com を持つユーザーの PSTN トラフィックを受信および送信できます。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC のパブリック信頼された証明書

認定署名要求 (CSR) を生成して、SBC の証明書を要求することをお勧めします。 SBC の CSR の生成に関する具体的な手順については、SBC ベンダーが提供する相互接続の手順またはドキュメントを参照してください。 

> [!NOTE]
> ほとんどの証明機関 (CA) では、秘密キーのサイズが少なくとも 2048 である必要があります。 CSR を生成するときは、この点に注意してください。

証明書には、共通名 (CN) またはサブジェクト代替名 (SAN) フィールドとして SBC FQDN が必要です。

または、ダイレクト ルーティングでは CN または SAN でワイルドカードがサポートされており、ワイルドカードは標準 [の RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1) に準拠している必要があります。 たとえば、SBC FQDN sbc.contoso.com と一致するが、sbc.test.contoso.com と一致しない .contoso.com を使用 \*します。

ダイレクト ルーティング SIP インターフェイスは、Microsoft 信頼ルート証明書プログラムの一部である証明機関 (CA) によって署名された証明書のみを信頼します。 SBC 証明書が、プログラムの一部である CA によって署名されていること、および証明書の拡張キー使用法 (EKU) 拡張機能にサーバー認証が含まれていることを確認します。
詳細情報: [プログラム要件 - Microsoft Trusted Root Program](/security/trusted-root/program-requirements)
  
[含まれる CA 証明書の一覧](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 gccH および DoD 環境Office 365ダイレクト ルーティングの場合、証明書は次のいずれかのルート証明機関によって生成される必要があります。

- DigiCert グローバル ルート CA
- DigiCert High Assurance EV ルート CA

> [!NOTE]
> SBC 上の Teams 接続に対して相互 TLS (MTLS) のサポートが有効になっている場合は、Teams TLS コンテキストの SBC 信頼ルート ストアに、Baltimore CyberTrust ルートと DigiCert Global Root G2 証明書をインストールする必要があります。 (これは、Microsoft サービス証明書でこれら 2 つのルート証明書のいずれかを使用するためです)。これらのルート証明書をダウンロードするには、「[Office 365暗号化チェーン](/microsoft-365/compliance/encryption-office-365-certificate-chains)」を参照してください。 詳細については、「 [Office TLS 証明書の変更](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes)」を参照してください。

## <a name="sip-signaling-fqdns"></a>SIP シグナリング: FQDN 

ダイレクト ルーティングは、次の環境で提供されます。

- Microsoft 365 またはOffice 365
- gcc のOffice 365
- Office 365 GCC High
- Office 365 DoD

GCC、GCC High、DoD などの[Office 365環境と米国政府環境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)の詳細について説明します。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、および Office 365 GCC 環境

ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN – を最初に試す必要があります。 SBC からこの名前を解決するための要求が送信されると、Microsoft Azure DNS サーバーは、SBC に割り当てられたプライマリ Azure データセンターを指す IP アドレスを返します。 この割り当ては、データセンターのパフォーマンス メトリックと SBC への地理的近接性に基づいています。 返される IP アドレスは、プライマリ FQDN に対応します。

- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に 2 番目の優先度リージョンにマップされます。

- **sip3.pstnhub.microsoft.com** – ターシャリ FQDN – 地理的に 3 番目の優先度リージョンにマップされます。

次の目的でこれら 3 つの FQDN を配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込みが少なく、最初の FQDN にクエリを実行して割り当てられた SBC データセンターに最も近い)。

- SBC から一時的な問題が発生しているデータセンターへの接続が確立されたときにフェールオーバーを提供します。 詳細については、以下の [フェールオーバー メカニズム](#failover-mechanism-for-sip-signaling) に関する記事を参照してください。  

FQDN (sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.com) は、次のサブネットの IP アドレスに解決されます。

- 52.112.0.0/14
- 52.120.0.0/14

ファイアウォール内のすべての IP アドレス範囲のポートを開き、シグナリング用のアドレスとの間で送受信トラフィックを許可する必要があります。

### <a name="office-gcc-dod-environment"></a>Office GCC DoD 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。 Office 365 DoD 環境は米国のデータ センターにのみ存在するため、セカンダリおよびターシャリ FQDN はありません。

FQDN sip.pstnhub.dod.teams.microsoft.us は、次のサブネットの IP アドレスに解決されます。

- 52.127.64.0/21

ファイアウォール内のすべてのこれらの IP アドレスのポートを開き、シグナリング用のアドレスとの間で送受信トラフィックを許可する必要があります。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 GCC High 環境は米国のデータ センターにのみ存在するため、セカンダリおよびターシャリ FQDN はありません。

FQDN sip.pstnhub.gov.teams.microsoft.us は、次のサブネットの IP アドレスに解決されます。

- 52.127.88.0/21

ファイアウォール内のすべてのこれらの IP アドレスのポートを開き、シグナリング用のアドレスとの間で送受信トラフィックを許可する必要があります。

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

Microsoft 365 またはダイレクト ルーティングが提供されるOffice 365環境では、次のポートを使用する必要があります。

- Microsoft 365 またはOffice 365
- gcc のOffice 365
- Office 365 GCC High
- Office 365 DoD

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP プロキシ|SBC|1024 – 65535|SBC で定義されている (Office 365 GCC High/DoD の場合はポート 5061 のみを使用する必要があります)|
SIP/TLS|SBC|SIP プロキシ|SBC で定義されている|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP シグナリングのフェールオーバー メカニズム

SBC では、sip.pstnhub.microsoft.com を解決するための DNS クエリが作成されます。 SBC の場所とデータセンターのパフォーマンス メトリックに基づいて、プライマリ データセンターが選択されます。 プライマリ データセンターで問題が発生した場合、SBC は 2 つ目の割り当てデータセンターに解決される sip2.pstnhub.microsoft.com を試行し、まれに 2 つのリージョンのデータセンターを使用できない場合、SBC は 3 次データセンター IP を提供する最後の FQDN (sip3.pstnhub.microsoft.com) を再試行します。

次の表は、プライマリ、セカンダリ、およびターシャリ データセンター間の関係をまとめたものです。

|プライマリ データセンターが|EMEA|NOAM|アジア|
|:--- |:--- |:--- |:--- |
|セカンダリ データセンター (sip2.pstnhub.microsoft.com)|私たち|EU|私たち|
|ターシャリ データセンター (sip3.pstnhub.microsoft.com)|アジア|アジア|EU|
|||||

## <a name="media-traffic-port-ranges"></a>メディア トラフィック: ポート範囲
メディア バイパスなしでダイレクト ルーティングを展開する場合は、次の要件が適用されることに注意してください。 Media Bypass のファイアウォール要件については、「 [ダイレクト ルーティングを使用したメディア バイパスの計画](./direct-routing-plan-media-bypass.md)」を参照してください。

メディア トラフィックは、Microsoft Cloud 内の別のサービスとの間で送受信されます。 メディア トラフィックの IP アドレス範囲は次のとおりです。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、および Office 365 GCC 環境

- 52.112.0.0/14 (52.112.0.1 から 52.115.255.254 までの IP アドレス)。
- 52.120.0.0/14 (52.120.0.1 から 52.123.255.254 までの IP アドレス)。

### <a name="office-365-dod-environment"></a>Office 365 DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>ポート範囲 (すべての環境に適用)
メディア プロセッサのポート範囲を次の表に示します。 

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|メディア プロセッサ|SBC|3478-3481 および 49152 – 53247|SBC で定義されている|
|UDP/SRTP|SBC|メディア プロセッサ|SBC で定義されている|3478-3481 および 49152 – 53247|

  > [!NOTE]
  > Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートを推奨しています。


## <a name="media-traffic-media-processors-geography"></a>メディア トラフィック: メディア プロセッサの地理

メディア トラフィックは、メディア プロセッサと呼ばれるコンポーネントを介して流れます。 メディア プロセッサは、SIP プロキシと同じデータセンターに配置されます。

- NOAM (米国中南部、米国西部と米国東部の 2 つのデータセンター)
- ヨーロッパ (英国南部、フランス中部、アムステルダム、ダブリンのデータセンター)
- アジア (シンガポールデータセンター)
- 日本 (JP 東日本および西日本のデータセンター)
- オーストラリア (AU 東部と南東のデータセンター)
- LATAM (ブラジル南部)
- アフリカ (南アフリカ北部)

## <a name="media-traffic-codecs"></a>メディア トラフィック: コーデック

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC と Cloud Media Processor または Microsoft Teams クライアント間のレッグ

メディア バイパス ケースとバイパス以外のケースの両方に適用されます。

セッション ボーダー コントローラーとクラウド メディア プロセッサ (メディア バイパスなし) 間、または Teams クライアントと SBC (メディア バイパスが有効な場合) の間の脚のダイレクト ルーティング インターフェイスでは、次のコーデックを使用できます。

- メディア以外のバイパス (SBC からクラウド メディア プロセッサ): SILK、G.711、G.722、G.729
- メディア バイパス (SBC から Teams クライアント): SILK、G.711、G.722、G.729

セッション ボーダー コントローラーで特定のコーデックを強制的に使用するには、オファーから望ましくないコーデックを除外します。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams クライアントとクラウド メディア プロセッサの間の区間

メディア以外のバイパス ケースにのみ適用されます。 Media Bypass を使用すると、メディアは Teams クライアントと SBC の間で直接流れます。

Cloud Media Processor と Microsoft Teams クライアントの間の区間では、SILK または G.722 が使用されます。 この区間のコーデックの選択は、複数のパラメーターを考慮した Microsoft アルゴリズムに基づいています。 

  > [!NOTE]
  > メディアの再ターゲット設定はサポートされていません。 ダイレクト ルーティングの呼び出し中に、SBC が Teams Direct Routing に新しいメディア IP を送信する場合、SIP シグナリングでネゴシエートされますが、メディアは Teams ダイレクト ルーティングから新しい IP アドレスに送信されることはありません。

## <a name="supported-session-border-controllers-sbcs"></a>サポートされているセッション ボーダー コントローラー (SBC)

Microsoft では、ダイレクト ルーティングとペアリングするための認定された SBC のみがサポートされています。 エンタープライズ VoIPは企業にとって非常に重要であるため、Microsoft は選択した SBC で集中的なテストを実行し、SBC ベンダーと連携して 2 つのシステムの互換性を確保します。 

検証済みのデバイスは、Teams ダイレクト ルーティングの認定済みデバイスとして一覧表示されます。 認定されたデバイスは、すべてのシナリオで動作することが保証されています。 

サポートされている SBC の詳細については、「 [ダイレクト ルーティング用に認定されたセッション ボーダー コントローラー](direct-routing-border-controllers.md)」を参照してください。

 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
