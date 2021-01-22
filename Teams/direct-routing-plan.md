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
description: Microsoft Phone System Direct Routing を使用して、サポートされている顧客提供のセッション ボーダー コントローラー (SBC) を Microsoft Phone System に接続する方法について説明します。
ms.openlocfilehash: 77757cf76215dbed0b3ec572b5f1f57120551d86
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923829"
---
# <a name="plan-direct-routing"></a>ダイレクト ルーティングを計画する

> [!Tip]
> 次のセッションを見て、ダイレクト ルーティングの利点、その計画方法、展開方法について説明します[。Microsoft Teams](https://aka.ms/teams-direct-routing)での直接ルーティング

Microsoft Phone System Direct Routing を使用すると、サポートされている顧客提供のセッション ボーダー コントローラー (SBC) を Microsoft Phone System に接続できます。  たとえば、この機能を使用すると、次の図に示すように、Microsoft Teams クライアントとのオンプレミスの公衆交換電話網 (PSTN) 接続を構成できます。 

![オンプレミス PSTN 接続の構成を示す図](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft Teams クライアントとのオンプレミス PSTN 接続の構成")

  > [!NOTE]
  > Skype for Business Online では、顧客が提供する SBC をペアリングすることもできますが、これには、SBC と Microsoft Cloud の間にオンプレミスの Skype for Business Server 展開またはクラウド コネクタと呼ばれる特別なエディションの Skype for Business が必要です。 このシナリオはハイブリッド 音声と呼ばれる。 これに対し、ダイレクト ルーティングでは、サポートされている SBC と Microsoft Cloud 間の直接接続が可能になります。

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](direct-routing-landing-page.md)。 

ダイレクト ルーティングを使用すると、ほぼすべてのテレフォニー トランクまたはサードパーティ PSTN 機器との相互接続に SBC を接続できます。 直接ルーティングを使用すると、次の操作を行います。 

- Microsoft Phone System で PSTN トランクを事実上使用します。 
- サードパーティのプライベートブランチ交換 (PBX)、アナログ デバイス、Microsoft Phone System など、顧客所有のテレフォニー機器間の相互運用性を構成します。

Microsoft では、通話プランなどのクラウド内音声ソリューションも提供しています。 ただし、次の場合は、ハイブリッド 音声ソリューションが組織に最適な場合があります。 

- Microsoft 通話プランは、お客様の国ではご利用になられません。 
- お客様の組織では、サード パーティ製アナログ デバイスやコール センターなどへの接続が必要です。 
- お客様の組織には、PSTN 通信事業者との既存の契約があります。

ダイレクト ルーティングは、Microsoft 通話プランの追加ライセンスを持つユーザーもサポートします。 詳細については、[電話システムと通話プラン](calling-plan-landing-page.md)に関する記事をご覧ください。 

直接ルーティングを使用すると、ユーザーがスケジュールされた電話会議に参加すると、ダイヤルイン番号は Microsoft 電話会議サービスによって提供され、適切なライセンスが必要です。  Microsoft 電話会議サービスは、ダイヤルアウト時にオンライン通話機能を使用して通話を発信します。この機能には適切なライセンスが必要です。 (ユーザーが Microsoft 電話会議ライセンスを持ってない場合は、通話がダイレクト ルーティングを経由してルーティングされます。詳細については [、「Teams でのオンライン会議」を参照してください](https://products.office.com/microsoft-teams/online-meeting-solutions)。 
 
ダイレクト ルーティングの展開を計画すると、実装を成功に役立つ鍵になります。 この記事では、インフラストラクチャとライセンスの要件について説明し、SBC 接続に関する情報を提供します。 

- [インフラストラクチャの要件](#infrastructure-requirements)
- [ライセンスと他の要件](#licensing-and-other-requirements)
- [SBC ドメイン名](#sbc-domain-names)
- [SBC のパブリック信頼済み証明書](#public-trusted-certificate-for-the-sbc)
- [SIP シグナリング: FQDN](#sip-signaling-fqdns)
- [SIP シグナリング: ポート](#sip-signaling-ports)
- [メディア トラフィック: ポート範囲](#media-traffic-port-ranges)
- [サポートされているセッション ボーダー コントローラー (SBC)](#supported-session-border-controllers-sbcs)

ダイレクト ルーティングの構成の詳細については、「ダイレクト ルーティングを構成する [」を参照してください](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
ダイレクト ルーティングを展開するためにサポートされる SPC、ドメイン、その他のネットワーク接続要件のインフラストラクチャ要件を次の表に示します。  

|インフラストラクチャ要件|次の情報が必要です|
|:--- |:--- |
|セッション ボーダー コントローラー (SBC)|サポートされている SBC。 詳細については、サポートされている [SPC を参照してください](#supported-session-border-controllers-sbcs)。|
|SBC に接続されているテレフォニー トランク|SBC に接続されている 1 つ以上のテレフォニー トランク。 一方の端では、SBC はダイレクト ルーティングを介して Microsoft 電話システムに接続します。 SBC は、PBX、アナログ テレフォニー アダプターなどのサードパーティのテレフォニー エンティティにも接続できます。 SBC に接続されている PSTN 接続オプションが動作します。 (SBC への PSTN トランクの構成については、SBC ベンダーまたはトランク プロバイダーを参照してください)。|
|Microsoft 365 または Office 365 組織|Microsoft Teams ユーザーをOffice、SBC への構成と接続に使用する Microsoft 365 または Office 365 組織。|
|ユーザー レジストラー|ユーザーは Microsoft 365 または Office 365 に持ち込む必要があります。<br/>会社に Microsoft 365 または Office 365 へのハイブリッド接続を備えるオンプレミスの Skype for Business または Lync 環境がある場合、オンプレミスのユーザーに対して Teams で音声を有効にすることはできません。<br/><br/>ユーザーのレジストラーを確認するには、次の Skype for Business Online PowerShell コマンドレットを使用します。<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>コマンドレットの出力は次を示す必要があります。<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|ドメイン|Microsoft 365 または 365 組織に追加Office 1 つ以上のドメイン。<br/><br/>テナント用に自動的に作成される既定 \* のドメインである .onmicrosoft.com を使用することはできません。<br/><br/>ドメインを表示するには、次の Skype for Business Online PowerShell コマンドレットを使用できます。<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>ドメインと Microsoft 365 または 365 組織Office詳細については、ドメインに関する [FAQ を参照してください](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC のパブリック IP アドレス|SBC への接続に使用できるパブリック IP アドレス。 SBC の種類に基づいて、SBC は NAT を使用できます。|
|SBC の完全修飾ドメイン名 (FQDN)|SBC の FQDN。FQDN のドメイン部分は、Microsoft 365 または Office 365 組織に登録されているドメインの 1 つです。 詳細については [、SBC ドメイン名を参照してください](#sbc-domain-names)。|
|SBC のパブリック DNS エントリ |SBC FQDN をパブリック IP アドレスにマッピングするパブリック DNS エントリ。 |
|SBC のパブリック信頼済み証明書 |ダイレクト ルーティングを使用してすべての通信に使用される SBC の証明書。 詳細については [、SBC のパブリック信頼済み証明書を参照してください](#public-trusted-certificate-for-the-sbc)。|
|ダイレクト ルーティングの接続ポイント |ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。<br/><br/>`sip.pstnhub.microsoft.com` – グローバル FQDN は、最初に試す必要があります。<br/>`sip2.pstnhub.microsoft.com` – セカンダリ FQDN。地理的に第 2 の優先度の領域にマップされます。<br/>`sip3.pstnhub.microsoft.com` – 第 3 優先度の地域に地理的にマップされる、第 3 の FQDN。<br/><br/>構成要件の詳細については [、「SIP シグナリング: FQDN」を参照してください](#sip-signaling-fqdns)。|
|ダイレクト ルーティング メディアのファイアウォール IP アドレスとポート |SBC は、クラウド内の次のサービスに通信します。<br/><br/>シグナリングを処理する SIP プロキシ<br/>メディア を処理するメディア プロセッサ (メディア バイパスがオンの場合を除く)<br/><br/>これら 2 つのサービスには、このドキュメントで後述する Microsoft Cloud の個別の IP アドレスがあります。<br/><br/>詳細については、URL と IP アドレス範囲 [の Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [セクションを参照してください](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 |
|メディアトランスポート プロファイル|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams メディアのファイアウォール IP アドレスとポート |詳細については、「URL と [IP アドレス範囲」を参照してください](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>ライセンスと他の要件 

直接ルーティングのユーザーには、Microsoft 365 または 365 で次のライセンスOffice必要があります。 

- Microsoft Phone System。 
- Microsoft Teams + Skype for Business プラン 2 (ライセンスに含まれている場合)。
- Microsoft 電話会議 (ライセンスが必要な場合の具体的な例については、以下のメモと段落をお読みください)。

> [!NOTE]
> Skype for Business プランは、含まれているライセンス契約から削除することはできません。 


> [!IMPORTANT]
>  外部参加者をスケジュールされた会議に追加する場合は、外部参加者にダイヤルアウトするか、ダイヤルイン番号を指定して、電話会議ライセンスが必要です。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>アドホック通話のエスカレーションと電話会議ライセンス

Teams ユーザーは、1 対 1 の Teams から PSTN または Teams から Teams への通話を開始し、PSTN 参加者を追加できます。 このシナリオは、アドホック会議と呼ばれる場合があります。 通話のパスは、通話をエスカレーションするユーザーに Microsoft 電話会議ライセンスが割り当てられているかどうかによって異なります。

- 通話をエスカレーションする Teams ユーザーに Microsoft 電話会議ライセンスが割り当てられている場合、エスカレーションは Microsoft 電話会議サービスを通じて行います。 既存の通話に招待されたリモート PSTN 参加者は、着信に関する通知を受け取り、エスカレーションを開始した Teams ユーザーに割り当てられた Microsoft ブリッジの数を確認します。
- 通話をエスカレーションする Teams ユーザーに Microsoft 電話会議ライセンスが割り当てられていない場合、エスカレーションは直接ルーティング インターフェイスに接続されたセッション ボーダー コントローラーを介して行います。 通話に招待されたリモート PSTN 参加者は、着信に関する通知を受け取り、エスカレーションを開始した Teams ユーザーの数を確認します。 エスカレーションに使用される特定の SBC は、ユーザーのルーティング ポリシーによって定義されます。 


さらに、次の情報を確認する必要があります。
 
- CsOnlineVoiceRoutingPolicy がユーザーに割り当てられます。 
- プライベート通話を許可する機能は、Microsoft Teams のテナント レベルで有効になっています。 

直接ルーティングは、Microsoft 通話プランのライセンスを取得しているユーザーもサポートします。 通話プランが設定された Microsoft 電話システムでは、ダイレクト ルーティング インターフェイスを使用して一部の通話をルーティングできます。 ただし、ユーザーの電話番号はオンラインで取得するか、Microsoft に移植する必要があります。  

同じユーザーの通話プランとダイレクト ルーティング接続の混在はオプションですが、便利な場合があります (たとえば、ユーザーに Microsoft 通話プランが割り当てられているが、SBC を使用して一部の通話をルーティングする場合)。 最も一般的なシナリオの 1 つは、サードパーティ PBX への呼び出しです。  サードパーティ PBX では、PBX に接続されている電話への通話を除くすべての通話が Microsoft 通話プランを使用してルーティングされますが、サードパーティ PBX に接続されている電話への通話は SBC に移動するため、PSTN ではなくエンタープライズ ネットワーク内に残っています。 

電話システムのライセンスの詳細については、「電話システムの概要とプランのオプション[Officeを](https://products.office.com/compare-all-microsoft-office-products?tab=2)[参照してください](https://technet.microsoft.com/library/office-365-plan-options.aspx)。 

電話システム のライセンスの詳細については [、Microsoft Teams のアドオン ライセンスを参照してください](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。 

## <a name="supported-end-points"></a>サポートされているエンド ポイント 

終了点として使用できます。

- 任意の Teams クライアント。 
- 共通領域の電話。 「Microsoft [Teams の共通領域電話ライセンスを設定する」を参照してください](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)。 直接ルーティングを使用して共通領域の電話を設定する場合は、通話プランのライセンスは必要ない点に注意してください。
- Skype for Business 3PIP 電話機。 [Microsoft Teams での Skype for Business 電話機 (3PIP) のサポートを参照する](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC ドメイン名

SBC ドメイン名は、テナントのドメインに登録されている名前の 1 つである必要があります。 SBC の \* FQDN onmicrosoft.comに .onmicrosoft.com テナントを使用することはできません。

次の表は、テナントに登録されている DNS 名の例、名前を SBC の FQDN として使用できるかどうか、および有効な FQDN 名の例を示しています。

|DNS 名|SBC FQDN に使用できます|FQDN 名の例|
|:--- |:--- |:--- |
contoso.com|はい|**有効な名前:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|いいえ|SBC 名onmicrosoft.com *.onmicrosoft.comの使用はサポートされていません

新しいドメイン名を使用するとします。 たとえば、テナントがテナントcontoso.com登録されているドメイン名として保存されている場合、テナントを使用sbc1.sip.contoso.com。 SBC とドメイン名を組み合sbc1.sip.contoso.com、テナントの [ドメイン] にドメインsip.contoso.comを登録する必要があります。 ドメイン名を登録する前に SBC と sbc1.sip.contoso.com をペアリングすると、"このテナント用に構成されていない "sbc1.sip.contoso.com" ドメインを使用できません。
ドメイン名を追加した後、UPN アカウントを持つユーザーを作成し、Teams user@sip.contoso.com割り当てる必要があります。 ドメイン名がテナントのドメインに追加され、新しい名前のユーザーが作成され、ユーザーにライセンスが割り当てられるまで、最大で 24 時間かかる場合があります。 

会社が 1 つのテナントに複数の SIP アドレス 空間を持っている可能性があります。 たとえば、会社が SIP アドレス空間としてcontoso.com、2 つ目の SIP アドレスfabrikam.com 2 番目の SIP アドレス空間として使用されている場合があります。 一部のユーザーはuser@contoso.comを持ち、一部のユーザーはアドレスを持user@fabrikam.com。 

SBC は 1 つの FQDN のみを必要とし、ペアリングされたテナント内の任意のアドレス空間からユーザーにサービスを提供できます。 たとえば、sbc1.contoso.com という名前の SBC は、これらの SIP アドレス空間が同じテナントに登録されている限り、アドレス user@contoso.com と user@fabrikam.com を持つユーザーの PSTN トラフィックを受信および送信できます。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC のパブリック信頼済み証明書

Microsoft では、証明書署名要求 (CSR) を生成して SBC の証明書を要求する必要があります。 SBC の CSR の生成に関する具体的な手順については、SBC ベンダーが提供する相互関係の手順またはドキュメントを参照してください。 

  > [!NOTE]
  > ほとんどの認証局 (CA) では、2048 以上のプライベート キー サイズが必要です。 CSR を生成する際は、この問題に気を付ける必要があります。

証明書には、共通名 (CN) または件名の代替名 (SAN) フィールドとして SBC FQDN が必要です。 証明書は、中間プロバイダーからではなく、証明機関から直接発行する必要があります。

または、ダイレクト ルーティングは CN または SAN のワイルドカードをサポートし、ワイルドカードは標準の [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1)に準拠する必要があります。 たとえば、SBC FQDN contoso.com と一致するが、sbc.contoso.com と一致しない \* .sbc.test.contoso.com を使用する場合があります。

証明書は、次のいずれかのルート証明機関によって生成される必要があります。

- Trust
- AddTrust External CA Root
- Baltimore CyberTrust Root*
- Buypass
- Cybertrust
- Class 3 Public Primary Certification Authority
- Comodo Secure Root CA
- ドイツ テレコム 
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- 預け
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Symantec Enterprise Mobile Root for Microsoft 
- スイス
- 解凍タイムスタンプ CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Office 365 GCCH および DoD 環境での直接ルーティングの場合、証明書は次のいずれかのルート証明機関によって生成される必要があります。
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> * SBC の Teams 接続で Mutual TLS (MTLS) のサポートが有効になっている場合は、Teams TLS コンテキストの SBC 信頼済みルート ストアに Baltimore CyberTrust ルート証明書をインストールする必要があります。 (これは、Microsoft サービス証明書で Baltimore ルート証明書が使用されているためです)。Baltimore ルート証明書をダウンロードするには、「Office [365 暗号化チェーン」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)。

Microsoft では、お客様からの要求に基づいて、追加の証明機関の追加に取り組み中です。 

## <a name="sip-signaling-fqdns"></a>SIP シグナリング: FQDN 

ダイレクト ルーティングは、次の環境で提供されます。
- Microsoft 365 または Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

GCC、GCC high Office DoD などの [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) および米国政府機関の環境の詳細については、以下を参照してください。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN - 最初に試す必要があります。 SBC からこの名前を解決するための要求が送信された場合、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。 この割り当ては、データセンターのパフォーマンスメトリックと SBC への地理的近接性に基づいて行われます。 返される IP アドレスはプライマリ FQDN に対応します。
- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に第 2 の優先度の地域にマップされます。
- **sip3.pstnhub.microsoft.com** – 優先 FQDN – 第 3 の優先度の地域に地理的にマップされます。

次の 3 つの FQDN を配置するには、次の手順を実行する必要があります。

- 最適なエクスペリエンスを提供します (読み込まれ少なく、最初の FQDN にクエリを実行して割り当てられた SBC データセンターに最も近い)。
- 一時的な問題が発生しているデータセンターに SBC からの接続が確立された場合は、フェールオーバーを提供します。 詳細については、以下のフェールオーバー [メカニズムを参照](#failover-mechanism-for-sip-signaling) してください。  

FQDN (sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.com) は、次のいずれかの IP アドレスに解決されます。

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合 **、FQDN** sip-all.pstnhub.microsoft.comすべての IP アドレスに解決されます。 

> [!IMPORTANT]
>  Teams のダイレクト ルーティングの拡張とサービスの改善の一環として、オーストラリアではダイレクト ルーティング インフラストラクチャの新しいインスタンスを展開しました。 これは、オーストラリアのお客様 (sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.com の 2 つの追加 IP アドレス (52.114.16.74 と 52.114.20.29) に反映されます。 これら 2 つの IP アドレス (52.114.16.74 と 52.114.20.29) を IP アクセス制御リスト (ACL) に追加し、ファイアウォールでこれらすべての IP アドレスのポートを開いて、シグナリング用のアドレスに対する着信および発信トラフィックを許可する必要があります。

### <a name="office-365-gcch-and-dod-environment"></a>Office 365 GCCH および DoD 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。 Office 365 DoD 環境は米国のデータ センターにのみ存在し、第 2 および第 3 の FQDN はありません。

FQDN sip.pstnhub.dod.teams.microsoft.us、次のいずれかの IP アドレスに解決されます。

- 52.127.64.33
- 52.127.68.34

シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 GCC High 環境は米国のデータ センターにのみ存在しますが、第 2 および第 3 の FQDN はありません。

FQDN sip.pstnhub.gov.teams.microsoft.us、次のいずれかの IP アドレスに解決されます。

- 52.127.88.59
- 52.127.92.64

シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。 ファイアウォールで DNS 名がサポートされている場合 **、FQDN** sip-all.pstnhub.gov.teams.microsoft.us IP アドレスはすべて解決されます。 この FQDN は、着信通話の分類にフェデレーション FQDN として使用できます。

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

ダイレクト ルーティングが提供される Microsoft 365 または Office 365 環境では、次のポートを使用する必要があります。
- Microsoft 365 または Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP プロキシ|SBC|1024 – 65535|SBC で定義されます (Office 365 GCC High/DoD の場合は、ポート 5061 のみを使用する必要があります)|
SIP/TLS|SBC|SIP プロキシ|SBC で定義|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP シグナリングのフェールオーバー メカニズム

SBC は、DNS クエリを実行して問題をsip.pstnhub.microsoft.com。 SBC の場所とデータセンターのパフォーマンスメトリックに基づいて、プライマリ データセンターが選択されます。 プライマリ データセンターで問題が発生した場合、SBC は sip2.pstnhub.microsoft.com を試します。これは、2 つ目に割り当てられたデータセンターに解決され、まれに 2 つの地域のデータセンターが利用できない場合、SBC は最後の FQDN (sip3.pstnhub.microsoft.com) を再試行し、データセンターの IP を提供します。

次の表は、プライマリ データセンター、セカンダリ データセンター、およびデータセンター間の関係をまとめたものです。

|プライマリ データセンターが|EMEA|NOAM|アジア|
|:--- |:--- |:--- |:--- |
|セカンダリ データセンター (sip2.pstnhub.microsoft.com)|米国|EU|米国|
|データセンター (sip3.pstnhub.microsoft.com)|アジア|アジア|EU|
|||||

## <a name="media-traffic-port-ranges"></a>メディア トラフィック: ポート範囲
メディア バイパスを使用せずにダイレクト ルーティングを展開する場合は、以下の要件が適用されます。 メディア バイパスのファイアウォール要件については、「ダイレクト ルーティングを使用したメディア バイパスの計画」 [を参照してください](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)。



メディア トラフィックは、Microsoft Cloud の別のサービスに対して、および Microsoft Cloud 内の別のサービスに対してフローします。 メディア トラフィックの IP アドレス範囲は次のとおりです。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

- 52.112.0.0/14 (52.112.0.1 から 52.115.255.254 の IP アドレス)。
- 52.120.0.0/14 (52.120.0.1 から 52.123.255.254 の IP アドレス)。

### <a name="office-365-dod-environment"></a>Office 365 DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>ポート範囲 (すべての環境に適用)
メディア プロセッサのポート範囲を次の表に示します。 

|トラフィック|開始|終了|送信元ポート|宛先ポート|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|メディア プロセッサ|SBC|3478-3481 および 49152 – 53247|SBC で定義|
|UDP/SRTP|SBC|メディア プロセッサ|SBC で定義|3478-3481 および 49152 – 53247|

  > [!NOTE]
  > Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートを推奨しています。


## <a name="media-traffic-media-processors-geography"></a>メディア トラフィック: メディア プロセッサの地理

メディア トラフィックは、メディア プロセッサと呼ばれるコンポーネントを介して流れます。 メディア プロセッサは、SIP プロキシと同じデータセンターに配置されます。 また、メディア フローを最適化する追加のメディア プロセッサがあります。 たとえば、現在、オーストラリアには SIP プロキシ コンポーネントが含んでいな (シンガポールまたは香港経由の SIP フロー)、オーストラリアにはローカルにメディア プロセッサがあります。 ローカルのメディア プロセッサの必要性は、オーストラリアからシンガポールや香港など、トラフィックを長距離に送信することで発生する遅延によって決まる。 オーストラリアから香港またはシンガポールに流れるトラフィックの例の遅延は、SIP トラフィックに対して良好な通話品質を維持するために許容されるが、リアルタイム メディア トラフィックでは許容されない。

メディア プロセッサの場所:

SIP プロキシコンポーネントとメディア プロセッサ コンポーネントの両方が展開されている場所:
- 米国 (米国西部と米国東部のデータセンターの 2 つ)
- ヨーロッパ (アムステルダムとダブリンのデータセンター)
- アジア (シンガポールと香港のデータセンター)

メディア プロセッサだけが展開されている場所 (上記の最も近いデータセンター経由の SIP フロー):
- 日本 (JP 東/西のデータセンター)
- オーストラリア (AU 東部および東南地域のデータセンター)




## <a name="media-traffic-codecs"></a>メディア トラフィック: コーデック

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC とクラウド メディア プロセッサまたは Microsoft Teams クライアントの間の脚。
メディア バイパス ケースと非バイパス ケースの両方に適用されます。

セッション ボーダー コントローラーとクラウド メディア プロセッサの間 (メディア バイパスなし) または Teams クライアントと SBC (メディア バイパスが有効な場合) 間の脚のダイレクト ルーティング インターフェイスでは、次のコーデックを使用できます。

- 非メディア バイパス (SBC からクラウド メディア プロセッサ): SILK、G.711、G.722、G.729
- メディア バイパス (SBC から Teams クライアント): SILK、G.711、G.722、G.729

セッション ボーダー コントローラーで特定のコーデックを強制的に使用するには、オファーから望ましくないコーデックを除外します。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams クライアントとクラウド メディア プロセッサの間の脚
メディア 以外のバイパス ケースにのみ適用されます。 メディア バイパスを使用すると、メディアは Teams クライアントと SBC の間で直接流れます。

クラウド メディア プロセッサと Microsoft Teams クライアントの間の脚では SILK または G.722 が使用されます。 この脚のコーデックの選択は、複数のパラメーターを考慮した Microsoft アルゴリズムに基づいて行います。 


## <a name="supported-session-border-controllers-sbcs"></a>サポートされているセッション ボーダー コントローラー (SBC)

Microsoft では、ダイレクト ルーティングとペアリングする認定された SPC のみをサポートしています。 Microsoft はエンタープライズ VoIP企業にとって重要なので、Microsoft は選択した SBC で集中的なテストを実行し、SBC ベンダーと組み合わせて、2 つのシステムに互換性を確保します。 

検証されたデバイスは、Teams ダイレクト ルーティングの認定済みとして表示されます。 認定デバイスは、すべてのシナリオで動作する保証があります。 

サポートされている SPC の詳細については、「ダイレクト ルーティング用に認定されたセッション ボーダー コントローラーの一覧 [」を参照してください](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
