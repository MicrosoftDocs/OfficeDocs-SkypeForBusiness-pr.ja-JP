---
title: ダイレクト ルーティングでメディア バイパスを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 電話システム ダイレクト ルーティングを使用してメディア バイパスを計画する方法について説明します。これにより、メディア トラフィックのパスを短縮し、パフォーマンスを向上させることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea92103789927d35ae8bdd317987f32863d4d74e
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981792"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>ダイレクト ルーティングでメディア バイパスを計画する

## <a name="about-media-bypass-with-direct-routing"></a>ダイレクト ルーティングを使用したメディア バイパスについて

メディア バイパスを使用すると、メディア トラフィックのパスを短縮し、転送中のホップ数を減らしてパフォーマンスを向上させることができます。 メディア バイパスでは、メディアは Microsoft Phone システム経由で送信されるのではなく、セッション ボーダー コントローラー (SBC) とクライアントの間で保持されます。 メディア バイパスを構成するには、SBC とクライアントが同じ場所またはネットワーク内にある必要があります。

**-MediaBypass** パラメーターを true または false に設定した **Set-CSOnlinePSTNGateway** コマンドを使用して、各 SBC のメディア バイパスを制御できます。 メディア バイパスを有効にした場合、すべてのメディア トラフィックが企業ネットワーク内に留まるわけではありません。 この記事では、さまざまなシナリオでの通話フローについて説明します。

次の図は、メディア バイパスの有無に関する通話フローの違いを示しています。

メディア バイパスを使用しない場合、クライアントが呼び出しを行ったり受信したりすると、次の図に示すように、SBC、Microsoft Phone System、Teams クライアント間のシグナリングとメディア フローの両方が行われます。

> [!div class="mx-imgBorder"]
> ![メディア バイパスなしのシグナリングとメディア フローを示します。](media/direct-routing-media-bypass-1.png)


ただし、ユーザーが SBC と同じ建物またはネットワーク内にあるとします。 たとえば、フランクフルトの建物内にいるユーザーが PSTN ユーザーを呼び出すとします。 

- **メディア バイパスがないと**、メディアはアムステルダムまたはダブリン (Microsoft データセンターがデプロイされている場所) を経由して、フランクフルトの SBC に戻ります。 

  SBC がヨーロッパにあり、Microsoft は SBC に最も近いデータセンターを使用するため、ヨーロッパのデータセンターが選択されています。 この方法は、ほとんどの地域の Microsoft ネットワーク内のトラフィック フローの最適化による通話品質には影響しませんが、トラフィックには不要なループがあります。     

- **メディア バイパスでは**、次の図に示すように、メディアは Teams ユーザーと SBC の間で直接保持されます。

  > [!div class="mx-imgBorder"]
  > ![メディア バイパスを使用したシグナリングとメディア フローを示します。](media/direct-routing-media-bypass-2.png)

メディア バイパスは、Teams クライアント上の対話型接続確立 (ICE) と SBC の ICE lite と呼ばれるプロトコルを利用します。 これらのプロトコルを使用すると、Direct Routing で最適な品質のために最も直接的なメディア パスを使用できます。 ICE と ICE Lite は WebRTC 標準です。 これらのプロトコルの詳細については、RFC 5245 を参照してください。


## <a name="call-flow-and-firewall-planning"></a>通話フローとファイアウォールの計画

通話フローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうかと、ユーザーがネットワークの内部か外部かに依存します。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合の通話フロー

ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、呼び出しフローは次のようになります。

- メディア バイパスの場合、Teams クライアントは、内部ネットワークからでも SBC のパブリック IP アドレスにアクセスできる必要があります。 直接メディアが望ましくない場合、メディアはトランスポート リレー経由でフローできます。

- これは、ユーザーが SBC と同じ建物やネットワークにいる場合に推奨されるソリューションです。メディア パスから Microsoft Cloud コンポーネントを削除します。

- シグナリングは常に Microsoft クラウド経由で流れます。

次の図は、メディア バイパスが有効になっていて、クライアントが内部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。 

- パスの矢印と数値は、 [Microsoft Teams の通話フロー](./microsoft-teams-online-call-flows.md)に従います。

- SIP シグナリングは常にパス 4 と 4' を受け取ります (トラフィックの方向に応じて)。 メディアはローカルのままで、パス 5b を受け取ります。

> [!div class="mx-imgBorder"]
> ![メディア バイパスが有効になっている通話フローを示します。クライアントは内部です。](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の通話フロー

次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフローについて説明します。 

たとえば、ユーザーが外部であり、テナント管理者が SBC のパブリック IP アドレスをインターネット内のすべてのユーザーに対して開くのではなく、Microsoft Cloud にのみ開くことにしたとします。 トラフィックの内部コンポーネントは、Teams トランスポート リレーを介してフローできます。 次の状況について検討しましょう。

- Teams トランスポート リレーが使用されます。

- メディア バイパスの場合、Microsoft では、Teams トランスポート リレーと SBC の間でポート 50 000 から 59 999 を開く必要があるバージョンのトランスポート リレーを使用します (将来的には、3478 から 3481 ポートが必要なバージョンに移行する予定です)。


次の図は、メディア バイパスが有効になっていて、クライアントが外部であり、クライアントがセッション ボーダー コントローラーのパブリック IP アドレスに到達できない場合の通話フローを示しています (メディアは Teams トランスポート リレーによって中継されます)。

- パスの矢印と数値は、 [Microsoft Teams の通話フロー](./microsoft-teams-online-call-flows.md)に従います。

- メディアは、パス 3、3'、4、4' を介して中継されます

> [!div class="mx-imgBorder"]
> ![ユーザーが SBC のパブリック IP にアクセスできない場合は、通話フローを表示します。](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>ユーザーがネットワークの外部にあり、SBC のパブリック IP にアクセスできる場合の通話フロー

> [!NOTE]
> これは、Teams トランスポート リレーを利用しないため、推奨される構成ではありません。 代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを検討する必要があります。 

次の図は、メディア バイパスが有効で、クライアントが外部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の通話フローを示しています。

- パスの矢印と数値は、 [Microsoft Teams 通話フロー](./microsoft-teams-online-call-flows.md) に関する記事に従います。

- SIP シグナリングは常にパス 3 と 3' を受け取ります (トラフィックの方向に応じて)。 パス 2 を使用したメディア フロー。

> [!div class="mx-imgBorder"]
> ![ユーザーが SBC のパブリック IP にアクセスできない場合は、通話フローを表示します。](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>メディア プロセッサとトランスポート リレーの使用

Microsoft Cloud には、メディア トラフィックのパスにメディア プロセッサとトランスポート リレーという 2 つのコンポーネントがあります。 

- メディア プロセッサは、非バイパス ケースのメディアを処理し、音声アプリケーションのメディアを処理する、パブリックに接続するコンポーネントです。

   メディア プロセッサは、常にエンド ユーザーのバイパスされていない呼び出しのパスにありますが、バイパスされた呼び出しのパス内にありません。 メディア プロセッサは、コール パーク、組織の自動応答、通話キューなど、すべての音声アプリケーションのパスに常に存在します。

- トランスポート リレーは、最も近いトランスポート サービスに接続してリアルタイム トラフィックを送信するために使用されます。

   トランスポート リレーは、ユーザーの場所とネットワークの構成方法に応じて、バイパスされた呼び出しのパス内にある場合と、エンド ユーザー宛てに送信される場合があります。

次の図は、2 つの呼び出しフローを示しています。1 つはメディア バイパスが有効で、もう 1 つはメディア バイパスが無効になっています。

> [!NOTE]
> この図は、送信元または宛先からエンド ユーザーへのトラフィックのみを示しています。  

- メディア コントローラーは、メディア プロセッサを割り当て、セッション記述プロトコル (SDP) オファーを作成する Azure のマイクロサービスです。

- SIP プロキシは、Teams で使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。    

> [!div class="mx-imgBorder"]
> ![メディア バイパスが有効または無効になっている通話フローを表示します。](media/direct-routing-media-bypass-6.png)


次の表は、メディア プロセッサとトランスポート リレーの違いをまとめたものです。

|  &nbsp; | メディア プロセッサ | トランスポート リレー|
| :--------------|:---------------|:------------|
|エンド ユーザーのバイパスされていない呼び出しのメディア パス | いつも | クライアントがメディア プロセッサに直接到達できない場合 |
|エンド ユーザーのバイパスされた呼び出しのメディア パス | ぜんぜん | クライアントがパブリック IP アドレスで SBC に到達できない場合 |
|音声アプリケーションのメディア パス | いつも | ぜんぜん |
|トランスコーディングを実行できます (B2BUA)\* | Yes | いいえ。エンドポイント間でオーディオのみをリレーします |

IP 範囲は次のとおりです。
- 52.112.0.0/14 (52.112.0.1 から 52.115.255.254 への IP アドレス)
- 52.122.0.0/15 (52.122.0.1 から 52.123.255.254 への IP アドレス)

\* コード変換の説明: 

- メディア プロセッサは B2BUA です。つまり、コーデック (たとえば、TEAMS クライアントから MP に SILK、MP と SBC の間で G.711 など) を変更できます。

- トランスポート リレーは B2BUA ではありません。つまり、トラフィックがリレー経由で流れる場合でも、クライアントと SBC の間でコーデックが変更されることはありません。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>トランクがメディア バイパス用に構成されている場合の Teams メディア プロセッサの使用

Teams メディア プロセッサは、次のシナリオでは常にメディア パスに挿入されます。

- 通話が 1:1 からグループ呼び出しにエスカレートされる
- 通話がフェデレーション Teams ユーザーに送信される
- 通話がSkype for Business ユーザーに転送または転送される

以下で説明するように、SBC がメディア プロセッサとトランスポート リレーの範囲にアクセスできることを確認します。    


## <a name="sip-signaling-fqdns"></a>SIP シグナリング: FQDN

SIP シグナリングの場合、FQDN とファイアウォールの要件は、バイパスされていないケースの場合と同じです。 

ダイレクト ルーティングは、次の Microsoft 365 またはOffice 365環境で提供されます。
- Microsoft 365 または Office 365
- GCC をOffice 365する
- OFFICE 365 GCC High
- Office 365 DoD GCC、GCC High、DoD などの[Office 365と米国政府の環境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)の詳細を確認します。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN – を最初に試す必要があります。 SBC がこの名前を解決する要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。 割り当ては、データセンターのパフォーマンス メトリックと SBC への地理的近接性に基づいています。 返される IP アドレスは、プライマリ FQDN に対応します。

- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に 2 番目の優先度リージョンにマップされます。

- **sip3.pstnhub.microsoft.com** – 第 3 の FQDN – 地理的に 3 番目の優先度のリージョンにマップされます。

次の 3 つの FQDN を配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込みの少なく、最初の FQDN のクエリによって割り当てられた SBC データセンターに最も近い)。

- SBC からの接続が確立され、一時的な問題が発生しているデータセンターにフェールオーバーを提供します。 詳細については、以下の「フェールオーバー メカニズム」を参照してください。


FQDN **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**、 **sip3.pstnhub.microsoft.com** は、次のサブネットの IP アドレスに解決されます。
- 52.112.0.0/14
- 52.122.0.0/15

シグナリングのためにアドレスとの間で送受信されるトラフィックを許可するには、ファイアウォール内のすべての IP 範囲のポートを開く必要があります。

### <a name="office-365-gcc-dod-environment"></a>GCC DoD 環境のOffice 365

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。 Office 365 DoD 環境は米国のデータ センターにのみ存在します。セカンダリ FQDN とターシャリ FQDN はありません。

FQDN sip.pstnhub.dod.teams.microsoft.us は、次のサブネットから IP アドレスに解決されます。

- 52.127.64.0/21

シグナリングのためにアドレスとの間で送受信されるトラフィックを許可するには、ファイアウォール内のすべての IP 範囲のポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.dod.teams.microsoft.us はこれらのすべての IP サブネットに解決されます。 

### <a name="office-365-gcc-high-environment"></a>GCC High 環境のOffice 365

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 GCC High 環境は米国のデータ センターにのみ存在します。セカンダリ FQDN とターシャリ FQDN はありません。

FQDN sip.pstnhub.gov.teams.microsoft.us は、次のサブネットから IP アドレスに解決されます。

- 52.127.88.0/21

シグナリングのためにアドレスとの間で送受信されるトラフィックを許可するには、ファイアウォール内のすべての IP 範囲のポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us はこれらのすべての IP サブネットに解決されます。 

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

ポート要件は、ダイレクト ルーティングが提供されるすべてのOffice 365環境で同じです。
- Microsoft 365 または Office 365
- GCC をOffice 365する
- OFFICE 365 GCC High
- Office 365 DoD

次のポートを使用する必要があります。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP プロキシ | Sbc | 1024 - 65535 | SBC で定義されている |
| SIP/TLS | Sbc | SIP プロキシ | SBC で定義されている | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>メディア トラフィック: IP とポートの範囲

直接接続が利用可能な場合は SBC と Teams クライアント間のメディア トラフィックが流れます。また、クライアントがパブリック IP アドレスを使用して SBC に到達できない場合は Teams トランスポート リレー経由で送信されます。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>直接メディア トラフィックの要件 (Teams クライアントと SBC の間) 

クライアントは、SBC のパブリック IP アドレスで指定されたポート (表を参照) にアクセスできる必要があります。 

> [!NOTE]
> クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに流れます。 NAT デバイスでヘア ピン留めを構成して、トラフィックがエンタープライズ ネットワーク機器から離れることがないようにすることができます。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | クライアント | Sbc | 50000-50019| SBC で定義されている |
| UDP/SRTP | Sbc | クライアント | SBC で定義されている | 50000-50019  |


> [!NOTE]
> クライアントのソース ポートを変換するネットワーク デバイスがある場合は、ネットワーク機器と SBC の間で変換されたポートが開いていることを確認してください。 

### <a name="requirements-for-using-transport-relays"></a>トランスポート リレーを使用するための要件

トランスポート リレーは、メディア プロセッサと同じ範囲にあります (バイパス以外の場合)。 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

- 52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 までの IP アドレス)

### <a name="office-365-gcc-dod-environment"></a>GCC DoD 環境のOffice 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>GCC High 環境のOffice 365

- 52.127.88.0/21


Teams トランスポート リレー (すべての環境に適用可能) のポート範囲を次の表に示します。


| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | トランスポート リレー | Sbc | 50 000 -59 999    | SBC で定義されている |
| UDP/SRTP | Sbc | トランスポート リレー | SBC で定義されている | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートを推奨しています。 Microsoft には 2 つのバージョンのトランスポート リレーがあるため、次のものが必要です。
> 
> - v4。ポート範囲 50 000 ~ 59 999 でのみ動作します
> 
> - ポート 3478-3481 で動作する v6

現時点では、メディア バイパスでは v4 バージョンのトランスポート リレーのみがサポートされています。 今後、v6 のサポートを紹介します。 

移行するには、ポート 3478 から 3481 を開く必要があります。 Microsoft がメディア バイパスを使用した v6 トランスポート リレーのサポートを導入する場合、ネットワーク機器や SBC を再構成する必要はありません。 

### <a name="requirements-for-using-media-processors"></a>メディア プロセッサを使用するための要件

メディア プロセッサは、音声アプリケーションと Web クライアント (Edge や Google Chrome の Teams クライアントなど) のメディア パスに常に存在します。 要件は、バイパス以外の構成の場合と同じです。


メディア トラフィックの IP 範囲は、 

### <a name="office-365-and-office-365-gcc-environments"></a>GCC 環境のOffice 365とOffice 365

- 52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 までの IP アドレス)

### <a name="office-365-gcc-dod-environment"></a>GCC DoD 環境のOffice 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>GCC High 環境のOffice 365

- 52.127.88.0/21

メディア プロセッサ (すべての環境に適用可能) のポート範囲を次の表に示します。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | メディア プロセッサ | Sbc | 3478-3481 および 49 152 – 53 247    | SBC で定義されている |
| UDP/SRTP | Sbc | メディア プロセッサ | SBC で定義されている | 3478-3481 および 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>メディア バイパスと非メディア バイパス用に個別のトランクを構成する  

メディア バイパス以外からメディア バイパスに移行し、すべての使用状況をメディア バイパスに移行する前に機能を確認する場合は、個別のトランクと個別のオンライン音声ルーティング ポリシーを作成して、メディア バイパス トランクにルーティングし、特定のユーザーに割り当てることができます。 

大まかな構成手順:

- メディア バイパスをテストするユーザーを特定します。

- 異なる FQDN を持つ 2 つの独立したトランクを作成します。1 つはメディア バイパスを有効にします。もう 1 つではありません。 

  どちらのトランクも同じ SBC を指します。 TLS SIP シグナリングのポートは異なる必要があります。 メディアのポートは同じである必要があります。

- 新しいオンライン音声ルーティング ポリシーを作成し、このポリシーの PSTN 使用状況に関連付けられている対応するルートにメディア バイパス トランクを割り当てます。

- メディア バイパスをテストするために特定したユーザーに、新しいオンライン音声ルーティング ポリシーを割り当てます。

次の例は、このロジックを示しています。

| ユーザーのセット | ユーザーの数 | OVRP で割り当てられたトランク FQDN | メディア バイパスが有効 |
| :------------ |:----------------- |:--------------|:--------------|
| メディア以外のバイパス トランクを持つユーザー | 980 | sbc1.contoso.com:5061 | false |
| メディア バイパス トランクを持つユーザー | 20 | sbc2.contoso.com:5060 | true | 

どちらのトランクも、同じパブリック IP アドレスを持つ同じ SBC を指すことができます。 次の図に示すように、SBC の TLS シグナリング ポートは異なる必要があります。 証明書が両方のトランクをサポートしていることを確認する必要があることに注意してください。 SAN では、2 つの名前 (**sbc1.contoso.com** と **sbc2.contoso.com**) を持っているか、ワイルドカード証明書が必要です。

> [!div class="mx-imgBorder"]
> ![両方のトランクが同じパブリック IP を持つ同じ SBC を指し示します。](media/direct-routing-media-bypass-7.png)

同じ SBC で 2 つのトランクを構成する方法については、SBC ベンダーが提供するドキュメントを参照してください。

 - [AudioCodes の展開に関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle デプロイに関するドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボン通信の展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) の展開に関するドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>メディア バイパスでサポートされるクライアント エンドポイント

メディア バイパスは、すべてのスタンドアロン Teams デスクトップ クライアント、Android および iOS クライアント、および Teams Phone Devices でサポートされます。 

メディア バイパスをサポートしていない他のすべてのエンドポイントについては、バイパス呼び出しとして開始された場合でも、呼び出しを非バイパスに変換します。 これは自動的に行われ、管理者からの操作は必要ありません。 これには、Skype for Business 3PIP 電話と、ダイレクト ルーティング呼び出しをサポートする Teams Web クライアント (Microsoft Edge、Google Chrome、Mozilla Firefox で実行されている WebRTC ベースのクライアント) が含まれます。 
 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングでメディア バイパスを構成する](direct-routing-configure-media-bypass.md)
