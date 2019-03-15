---
title: ダイレクト ルーティングを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Microsoft 電話システム直接ルーティングを使用する方法マイクロソフトの電話システムに、サポートされている、お客様が用意したセッション ボーダー コント ローラー (SBC) の接続については、このトピックを参照してください。
ms.openlocfilehash: 202b25903a3e48b0a2a2f32853f061eb8ca73cc8
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569943"
---
# <a name="plan-direct-routing"></a>ダイレクト ルーティングを計画する

> [!Tip]
> ルーティング、それを計画する方法と展開方法は、直接の利点について説明するのには次のセッションを監視する:[マイクロソフトのチームに直接ルーティング](https://aka.ms/teams-direct-routing)

Microsoft 電話システム直接ルーティングするには、マイクロソフトの電話システムに、サポートされている、お客様が用意したセッション ボーダー コント ローラー (SBC) に接続することができます。  この機能により、たとえばを構成できます設置した PSTN 接続マイクロソフト チームのクライアントを使用して次の図に示すように。 

![マイクロソフト チームのクライアントを使用して設置した PSTN 接続の構成を示しています。](media/PlanDirectRouting1-PSTNwithTeams.png)

  > [!NOTE]
  > Skype ビジネスをオンラインにすることもできますペアお客様が用意した SBC では、ですが、ビジネスのサーバーの展開や、SBC とマイクロソフトのクラウドの間に、クラウドのコネクタと呼ばれる、ビジネスの Skype の特別な版の設置、Skype が必要です。 このシナリオは、ハイブリッドのボイスと呼ばれます。 対照的に、直接ルーティングには、サポートされている SBC とマイクロソフトのクラウドとの間の直接接続することができます。 

直接ルーティングでは、ほぼすべてのテレフォニーのトランクに、SBC を接続したり、サード パーティ製の公衆交換電話網 (PSTN) 機器と相互接続できます。 直接ルーティングできます。 

- マイクロソフトの電話システムのほぼすべての PSTN トランクを使用します。 
- サード ・ パーティ製の構内交換 (機 PBX)、アナログ デバイス、および Microsoft の電話システムなど、お客様が所有するテレフォニー機器間の相互運用性を構成します。

マイクロソフトでは、計画を呼び出すなどのクラウドをすべて音声ソリューションも提供しています。  ただし、ハイブリッド音声ソリューションは、組織に最適な場合がある場合。 

- Microsoft の計画を呼び出すことはお住まいの国で。 
- 組織では、サード ・ パーティ製のアナログ デバイス、コール センターへの接続が必要です。 
- 組織には、PSTN のキャリアで既存の契約があります。

直接ルーティングでは、Microsoft を呼び出す予定の追加のライセンスを持つユーザーもサポートしています。 詳細については、 [Office 365 のプランを呼び出す](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)と、[使用許諾契約とその他の要件](#licensing-and-other-requirements)を参照してください。 

直接ルーティングでは、ユーザーは、スケジュールされた会議に参加すると、ダイヤルイン番号が Microsoft オーディオ会議サービスは、適切なライセンスを必要とするによって提供されます。  発信では、Microsoft のオーディオ会議サービスは、適切なライセンスを必要とするオンラインの呼び出し機能を使用して呼び出しを配置します。 (その発信ルーティングせず直接ルーティングを使用に注意してください)。詳細については、[チームとのオンライン会議](https://products.office.com/microsoft-teams/online-meeting-solutions)を参照してください。 
 
直接ルーティングの展開の計画は、実装を成功させるキーです。 この資料では、インフラストラクチャとライセンスの要件について説明し、SBC の接続に関する情報を提供します。 

- [インフラストラクチャの要件](#infrastructure-requirements)
- [ライセンスおよびその他の要件](#licensing-and-other-requirements)
- [SBC ドメイン名](#sbc-domain-names)
- [SBC の信頼された証明書の公開](#public-trusted-certificate-for-the-sbc)
- [SIP シグナル: Fqdn およびファイアウォールのポート](#sip-signaling-fqdns-and-firewall-ports)
- [メディア トラフィック: ポートの範囲](#media-traffic-port-ranges)
- [SBCs のサポートされています。](#supported-session-border-controllers-sbcs)

直接ルーティングの構成の詳細については、[直接ルーティングの構成](direct-routing-configure.md)を参照してください。

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
サポートされている SBCs、ドメイン、およびその他のネットワーク接続の要件に直接ルーティングを展開のインフラストラクチャの要件は、次の表のとおりです。  

|**インフラストラクチャの要件**|**以下が必要**|
|:--- |:--- |
|セッション ボーダー コント ローラー (SBC)|サポートされている SBC の場合です。 詳細については、 [SBCs のサポート](#supported-session-border-controllers-sbcs)を参照してください。|
|SBC に接続されているテレフォニー トランク|1 つまたは複数のテレフォニーのトランクは、SBC に接続されています。 一方の端に、SBC は直接ルーティングを使用して Microsoft の電話システムに接続します。 SBC は、テレフォニー アダプターのアナログ Pbx などのサード パーティ製のテレフォニーのエンティティに接続し、ようにもできます。 SBC に接続されているすべての PSTN 接続性オプションが動作します。 (注: SBC に PSTN トランクの構成は、SBC ベンダーまたはトランクのプロバイダーを参照してください)。|
|Office 365 テナント|ホームのマイクロソフトのチームのユーザーの構成と、SBC への接続に使用する Office 365 テナントです。|
|ユーザー登録|Office 365 のユーザーが所属する必要があります。<br/>ユーザーのチームでの音声を有効にすることはできません会社、設置型の Skype ビジネスまたは Lync の環境を Office 365 のハイブリッド接続の場合は、設置型のホームです。<br/><br/>ユーザーのレジストラーを確認するには、ビジネス オンラインの PowerShell コマンドレットの次の Skype を使用します。<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>コマンドレットの出力を表示する必要があります。<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|ドメイン|1 つ以上のドメインが、Office 365 テナントに追加します。<br/><br/>**注:** 既定のドメインを使用することはできません *.、onmicrosoft.com、テナントが自動的に作成します。<br/><br/>ドメインを表示するには、ビジネス オンラインの PowerShell コマンドレットの次の Skype を使用できます。<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>ドメインと Office 365 のテナントの詳細については、[ドメインに関する FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)を参照してください。|
|SBC のパブリック IP アドレス|SBC への接続に使用できるパブリック IP アドレスです。 SBC の種類に基づいて、SBC は NAT を使用できます。|
|SBC の完全修飾ドメイン名 (FQDN)|FQDN のドメイン部分が、Office 365 テナントに登録されたドメインのいずれかを SBC の FQDN です。 詳細については、 [SBC のドメイン名](#sbc-domain-names)を参照してください。|
|SBC のパブリック DNS エントリ |SBC の FQDN をパブリック IP アドレスにマップするパブリック DNS エントリです。 |
|SBC の信頼された証明書の公開 |直接ルーティングですべての通信に使用する SBC の証明書です。 詳細については[、SBC の信頼された証明書の公開](#public-trusted-certificate-for-the-sbc)を参照してください。|
|直接ルーティングするための接続ポイント |直接ルーティングするための接続ポイントは、次の 3 つの Fqdn です。<br/><br/>`sip.pstnhub.microsoft.com`– グローバル FQDN が最初に試行する必要があります。<br/>`sip2.pstnhub.microsoft.com`– セカンダリ FQDN は、地理的に 2 番目の優先度の領域にマップします。<br/>`sip3.pstnhub.microsoft.com`– の第 3 の FQDN は、3 番目の優先度の領域に地理的にマップします。<br/><br/>構成要件についてを参照してください[SIP シグナリング: Fqdn およびファイアウォールのポート](#sip-signaling-fqdns-and-firewall-ports)。|
|ファイアウォールの IP アドレスとメディアの直接ルーティング用のポート |SBC がクラウド内の次のサービスを通信します。<br/><br/>SIP プロキシは、信号を処理します。<br/>メディア プロセッサは、メディアの処理のときに、メディアのバイパスを除く<br/><br/>これら 2 つのサービスでは、このドキュメントで後述する、マイクロソフトのクラウドで個別の IP アドレスがあります。<br/><br/>詳細については、 [Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)で、[マイクロソフトのチーム セクション](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を参照してください。 |
|メディア プロファイルを転送します。|TCP と RTP/SAVP <br/>UDP/RTP/SAVP|
ファイアウォールの IP アドレスとポートはマイクロソフトのチームのメディアの |詳細については、 [Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)を参照してください。 |
|||

## <a name="licensing-and-other-requirements"></a>ライセンスおよびその他の要件 

直接ルーティングのユーザーには、次のライセンスの Office 365 に割り当てられている必要があります。 

- マイクロソフトの電話システム 
- Microsoft Teams 
- Microsoft オーディオ会議 

オーディオ会議のライセンスにダイヤルアウトするか、ダイヤルイン番号を提供することによって、スケジュールされたミーティングの場合は、外部の参加者を追加する必要があります。 
 
  > [!NOTE]
  > E5 ライセンスには、電話システムと電話会議の両方が含まれています。   

さらに、次の操作を行う必要があります。
 
- CsOnlineVoiceRoutingPolicy は、ユーザーに割り当てられます。 
- マイクロソフトのチームのテナントのレベルの秘密を呼び出すことが有効になってを許可します。 

直接ルーティングに、Microsoft の計画を呼び出すことが許可されているユーザーもサポートしています。 計画を呼び出すことでマイクロソフトの電話システムには、直接ルーティング インターフェイスを使用していくつかの呼び出しをルーティングできます。 ただし、ユーザーの電話番号する必要があるかをオンラインで取得またはマイクロソフトに移植されました。  

同じユーザーについての計画を呼び出すと、直接ルーティング接続を混在させるオプションですが、役立つ可能性があります、たとえば、ユーザーが割り当てられている、Microsoft を呼び出すことを計画していますが、SBC を使用していくつかの呼び出しをルーティングしようとするとします。 最も一般的なシナリオの 1 つは、サード パーティの Pbx への呼び出しです。  サード パーティの Pbx とその Pbx に接続されている電話への呼び出しを除く、すべての呼び出しをルーティングして、を介して Microsoft の計画を呼び出すことです。SBC には、サード パーティの Pbx に接続されている電話への呼び出しが、エンタープライズ ネットワークと PSTN に常にそのためです。 

電話システムのライセンスの詳細については、 [Office と Office 365 を最大限に活用](https://products.office.com/compare-all-microsoft-office-products?tab=2)し、 [Office 365 のプランのオプション](https://technet.microsoft.com/library/office-365-plan-options.aspx)を参照してください。 

電話システムのライセンスの詳細については、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。 

## <a name="sbc-domain-names"></a>SBC ドメイン名

SBC ドメイン名は、テナントの「ドメイン」に登録された名前のいずれかをする必要があります。 使用することはできません、*.、SBC の FQDN 名を onmicrosoft.com テナントです。

有効な FQDN 名の例については、SBC の fqdn 名を使用することができるかどうかは、テナントに登録されている DNS 名の例を次に示します。

|**DNS 名**|**SBC の FQDN を使用することができます。**|**FQDN 名の例**|
|:--- |:--- |:--- |
contoso.com|はい|**有効な名前。**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|いいえ|<br/>使用して *. SBC 名を onmicrosoft.com ドメインはサポートされていません

新しいドメイン名を使用すると仮定します。 など、テナントには、テナントにドメイン名が登録されているし、sbc1.sip.contoso.com を使用する contoso.com です。 名前 sbc1.sip.contoso.com に SBC をペアには、前に、テナントの「ドメイン」でドメイン名の sip.contoso.com を登録してください。 ドメイン名を登録する前に sbc1.sip.contoso.com を持つ SBC をペアリングしようとすると、次のエラーが表示されます:"ことはできませんを使用して"sbc1.sip.contoso.com"ドメインとして、このテナント用に構成されていません。
ドメイン名を追加した後は、UPN の user@sip.contoso.com でユーザーを作成し、「チーム」ライセンスを割り当てる必要があります。 完全に準備が後にそのドメイン名は新しい名前を持つユーザーが作成され、ユーザーにライセンスが割り当てられている、テナントの「ドメイン」を追加するに最大 24 時間がかかる場合があります。 

会社が 1 つのテナントのいくつかの SIP アドレス スペースを必要があります。 たとえば、会社とがあります SIP アドレス空間 contoso.com fabrikam.com 2 つ目の SIP アドレス スペースとして。 一部のユーザーがあるアドレスに user@contoso.com と一部のユーザーがアドレス user@fabrikam.com にあります。 

SBC はのみ 1 つの FQDN が必要し、ペアのテナント内のすべてのアドレス領域からのユーザーにサービスを提供できます。 などの名 sbc1.contoso.com を持つ SBC 送受信できる PSTN トラフィック アドレス user@contoso.com と user@fabrikam.com を持つユーザーにこれらの SIP アドレス スペースは、同じテナントに登録されている限り。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC の信頼された証明書の公開

証明書署名要求 (CSR) を生成することで、SBC の証明書を要求することを強くお勧めします。 SBC の CSR を生成する具体的な方法については、相互接続の指示や、SBC ベンダーから提供されるマニュアルを参照してください。 

  > [!NOTE]
  > ほとんどの証明機関 (Ca) には、少なくとも 2048 を使用する秘密キーのサイズが必要です。 CSR を生成するときは、この点に留意してください。

証明書には、[件名]、[共通名、または [サブジェクト代替名フィールドに SBC の FQDN が必要です。

または、直接ルーティングでは、SAN のワイルドカードをサポートしているし、ワイルドカードは、標準の[TLS 経由で HTTP を RFC](https://tools.ietf.org/html/rfc2818#section-3.1)に準拠する必要があります。 例を使用する場合 *. contoso.com で、SAN には、SBC の FQDN の sbc.contoso.com、一致が sbc.test.contoso.com と一致しません。

証明書は、次のルート証明機関のいずれかによって生成される必要があります。

- AffirmTrust
- AddTrust 外部 CA のルート
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- クラス 3 の主要な公共の証明機関
- Comodo は、ルート CA をセキュリティで保護します。
- Deutsche telekom 社 
- DigiCert のグローバル ルート CA
- DigiCert 高保証 EV のルート CA
- 委託
- GlobalSign
- 行事を移動します。
- GeoTrust
- Verisign, inc. 
- スター フィールド 
- マイクロソフトのシマンテック社のエンタープライズ ・ モバイル ルート 
- SwissSign
- Thawte タイムスタンプ CA
- Trustwave
- TeliaSonera 
- T システム国際 GmbH (Deutsche telekom 社)
- QuoVadis

マイクロソフトは顧客の要求に基づいて、追加の証明機関を追加することに取り組んでいます。 

## <a name="sip-signaling-fqdns-and-firewall-ports"></a>SIP シグナル: Fqdn およびファイアウォールのポート 

直接ルーティングのためのコネクション ポイントは、次の 3 つの Fqdn です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN – が最初に試行する必要があります。 SBC では、この名前を解決するのには要求を送信するとき、Microsoft Azure の DNS サーバーは、SBC にプライマリの Azure データ センターを指す IP アドレスが割り当てられているを返します。 割り当ては、データ センターおよび、SBC に地理的な近接性のパフォーマンスの測定値に基づいています。 返された IP アドレスは、プライマリの FQDN に対応します。
- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – は、2 番目の優先度の領域に地理的にマップします。
- **sip3.pstnhub.microsoft.com** – 第 3 FQDN – は、3 番目の優先度の領域に地理的にマップします。

順序でこれらの 3 つの Fqdn を配置することは、するために必要です。

- (小さい読み込まれ、最初の FQDN を照会することによって割り当てられている SBC のデータ センターに最も近い) の最適なエクスペリエンスを提供します。
- SBC からの接続が確立されると一時的な問題が発生しているデータ センターへのフェイル オーバーを提供します。 詳細については、[フェイル オーバー ・ メカニズム](#failover-mechanism-for-sip-signaling)の下を参照してください。  

(Sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com および sip3.pstnhub.microsoft.com) の Fqdn は、次の IP アドレスのいずれかに解決されます。

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

シグナル用とアドレスからの着信および発信トラフィックを許可するファイアウォールでこれらのすべての IP アドレスのポートを開く必要があります。  お使いのファイアウォールでは、DNS 名をサポートする場合、上のすべての IP アドレスを FQDN、sip の all.pstnhub.microsoft.com が解決します。  次のポートを使用する必要があります。

|**トラフィック**|**開始**|**終了**|**送信元ポート**|**宛先ポート**|
|:--- |:--- |:--- |:--- |:--- |
|SIP や TLS|SIP プロキシ|SBC|1024-65535|SBC で定義されています。|
SIP や TLS|SBC|SIP プロキシ|SBC で定義されています。|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP シグナリングのフェイル オーバー ・ メカニズム

SBC では、sip.pstnhub.microsoft.com を解決するための DNS クエリを使用できます。 SBC の場所およびデータ センターのパフォーマンス測定値に基づき、プライマリ データ センターが選択されています。 SBC が、最後の FQDN (を再試行する場合は、プライマリ データ センターには、問題が発生した、SBC は、sip2.pstnhub.microsoft.com は、2 番目の割り当てられているデータ センターに解決して、まれなケースでそのデータ センターの 2 つの領域では使用できません、sip3.pstnhub.microsoft.com)、3 番目のデータ センターの ip アドレスを提供します。

次の表は、プライマリ、セカンダリ、および第 3 のデータ センター間の関係をまとめたものです。

|**プライマリ データ センターの場合**|**EMEA**|**NOAM**|**アジア**|
|:--- |:--- |:--- |:--- |
|セカンダリ ・ データ ・ センター (sip2.pstnhub.microsoft.com)|ご|EU|ご|
|第 3 データ センター (sip3.pstnhub.microsoft.com)|アジア|アジア|EU|
|||||

## <a name="media-traffic-port-ranges"></a>メディア トラフィック: ポートの範囲

メディア トラフィックは、マイクロソフトのクラウド内の個別のサービスとの間をフローします。 メディア トラフィック用の IP の範囲。
- 52.112.0.0/14 (IP アドレス 52.112.0.1 から 52.115.255.254 に)。

メディア プロセッサのポートの範囲は、次の表で示されます。 

|**トラフィック**|**開始**|**終了**|**送信元ポート**|**宛先ポート**|
|:--- |:--- |:--- |:--- |:--- |
|UDP または SRTP|メディア プロセッサ|SBC|49 152 – 53 247|SBC で定義されています。|
|UDP または SRTP|SBC|メディア プロセッサ|SBC で定義されています。|49 152 – 53 247|
|

  > [!NOTE]
  > SBC の同時呼び出しごとに少なくとも 2 つのポートをお勧めします。

## <a name="media-traffic-codecs"></a>メディア トラフィック: コーデック

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC とクラウド メディア プロセッサ、またはマイクロソフトのチームのクライアントとの間のレグです。
メディア バイ パスの場合と非バイパスの場合の両方に適用されます。

レグ セッション ボーダー コント ローラーとメディアのバイパス) を付けずにクラウド メディア プロセッサとの間やチームのクライアントとメディアのバイパスが有効な場合)、SBC との間で直接ルーティング インターフェイスには、以下のコーデックを使用できます。
- 非メディア (SBC クラウド メディア プロセッサ) を使用しない: 絹、G.711、G.722, G, 729
- メディアのバイパス (チームのクライアントに SBC): 絹、G.711、G.722, G, 729、著作

セッション ボーダー コント ローラーの特定のコーデックの使用を強制するには、申し出リストから不要なコーデックを除きます。

### <a name="leg-between-microsoft-teams-client--and-cloud-media-processor"></a>マイクロソフト チームのクライアントとクラウド メディア プロセッサとの間の区間
適用されるメディアではないが大文字と小文字のみを使用しません。 チームのクライアントとの間で直接メディア フローをメディア バイ パスで

クラウド メディア プロセッサとマイクロソフトのチームのクライアントとの間の区間に絹または G.722 のいずれかが使用されます。 マイクロソフトのアルゴリズムは、複数のパラメーターを考慮に基づくこの区間のコーデックを選択します。 


## <a name="supported-session-border-controllers-sbcs"></a>セッション ボーダー コント ローラー (SBCs) のサポート

マイクロソフトでは、直接ルーティングとペアにする認定の SBCs のみサポートします。 エンタープライズ VoIP は企業にとって重要であるため、マイクロソフトでは、集中的なテストを実行を選択した SBCs と、2 つのシステムを確実に SBC ベンダーとの連携は互換性があります。 

検証済みのデバイスは、チームの直接のルーティングのための認定として表示されます。 認定済みのデバイスは、すべてのシナリオで動作が保証されます。 

SBCs のサポートの詳細については、[リストのセッション ボーダー コント ローラーが直接ルーティングの認定](direct-routing-border-controllers.md)を参照してください。

 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを構成する](direct-routing-configure.md)



