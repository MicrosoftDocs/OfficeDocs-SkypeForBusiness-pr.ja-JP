---
title: 直接ルーティングのローカル メディアの最適化
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接ルーティング用にローカル メディアの最適化を構成する
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576989"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>直接ルーティング用にローカル メディアの最適化を構成する

ローカル メディア最適化の構成は、ルーティングや動的緊急通話などの他のクラウド音声機能に共通Location-Based設定に基づいて行います。 ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネット、信頼済み IP アドレスの詳細については、「クラウド音声機能のネットワーク設定」 [を参照してください](cloud-voice-network-settings.md)。

ローカル メディアの最適化を構成する前に、「直接ルーティングのための [ローカル メディアの最適化」を参照してください](direct-routing-media-optimization.md)。  

ローカル メディアの最適化を構成するには、次の手順が必要です。 管理センターまたは PowerShell Teamsを使用できます。 詳細については、「ネットワーク トポロジ [の管理」を参照してください](manage-your-network-topology.md)。

1. ユーザーと SBC サイトを構成します (この記事で説明します)。
2. (SBC ベンダーの仕様に従って) ローカル メディアの最適化用に SBC を構成します。

次の図は、この記事全体の例で使用されるネットワーク セットアップを示しています。

![例のネットワークセットアップを示す図](media/direct-routing-media-op-9.png "例のネットワークセットアップ")


## <a name="configure-the-user-and-the-sbc-sites"></a>ユーザーと SBC サイトを構成する

ユーザーと SBC サイトを構成するには、次の手順を実行する必要があります。

1. [外部の信頼できる IP アドレスを管理します](#manage-external-trusted-ip-addresses)。  

2. [ネットワーク リージョン、ネットワーク サイト](#define-the-network-topology) 、ネットワーク サブネットを構成して、ネットワーク トポロジを定義します。

3. [関連するモードとプロキシ](#define-the-virtual-network-topology) SBC 値を使用して SBC をサイトに割り当て、仮想ネットワーク トポロジを定義します。


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>SBC ベンダーの仕様に従ってローカル メディアの最適化用に SBC を構成する

この記事では、Microsoft コンポーネントの構成について説明します。 SBC 構成については、SBC ベンダーのドキュメントを参照してください。

ローカル メディアの最適化は、次の SBC ベンダーによってサポートされています。

| 仕入先 | Product |    ソフトウェアのバージョン |
|:------------|:-------|:-------|
| [AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.256 | 
|            |  Mediant 2600 SBC |  7.20A.256 | 
|            |  Mediant 4000 SBC |  7.20A.256 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.256 | 
|            |  Mediant Virtual Edition SBC |   7.20A.256 | 
|            |  Mediant Cloud Edition SBC | 7.20A.256 |
| [リボン SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [リボン SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>外部の信頼済み IP アドレスを管理する

外部の信頼できる IPs は、エンタープライズ ネットワークのインターネット外部の IPS です。 これらの IP は、クライアントがクライアントに接続するときにMicrosoft Teamsによって使用される IP アドレスMicrosoft 365。 ローカル メディアの最適化を使用するユーザーがいるサイトごとに、これらの外部 IPs を追加する必要があります。

各サイトのパブリック IP アドレスを追加するには、次のコマンドレットNew-CsTenantTrustedIPAddressします。 テナントの信頼できる IP アドレスの数に制限はありません。 IPv4 アドレスと IPv6 Microsoft 365外部 IP アドレスが両方とも表示される場合は、両方の種類の IP アドレスを追加する必要があります。 IPv4 の場合は、マスク 32 を使用します。 IPv6 の場合は、マスク 128 を使用します。 コマンドレットで異なる MaskBits を指定することで、個々の外部 IP アドレスと外部 IP サブネットの両方を追加できます。

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


信頼できる IP アドレスの追加の例。

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>ネットワーク トポロジを定義する

このセクションでは、ネットワーク トポロジのネットワーク リージョン、ネットワーク サイト、ネットワーク サブネットを定義する方法について説明します。

すべてのパラメーターでは大文字と小文字が区別されます。そのため、セットアップ時に使用したのと同じ大文字と小文字を必ず使用する必要があります。  (たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は異なるサイトとして扱います)。

### <a name="define-network-regions"></a>ネットワーク リージョンを定義する

ネットワーク リージョンを定義するには、次のコマンドレットNew-CsTenantNetworkRegionします。 RegionID パラメーターは、リージョンの地理を表す論理名であり、依存関係や制限はありません。 CentralSite パラメーター <site ID> は省略可能です。

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

次の例では、APAC という名前のネットワーク リージョンを作成します。

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>ネットワーク サイトを定義する

ネットワーク サイトを定義するには、次のコマンドレットNew-CsTenantNetworkSiteします。 各ネットワーク サイトは、ネットワーク リージョンに関連付けられている必要があります。

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

次の例では、APAC リージョンに 3 つの新しいネットワーク サイト (ベトナム、インドネシア、シンガポール) を作成します。

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>ネットワーク サブネットを定義する

ネットワーク サブネットを定義し、ネットワーク サイトに関連付けるには、次のコマンドレットNew-CsTenantNetworkSubnetします。 各ネットワーク サブネットは、1 つのサイトにのみ関連付けできます。 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

次の例では、3 つのネットワーク サブネットを定義し、3 つのネットワーク サイト (ベトナム、インドネシア、シンガポール) に関連付けします。

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>仮想ネットワーク トポロジを定義する 

最初に、テナント管理者は、 コマンドレットを使用して、関連する SBC ごとに新しい SBC New-CsOnlinePSTNGatewayします。
テナント管理者は、次のコマンドレットを使用して PSTN ゲートウェイ オブジェクトのネットワーク サイトを指定することで、仮想ネットワーク トポロジSet-CsOnlinePSTNGatewayします。

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

次の点に注意してください。 
   - 顧客が 1 つの SBC を持っている場合、-ProxySBC パラメーターは必須の $null または SBC FQDN 値である必要があります (中央 SBC と一元化されたトランクのシナリオ)。
   - ローカル メディアの最適化をサポートするには、-MediaBypass パラメーターを $true に設定する必要があります。
   - SBC に -BypassMode パラメーターが設定されていない場合、X-MS ヘッダーは送信されません。 
   - すべてのパラメーターでは大文字と小文字が区別されます。そのため、セットアップ時に使用したのと同じ大文字と小文字を必ず使用する必要があります。  (たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は異なるサイトとして扱います)。

次の例では、モード Always bypass を使用して、APAC リージョンのベトナム、インドネシア、シンガポールのネットワーク サイトに 3 つの SBC を追加します。

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

注: ローカル メディアの最適化と Location-Based ルーティング (LBR) が同時に構成されている場合に中断されない操作を確実に行う場合は、ダウンストリーム SBC ごとに GatewaySiteLbrEnabled パラメーターを $true に設定して、LBR に対してダウンストリーム SBC を有効にする必要があります。 (この設定は、プロキシ SBC では必須ではありません)。

上記の情報に基づいて、直接ルーティングには、次の表に示すように、SIP 招待と再招待に対する 3 つの独自の SIP ヘッダーが含まれます。

BypassMode が定義されている場合は、「招待時の直接ルーティング」および「Re-Invites X-MS ヘッダー」で紹介されています。

| ヘッダー名 | 値 | 注釈 | 
|:------------|:-------|:-------|
| X-MS-UserLocation | internal/external | ユーザーが内部か外部かを示します。 |
| 要求 URI INVITE SIP: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | SBC が直接ルーティングに直接接続されていない場合でも、呼び出しの対象となる FQDN |
| X-MS-MediaPath | 例: proxysbc.contoso.com、VNsbc.contoso.com | ユーザーとターゲット SBC の間のメディア パスに使用する必要がある SBC の順序。 最後の SBC は常に最後です |
| X-MS-UserSite | usersiteID | テナント管理者によって定義された文字列 |

## <a name="call-flows"></a>呼び出しフロー 

2 つのモードの呼び出しフローを次に示します。

- [Always Bypass](#always-bypass-mode)
- [ローカル ユーザーの場合のみ](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>常にバイパス モード

Always Bypass モードは、構成する最も簡単なオプションです。 すべての SBC に任意のサイトから到達可能な場合、テナント管理者は、すべてのユーザーと SBC に対して 1 つのサイトを構成できます。

例では、次のシナリオの Always バイパス モードを示します。

- [発信呼び出しとユーザーが SBC と同じ場所にある](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [受信呼び出しとユーザーが SBC と同じ場所にある](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [発信呼び出しとユーザーが外部](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [受信呼び出しとユーザーが外部](#inbound-calls-and-the-user-is-external-with-always-bypass)

次の表は、例で使用されている FQDN と IP アドレスを示しています。

| FQDN | SBC 外部 IP アドレス | SBC 内部 IP アドレス | 内部サブネット | 場所 | 外部 NAT (信頼済み IP) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | なし | 192.168.1.5 | 192.168.1.0/24 | ベトナム | 172.16.240.110 |
| IDsbc.contoso.com | なし | 192.168.2.5 | 192.168.2.0/24 | インドネシア | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | シンガポール | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>発信呼び出しとユーザーが Always Bypass を使用する SBC と同じ場所にある

| モード |    ユーザー |  場所 |  通話の方向 |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    内部 |  SBC と同じサイト |  発信 |

次の表は、エンド ユーザーの構成とアクションを示しています。

| ユーザーの物理的な場所| ユーザーが番号に対して通話を行う、または番号から通話を受信する | ユーザーの電話番号  | オンライン音声ルーティング ポリシー | SBC 用に構成されたモード |
|:------------|:-------|:-------|:-------|:-------|
| ベトナム | +84 4 3926 3000 | +84 4 5555 5555   | 優先度 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> 優先度 2: .* - proxysbc.contoso.com   | VNsbc.contoso.com – Always Bypass <br> proxysbc.contoso.com – 常にバイパス


次の図は、Always バイパス モードの発信呼び出しの SIP ラダーと、SBC と同じ場所のユーザーを示しています。

![発信呼び出しを示す図](media/direct-routing-media-op-10.png "発信呼び出し")

次の表は、ダイレクト ルーティングによって送信される X-MS ヘッダーを示しています。

| パラメーター | 説明 |
|:------------|:-------|
| 招待 + 8443926300@VNsbc.contoso.com | オンライン音声ルーティング ポリシーで定義されている SBC のターゲット FQDN は、要求 URI で送信されます。 | 
| X-MS-UserLocation: internal | フィールドは、ユーザーが企業ネットワーク内に位置する |
| X-MS-MediaPath: VNsbc.contoso.com |   クライアントがターゲット SBC に走査する必要がある SBC を指定します。 この場合は Always Bypass を使用し、クライアントはヘッダー内の唯一の名前として送信されるターゲット名の内部です。 | 
|X-MS-UserSite: ベトナム |   ユーザーが位置するサイト内で示されるフィールド。 |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>着信呼び出しとユーザーが Always Bypass を使用する SBC と同じ場所にある

| モード |    ユーザー |  場所 |  通話の方向 |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    内部 | SBC と同じサイト | 受信 |


受信呼び出しでは、ユーザーの場所は不明であり、SBC はユーザーの場所を推測する必要があります。 推測が正しくない場合は、再招待が必要になります。 このケースでは、ユーザーが内部的であり、メディアが直接フローできると想定され、それ以上のアクションは必要ありません (再招待)。
ダイレクト ルーティング サービスに接続されている SBC は、元の SBC の場所を報告します。この場合は、[Record-Route] フィールドを指定します。 これらのフィールドに基づいて、メディア パスは直接ルーティングによって計算されます。

注: ユーザーが複数のエンドポイントを持つ場合、183 はサポートできません。 この場合、ダイレクト ルーティングでは常に 180 リングが使用されます。 

次の図は、AlwaysBypass モードでの着信呼び出しの SIP ラダーを示しています。ユーザーは SBC と同じ場所にいます。

![SIP ラダーを示す図](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>発信呼び出しとユーザーが Always Bypass を使用して外部に

| モード |    ユーザー |  サイト |  通話の方向
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  該当なし | 発信 |


次の図は、AlwaysBypass モードの発信呼び出しの SIP ラダーを示しています。ユーザーは外部です。

![SIP ラダーを示す図](media/direct-routing-media-op-12.png)

次の表は、ダイレクト ルーティング サービスによって送信される X-MS ヘッダーを示しています。

| パラメーター |   説明 |
|:------------|:-------|
|招待 + 8443926300@VNsbc.contoso.com | オンライン音声ルーティング ポリシーで定義されている SBC のターゲット FQDN は、要求 URI で送信されます。|
| X-MS-UserLocation: external | フィールドは、ユーザーが企業ネットワークの外部に位置する必要があります。 |
| X-MS-MediaPath: proxysbc.contoso.com、VNsbc.contoso.com    | クライアントがターゲット SBC に走査する必要がある SBC を指定します。 この場合は Always Bypass が使用され、クライアントは外部であるためです。 |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>着信呼び出しとユーザーが Always Bypass を使用して外部に

| モード | ユーザー | サイト |  通話の方向 |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  該当なし |   受信 |

着信呼び出しの場合、ユーザーの場所が外部にある場合、ダイレクト ルーティングに接続されている SBC は再招待を送信する必要があります (既定では、ローカル メディア候補は常に提供されます)。  X-MediaPath は、指定された SBC Record-Routeに基づいて計算されます。

次の図は、AlwaysBypass モードの着信呼び出しの SIP ラダーを示しています。ユーザーは外部です。

![SIP ラダーを示す図](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>ローカル ユーザー モードの場合のみ

ターゲット SBC のローカル メディア候補は、ユーザーが SBC と同じ場所にある場合にのみ提供されます。 それ以外のすべての場合、メディアはプロキシ SBC の内部 IP または外部 IP を経由します。

次のシナリオについて説明します。

- [発信呼び出しとユーザーが SBC と同じ場所にある](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [受信呼び出しとユーザーが SBC と同じ場所にある](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [ユーザーが SBC と同じ場所ではなく、企業ネットワーク内にある](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [受信呼び出しとユーザーは内部的ですが、SBC と同じ場所ではありません](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

次の表は、エンド ユーザーの構成とアクションを示しています。

| ユーザーの物理的な場所 |  ユーザーが番号に対して通話を行う、または番号から通話を受信する |  ユーザーの電話番号 | オンライン音声ルーティング ポリシー |   SBC 用に構成されたモード |
|:------------|:-------|:-------|:-------|:-------|
| ベトナム | +84 4 3926 3000 |  +84 4 5555 5555 | 優先度 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> 優先度 2: .* - proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>発信呼び出しとユーザーが SBC と同じ場所にある (ローカル ユーザーの場合のみ)

| モード | ユーザー | サイト | 通話の方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   内部 |SBC と同じ   | 発信 |

次の図は、OnlyForLocalUsers モードの発信呼び出しを示しています。ユーザーは SBC と同じ場所にいます。 これは、ユーザーが SBC と同じ場所にある場合の送信呼び出しに [表示されるのと同じフローです](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。

![SIP ラダーを示す図](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>受信呼び出しとユーザーが SBC と同じ場所にいて、ローカル ユーザーの場合のみ

| モード | ユーザー | サイト | 通話の方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   内部 | SBC と同じ | 受信 |

次の図は、OnlyForLocalUsers モードの受信呼び出しを示しています。ユーザーは SBC と同じ場所にいます。 これは、ユーザーが SBC と同じ場所にある場合の受信呼び出しで示されている [のと同じフローです](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。

![SIP ラダーを示す図](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>ユーザーは SBC と同じ場所ではなく、ローカル ユーザーの場合のみと企業ネットワーク内にある

| モード | ユーザー | サイト |通話の方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | 内部 |   SBC とは異なる | 発信 |

ダイレクト ルーティングは、SBC で構成されたユーザーとモードの報告された場所に基づいて X-MediaPath を計算します。


次の図は、OnlyForLocalUsers モードの送信呼び出しと、SBC と同じ場所にいない内部ユーザーを示しています。

![SIP ラダーを示す図](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>受信呼び出しとユーザーは内部的ですが、ローカル ユーザーの場合のみ SBC と同じ場所ではありません

| モード |    ユーザー |  サイト |  通話の方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | 内部 |    SBC とは異なる |    受信 |

次の図は、OnlyForLocalUsers モードでの受信呼び出しと、SBC と同じ場所にない内部ユーザーを示しています。

![SIP ラダーを示す図](media/direct-routing-media-op-17.png)









