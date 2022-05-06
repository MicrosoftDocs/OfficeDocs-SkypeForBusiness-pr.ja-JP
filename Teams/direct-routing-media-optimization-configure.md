---
title: ダイレクト ルーティング用のローカル メディアの最適化を構成する
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
description: ダイレクト ルーティング用のローカル メディアの最適化を構成する
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59524c620525505b9fcc19d909f5b4b84cc60720
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356441"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>ダイレクト ルーティング用のローカル メディアの最適化を構成する

ローカル メディア最適化の構成は、Location-Based ルーティングや動的緊急通報など、他のクラウド音声機能に共通するネットワーク設定に基づいています。 ネットワークリージョン、ネットワーク サイト、ネットワーク サブネット、信頼された IP アドレスの詳細については、「 [クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。

ローカル メディアの最適化を構成する前に、「 [ダイレクト ルーティングのローカル メディアの最適化」を](direct-routing-media-optimization.md)参照してください。  

ローカル メディアの最適化を構成するには、次の手順が必要です。 Teams管理センターまたは PowerShell を使用できます。 詳細については、「 [ネットワーク トポロジの管理」を参照してください](manage-your-network-topology.md)。

1. ユーザーと SBC サイトを構成します (この記事で説明します)。
2. ローカル メディア最適化用の SBC を構成します (SBC ベンダーの仕様に従います)。

次の図は、この記事全体の例で使用されるネットワーク設定を示しています。

> [!div class="mx-imgBorder"]
> ![例のネットワーク設定を示す図。](media/direct-routing-media-op-9.png "例のネットワーク設定")


## <a name="configure-the-user-and-the-sbc-sites"></a>ユーザーと SBC サイトを構成する

ユーザーと SBC サイトを構成するには、次の操作を行う必要があります。

1. [外部の信頼できる IP アドレスを管理します](#manage-external-trusted-ip-addresses)。  

2. [ネットワーク リージョン、ネットワーク サイト、およびネットワーク](#define-the-network-topology) サブネットを構成して、ネットワーク トポロジを定義します。

3. 関連するモードとプロキシ SBC 値を使用して SBC をサイトに割り当てることで[、仮想ネットワーク トポロジを定義](#define-the-virtual-network-topology)します。

> [!NOTE]
> ローカル メディアの最適化は、ダイレクト ルーティング (DR) セッション ボーダー コントローラー (SBC) 内部インターフェイスに到達する会社のネットワークに対する外部または内部として検出されるクライアントの場所に依存します。
> クライアント エンドポイントが顧客のネットワークの外部として検出された場合、クライアントが顧客のダイレクト ルーティング SBC の内部インターフェイスに到達できる場合でも、Microsoft は外部の場所を SBC に通知します。 ローカル メディア最適化を使用しているダイレクト ルーティングのお客様は、長時間の通話セットアップ時間が発生し、PSTN から通話を受信するときに音声が発生しない場合があります。
> これを回避するには、VPN 管理者はリモート VPN ユーザーとダイレクト ルーティング SBC 内部インターフェイス間のアクセスをブロックする必要があります。



## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>SBC ベンダーの仕様に従ってローカル メディア最適化用に SBC を構成する

この記事では、Microsoft コンポーネントの構成について説明します。 SBC の構成については、SBC ベンダーのドキュメントを参照してください。 どの SBC ベンダーがローカル メディアの最適化をサポートするかについては、「 [ダイレクト ルーティング用に認定されたセッション ボーダー コントローラー](direct-routing-border-controllers.md)」を参照してください。

## <a name="manage-external-trusted-ip-addresses"></a>外部信頼済み IP アドレスを管理する

外部信頼 IP は、エンタープライズ ネットワークのインターネット外部 IP です。 これらの IP は、Microsoft Teams クライアントがMicrosoft 365に接続するときに使用する IP アドレスです。 ローカル メディア最適化を使用しているユーザーがいるサイトごとに、これらの外部 IP を追加する必要があります。

各サイトのパブリック IP アドレスを追加するには、New-CsTenantTrustedIPAddress コマンドレットを使用します。 テナントに対して信頼できる IP アドレスの数を無制限に定義できます。 Microsoft 365によって表示される外部 IP が IPv4 アドレスと IPv6 アドレスの両方である場合は、両方の種類の IP アドレスを追加する必要があります。 IPv4 の場合は、マスク 32 を使用します。 IPv6 の場合は、mask 128 を使用します。 コマンドレットで異なる MaskBits を指定することで、個々の外部 IP アドレスと外部 IP サブネットの両方を追加できます。

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


信頼できる IP アドレスを追加する例。

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>ネットワーク トポロジを定義する

このセクションでは、ネットワーク トポロジのネットワーク リージョン、ネットワーク サイト、およびネットワーク サブネットを定義する方法について説明します。

すべてのパラメーターでは大文字と小文字が区別されるため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。  (たとえば、GatewaySiteID 値 "Vietnam" と "vietnam" は異なるサイトとして扱われます)。

### <a name="define-network-regions"></a>ネットワークリージョンを定義する

ネットワークリージョンを定義するには、New-CsTenantNetworkRegion コマンドレットを使用します。 RegionID パラメーターは、リージョンの地理を表す論理名であり、依存関係や制限はありません。 CentralSite `<site ID>` パラメーターは省略可能です。

```powershell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

次の例では、APAC という名前のネットワーク リージョンを作成します。

```powershell
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>ネットワーク サイトを定義する

ネットワーク サイトを定義するには、New-CsTenantNetworkSite コマンドレットを使用します。 各ネットワーク サイトは、ネットワーク リージョンに関連付けられている必要があります。

```powershell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

次の例では、APAC リージョンに 3 つの新しいネットワーク サイト (ベトナム、インドネシア、シンガポール) を作成します。

```powershell
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>ネットワーク サブネットを定義する

ネットワーク サブネットを定義し、それらをネットワーク サイトに関連付けるには、New-CsTenantNetworkSubnet コマンドレットを使用します。 各ネットワーク サブネットは、1 つのサイトにのみ関連付けることができます。 

```powershell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

次の例では、3 つのネットワーク サブネットを定義し、3 つのネットワーク サイト (ベトナム、インドネシア、シンガポール) に関連付けます。

```powershell
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>仮想ネットワーク トポロジを定義する 

最初に、テナント管理者は、New-CsOnlinePSTNGateway コマンドレットを使用して、関連する SBC ごとに新しい SBC 構成を作成します。
テナント管理者は、Set-CsOnlinePSTNGateway コマンドレットを使用して PSTN ゲートウェイ オブジェクトのネットワーク サイトを指定することで、仮想ネットワーク トポロジを定義します。

```powershell
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

次の点に注意してください。 
   - お客様が 1 つの SBC を持っている場合、-ProxySBC パラメーターは必須の$nullまたは SBC FQDN 値 (中央 SBC と一元化されたトランクシナリオ) である必要があります。
   - ローカル メディアの最適化をサポートするには、-MediaBypass パラメーターを $true に設定する必要があります。
   - SBC に -BypassMode パラメーターが設定されていない場合、X-MS ヘッダーは送信されません。 
   - すべてのパラメーターでは大文字と小文字が区別されるため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。  (たとえば、GatewaySiteID 値 "Vietnam" と "vietnam" は異なるサイトとして扱われます)。

次の例では、モード Always bypass を使用して、APAC リージョンのネットワーク サイトベトナム、インドネシア、シンガポールに 3 つの SBC を追加します。

```powershell
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

> [!NOTE]
> ローカル メディア最適化とLocation-Based ルーティング (LBR) が同時に構成されている場合に中断されない操作を確実にするには、ダウンストリーム SBC ごとに GatewaySiteLbrEnabled パラメーターを$trueに設定して、ダウンストリーム SBC を LBR に対して有効にする必要があります。 (この設定は、プロキシ SBC では必須ではありません。

上記の情報に基づいて、ダイレクト ルーティングには、次の表に示すように、SIP 招待と再招待に対する 3 つの独自の SIP ヘッダーが含まれます。

BypassMode が定義されている場合の招待とRe-Invitesのダイレクト ルーティングで導入された X-MS ヘッダー:

| ヘッダー名 | 値 | 注釈 | 
|:------------|:-------|:-------|
| X-MS-UserLocation | internal/external | ユーザーが内部か外部かを示します |
| Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | SBC がダイレクト ルーティングに直接接続されていない場合でも、呼び出しの対象となる FQDN |
| X-MS-MediaPath | 例: proxysbc.contoso.com、VNsbc.contoso.com | ユーザーとターゲット SBC 間のメディア パスに使用する必要がある SBC の順序。 最後の SBC は常に最後です |
| X-MS-UserSite | usersiteID | テナント管理者によって定義された文字列 |

## <a name="call-flows"></a>通話フロー 

次に、2 つのモードの呼び出しフローを示します。

- [Always Bypass](#always-bypass-mode)
- [ローカル ユーザーの場合のみ](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>常にバイパス モード

常にバイパス モードは、構成する最も簡単なオプションです。 テナント管理者は、すべての SBC に任意のサイトから到達可能な場合、すべてのユーザーと SBC に対して 1 つのサイトを構成できます。

次のシナリオでは、常にバイパス モードを示す例を示します。

- [送信呼び出しとユーザーが SBC と同じ場所にある](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [受信呼び出しとユーザーが SBC と同じ場所にある](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [送信呼び出しとユーザーが外部である](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [受信呼び出しとユーザーが外部である](#inbound-calls-and-the-user-is-external-with-always-bypass)

次の表は、例で使用されている FQDN と IP アドレスを示しています。

| FQDN | SBC 外部 IP アドレス | SBC 内部 IP アドレス | 内部サブネット | 場所 | 外部 NAT (信頼された IP) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | なし | 192.168.1.5 | 192.168.1.0/24 | ベトナム | 172.16.240.110 |
| IDsbc.contoso.com | なし | 192.168.2.5 | 192.168.2.0/24 | インドネシア | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | シンガポール | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>送信呼び出しとユーザーが Always Bypass の SBC と同じ場所にある

| モード |    ユーザー |  場所 |  通話方向 |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    内部 |  SBC と同じサイト |  発信 |

次の表に、エンド ユーザーの構成とアクションを示します。

| ユーザーの物理的な場所| ユーザーが番号との間で通話を発信または受信する | ユーザーの電話番号  | オンライン音声ルーティング ポリシー | SBC 用に構成されたモード |
|:------------|:-------|:-------|:-------|:-------|
| ベトナム | +84 4 3926 3000 | +84 4 5555 5555   | 優先度 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> 優先度 2: .* - proxysbc.contoso.com   | VNsbc.contoso.com – 常にバイパス <br> proxysbc.contoso.com – 常にバイパス


次の図は、常にバイパス モードの送信呼び出しの SIP ラダーと、SBC と同じ場所のユーザーを示しています。

> [!div class="mx-imgBorder"]
> ![発信呼び出しを示す図。](media/direct-routing-media-op-10.png "発信呼び出し")

次の表は、ダイレクト ルーティングによって送信された X-MS ヘッダーを示しています。

| パラメーター | 説明 |
|:------------|:-------|
| +8443926300@VNsbc.contoso.com を招待する | オンライン音声ルーティング ポリシーで定義されている SBC のターゲット FQDN は、要求 URI で送信されます。 | 
| X-MS-UserLocation: internal | ユーザーが企業ネットワーク内に存在することを示すフィールド |
| X-MS-MediaPath: VNsbc.contoso.com |   クライアントがターゲット SBC に走査する必要がある SBC を指定します。 この場合、Always Bypass があり、クライアントはヘッダー内の唯一の名前として送信されるターゲット名の内部です。 | 
|X-MS-UserSite: ベトナム |   ユーザーが配置されているサイト内で示されるフィールド。 |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>受信呼び出しとユーザーが Always Bypass の SBC と同じ場所にある

| モード |    ユーザー |  場所 |  通話方向 |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    内部 | SBC と同じサイト | 受信 |


受信呼び出しでは、ユーザーの場所が不明であり、SBC はユーザーの場所を推測する必要があります。 推測が正しくない場合は、再招待が必要です。 このケースでは、ユーザーが内部であり、メディアを直接フローでき、それ以上のアクションは必要ありません (再招待)。
ダイレクト ルーティング サービスに接続されている SBC は、Record-Routeフィールドと連絡先フィールドを指定して、元の SBC の場所を報告します。 これらのフィールドに基づいて、メディア パスはダイレクト ルーティングによって計算されます。

注: ユーザーが複数のエンドポイントを持つ可能性があることを考えると、183 をサポートすることはできません。 この場合、ダイレクト ルーティングでは常に 180 リンギングが使用されます。 

次の図は、AlwaysBypass モードの受信呼び出しでの SIP ラダーを示しており、ユーザーは SBC と同じ場所にあります。

> [!div class="mx-imgBorder"]
> ![SIP ラダーを示す図。](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>送信呼び出しとユーザーが Always Bypass を使用して外部である

| モード |    ユーザー |  サイト |  通話方向
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  N/A | 発信 |


次の図は、AlwaysBypass モードで送信呼び出しの SIP ラダーを示しており、ユーザーは外部です。

> [!div class="mx-imgBorder"]
> ![図は、SIP ラダーを示しています。](media/direct-routing-media-op-12.png)

次の表は、ダイレクト ルーティング サービスによって送信された X-MS ヘッダーを示しています。

| パラメーター |   説明 |
|:------------|:-------|
|+8443926300@VNsbc.contoso.com を招待する | オンライン音声ルーティング ポリシーで定義されている SBC のターゲット FQDN は、要求 URI で送信されます。|
| X-MS-UserLocation: external | フィールドは、ユーザーが企業ネットワークの外部に存在することを示しました。 |
| X-MS-MediaPath: proxysbc.contoso.com、VNsbc.contoso.com    | クライアントがターゲット SBC に走査する必要がある SBC を指定します。 この場合、Always Bypass があり、クライアントは外部です。 |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>受信呼び出しとユーザーが Always Bypass を使用して外部である

| モード | ユーザー | サイト |  通話方向 |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  N/A |   受信 |

受信呼び出しの場合、ユーザーの場所が外部である場合、Direct Routing に接続されている SBC は再招待を送信する必要があります (既定では、ローカル メディア候補は常に提供されます)。  X-MediaPath は、Record-Routeと指定された SBC ユーザーに基づいて計算されます。

次の図は、AlwaysBypass モードで受信呼び出しの SIP ラダーを示しており、ユーザーは外部です。

> [!div class="mx-imgBorder"]
> ![SIP ラダーを再び示す図。](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>ローカル ユーザー モードの場合のみ

ターゲット SBC のローカル メディア候補は、ユーザーが SBC と同じ場所にある場合にのみ提供されます。 それ以外のすべての場合、メディアはプロキシ SBC の内部 IP または外部 IP を経由します。

次のシナリオについて説明します。

- [送信呼び出しとユーザーが SBC と同じ場所にある](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [受信呼び出しとユーザーが SBC と同じ場所にある](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [ユーザーは SBC と同じ場所ではなく、企業ネットワーク内にいます](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [受信呼び出しとユーザーは内部ですが、SBC と同じ場所にありません](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

次の表に、エンド ユーザーの構成とアクションを示します。

| ユーザーの物理的な場所 |  ユーザーが番号との間で通話を発信または受信する |  ユーザーの電話番号 | オンライン音声ルーティング ポリシー |   SBC 用に構成されたモード |
|:------------|:-------|:-------|:-------|:-------|
| ベトナム | +84 4 3926  3000 |  +84 4 5555 5555 | 優先度 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> 優先度 2: .* - proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – 常にバイパス |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>発信呼び出しとユーザーが SBC と同じ場所にあり、ローカル ユーザーの場合のみ

| モード | ユーザー | サイト | 通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   内部 |SBC と同じ   | 発信 |

次の図は、OnlyForLocalUsers モードでの送信呼び出しを示しており、ユーザーは SBC と同じ場所にあります。 これは、 [ユーザーが SBC と同じ場所にある場合の送信呼び出し](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)で示されるフローと同じです。

> [!div class="mx-imgBorder"]
> ![もう一度図に SIP ラダーを示します。](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>受信呼び出しとユーザーが SBC と同じ場所にあり、ローカル ユーザーの場合のみ

| モード | ユーザー | サイト | 通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   内部 | SBC と同じ | 受信 |

次の図は、OnlyForLocalUsers モードでの受信呼び出しを示しており、ユーザーは SBC と同じ場所にあります。 これは、ユーザーが SBC と同 [じ場所にある場合の受信呼び出しに示されているフローと同じです](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。

> [!div class="mx-imgBorder"]
> ![SIP ラダーを示す別の図。](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>ユーザーは SBC と同じ場所ではなく、ローカル ユーザー専用の企業ネットワーク内にあります

| モード | ユーザー | サイト |通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | 内部 |   SBC とは異なる | 発信 |

ダイレクト ルーティングは、SBC で構成されたユーザーとモードの報告された場所に基づいて X-MediaPath を計算します。


次の図は、OnlyForLocalUsers モードでの送信呼び出しと、SBC と同じ場所にない内部ユーザーを示しています。

> [!div class="mx-imgBorder"]
> ![別の図は、SIP ラダーを示しています。](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>受信呼び出しとユーザーは内部ですが、ローカル ユーザー専用の SBC と同じ場所にありません

| モード |    ユーザー |  サイト |  通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | 内部 |    SBC とは異なる |    受信 |

次の図は、OnlyForLocalUsers モードでの受信呼び出しと、SBC と同じ場所にない内部ユーザーを示しています。

> [!div class="mx-imgBorder"]
> ![SIP ラダーを示すさらに別の図。](media/direct-routing-media-op-17.png)

