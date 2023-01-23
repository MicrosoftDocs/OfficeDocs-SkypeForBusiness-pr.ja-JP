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
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft Direct Routing を使用して、サポートされているカスタマー 提供のセッション ボーダー コントローラー (SBC) を電話システムに接続する方法について説明します。
ms.openlocfilehash: ba0db105d94fef7c81d79929c5cc7f9371f0fc6c
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948514"
---
# <a name="plan-direct-routing"></a>ダイレクト ルーティングを計画する

> [!Tip]
> 次のセッションを見て、ダイレクト ルーティングの利点、その計画方法、展開方法について説明します。 [Microsoft Teams でのダイレクト ルーティング](https://aka.ms/teams-direct-routing)

ダイレクト ルーティングを使用すると、サポートされている顧客が提供するセッション ボーダー コントローラー (SBC) を電話システムに接続できます。 この機能を使用すると、次の図に示すように、Microsoft Teams クライアントとのオンプレミスの公衆交換電話網 (PSTN) 接続を構成できます。 

![オンプレミスの PSTN 接続の構成を示す図。](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft Teams クライアントとのオンプレミス PSTN 接続の構成")

  > [!NOTE]
  > Skype for Business Online では、顧客が提供する SBC をペアリングすることもできますが、これには、オンプレミスのSkype for Business Server展開、または SBC と Microsoft Cloud の間に Cloud Connector と呼ばれる特別なエディションのSkype for Businessが必要です。 このシナリオはハイブリッド音声と呼ばれます。 一方、ダイレクト ルーティングでは、サポートされている SBC と Microsoft Cloud の間で直接接続できます。

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードされたら、 [ダイレクト ルーティング](direct-routing-landing-page.md)を使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法について説明します。 

ダイレクト ルーティングを使用すると、SBC をほぼすべてのテレフォニー トランクに接続したり、サードパーティの PSTN 機器と相互接続することができます。 ダイレクト ルーティングを使用すると、次のことが可能になります。 

- 電話システムでほぼすべての PSTN トランクを使用します。 

- サード パーティのプライベート ブランチ交換 (PBX)、アナログ デバイス、Teams など、顧客所有のテレフォニー機器間の相互運用性を構成します。

Microsoft では、通話プランなどのクラウド内の音声ソリューションも提供しています。 ただし、次の場合は、ハイブリッド音声ソリューションが組織に最適な場合があります。 

- Microsoft 通話プランは、お客様の国ではご利用いただけません。 

- 組織では、サード パーティ製のアナログ デバイス、コール センターなどへの接続が必要です。 

- 組織は PSTN 通信事業者との既存の契約を持っています。

ダイレクト ルーティングでは、Microsoft 通話プランの追加ライセンスを持つユーザーもサポートされています。 詳細については、[電話システムと通話プラン](calling-plan-landing-page.md)に関する記事をご覧ください。 

ダイレクト ルーティングでは、ユーザーがスケジュールされた会議に参加すると、ダイヤルイン番号が Microsoft 電話会議サービスによって提供されます。これには適切なライセンスが必要です。  ダイヤルアウト時に、Microsoft 電話会議サービスは、適切なライセンスが必要なオンライン通話機能を使用して通話を発信します。 (ユーザーが Microsoft 電話会議ライセンスを持っていない場合、通話はダイレクト ルーティングを介してルーティングされることに注意してください)。詳細については、「 [Teams でのオンライン会議](https://www.microsoft.com/en-us/microsoft-teams/online-meetings)」を参照してください。 
 
Direct Routing のデプロイを計画することは、実装を成功させるために重要です。 この記事では、インフラストラクチャとライセンスの要件について説明し、SBC 接続に関する情報を提供します。 

- [インフラストラクチャの要件](#infrastructure-requirements)
- [ライセンスとその他の要件](#licensing-and-other-requirements)
- [SBC ドメイン名](#sbc-domain-names)
- [SBC のパブリック信頼証明書](#public-trusted-certificate-for-the-sbc)
- [SIP シグナリング: FQDN](#sip-signaling-fqdns)
- [SIP シグナリング: ポート](#sip-signaling-ports)
- [メディア トラフィック: ポート範囲](#media-traffic-port-ranges)
- [サポートされているセッション ボーダー コントローラー (SBC)](#supported-session-border-controllers-sbcs)

ダイレクト ルーティングの構成の詳細については、「ダイレクト ルーティングの [構成](direct-routing-configure.md)」を参照してください。

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
ダイレクト ルーティングを展開するためのサポートされる SBC、ドメイン、およびその他のネットワーク接続要件のインフラストラクチャ要件を次の表に示します。  

|インフラストラクチャ要件|次のものが必要です|
|:--- |:--- |
|セッション ボーダー コントローラー (SBC)|サポートされている SBC。 詳細については、「 [サポートされる SBC](#supported-session-border-controllers-sbcs)」を参照してください。|
|SBC に接続されているテレフォニー トランク|SBC に接続されている 1 つ以上のテレフォニー トランク。 一方の端では、SBC はダイレクト ルーティングを介して電話システムに接続します。 SBC は、PBX、アナログ テレフォニー アダプターなどのサード パーティのテレフォニー エンティティにも接続できます。 SBC に接続されている PSTN 接続オプションは機能します。 (SBC への PSTN トランクの構成については、SBC ベンダーまたはトランク プロバイダーを参照してください)。|
|Microsoft 365 組織|Microsoft Teams ユーザーのホームに使用する Microsoft 365 組織、および SBC への構成と接続。|
|ユーザー レジストラー|ユーザーは Microsoft 365 に所属している必要があります。<br/>会社にオンプレミスのSkype for Businessまたは Lync 環境があり、Microsoft 365 へのハイブリッド接続がある場合、オンプレミスに所属するユーザーに対して Teams で音声を有効にすることはできません。<br/><br/>ユーザーのレジストラーを確認するには、次のSkype for Business Online PowerShell コマンドレットを使用します。<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>コマンドレットの出力には、次の情報が表示されます。<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|ドメイン|Microsoft 365 またはOffice 365組織に追加された 1 つ以上のドメイン。<br/><br/>テナント用に自動的に作成される既定のドメイン \*.onmicrosoft.com は使用できないことに注意してください。<br/><br/>ドメインを表示するには、次のSkype for Business Online PowerShell コマンドレットを使用します。<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>ドメインと Microsoft 365 またはOffice 365組織の詳細については、「[ドメインに関する FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)」を参照してください。|
|SBC のパブリック IP アドレス|SBC への接続に使用できるパブリック IP アドレス。 SBC の種類に基づいて、SBC は NAT を使用できます。|
|SBC の完全修飾ドメイン名 (FQDN)|SBC の FQDN。FQDN のドメイン部分は、Microsoft 365 またはOffice 365組織に登録されているドメインのいずれかです。 詳細については、「 [SBC ドメイン名](#sbc-domain-names)」を参照してください。|
|SBC のパブリック DNS エントリ |SBC FQDN をパブリック IP アドレスにマッピングするパブリック DNS エントリ。 |
|SBC のパブリック信頼証明書 |ダイレクト ルーティングとのすべての通信に使用する SBC の証明書。 詳細については、「 [SBC のパブリック信頼された証明書](#public-trusted-certificate-for-the-sbc)」を参照してください。|
|ダイレクト ルーティングの接続ポイント |ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。<br/><br/>`sip.pstnhub.microsoft.com` – グローバル FQDN、最初に試行する必要があります。<br/>`sip2.pstnhub.microsoft.com` セカンダリ FQDN、地理的に 2 番目の優先度のリージョンにマップされます。<br/>`sip3.pstnhub.microsoft.com` – 第 3 の FQDN、地理的に 3 番目の優先度のリージョンにマップされます。<br/><br/>構成要件については、「 [SIP シグナリング: FQDN」を](#sip-signaling-fqdns)参照してください。|
|ダイレクト ルーティング メディアのファイアウォール IP アドレスとポート |SBC は、クラウド内の次のサービスと通信します。<br/><br/>シグナリングを処理する SIP プロキシ<br/>メディア バイパスがオンになっている場合を除き、メディア を処理するメディア プロセッサ<br/><br/>これら 2 つのサービスは、このドキュメントで後述する Microsoft Cloud で個別の IP アドレスを持ちます。<br/><br/>詳細については、「[URL と IP アドレス範囲」](/office365/enterprise/urls-and-ip-address-ranges)の[「Microsoft Teams」セクション](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を参照してください。 |
|メディア トランスポート プロファイル|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams メディアのファイアウォール IP アドレスとポート |詳細については、「 [URL と IP アドレス範囲」を](/office365/enterprise/urls-and-ip-address-ranges)参照してください。 |
|||

## <a name="licensing-and-other-requirements"></a>ライセンスとその他の要件 

ダイレクト ルーティングのユーザーには、Microsoft 365 で次のライセンスが割り当てられている必要があります。 

- Microsoft Phone System
- Microsoft Teams + Skype for Business プラン 2 (ライセンスに含まれている場合)
- Microsoft 電話会議 (このライセンスが必要な場合の具体的な例については、以下のメモと段落を読んでください)。

> [!NOTE]
> Skype for Businessプランは、含まれているライセンス契約から削除しないでください。 
> 
> [!IMPORTANT]
> GCC High ユーザーと DoD ユーザーは、G5 に含まれる電話会議ライセンスを無効にし、ダイレクト ルーティングが完全に構成されるまで電話会議を有効にするまで待つ必要があります。 ユーザーは、電話会議ライセンスを有効にする前に、ダイヤルイン電話番号と作業ダイヤル パッドを構成する必要があります。 詳細については、「 [GCC High と DoD のダイレクト ルーティングを使用した電話会議](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) 」を参照してください。


> [!IMPORTANT]
>  スケジュールされた会議に外部参加者を追加する場合は、ダイヤルアウトするか、ダイヤルイン番号を指定して、電話会議ライセンスが必要です。
> GCC High と DoD の場合は、G5 ユーザーに電話会議ライセンスを割り当てないでください。 G3 ユーザーの場合は、ダイレクト ルーティングが完全に構成され、ユーザーに作業ダイヤル パッドが割り当てられるまで、電話会議ライセンスを割り当てないでください。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>アドホック通話のエスカレーションと電話会議ライセンス

Teams ユーザーは、1 対 1 の Teams から PSTN または Teams 間の通話を開始し、PSTN 参加者を追加できます。 このシナリオはアドホック会議と呼ばれます。 通話のパスは、通話をエスカレートするユーザーに Microsoft 電話会議ライセンスが割り当てられているかどうかによって異なります。

- **通話をエスカレートする Teams ユーザーに Microsoft 電話会議ライセンスが割り当てられている場合**、エスカレーションは Microsoft 電話会議サービスを通じて行われます。 既存の通話に招待されたリモート PSTN 参加者は、着信通話に関する通知を受け取り、エスカレーションを開始した Teams ユーザーに割り当てられた Microsoft ブリッジの数を確認します。

- **通話をエスカレートする Teams ユーザーに Microsoft 電話会議ライセンスが割り当てられない場合**、エスカレーションはダイレクト ルーティング インターフェイスに接続されているセッション ボーダー コントローラーを介して行われます。 通話に招待されたリモート PSTN 参加者は、着信通話に関する通知を受け取り、エスカレーションを開始した Teams ユーザーの数を確認します。 エスカレーションに使用される特定の SBC は、ユーザーのルーティング ポリシーによって定義されます。 

次のことを確認する必要があります。
 
- CsOnlineVoiceRoutingPolicy がユーザーに割り当てられます。

- プライベート通話の許可は、Microsoft Teams のテナント レベルで有効になっています。

ダイレクト ルーティングでは、Microsoft 通話プランのライセンスを持つユーザーもサポートされています。 通話プランを持つ電話システムは、ダイレクト ルーティング インターフェイスを使用して一部の通話をルーティングできます。 ただし、ユーザーの電話番号は、オンラインで取得するか、Microsoft に移植する必要があります。  

同じユーザーの通話プランとダイレクト ルーティング接続の混在は省略可能ですが、便利な場合があります。 たとえば、ユーザーに Microsoft 通話プランが割り当てられているが、SBC を使用していくつかの呼び出しをルーティングする場合などです。 最も一般的なシナリオの 1 つは、サード パーティの PBX への呼び出しです。  サード パーティの PBX では、その PBX に接続されている電話への呼び出しを除くすべての通話は Microsoft 通話プランを使用してルーティングされますが、サード パーティの PBX に接続されている電話への通話は SBC に送信されるため、PSTN ではなくエンタープライズ ネットワーク内にとどまります。

電話システム ライセンスの詳細については、「Office および[プラン オプション](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)と [Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)[を最大限](https://products.office.com/compare-all-microsoft-office-products?tab=2)に活用する」を参照してください。

## <a name="supported-end-points"></a>サポートされているエンドポイント

エンドポイントとして使用できます。

- 任意の Teams クライアント。

- 共通エリア電話。 [「Microsoft Teams の共通エリア電話を設定する」を](./set-up-common-area-phones.md)参照してください。 ダイレクト ルーティングを使用して共通エリア電話を設定する場合、通話プラン ライセンスは必要ありません。

- Skype for Business 3PIP 電話。 [Microsoft Teams Skype for Business電話 (3PIP) のサポートに関するページを](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)参照してください

## <a name="sbc-domain-names"></a>SBC ドメイン名

SBC ドメイン名は、テナントのドメインに登録されている名前のいずれかからである必要があります。 SBC の FQDN 名に \*.onmicrosoft.com テナントを使用することはできません。

次の表は、テナントに登録されている DNS 名の例、名前を SBC の FQDN として使用できるかどうか、および有効な FQDN 名の例を示しています。

|DNS 名|SBC FQDN に使用できます|FQDN 名の例|
|:--- |:--- |:--- |
contoso.com|Yes|**有効な名前:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|いいえ|*.onmicrosoft.com ドメインの使用は、SBC 名ではサポートされていません

新しいドメイン名を使用するとします。 たとえば、テナントには、テナントに登録されているドメイン名として contoso.com があり、sbc1.sip.contoso.com を使用する必要があります。 SBC と名前 sbc1.sip.contoso.com をペアリングする前に、テナントのドメインにドメイン名 sip.contoso.com を登録する必要があります。 ドメイン名を登録する前に SBC と sbc1.sip.contoso.com をペアリングしようとすると、"このテナント用に構成されていないため、"sbc1.sip.contoso.com" ドメインを使用できません" というエラーが表示されます。

ドメイン名を追加した後、UPN user@sip.contoso.com を使用してユーザーを作成し、Teams ライセンスを割り当てる必要もあります。 ドメイン名がテナントのドメインに追加され、新しい名前のユーザーが作成され、ライセンスがユーザーに割り当てられた後、ドメイン名が完全にプロビジョニングされるまでに最大 24 時間かかる場合があります。

会社が 1 つのテナントに複数の SIP アドレス空間を持っている可能性があります。 たとえば、ある会社は SIP アドレス空間として contoso.com し、2 つ目の SIP アドレス空間として fabrikam.com します。 一部のユーザーはアドレス user@contoso.com を持ち、一部のユーザーはアドレス user@fabrikam.com を持っています。 

SBC で必要な FQDN は 1 つだけであり、ペアのテナント内の任意のアドレス空間からユーザーにサービスを提供できます。 たとえば、sbc1.contoso.com という名前の SBC は、これらの SIP アドレス空間が同じテナントに登録されている限り、user@contoso.com および user@fabrikam.com アドレスを持つユーザーの PSTN トラフィックを受信および送信できます。  

 > [!NOTE]
 > Azure Communication Servicesダイレクト ルーティングの SBC FQDN は、Teams ダイレクト ルーティングの SBC FQDN とは異なる必要があります。
  
## <a name="public-trusted-certificate-for-the-sbc"></a>SBC のパブリック信頼証明書

Microsoft では、認定署名要求 (CSR) を生成して、SBC の証明書を要求することをお勧めします。 SBC の CSR の生成に関する具体的な手順については、SBC ベンダーが提供する相互接続の手順またはドキュメントを参照してください。

> [!NOTE]
> ほとんどの証明機関 (CA) では、秘密キーサイズが少なくとも 2048 である必要があります。 CSR を生成する場合は、この点に注意してください。

証明書には、共通名 (CN) またはサブジェクト別名 (SAN) フィールドとして SBC FQDN が必要です。

または、ダイレクト ルーティングでは CN または SAN のワイルドカードがサポートされており、ワイルドカードは標準 [の RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1) に準拠している必要があります。

たとえば、SBC FQDN sbc.contoso.com と一致するが、sbc.test.contoso.com と一致しない .contoso.com を使用 \*します。

ダイレクト ルーティング SIP インターフェイスは、Microsoft 信頼されたルート証明書プログラムの一部である証明機関 (CA) によって署名された証明書のみを信頼します。 SBC 証明書が、プログラムの一部である CA によって署名されていること、および証明書の拡張キー使用法 (EKU) 拡張機能にサーバー認証が含まれていることを確認します。
詳細情報: [プログラム要件 - Microsoft Trusted Root Program](/security/trusted-root/program-requirements)
  
[含まれる CA 証明書の一覧](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 GCCH 環境と DoD 環境Office 365ダイレクト ルーティングの場合、証明書は次のいずれかのルート証明機関によって生成される必要があります。

- DigiCert グローバル ルート CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> SBC 上の Teams 接続に対して相互 TLS (MTLS) サポートが有効になっている場合は、Teams TLS コンテキストの SBC 信頼されたルート ストアに Baltimore CyberTrust Root 証明書と DigiCert グローバル ルート G2 証明書をインストールする必要があります。 (これは、Microsoft サービス証明書でこれら 2 つのルート証明書のいずれかを使用するためです)。これらのルート証明書をダウンロードするには、「[Office 365暗号化チェーン](/microsoft-365/compliance/encryption-office-365-certificate-chains)」を参照してください。 詳細については、「 [Office TLS 証明書の変更](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes)」を参照してください。

## <a name="sip-signaling-fqdns"></a>SIP シグナリング: FQDN

ダイレクト ルーティングは、次の環境で提供されます。

- Microsoft 365 または Office 365
- GCC をOffice 365する
- OFFICE 365 GCC High
- Office 365 DoD

GCC、GCC High、DoD などの[Office 365と米国政府の環境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)について詳しく説明します。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN – を最初に試す必要があります。 SBC がこの名前を解決する要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。 割り当ては、データセンターのパフォーマンス メトリックと SBC への地理的近接性に基づいています。 返される IP アドレスは、プライマリ FQDN に対応します。

- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に 2 番目の優先度リージョンにマップされます。

- **sip3.pstnhub.microsoft.com** – 第 3 の FQDN – 地理的に 3 番目の優先度のリージョンにマップされます。

次の 3 つの FQDN を順番に配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込みの少なく、最初の FQDN のクエリによって割り当てられた SBC データセンターに最も近い)。

- SBC からの接続が確立され、一時的な問題が発生しているデータセンターにフェールオーバーを提供します。 詳細については、以下の [「フェールオーバー メカニズム](#failover-mechanism-for-sip-signaling) 」を参照してください。  

FQDN (sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.com) は、次のサブネットの IP アドレスに解決されます。

- 52.112.0.0/14
- 52.120.0.0/14
  
ファイアウォールでこれらすべての IP アドレス範囲のポートを開き、アドレスとの間でシグナリングを行う送受信トラフィックを許可する必要があります。

### <a name="office-gcc-dod-environment"></a>Office GCC DoD 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。 Office 365 DoD 環境は米国のデータ センターにのみ存在します。セカンダリ FQDN とターシャリ FQDN はありません。

FQDN sip.pstnhub.dod.teams.microsoft.us は、次のサブネットから IP アドレスに解決されます。

- 52.127.64.0/21

シグナリングのためにアドレスとの間で送受信されるトラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。

### <a name="office-365-gcc-high-environment"></a>GCC High 環境のOffice 365

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 GCC High 環境は米国のデータ センターにのみ存在します。セカンダリ FQDN とターシャリ FQDN はありません。

FQDN sip.pstnhub.gov.teams.microsoft.us は、次のサブネットから IP アドレスに解決されます。

- 52.127.88.0/21

シグナリングのためにアドレスとの間で送受信されるトラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

ダイレクト ルーティングが提供される Microsoft 365 またはOffice 365環境では、次のポートを使用する必要があります。

- Microsoft 365 または Office 365
- GCC をOffice 365する
- OFFICE 365 GCC High
- Office 365 DoD

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP プロキシ|Sbc|1024 – 65535|SBC で定義されている (Office 365 GCC High/DoD の場合は、ポート 5061 のみを使用する必要があります)|
SIP/TLS|Sbc|SIP プロキシ|SBC で定義されている|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP シグナリングのフェールオーバー メカニズム

SBC は、sip.pstnhub.microsoft.com を解決するための DNS クエリを作成します。 SBC の場所とデータセンターのパフォーマンス メトリックに基づいて、プライマリ データセンターが選択されます。 プライマリ データセンターで問題が発生した場合、SBC は 2 番目に割り当てられたデータセンターに解決される sip2.pstnhub.microsoft.com を試し、まれに 2 つのリージョンのデータセンターが使用できない場合は、SBC によって最後の FQDN (sip3.pstnhub.microsoft.com) が再試行されます。これにより、3 番目のデータセンター IP が提供されます。

次の表は、プライマリ、セカンダリ、およびターシャリー の各データセンター間の関係をまとめたものです。

|プライマリ データセンターが|EMEA|Noam|アジア|
|:--- |:--- |:--- |:--- |
|セカンダリ データセンター (sip2.pstnhub.microsoft.com)|私たち|Eu|私たち|
|第 3 データセンター (sip3.pstnhub.microsoft.com)|アジア|アジア|Eu|
|||||

## <a name="media-traffic-port-ranges"></a>メディア トラフィック: ポート範囲

メディア バイパスなしでダイレクト ルーティングを展開する場合は、次の要件が適用されることに注意してください。 メディア バイパスのファイアウォール要件については、「 [ダイレクト ルーティングを使用したメディア バイパスの計画](./direct-routing-plan-media-bypass.md)」を参照してください。

メディア トラフィックは、Microsoft Cloud 内の別のサービスとの間で送受信されます。 メディア トラフィックの IP アドレス範囲は次のとおりです。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

- 52.112.0.0/14 (52.112.0.1 から 52.115.255.254 への IP アドレス)。
- 52.120.0.0/14 (52.120.0.1 から 52.123.255.254 への IP アドレス)。

### <a name="office-365-dod-environment"></a>Office 365 DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>GCC High 環境のOffice 365

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>ポート範囲 (すべての環境に適用)

メディア プロセッサのポート範囲を次の表に示します。

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|メディア プロセッサ|Sbc|3478-3481 および 49152 – 53247|SBC で定義されている|
|UDP/SRTP|Sbc|メディア プロセッサ|SBC で定義されている|3478-3481 および 49152 – 53247|

  > [!NOTE]
  > Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートを推奨しています。

## <a name="media-traffic-media-processors-geography"></a>メディア トラフィック: メディア プロセッサの地域

メディア トラフィックは、メディア プロセッサと呼ばれるコンポーネントを介して流れます。 メディア プロセッサは、SIP プロキシと同じデータセンターに配置されます。

- NOAM (米国中南部、米国西部と米国東部のデータセンターに 2 つ)
- ヨーロッパ (英国南部、フランス中部、アムステルダム、ダブリンのデータセンター)
- アジア (シンガポール データセンター)
- 日本 (JP 東日本および西データセンター)
- オーストラリア (AU 東部および南東部のデータセンター)
- LATAM (ブラジル南部)

## <a name="media-traffic-codecs"></a>メディア トラフィック: コーデック

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC とクラウド メディア プロセッサまたは Microsoft Teams クライアントの間の脚

メディア バイパス ケースと非バイパス ケースの両方に適用されます。

セッション ボーダー コントローラーとクラウド メディア プロセッサ間 (メディア バイパスなし) 間、または Teams クライアントと SBC (メディア バイパスが有効な場合) の間のダイレクト ルーティング インターフェイスでは、次のコーデックを使用できます。

- 非メディア バイパス (SBC からクラウド メディア プロセッサ): SILK、G.711、G.722、G.729
- メディア バイパス (SBC から Teams クライアント): SILK、G.711、G.722、G.729

オファーから望ましくないコーデックを除外することで、セッション ボーダー コントローラーで特定のコーデックを強制的に使用できます。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams クライアントとクラウド メディア プロセッサの間の脚

メディア以外のバイパス ケースにのみ適用されます。 メディア バイパスを使用すると、メディアは Teams クライアントと SBC の間で直接流れます。

クラウド メディア プロセッサと Microsoft Teams クライアントの間の脚では、SILK または G.722 が使用されます。 この脚のコーデックの選択は、複数のパラメーターを考慮した Microsoft アルゴリズムに基づいています。

  > [!NOTE]
  > メディアの再ターゲット設定はサポートされていません。 ダイレクト ルーティングの呼び出し中に、SBC が新しいメディア IP を Teams ダイレクト ルーティングに送信する場合、SIP 信号でネゴシエートされますが、メディアは Teams ダイレクト ルーティングから新しい IP アドレスに送信されることはありません。

## <a name="supported-session-border-controllers-sbcs"></a>サポートされているセッション ボーダー コントローラー (SBC)

Microsoft では、ダイレクト ルーティングとペアリングする認定された SBC のみがサポートされています。 エンタープライズ VoIPは企業にとって重要であるため、Microsoft は選択した SBC で集中的なテストを実行し、SBC ベンダーと連携して 2 つのシステムに互換性があることを確認します。

検証済みのデバイスは、Teams ダイレクト ルーティングの認定済みとして一覧表示されます。 認定されたデバイスは、すべてのシナリオで動作することが保証されています。

サポートされている SBC の詳細については、「 [ダイレクト ルーティングの認定を受けたセッション ボーダー コントローラー](direct-routing-border-controllers.md)」を参照してください。

## <a name="support-boundaries"></a>サポート境界

Microsoft は、認定されたデバイスで使用する場合にのみ、ダイレクト ルーティングを備えた電話システムをサポートします。 問題が発生した場合は、最初に SBC ベンダーのカスタマー サポートに連絡する必要があります。 必要に応じて、SBC ベンダーは内部チャネルを介して問題を Microsoft にエスカレートします。 Microsoft は、認定済みでないデバイスがダイレクト ルーティング経由で電話システムに接続されている場合に、サポート ケースを拒否する権利を留保します。 お客様のダイレクト ルーティングの問題がベンダーの SBC デバイスにあると Microsoft が判断した場合、お客様は SBC ベンダーにサポートを再び依頼する必要があります。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
