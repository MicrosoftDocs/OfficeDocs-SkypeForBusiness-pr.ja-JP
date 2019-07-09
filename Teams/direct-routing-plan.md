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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: このトピックでは、Microsoft Phone システムのダイレクトルーティングを使用して、サポートされているユーザーが指定したセッションボーダーコントローラー (SBC) を Microsoft 電話システムに接続する方法について説明します。
ms.openlocfilehash: 06a5764cc0dd022f1a3077e9b00580a3dc95bfe9
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588200"
---
# <a name="plan-direct-routing"></a>ダイレクト ルーティングを計画する

> [!Tip]
> ダイレクトルーティングの利点、計画方法、展開方法については、次のセッションをご覧ください。 [Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)

Microsoft Phone システムのダイレクトルーティングでは、サポートされている、ユーザーが指定したセッションボーダーコントローラー (SBC) を Microsoft 電話システムに接続することができます。  たとえば、次の図に示すように、この機能を使用して、Microsoft Teams クライアントとオンプレミスの PSTN 接続を構成できます。 

![オンプレミスの PSTN 接続の構成を示す図](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft Teams クライアントとのオンプレミス PSTN 接続の構成")

  > [!NOTE]
  > Skype for Business Online では、お客様が指定した SBC をペアリングすることもできますが、これには、SBC と Microsoft Cloud の間に、オンプレミスの Skype for business Server を展開するか、クラウドコネクタと呼ばれる特別なエディションの Skype for Business を使用する必要があります。 このシナリオは、ハイブリッドボイスと呼ばれています。 一方、直接ルーティングでは、サポートされている SBC と Microsoft Cloud の間で直接接続できます。 

ダイレクトルーティングを使用すると、SBC をほとんどすべてのテレフォニートランクや、サードパーティ公衆交換電話網 (PSTN) 機器と接続できます。 ダイレクトルーティングでは、次のことができます。 

- Microsoft 電話システムでは、ほぼすべての PSTN トランクを使用できます。 
- サードパーティの構内交換機 (PBX)、アナログデバイス、Microsoft 電話システムなど、ユーザーが所有するテレフォニー機器の間の相互運用性を構成します。

また、Microsoft は、プランなどのクラウド間のボイスソリューションも提供しています。  ただし、次の場合には、ハイブリッドボイスソリューションが組織にとって最適な場合があります。 

- Microsoft 通話プランは、お住まいの国ではご利用になれません。 
- 組織では、サードパーティのアナログデバイス、コールセンターなどへの接続が必要です。 
- 組織には、PSTN キャリアを使った既存の契約があります。

また、直接ルーティングでは、Microsoft 通話プランの追加ライセンスを所有しているユーザーもサポートされます。 詳細については、「[電話システムと通話プラン](calling-plan-landing-page.md)」を参照してください。 

ダイレクトルーティングでは、ユーザーがスケジュールされた電話会議に参加するときに、ダイヤルイン番号は Microsoft 電話会議サービスによって提供されます。これには、適切なライセンスが必要です。  ダイヤルアウトの場合、Microsoft 電話会議サービスは、適切なライセンスが必要なオンライン通話機能を使用して通話を発信します。 (ダイヤルアウトでは、直接ルーティングによるルーティングが行われないことに注意してください)。詳細については、「[チームとのオンライン会議](https://products.office.com/microsoft-teams/online-meeting-solutions)」を参照してください。 
 
直接ルーティングの展開を計画することは、実装を成功させるための鍵となります。 この記事では、インフラストラクチャとライセンスの要件について説明し、SBC 接続に関する情報を提供します。 

- [インフラストラクチャの要件](#infrastructure-requirements)
- [ライセンスおよびその他の要件](#licensing-and-other-requirements)
- [SBC ドメイン名](#sbc-domain-names)
- [SBC 用の公開された信頼できる証明書](#public-trusted-certificate-for-the-sbc)
- [SIP シグナリング: Fqdn とファイアウォールのポート](#sip-signaling-fqdns-and-firewall-ports)
- [メディアトラフィック: ポート範囲](#media-traffic-port-ranges)
- [サポートされている SBCs](#supported-session-border-controllers-sbcs)

直接ルーティングの構成の詳細については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件
直接ルーティングを展開するためにサポートされている SBCs、ドメイン、およびその他のネットワーク接続要件のインフラストラクチャ要件を次の表に示します。  

|**インフラストラクチャの要件**|**次のものが必要です**|
|:--- |:--- |
|セッションボーダーコントローラー (SBC)|サポートされている SBC。 詳細については、「[サポートされる SBCs](#supported-session-border-controllers-sbcs)」を参照してください。|
|SBC に接続されたテレフォニー trunks|SBC に接続されている1つ以上のテレフォニー trunks。 一方の端では、SBC は直接ルーティングを介して Microsoft 電話システムに接続します。 SBC は、Pbx、アナログテレフォニーアダプターなどのサードパーティ製のテレフォニーエンティティにも接続できます。 SBC に接続された PSTN 接続オプションは動作します。 (注: PSTN trunks を SBC に構成するには、SBC ベンダーまたはトランクプロバイダを参照してください。)|
|Office 365 テナント|Microsoft Teams ユーザーのホームに使用する Office 365 テナント、および SBC への構成と接続。|
|ユーザーレジストラー|ユーザーは、Office 365 に所属している必要があります。<br/>会社に Office 365 へのハイブリッド接続を備えたオンプレミスの Skype for Business または Lync 環境がある場合は、オンプレミスのユーザーに対して Teams でボイスを有効にすることはできません。<br/><br/>ユーザーのレジストラーを確認するには、次の Skype for Business Online PowerShell コマンドレットを使用します。<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>コマンドレットの出力は、次のように表示されます。<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domains|1つまたは複数のドメインが Office 365 テナントに追加されている。<br/><br/>**注:** テナント用に自動的に作成される既定のドメイン * onmicrosoft.com を使用することはできません。<br/><br/>ドメインを表示するには、次の Skype for Business Online PowerShell コマンドレットを使用できます。<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>ドメインと Office 365 テナントの詳細については、「ドメインに関する[FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)」を参照してください。|
|SBC のパブリック IP アドレス|SBC への接続に使用できるパブリック IP アドレス。 Sbc は、SBC の種類に基づいて NAT を使うことができます。|
|SBC の完全修飾ドメイン名 (FQDN)|SBC の FQDN。 FQDN のドメイン部分は、Office 365 テナントで登録されているドメインの1つです。 詳細については、「 [SBC ドメイン名](#sbc-domain-names)」を参照してください。|
|SBC のパブリック DNS エントリ |SBC FQDN をパブリック IP アドレスにマッピングするパブリック DNS エントリ。 |
|SBC 用の公開された信頼できる証明書 |直接ルーティングを使用するすべての通信に使用する SBC の証明書。 詳細については、「 [SBC 用の公開された信頼できる証明書](#public-trusted-certificate-for-the-sbc)」を参照してください。|
|直接ルーティングの接続ポイント |直接ルーティングの接続ポイントは、次の3つの Fqdn です。<br/><br/>`sip.pstnhub.microsoft.com`–グローバル FQDN を最初に試す必要があります。<br/>`sip2.pstnhub.microsoft.com`–セカンダリ FQDN、地理的には2番目の優先度の地域にマップされます。<br/>`sip3.pstnhub.microsoft.com`–第3の優先度の領域に地理的にマップされています。<br/><br/>構成の要件については、「 [SIP シグナリング: fqdn とファイアウォールポート](#sip-signaling-fqdns-and-firewall-ports)」を参照してください。|
|ダイレクトルーティングメディアのファイアウォールの IP アドレスとポート |SBC は、クラウドの次のサービスに通信します。<br/><br/>SIP プロキシ: 信号を処理します。<br/>メディアプロセッサ: メディアのバイパスがオンになっている場合を除き、メディアを処理します。<br/><br/>この2つのサービスは、このドキュメントの後半で説明するように、Microsoft Cloud で個別の IP アドレスを持ちます。<br/><br/>詳細については、「 [Office 365 の url と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」の「 [Microsoft Teams」セクション](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を参照してください。 |
|メディアトランスポートプロファイル|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams メディアのファイアウォールの IP アドレスとポート |詳細については、「 [Office 365 の url と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」を参照してください。 |
|||

## <a name="licensing-and-other-requirements"></a>ライセンスおよびその他の要件 

直接ルーティングのユーザーには、Office 365 で次のライセンスが割り当てられている必要があります。 

- Microsoft 電話システム 
- Microsoft Teams 
- Microsoft 電話会議 

> [!NOTE]
> 1:1 通話からエスカレーションする場合は、電話会議のライセンスが必要です。

> [!IMPORTANT]
>  スケジュールされた会議に外部の参加者を追加したい場合は、電話会議のライセンスが*必要*です。また、ダイヤルイン番号を提供することによって、その会議に外部参加者を追加することもできます。

> [!NOTE]
> E5 ライセンスには、電話システムと電話会議の両方が含まれています。   

さらに、次のことを確認する必要があります。
 
- CsOnlineVoiceRoutingPolicy がユーザーに割り当てられます。 
- [プライベート通話を許可する] は、Microsoft Teams のテナントレベルで有効にします。 

また、直接ルーティングは、Microsoft 通話プランのライセンスが付与されているユーザーもサポートします。 通話プランを使用する Microsoft 電話システムでは、一部の通話を直接ルーティングインターフェイスを使ってルーティングできます。 ただし、ユーザーの電話番号は、オンラインで入手するか、Microsoft に移植する必要があります。  

同じユーザーに対して、通話プランと直接ルーティング接続の混在は任意ですが、たとえば、ユーザーに Microsoft 通話プランが割り当てられていて、SBC 経由で一部の通話をルーティングする必要がある場合などに役立ちます。 最も一般的なシナリオの1つは、サードパーティ Pbx への通話です。  サードパーティの Pbx では、その Pbx に接続された電話を除くすべての通話が Microsoft の通話プランによってルーティングされます。ただし、サードパーティ Pbx に接続されている電話への通話は SBC にアクセスするため、PSTN には関係なく、企業ネットワーク内にとどまります。 

電話システムのライセンスの詳細については、「office 365 および[office 365 プランのオプション](https://technet.microsoft.com/library/office-365-plan-options.aspx)[を使用して office を最大限に活用する](https://products.office.com/compare-all-microsoft-office-products?tab=2)」を参照してください。 

電話システムのライセンスの詳細については、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。 

## <a name="sbc-domain-names"></a>SBC ドメイン名

SBC ドメイン名は、テナントの "Domains" に登録されている名前のいずれかである必要があります。 Onmicrosoft.com テナントを SBC の FQDN 名として使用することはできません。

次の表は、テナントに登録されている DNS 名の例を示しています。この名前は、SBC の FQDN として使用できるかどうか、有効な FQDN 名の例です。

|**DNS 名**|**SBC FQDN に使用できます**|**FQDN 名の例**|
|:--- |:--- |:--- |
contoso.com|はい|**有効な名前:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|いいえ|<br/>Onmicrosoft.com ドメインを使用する場合、SBC 名はサポートされません。

新しいドメイン名を使用することを前提としています。 たとえば、テナントには、テナントに登録されているドメイン名として contoso.com があるため、sbc1.sip.contoso.com を使用します。 SBC という名前の sbc1.sip.contoso.com を組み合わせるには、その前に、テナントの "Domains" にドメイン名 sip.contoso.com を登録する必要があります。 ドメイン名を登録する前に、sbc1.sip.contoso.com と SBC をペアリングしようとすると、次のエラーメッセージが表示されます: "sbc1.sip.contoso.com" ドメインはこのテナント用に構成されていないため、使用できません。 "
ドメイン名を追加したら、UPN user@sip.contoso.com でユーザーを作成して、"Teams" ライセンスを割り当てる必要もあります。 ドメイン名がテナントの "Domains" に追加された後は、最大24時間かかる場合があります。新しい名前を持つユーザーが作成され、ライセンスがユーザーに割り当てられます。 

1つのテナントに複数の SIP アドレス空間がある場合もあります。 たとえば、会社が SIP アドレススペースとして contoso.com を持ち、2番目の SIP アドレススペースとして fabrikam.com を持っているとします。 一部のユーザーには住所 user@contoso.com があり、一部のユーザーは住所 user@fabrikam.com を使用しています。 

SBC には1つの FQDN しか必要ありません。ペアリングされたテナント内の任意のアドレス空間のユーザーを処理することができます。 たとえば、sbc1.contoso.com という名前の SBC は、同じテナントに SIP アドレススペースが登録されていれば、アドレス user@contoso.com と user@fabrikam.com を持つユーザーの PSTN トラフィックを受信して送信することができます。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC 用の公開された信頼できる証明書

Microsoft は、認定署名要求 (CSR) を生成して、SBC の証明書を要求することを強くお勧めします。 SBC の CSR を生成するための具体的な手順については、SBC ベンダーから提供されている相互接続の手順またはドキュメントを参照してください。 

  > [!NOTE]
  > ほとんどの証明機関 (Ca) では、秘密キーのサイズを2048以上にする必要があります。 CSR を生成するときは、この点に注意してください。

証明書は、subject、common name、またはサブジェクトの代替名の各フィールドに SBC FQDN を設定する必要があります。

または、ダイレクトルーティングは SAN のワイルドカードをサポートしており、ワイルドカードは[TLS 経由の標準 RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)に準拠している必要があります。 例としては、SAN で *. contoso.com を使います。これは、SBC FQDN sbc.contoso.com と一致しますが、sbc.test.contoso.com とは一致しません。

証明書は、次のルート証明機関のいずれかによって生成される必要があります。

- AffirmTrust
- AddTrust 外部 CA ルート
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- Class 3 パブリックプライマリ証明機関
- Comodo のセキュリティで保護されたルート CA
- ドイツのテレタイプ 
- DigiCert グローバルルート CA
- DigiCert 高保証 EV ルート CA
- Entrust
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign、Inc. 
- Starfield 
- シマンテック Enterprise Mobile Root for Microsoft 
- SwissSign
- Thawte のタイムスタンプ CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (ドイツのテレ・ Om)
- QuoVadis

Microsoft は、お客様のリクエストに基づく追加の証明機関の追加に取り組んでいます。 

## <a name="sip-signaling-fqdns-and-firewall-ports"></a>SIP シグナリング: Fqdn とファイアウォールのポート 

直接ルーティングの接続ポイントは、次の3つの Fqdn です。

- **sip.pstnhub.microsoft.com** –グローバル FQDN –最初に試す必要があります。 SBC がこの名前を解決するための要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure datacenter をポイントしている IP アドレスを返します。 課題は、データセンターのパフォーマンスメトリックと SBC への地理的な距離に基づいています。 返される IP アドレスは、プライマリ FQDN に対応しています。
- **sip2.pstnhub.microsoft.com** –セカンダリ FQDN –地理的に2番目の優先度の地域にマップされます。
- **sip3.pstnhub.microsoft.com** –第3の FQDN –地理的に3番目の優先度の地域にマップされます。

これら3つの Fqdn を順番に配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込みが少なく、最初の FQDN を照会することによって割り当てられた SBC データセンターに最も近い)。
- SBC からの接続が一時的な問題が発生しているデータセンターに確立されている場合は、フェールオーバーを行います。 詳細については、以下の「[フェールオーバーのメカニズム](#failover-mechanism-for-sip-signaling)」をご覧ください。  

Fqdn – sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.com –次のいずれかの IP アドレスに解決されます。

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip-all.pstnhub.microsoft.com は上記のすべての IP アドレスに解決されます。  次のポートを使用する必要があります。

|**通過**|**開始**|**終了**|**送信元ポート**|**宛先ポート**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP プロキシ|SBC|1024–65535|SBC で定義|
SIP/TLS|SBC|SIP プロキシ|SBC で定義|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP シグナリングのフェイルオーバーメカニズム

SBC は、sip.pstnhub.microsoft.com を解決する DNS クエリを行います。 SBC の場所とデータセンターのパフォーマンスの指標に基づいて、プライマリデータセンターが選択されます。 プライマリデータセンターで問題が発生した場合、SBC は sip2.pstnhub.microsoft.com を試みます。この場合、2つ目の領域にあるデータセンターは使用できないため、SBC は最後の FQDN をリトライします (sip3.pstnhub.microsoft.com)。第3の datacenter IP を提供します。

次の表は、プライマリデータセンターと第2データセンター間の関係をまとめたものです。

|**プライマリデータセンターの場合**|**EMEA**|**NOAM**|**北部**|
|:--- |:--- |:--- |:--- |
|セカンダリデータセンター (sip2.pstnhub.microsoft.com)|プロセッサー|ヨーロッパ|プロセッサー|
|第3のデータセンター (sip3.pstnhub.microsoft.com)|北部|北部|ヨーロッパ|
|||||

## <a name="media-traffic-port-ranges"></a>メディアトラフィック: ポート範囲
注: メディアをバイパスせずにダイレクトルーティングを展開する場合は、以下の要件が適用されます。 メディアをバイパスするためのファイアウォール要件については、「[ダイレクトルーティングによるメディアバイパスの計画](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-plan-media-bypass)」を参照してください。

メディアトラフィックは、Microsoft Cloud の別のサービスとの間でフローします。 メディアトラフィックの IP 範囲:
- 52.112.0.0/14 (52.112.0.1 から52.115.255.254 に対する IP アドレス)。

メディアプロセッサのポート範囲は、次の表のように表示されます。 

|**通過**|**開始**|**終了**|**送信元ポート**|**宛先ポート**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|メディアプロセッサ|SBC|49 152 – 53 247|SBC で定義|
|UDP/SRTP|SBC|メディアプロセッサ|SBC で定義|49 152 – 53 247|
|

  > [!NOTE]
  > Microsoft は、SBC で同時呼び出しごとに少なくとも2つのポートをお勧めします。

## <a name="media-traffic-codecs"></a>メディアトラフィック: コーデック

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC と Cloud Media Processor または Microsoft Teams クライアント間の区間。
メディアバイパスのケースと非バイパスのケースの両方に適用されます

セッション境界コントローラーとクラウドメディアプロセッサ間 (メディアをバイパスしない場合)、または Teams クライアントと SBC (メディアバイパスを有効にしている場合) 間の直接ルーティングインターフェイスでは、次のコーデックを使用できます。
- メディア以外のバイパス (SBC から Cloud Media Processor): SILK、g、g.729、722、G、
- メディアのバイパス (SBC と Teams クライアント): SILK、722、g、g.729、OPUS

サービスの境界コントローラーで特定のコーデックを使うことができます。そのためには、プランから不要なコーデックを除外します。

### <a name="leg-between-microsoft-teams-client--and-cloud-media-processor"></a>Microsoft Teams クライアントとクラウドメディアプロセッサの間の区間
メディア以外のバイパスのケースにのみ適用されます。 Media では、Teams クライアントと SBC の間でメディアフローを直接バイパスします。

クラウドメディアプロセッサと Microsoft Teams クライアントの間の区間では、SILK または722が使用されています。 この区間での、複数のパラメーターを考慮した Microsoft アルゴリズムに基づくコーデックの選択肢。 


## <a name="supported-session-border-controllers-sbcs"></a>サポートされているセッション境界コントローラー (SBCs)

Microsoft は、認定された SBCs と直接ルーティングをサポートしています。 エンタープライズボイスは企業にとって重要であるため、Microsoft は選択された SBCs で集中的なテストを実行し、SBC ベンダーと協力して2つのシステムに互換性があることを確認します。 

検証されたデバイスは、Teams のダイレクトルーティングで認定されているものとして表示されます。 認定済みデバイスは、すべてのシナリオで動作することが保証されています。 

サポートされている SBCs の詳細については、「[直接ルーティング用に認定されたセッション境界コントローラーの一覧](direct-routing-border-controllers.md)」を参照してください。

 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを構成する](direct-routing-configure.md)



