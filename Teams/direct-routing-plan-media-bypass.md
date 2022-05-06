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
ms.openlocfilehash: 560a3a5802469b0cb17170dfae377d8d6f358c8b
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518619"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>ダイレクト ルーティングでメディア バイパスを計画する

## <a name="about-media-bypass-with-direct-routing"></a>ダイレクト ルーティングを使用したメディア バイパスについて

メディア バイパスを使用すると、メディア トラフィックのパスを短縮し、転送中のホップの数を減らしてパフォーマンスを向上させることができます。 メディア バイパスでは、メディアは、Microsoft 電話 システム経由で送信するのではなく、セッション ボーダー コントローラー (SBC) とクライアントの間に保持されます。 メディア バイパスを構成するには、SBC とクライアントが同じ場所またはネットワーク内にある必要があります。

各 SBC のメディア バイパスを制御するには、**-MediaBypass** パラメーターを true または false に設定した **Set-CSOnlinePSTNGateway** コマンドを使用します。 メディア バイパスを有効にした場合、これは、すべてのメディア トラフィックが企業ネットワーク内に留まることを意味するわけではありません。 この記事では、さまざまなシナリオでの呼び出しフローについて説明します。

次の図は、メディア バイパスの有無に関するコール フローの違いを示しています。

メディア バイパスがない場合、クライアントが通話を発信または受信すると、次の図に示すように、SBC、Microsoft 電話 システム、Teams クライアントの間でシグナリングとメディアの両方がフローします。

> [!div class="mx-imgBorder"]
> ![メディア バイパスのないシグナリングとメディア フローを表示します。](media/direct-routing-media-bypass-1.png)


ただし、ユーザーが SBC と同じ建物またはネットワークにいるとします。 たとえば、フランクフルトのビルにいるユーザーが PSTN ユーザーを呼び出したとします。 

- **メディア バイパスを使用しない場合**、メディアはアムステルダムまたはダブリン (Microsoft データセンターがデプロイされている) 経由で、フランクフルトの SBC に戻ります。 

  SBC がヨーロッパにあり、Microsoft が SBC に最も近いデータセンターを使用しているため、ヨーロッパのデータセンターが選択されます。 この方法は、ほとんどの地域の Microsoft ネットワーク内のトラフィック フローの最適化のために通話品質に影響を与えませんが、トラフィックには不要なループがあります。     

- **メディア バイパスでは**、次の図に示すように、メディアはTeams ユーザーと SBC の間に直接保持されます。

  > [!div class="mx-imgBorder"]
  > ![メディア バイパスを使用したシグナリングとメディア フローを表示します。](media/direct-routing-media-bypass-2.png)

メディア バイパスでは、Teams クライアントの対話型接続確立 (ICE) と呼ばれるプロトコルと、SBC 上の ICE ライトが利用されます。 これらのプロトコルを使用すると、ダイレクト ルーティングで最もダイレクト メディア パスを使用して最適な品質を実現できます。 ICE と ICE Lite は WebRTC 標準です。 これらのプロトコルの詳細については、RFC 5245 を参照してください。


## <a name="call-flow-and-firewall-planning"></a>通話フローとファイアウォールの計画

通話フローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうかと、ユーザーがネットワークの内部または外部にあるかどうかによって異なります。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合の呼び出しフロー

ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、呼び出しフローは次のようになります。

- メディア バイパスの場合、Teams クライアントは、内部ネットワークからでも SBC のパブリック IP アドレスにアクセスできる必要があります。 ダイレクト メディアが不要な場合は、トランスポート リレー経由でメディアを流すことができます。

- これは、ユーザーが SBC と同じ建物やネットワークにいて、メディア パスから Microsoft Cloud コンポーネントを削除する場合に推奨されるソリューションです。

- シグナリングは常に Microsoft クラウド経由で流れます。

次の図は、メディア バイパスが有効になっていて、クライアントが内部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。 

- パスの矢印と数値は、[Microsoft Teams呼び出しフロー](./microsoft-teams-online-call-flows.md)に従います。

- SIP シグナリングは常にパス 4 と 4' を受け取ります (トラフィックの方向によって異なります)。 メディアはローカルのままで、パス 5b を受け取ります。

> [!div class="mx-imgBorder"]
> ![Media Bypass が有効になっている通話フローを表示します。クライアントは内部です。](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフロー

次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフローについて説明します。 

たとえば、ユーザーが外部であり、テナント管理者が SBC のパブリック IP アドレスをインターネット内のすべてのユーザーに開くのではなく、Microsoft Cloud にのみ開くことにしたとします。 トラフィックの内部コンポーネントは、Teams トランスポート リレーを介してフローできます。 次の状況について検討しましょう。

- Teamsトランスポート リレーが使用されます。

- メディア バイパスの場合、Microsoft では、Teams トランスポート リレーと SBC の間でポート 50 000 から 59 999 を開く必要があるトランスポート リレーのバージョンを使用します (今後は、3478~3481 ポートが必要なバージョンに移行する予定です)。


次の図は、メディア バイパスが有効になっていて、クライアントが外部であり、クライアントがセッション ボーダー コントローラーのパブリック IP アドレスに到達できない場合の呼び出しフローを示しています (メディアは、Teams トランスポート リレーによって中継されます)。

- パスの矢印と数値は、[Microsoft Teams呼び出しフロー](./microsoft-teams-online-call-flows.md)に従います。

- メディアはパス 3、3'、4、4' を介して中継されます

> [!div class="mx-imgBorder"]
> ![ユーザーが SBC のパブリック IP にアクセスできない場合の呼び出しフローを表示します。](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>ユーザーがネットワークの外部にあり、SBC のパブリック IP にアクセスできる場合の呼び出しフロー

> [!NOTE]
> これは、Teams トランスポート リレーを利用しないため、推奨される構成ではありません。 代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを検討する必要があります。 

次の図は、メディア バイパスが有効になっていて、クライアントが外部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。

- パスの矢印と数値は、[Microsoft Teamsコール フロー](./microsoft-teams-online-call-flows.md)に関する記事に従っています。

- SIP シグナリングは常にパス 3 と 3' を受け取ります (トラフィックの方向によって異なります)。 パス 2 を使用したメディア フロー。

> [!div class="mx-imgBorder"]
> ![ユーザーが SBC のパブリック IP にアクセスできない場合の呼び出しフローを表示します。](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>メディア プロセッサとトランスポート リレーの使用

メディア トラフィックのパスには、メディア プロセッサとトランスポート リレーの 2 つのコンポーネントがあります。 

- メディア プロセッサは、バイパス以外のケースでメディアを処理し、音声アプリケーション用のメディアを処理するパブリック向けコンポーネントです。

   メディア プロセッサは、エンド ユーザーがバイパスされていない呼び出しのパスに常に存在しますが、バイパスされた呼び出しのパスには入りません。 メディア プロセッサは、コール パーク、組織の自動応答、通話キューなど、すべての音声アプリケーションのパスに常に存在します。

- トランスポート リレーは、最も近いトランスポート サービスに接続してリアルタイム トラフィックを送信するために使用されます。

   トランスポート リレーは、ユーザーの場所とネットワークの構成方法に応じて、バイパスされた呼び出し (発信元またはエンド ユーザーへの宛先) のパスに含まれている場合とない場合があります。

次の図は、2 つの呼び出しフローを示しています。1 つはメディア バイパスが有効で、もう 1 つはメディア バイパスが無効です。

> [!NOTE]
> この図は、送信元または宛先のツーエンド ユーザーからのトラフィックのみを示しています。  

- Media Controller は Azure のマイクロサービスであり、メディア プロセッサを割り当て、セッション記述プロトコル (SDP) オファーを作成します。

- SIP プロキシは、Teamsで使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。    

> [!div class="mx-imgBorder"]
> ![Media Bypass が有効および無効になっている通話フローを表示します。](media/direct-routing-media-bypass-6.png)


次の表は、メディア プロセッサとトランスポート リレーの違いをまとめたものです。

|  &nbsp; | メディア プロセッサ | トランスポート リレー|
| :--------------|:---------------|:------------|
|エンド ユーザーのバイパスされていない呼び出しのメディア パス内 | いつも | クライアントがメディア プロセッサに直接到達できない場合 |
|エンド ユーザーのバイパスされた呼び出しのメディア パス内 | ぜんぜん | クライアントがパブリック IP アドレス上の SBC に到達できない場合 |
|音声アプリケーションのメディア パス内 | いつも | ぜんぜん |
|トランスコードを実行できます (B2BUA)\* | Yes | いいえ。エンドポイント間でオーディオのみをリレーします |
|世界中のインスタンスの数と場所 | 合計 15: 米国東部、西部、および中南部で 3。アムステルダム、ダブリン、英国南部、フランス中部の 4。香港とシンガポールの 2。日本では 2。オーストラリア東部と南東部の 2。ブラジル南部の 1。南アフリカ北部の 1 | 複数|

IP 範囲は次のとおりです。
- 52.112.0.0/14 (IP アドレス 52.112.0.1 から 52.115.255.254)
- 52.120.0.0/14 (IP アドレスは 52.120.0.1 から 52.123.255.254)

\* トランスコードの説明: 

- メディア プロセッサは B2BUA です。つまり、コーデックを変更できます (たとえば、SILK を Teams クライアントから MP に、G.711 を MP と SBC の間で変更できます)。

- トランスポート リレーは B2BUA ではありません。つまり、トラフィックがリレー経由で流れる場合でも、クライアントと SBC の間でコーデックが変更されることはありません。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>トランクがメディア バイパス用に構成されている場合は、Teams メディア プロセッサを使用する

Teams メディア プロセッサは、次のシナリオでは常にメディア パスに挿入されます。

- 通話が 1:1 からグループ呼び出しにエスカレートされる
- フェデレーション Teams ユーザーへの呼び出し
- 通話がSkype for Business ユーザーに転送または転送される

以下で説明するように、SBC がメディア プロセッサとトランスポート リレーの範囲にアクセスできることを確認します。    


## <a name="sip-signaling-fqdns"></a>SIP シグナリング: FQDN

SIP シグナリングの場合、FQDN とファイアウォールの要件は、バイパスされていないケースと同じです。 

ダイレクト ルーティングは、次のMicrosoft 365環境またはOffice 365環境で提供されます。
- Microsoft 365またはOffice 365
- Office 365 GCC
- Office 365 GCC高
- Office 365 DoD Office 365、GCC、GCC High、DoD などの[米国政府機関の環境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)について詳しく説明します。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC環境

ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN – を最初に試す必要があります。 SBC がこの名前を解決するための要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられたプライマリ Azure データセンターを指す IP アドレスを返します。 この割り当ては、データセンターのパフォーマンス メトリックと SBC への地理的近接性に基づいています。 返される IP アドレスは、プライマリ FQDN に対応します。

- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に 2 番目の優先度リージョンにマップされます。

- **sip3.pstnhub.microsoft.com** – ターシャリ FQDN – 地理的に 3 番目の優先度リージョンにマップされます。

次のことを行うには、次の 3 つの FQDN を配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込みが少なく、最初の FQDN にクエリを実行して割り当てられた SBC データセンターに最も近い)。

- SBC から一時的な問題が発生しているデータセンターへの接続が確立されたときにフェールオーバーを提供します。 詳細については、以下のフェールオーバー メカニズムに関する記事を参照してください。


FQDN **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**、 **および sip3.pstnhub.microsoft.com** は、次のサブネットの IP アドレスに解決されます。
- 52.112.0.0/14
- 52.120.0.0/14

シグナリングのアドレスとの間で送受信トラフィックを許可するには、ファイアウォール内のすべてのこれらの IP 範囲のポートを開く必要があります。

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。 Office 365 DoD 環境は米国のデータ センターにのみ存在するため、セカンダリおよびターシャリ FQDN はありません。

FQDN sip.pstnhub.dod.teams.microsoft.us は、次のサブネットの IP アドレスに解決されます。

- 52.127.64.0/21

シグナリングのアドレスとの間で送受信トラフィックを許可するには、ファイアウォール内のすべてのこれらの IP 範囲のポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.dod.teams.microsoft.us はこれらのすべての IP サブネットに解決されます。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高い環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 GCC High 環境は米国のデータ センターにのみ存在するため、セカンダリおよびターシャリ FQDN はありません。

FQDN sip.pstnhub.gov.teams.microsoft.us は、次のサブネットの IP アドレスに解決されます。

- 52.127.88.0/21

シグナリングのアドレスとの間で送受信トラフィックを許可するには、ファイアウォール内のすべてのこれらの IP 範囲のポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us はこれらのすべての IP サブネットに解決されます。 

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

ポート要件は、ダイレクト ルーティングが提供されるすべてのOffice 365環境で同じです。
- Microsoft 365またはOffice 365
- Office 365 GCC
- Office 365 GCC高
- Office 365 DoD

次のポートを使用する必要があります。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP プロキシ | SBC | 1024 - 65535 | SBC で定義されている |
| SIP/TLS | SBC | SIP プロキシ | SBC で定義されている | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>メディア トラフィック: IP とポートの範囲

直接接続が使用可能な場合、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合は、Teams トランスポート リレーを介して、SBC とTeams クライアントの間でメディア トラフィックがフローします。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>ダイレクト メディア トラフィックの要件 (Teams クライアントと SBC の間) 

クライアントは、SBC のパブリック IP アドレス上の指定されたポート (表を参照) にアクセスできる必要があります。 

> [!NOTE]
> クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに流れます。 トラフィックがエンタープライズ ネットワーク機器から送信されないように、NAT デバイスにヘア ピン留めを構成できます。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | クライアント | SBC | 50000-50019| SBC で定義されている |
| UDP/SRTP | SBC | クライアント | SBC で定義されている | 50000-50019  |


> [!NOTE]
> クライアントのソース ポートを変換するネットワーク デバイスがある場合は、変換されたポートがネットワーク機器と SBC の間で開かれていることを確認してください。 

### <a name="requirements-for-using-transport-relays"></a>トランスポート リレーを使用するための要件

トランスポート リレーは、メディア プロセッサと同じ範囲にあります (バイパス以外の場合)。 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC環境

- 52.112.0.0 /14 (IP アドレスは 52.112.0.1 から 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高い環境

- 52.127.88.0/21


Teams トランスポート リレーのポート範囲 (すべての環境に適用) を次の表に示します。


| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | トランスポート リレー | SBC | 50 000 -59 999    | SBC で定義されている |
| UDP/SRTP | SBC | トランスポート リレー | SBC で定義されている | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートを推奨しています。 Microsoft には 2 つのバージョンのトランスポート リレーがあるため、次のものが必要です。
> 
> - v4:ポート範囲 50 000 ~ 59 999 でのみ動作する
> 
> - ポート 3478-3481 で動作する v6

現時点では、メディア バイパスでは v4 バージョンのトランスポート リレーのみがサポートされています。 今後、v6 のサポートについて説明します。 

移行するには、ポート 3478 から 3481 を開く必要があります。 Microsoft がメディア バイパスを使用した v6 トランスポート リレーのサポートを導入した場合、ネットワーク機器または SBC を再構成する必要はありません。 

### <a name="requirements-for-using-media-processors"></a>メディア プロセッサを使用するための要件

メディア プロセッサは、音声アプリケーションと Web クライアント (たとえば、Edge または Google Chrome のTeams クライアント) のメディア パスに常に存在します。 要件は、バイパス以外の構成の場合と同じです。


メディア トラフィックの IP 範囲は次の値です。 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365環境とOffice 365 GCC環境

- 52.112.0.0 /14 (IP アドレスは 52.112.0.1 から 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高い環境

- 52.127.88.0/21

メディア プロセッサのポート範囲 (すべての環境に適用) を次の表に示します。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | メディア プロセッサ | SBC | 3478-3481 および 49 152 – 53 247    | SBC で定義されている |
| UDP/SRTP | SBC | メディア プロセッサ | SBC で定義されている | 3478-3481 および 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>メディア バイパスと非メディア バイパス用に個別のトランクを構成する  

メディア バイパス以外からメディア バイパスに移行していて、すべての使用状況をメディア バイパスに移行する前に機能を確認する場合は、メディア バイパス トランクにルーティングし、特定のユーザーに割り当てるために、個別のトランクと個別のオンライン音声ルーティング ポリシーを作成できます。 

高レベルの構成手順:

- メディア バイパスをテストするユーザーを特定します。

- 異なる FQDN を持つ 2 つの個別のトランクを作成します。1 つはメディア バイパスが有効になっています。もう 1 つではありません。 

  両方のトランクが同じ SBC を指しています。 TLS SIP シグナリングのポートは異なる必要があります。 メディアのポートは同じである必要があります。

- 新しいオンライン音声ルーティング ポリシーを作成し、このポリシーの PSTN 使用法に関連付けられている対応するルートにメディア バイパス トランクを割り当てます。

- 新しいオンライン音声ルーティング ポリシーを、メディア バイパスをテストするために識別したユーザーに割り当てます。

次の例は、このロジックを示しています。

| ユーザーのセット | ユーザーの数 | OVRP で割り当てられたトランク FQDN | メディア バイパスが有効になっている |
| :------------ |:----------------- |:--------------|:--------------|
| メディア以外のバイパス トランクを持つユーザー | 980 | sbc1.contoso.com:5061 | false |
| メディア バイパス トランクを持つユーザー | 20 | sbc2.contoso.com:5060 | true | 

どちらのトランクも、同じパブリック IP アドレスを持つ同じ SBC を指すことができます。 次の図に示すように、SBC の TLS シグナリング ポートは異なる必要があります。 証明書が両方のトランクをサポートしていることを確認する必要があることに注意してください。 SAN では、2 つの名前 (**sbc1.contoso.com** と **sbc2.contoso.com**) またはワイルドカード証明書が必要です。

> [!div class="mx-imgBorder"]
> ![両方のトランクが同じパブリック IP を持つ同じ SBC をポイントできることを示します。](media/direct-routing-media-bypass-7.png)

同じ SBC で 2 つのトランクを構成する方法については、SBC ベンダーが提供するドキュメントを参照してください。

 - [AudioCodes のデプロイに関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle デプロイのドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボン 通信の展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) の展開に関するドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>メディア バイパスでサポートされているクライアント エンドポイント

メディア バイパスは、すべてのスタンドアロン Teams デスクトップ クライアント、Android および iOS クライアント、Teams 電話 デバイスでサポートされています。 

メディア バイパスをサポートしていないその他のすべてのエンドポイントでは、バイパス呼び出しとして開始された場合でも、呼び出しを非バイパスに変換します。 これは自動的に発生し、管理者からの操作は必要ありません。 これには、Skype for Business 3PIP Phone、およびダイレクト ルーティング呼び出しをサポートする Teams web クライアント (Microsoft Edge、Google Chrome、Mozilla Firefox で実行されている WebRTC ベースのクライアント) が含まれます。 
 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングでメディア バイパスを構成する](direct-routing-configure-media-bypass.md)
