---
title: ダイレクト ルーティングでメディア バイパスを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 電話システムダイレクト ルーティングを使用してメディア バイパスを計画する方法について説明します。これにより、メディア トラフィックのパスを短縮し、パフォーマンスを向上させることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2cbe739a567588b44bef87f7b852ed8de965ad3
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899098"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>ダイレクト ルーティングでメディア バイパスを計画する

## <a name="about-media-bypass-with-direct-routing"></a>ダイレクト ルーティングを使用したメディア バイパスについて

メディア バイパスを使用すると、メディア トラフィックのパスを短縮し、転送中のホップ数を減らしてパフォーマンスを向上させることができます。 メディア バイパスでは、メディアは Microsoft Phone System 経由で送信する代わりに、セッション ボーダー コントローラー (SBC) とクライアントの間で保持されます。 メディア バイパスを構成するには、SBC とクライアントが同じ場所またはネットワークにある必要があります。

各 SBC のメディア バイパスを制御するには **、-MediaBypass** パラメーターを true または false に設定した **Set-CSOnlinePSTNGateway** コマンドを使用します。 メディア バイパスを有効にした場合、すべてのメディア トラフィックが企業ネットワーク内に残るという意味ではありません。 この記事では、さまざまなシナリオでの呼び出しフローについて説明します。

次の図は、メディア バイパスの使用と使用しない通話フローの違いを示しています。

次の図に示すように、メディア バイパスを使用しない場合、クライアントが通話を行った場合または受信すると、SBC、Microsoft Phone System、Teams クライアント間のシグナリングとメディア フローの両方が発生します。

> [!div class="mx-imgBorder"]
> ![メディア バイパスなしでシグナリングとメディア フローを表示する](media/direct-routing-media-bypass-1.png)


ただし、ユーザーが SBC と同じビルまたはネットワーク内にあるとします。 たとえば、フランクフルトの建物内にあるユーザーが PSTN ユーザーを呼び出したとします。 

- **メディア バイパスを使用しない** 場合、メディアはアムステルダムまたはダブリン (Microsoft データセンターがデプロイされている場所) を経由して、フランクフルトの SBC に戻されます。 

  ヨーロッパのデータセンターは、SBC がヨーロッパに存在し、Microsoft が SBC に最も近いデータセンターを使用するために選択されます。 この方法は、ほとんどの地域で Microsoft ネットワーク内のトラフィック フローを最適化するために呼び出しの品質には影響しませんが、トラフィックには不要なループがあります。     

- **メディア バイパスでは**、次の図に示すように、メディアは Teams ユーザーと SBC の間で直接保持されます。

  > [!div class="mx-imgBorder"]
  > ![メディア バイパスを使用したシグナリングとメディア フローの表示](media/direct-routing-media-bypass-2.png)

メディア バイパスでは、Teams クライアントの対話型接続確立 (ICE) と SBC 上の ICE lite というプロトコルが利用されます。 これらのプロトコルを使用すると、ダイレクト ルーティングは最適な品質のために最も直接的なメディア パスを使用できます。 ICE と ICE Lite は WebRTC 標準です。 これらのプロトコルの詳細については、「RFC 5245」を参照してください。


## <a name="call-flow-and-firewall-planning"></a>呼び出しフローとファイアウォールの計画

呼び出しフローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうか、およびユーザーがネットワークの内部または外部にあるかどうかによって異なります。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合の呼び出しフロー

ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、呼び出しフローは次のようになります。

- メディア バイパスの場合、Teams クライアントは内部ネットワークからでも SBC のパブリック IP アドレスにアクセスできる必要があります。 ダイレクト メディアが必要ない場合は、トランスポート リレー経由でメディアをフローできます。

- これは、ユーザーが SBC と同じ建物やネットワーク内にある場合に推奨されるソリューションです。メディア パスから Microsoft Cloud コンポーネントを削除します。

- シグナリングは常に Microsoft クラウド経由でフローします。

次の図は、メディア バイパスが有効で、クライアントが内部的であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。 

- パスの矢印と数値は、Microsoft Teams の呼び出しフロー [に従っています](./microsoft-teams-online-call-flows.md)。

- SIP シグナリングは常にパス 4 と 4' を受け取ります (トラフィックの方向に応じて)。 メディアはローカルに残り、パス 5b を受け取る。

> [!div class="mx-imgBorder"]
> ![Media Bypass を有効にした通話フローを表示します。クライアントは内部的です](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフロー

次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフローについて説明します。 

たとえば、ユーザーが外部ユーザーであり、テナント管理者は、インターネットのすべてのユーザーに対して SBC のパブリック IP アドレスを開くのではなく、Microsoft Cloud にのみ開くことを決定したとします。 トラフィックの内部コンポーネントは、Teams トランスポート リレーを介してフローできます。 次の状況について検討しましょう。

- Teams トランスポート リレーが使用されます。

- メディア バイパスの場合、Microsoft は、Teams トランスポート リレーと SBC の間にポート 50 000 から 59 999 を開く必要があるバージョンのトランスポート リレーを使用します (今後、3478 ポートと 3479 ポートのみを必要とするバージョンに移行する予定です)。


次の図は、メディア バイパスが有効で、クライアントが外部であり、クライアントがセッション ボーダー コントローラーのパブリック IP アドレスに到達できない場合の呼び出しフローを示しています (メディアは Teams トランスポート リレーによって中継されます)。

- パスの矢印と数値は、Microsoft Teams の呼び出しフロー [に従っています](./microsoft-teams-online-call-flows.md)。

- メディアは、パス 3、3、4、4' を介して中継されます。

> [!div class="mx-imgBorder"]
> ![ユーザーが SBC のパブリック IP にアクセスできない場合の通話フローを表示します。](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>ユーザーがネットワークの外部にいて、SBC のパブリック IP にアクセスできる場合にフローを呼び出す

> [!NOTE]
> これは、Teams トランスポート リレーを利用しないので、推奨される構成ではありません。 代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを検討する必要があります。 

次の図は、メディア バイパスが有効で、クライアントが外部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。

- パスの矢印と数値は、Microsoft Teams の呼び出しフローに関 [する記事に従](./microsoft-teams-online-call-flows.md) っています。

- SIP シグナリングは常にパス 3 と 3' を受け取ります (トラフィックの方向に応じて)。 パス 2 を使用したメディア フロー。

> [!div class="mx-imgBorder"]
> ![ユーザーが SBC のパブリック IP にアクセスできない場合の通話フローを表示します。](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>メディア プロセッサとトランスポート リレーの使用

メディア トラフィックのパスに含め得る Microsoft Cloud には、メディア プロセッサとトランスポート リレーの 2 つのコンポーネントがあります。 

- Media Processor は、バイパスされていないケースのメディアを処理し、音声アプリケーション用のメディアを処理するパブリック向けのコンポーネントです。

   メディア プロセッサは常にエンド ユーザーのバイパスされていない呼び出しのパスに入っていますが、バイパスされた呼び出しのパスには含めずにいます。 メディア プロセッサは、通話パーク、組織の通話、通話キューなど、すべての音声自動応答パスにあります。

- トランスポート リレーは、最も近いトランスポート サービスに接続してリアルタイム のトラフィックを送信するために使用されます。

   トランスポート リレーは、ユーザーの場所とネットワークの構成方法に応じて、バイパスされた呼び出し (発信元またはエンド ユーザー宛て) のパス内にある場合とない場合があります。

次の図は、メディア バイパスが有効な 2 つの呼び出しフローと、メディア バイパスが無効になっている 2 つの呼び出しフローを示しています。

> [!NOTE]
> この図は、発信元または宛先のエンドツーエンド ユーザーからのトラフィックのみを示しています。  

- Media Controller は、メディア プロセッサを割り当て、セッション記述プロトコル (SDP) オファーを作成する Azure のマイクロサービスです。

- SIP プロキシは、Teams で使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。    

> [!div class="mx-imgBorder"]
> ![Media Bypass を有効または無効にした通話フローを表示します。](media/direct-routing-media-bypass-6.png)


次の表は、メディア プロセッサとトランスポート リレーの違いをまとめたものです。

|    | メディア プロセッサ | トランスポート リレー|
| :--------------|:---------------|:------------|
エンド ユーザーのバイパスされていない呼び出しのメディア パス内 | いつも | クライアントがメディア プロセッサに直接アクセスできない場合 | 
エンド ユーザーのバイパスされた呼び出しのメディア パスで | ぜんぜん | クライアントがパブリック IP アドレスで SBC に到達できない場合 | 
音声アプリケーションのメディア パスで | いつも | ぜんぜん | 
トランスコードを実行できます (B2BUA)\* | はい | いいえ、エンドポイント間でオーディオのみを中継する | 
世界中のインスタンスと場所の数 | 10 合計: 米国東部と西部の 2 つ。アムステルダムとダブリンの 2;香港とシンガポールの 2;日本の 2;オーストラリア東部と南東部の 2 | 複数のユーザー

IP 範囲は次のとおりです。
- 52.112.0.0/14 (52.112.0.1 から 52.115.255.254 の IP アドレス)
- 52.120.0.0/14 (52.120.0.1 から 52.123.255.254 の IP アドレス)

\* トランスコードの説明: 

- メディア プロセッサは B2BUA です。つまり、コーデック (たとえば、TEAMS クライアントから MP に SILK、MP と SBC の間で G.711) を変更できます。

- トランスポート リレーは B2BUA ではありません。つまり、リレー経由でトラフィックが流れる場合でも、クライアントと SBC の間でコーデックが変更される可能性はありません。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>メディア バイパス用にトランクが構成されている場合の Teams Media Processors の使用

Teams Media Processors は、次のシナリオで常にメディア パスに挿入されます。

- 呼び出しが 1:1 からグループ呼び出しにエスカレートされます
- フェデレーション Teams ユーザーへの呼び出し
- Skype for Business ユーザーに転送または転送される通話

以下で説明するように、SBC が Media Processors および Transport Relay の範囲にアクセスできます。    


## <a name="sip-signaling-fqdns"></a>SIP シグナリング: FQDN

SIP シグナリングの場合、FQDN とファイアウォールの要件はバイパスされていない場合と同じです。 

ダイレクト ルーティングは、次の Microsoft 365 または 365 Officeで提供されます。
- Microsoft 365 または Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD GCC、GCC High、DoD など、Office [365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) および米国政府機関環境の詳細を確認します。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN – 最初に試す必要があります。 SBC がこの名前を解決するための要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。 割り当ては、データセンターのパフォーマンス メトリックと SBC への地理的な近接性に基づいて行われます。 返される IP アドレスは、プライマリ FQDN に対応します。

- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に 2 番目の優先度のリージョンにマップされます。

- **sip3.pstnhub.microsoft.com** – ターシャリ FQDN – 地理的に 3 番目の優先順位のリージョンにマップされます。

次の手順を実行するには、次の 3 つの FQDN を配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込まれ少なく、最初の FQDN を照会して割り当てられた SBC データセンターに最も近い)。

- SBC から一時的な問題が発生しているデータセンターへの接続が確立された場合は、フェールオーバーを提供します。 詳細については、以下の「フェールオーバー メカニズム」を参照してください。


FQDN **sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、** およびsip3.pstnhub.microsoft.com は、次のいずれかの IP アドレスに解決されます。
- 52.114.148.0
- 52.114.132.46
- 52.114.16.74
- 52.114.20.29
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。 ファイアウォールで DNS 名がサポートされている場合、FQDN **sip-all.pstnhub.microsoft.com** すべての IP アドレスに解決されます。 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。 365 DoD Officeは米国のデータ センターにのみ存在しますが、セカンダリ FQDN とターシャリー FQDN はありません。

FQDN – sip.pstnhub.dod.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。

- 52.127.64.33
- 52.127.68.34

これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.dod.teams.microsoft.us これらの IP アドレスすべてに解決されます。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 GCC High 環境は米国のデータ センターにのみ存在しますので、セカンダリ FQDN とターシャリ FQDN はありません。

FQDN – sip.pstnhub.gov.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。

- 52.127.88.59
- 52.127.92.64

これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us すべての IP アドレスに解決されます。 

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

ポート要件は、ダイレクト ルーティングが提供Office 365 環境で同じです。
- Microsoft 365 または Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

次のポートを使用する必要があります。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP プロキシ | SBC | 1024 - 65535 | SBC で定義されている |
| SIP/TLS | SBC | SIP プロキシ | SBC で定義されている | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>メディア トラフィック: IP とポートの範囲

直接接続が利用可能な場合、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合は、Teams トランスポート リレーを介して、SBC と Teams クライアントの間でメディア トラフィックが流れます。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>直接メディア トラフィックの要件 (Teams クライアントと SBC の間) 

クライアントは、SBC のパブリック IP アドレス上の指定されたポート (表を参照) にアクセスできる必要があります。 

> [!NOTE]
> クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに流れます。 NAT デバイスでヘア ピン留めを構成して、トラフィックがエンタープライズ ネットワーク機器から離れなくなじむのを行います。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | クライアント | SBC | 50 000 – 50 019  | SBC で定義されている |
| UDP/SRTP | SBC | クライアント | SBC で定義されている | 50 000 – 50 019  |


> [!NOTE]
> クライアントのソース ポートを変換するネットワーク デバイスがある場合は、ネットワーク機器と SBC の間で翻訳されたポートが開いているか確認してください。 

### <a name="requirements-for-using-transport-relays"></a>トランスポート リレーを使用する場合の要件

トランスポート リレーは、Media Processors と同じ範囲です (バイパス以外の場合)。 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

- 52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

- 52.127.88.0/21


Teams トランスポート リレー (すべての環境に適用) のポート範囲を次の表に示します。


| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | トランスポート リレー | SBC | 50 000 -59 999    | SBC で定義されている |
| UDP/SRTP | SBC | トランスポート リレー | SBC で定義されている | 50 000 – 59 999, 3478, 3479     |


> [!NOTE]
> Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートをお勧めします。 Microsoft には 2 つのバージョンのトランスポート リレーが含まれていますので、次が必要です。
> 
> - v4:ポート範囲 50 000 ~ 59 999 でのみ動作可能
> 
> - ポート 3478、3479 で動作する v6

現時点では、メディア バイパスは v4 バージョンのトランスポート リレーのみをサポートしています。 今後、v6 のサポートを紹介します。 

移行するには、ポート 3478 と 3479 を開く必要があります。 Microsoft が Media Bypass を使用した v6 トランスポート リレーのサポートを導入した場合、ネットワーク機器や SBC を再構成する必要が生じかねない。 

### <a name="requirements-for-using-media-processors"></a>メディア プロセッサを使用する場合の要件

メディア プロセッサは、音声アプリケーションと Web クライアント (Edge や Google Chrome の Teams クライアントなど) のメディア パスに常にあります。 要件は、バイパス以外の構成と同じです。


メディア トラフィックの IP 範囲は次の通り 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 および Office 365 GCC 環境

- 52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

- 52.127.88.0/21

メディア プロセッサ (すべての環境に適用) のポート範囲を次の表に示します。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | メディア プロセッサ | SBC | 3478、3479、49 152 – 53 247    | SBC で定義されている |
| UDP/SRTP | SBC | メディア プロセッサ | SBC で定義されている | 3478、3479、49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>メディア バイパスと非メディア バイパス用に個別のトランクを構成する  

メディア バイパス以外からメディア バイパスに移行し、すべての使用状況をメディア バイパスに移行する前に機能を確認する場合は、別のトランクを作成し、メディア バイパス トランクにルーティングし、特定のユーザーに割り当てる個別のオンライン 音声ルーティング ポリシーを作成できます。 

高レベルの構成手順:

- メディア バイパスをテストするユーザーを識別します。

- 異なる FQDN を持つ 2 つの独立したトランクを作成します。1 つはメディア バイパスに対して有効になっています。もう 1 つではありません。 

  両方のトランクが同じ SBC を指します。 TLS SIP シグナリングのポートは異なる必要があります。 メディアのポートは同じである必要があります。

- 新しいオンライン 音声ルーティング ポリシーを作成し、このポリシーの PSTN 使用法に関連付けられている対応するルートにメディア バイパス トランクを割り当てる。

- メディア バイパスをテストするために識別したユーザーに新しいオンライン 音声ルーティング ポリシーを割り当てる。

次の例は、このロジックを示しています。

| ユーザーのセット | ユーザー数 | OVRP で割り当てられたトランク FQDN | メディア バイパスが有効 |
| :------------ |:----------------- |:--------------|:--------------|
メディア以外のバイパス トランクを持つユーザー | 980 | sbc1.contoso.com:5061 | false |
メディア バイパス トランクを持つユーザー | 20 | sbc2.contoso.com:5060 | true | 

両方のトランクは、同じパブリック IP アドレスを持つ同じ SBC を指します。 次の図に示すように、SBC の TLS シグナリング ポートは異なっている必要があります。 証明書が両方のトランクをサポートしている必要があります。 SAN では、2 つの名前 **(sbc1.contoso.com** と sbc2.contoso.com) を持 **つ** か、ワイルドカード証明書が必要です。

> [!div class="mx-imgBorder"]
> ![両方のトランクが同じパブリック IP を持つ同じ SBC を指し示す](media/direct-routing-media-bypass-7.png)

同じ SBC で 2 つのトランクを構成する方法については、SBC ベンダーが提供するドキュメントを参照してください。

 - [AudioCodes のデプロイに関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle のデプロイに関するドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボン コミュニケーションの展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) のデプロイに関するドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>メディア バイパスでサポートされるクライアント エンドポイント

メディア バイパスは、すべてのスタンドアロン Teams デスクトップ クライアント、Android および iOS クライアント、Teams Phone Devices でサポートされます。 

メディア バイパスをサポートしていない他のすべてのエンドポイントでは、バイパス呼び出しとして開始された場合でも、呼び出しを非バイパスに変換します。 これは自動的に実行され、管理者からのアクションは必要とされません。 これには、Skype for Business 3PIP Phones と、ダイレクト ルーティング呼び出し (Microsoft Edge、Google Chrome、Mozilla Firefox で実行されている WebRTC ベースのクライアント) をサポートする Teams Web クライアントが含まれます。 
 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングでメディア バイパスを構成する](direct-routing-configure-media-bypass.md)
