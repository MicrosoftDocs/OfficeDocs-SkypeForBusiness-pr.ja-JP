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
description: メディア トラフィックのパスを短くし、パフォーマンスを向上できる電話システム ダイレクト ルーティングを使用してメディア バイパスを計画する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd31a62bf6ebcd481a3cdafeabaf29bb4767f2d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115595"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>ダイレクト ルーティングでメディア バイパスを計画する

## <a name="about-media-bypass-with-direct-routing"></a>ダイレクト ルーティングを使用したメディア バイパスについて

メディア バイパスを使用すると、メディア トラフィックのパスを短くし、送信中のホップ数を減らしてパフォーマンスを向上させることができます。 メディア バイパスを使用すると、Microsoft Phone System 経由で送信する代わりに、メディアはセッション ボーダー コントローラー (SBC) とクライアントの間に保持されます。 メディア バイパスを構成するには、SBC とクライアントが同じ場所またはネットワークにある必要があります。

各 SBC のメディア バイパスを制御するには **、-MediaBypass** パラメーターを true または false に設定して **Set-CSOnlinePSTNGateway** コマンドを使用します。 メディア バイパスを有効にしても、すべてのメディア トラフィックが企業ネットワーク内に残るという意味ではありません。 この記事では、さまざまなシナリオでのコール フローについて説明します。    

次の図は、メディア バイパスの場合とない場合のコール フローの違いを示しています。

次の図に示すように、メディア バイパスなしで、クライアントが通話を行う場合や受信するときに、SBC、Microsoft Phone System、Teams クライアント間のシグナリングとメディア フローの両方を行います。

> [!div class="mx-imgBorder"]
> ![メディア バイパスなしのシグナリングとメディア フローを示す](media/direct-routing-media-bypass-1.png)


ただし、ユーザーが SBC と同じ建物またはネットワークにいます。 たとえば、一部の場所にいたユーザーが Pstn ユーザーに対して通話を発信するとします。 

- **メディア バイパスを使用しない** 場合、メディアは、アムステルダムまたはダブリン (Microsoft データセンターが展開されている場所) を経由してメディアが流れ、その後、しずけの SBC に戻されます。 

  ヨーロッパのデータセンターは、SBC がヨーロッパに存在し、Microsoft が SBC に最も近いデータセンターを使用するために選択されます。 この方法は、ほとんどの地域で Microsoft ネットワーク内のトラフィック フローの最適化のために通話品質に影響しませんが、トラフィックには不必要なループがあります。     

- **メディア バイパスを使用** すると、次の図に示すように、メディアは Teams ユーザーと SBC の間に直接保持されます。

  > [!div class="mx-imgBorder"]
  > ![メディア バイパスによるシグナリングとメディア フローの表示](media/direct-routing-media-bypass-2.png)

メディア バイパスは、Teams クライアント上の Interactive Connectivity Connectivity(ICE) と呼ばれるプロトコルと SBC の ICE lite を利用します。 これらのプロトコルを使用すると、ダイレクト ルーティングで最適な品質を得る最適なメディア パスを使用できます。 ICE と ICE Lite は WebRTC 標準です。 これらのプロトコルの詳細については、RFC 5245 を参照してください。


## <a name="call-flow-and-firewall-planning"></a>コール フローとファイアウォールの計画

コール フローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうか、およびユーザーがネットワークの内部か外部かによって異なります。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合のコール フロー

ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、コール フローは次のようになります。

- メディア バイパスの場合、Teams クライアントは内部ネットワークからでも SBC のパブリック IP アドレスにアクセスできる必要があります。 直接メディアが必要ない場合、メディアはトランスポート リレー経由で流れる可能性があります。

- これは、ユーザーが SBC と同じ建物またはネットワーク上にある場合に推奨されるソリューションです。メディア パスから Microsoft Cloud コンポーネントを削除します。

- シグナリングは常に Microsoft クラウド経由で流れます。

次の図は、メディア バイパスが有効になっている場合、クライアントが内部であり、クライアントが SBC (直接メディア) のパブリック IP アドレスに到達できる場合のコール フローを示しています。 

- パスの矢印と数値は、Microsoft Teams のコール フロー [に準拠しています](./microsoft-teams-online-call-flows.md)。

- SIP シグナリングは常にパス 4 と 4' を受け取ります (トラフィックの方向に応じて異なる)。 メディアはローカルのままで、パス 5b を受け取る。

> [!div class="mx-imgBorder"]
> ![メディア バイパスが有効になっている通話フロー、クライアントが内部である](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコール フロー

次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコール フローについて説明します。 

たとえば、ユーザーが外部ユーザーであり、テナント管理者が SBC のパブリック IP アドレスをインターネット上のすべてのユーザーに対して開くのではなく、Microsoft Cloud にのみ開くことを決定したとします。 トラフィックの内部コンポーネントは、Teams トランスポート リレーを介してフローできます。 次の状況について検討しましょう。

- Teams トランスポート リレーが使用されます。

- メディア バイパスの場合、Microsoft は、Teams トランスポート リレーと SBC の間にポート 50 000 から 59 999 を開く必要があるトランスポート リレーのバージョンを使用します (今後、3478 ポートと 3479 ポートのみを必要とするバージョンに移行する予定です)。


次の図は、メディア バイパスが有効になっている場合、クライアントが外部であり、クライアントがセッション ボーダー コントローラーのパブリック IP アドレスに到達できない場合のコール フローを示しています (メディアは Teams トランスポート リレーによって中継されます)。

- パスの矢印と数値は、Microsoft Teams のコール フロー [に準拠しています](./microsoft-teams-online-call-flows.md)。

- メディアは、パス 3、3'、4、4' を介して中継されます。

> [!div class="mx-imgBorder"]
> ![ユーザーが SBC のパブリック IP にアクセスできない場合のコール フローを示す](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>ユーザーがネットワークの外にいて、SBC のパブリック IP にアクセスできる場合のコール フロー

> [!NOTE]
> これは、Teams トランスポート リレーを利用しないので、推奨される構成ではありません。 代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを検討する必要があります。 

次の図は、メディア バイパスが有効になっている場合、クライアントが外部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合のコール フローを示しています。

- パスの矢印と数値は [、Microsoft Teams](./microsoft-teams-online-call-flows.md) のコール フロー記事に従っています。

- SIP シグナリングは常にパス 3 と 3' を受け取ります (トラフィックの方向に応じて異なる)。 パス 2 を使用したメディア フロー。

> [!div class="mx-imgBorder"]
> ![ユーザーが SBC のパブリック IP にアクセスできない場合のコール フローを示す](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>メディア プロセッサとトランスポート リレーの使用

メディア トラフィックのパスに含み得る、メディア プロセッサとトランスポート リレーの 2 つのコンポーネントが Microsoft Cloud に含まれています。 

- メディア プロセッサは、バイパスしないケースでメディアを処理し、音声アプリケーション用のメディアを処理する一般向けのコンポーネントです。

   メディア プロセッサは常に、エンド ユーザーのバイパスされていない呼び出しのパスに入っていますが、バイパスされた呼び出しのパスには入ってこない。 メディア プロセッサは常に、コール パーク、組織の管理、通話キューなどのすべての音声自動応答パスにあります。

- トランスポート リレーは、リアルタイム トラフィックを送信するために最も近いトランスポート サービスに接続するために使用されます。

   トランスポート リレーは、ユーザーの場所とネットワークの構成方法に応じて、バイパスされた通話 (発信元またはエンド ユーザー宛て) のパス内にある場合とない場合があります。

次の図は、2 つのコール フローを示しています。1 つはメディア バイパスが有効で、もう 1 つはメディア バイパスが無効になっています。 この図は、エンド ユーザーから送信されるトラフィックまたは宛先のユーザーのみを示しています。  
- メディア コントローラーは、メディア プロセッサを割り当て、SDP (Session Description Protocol) オファーを作成する Azure のマイクロサービスです。

- SIP プロキシは、Teams で使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。    

> [!div class="mx-imgBorder"]
> ![メディア バイパスが有効または無効になっているコール フローを示す](media/direct-routing-media-bypass-6.png)


次の表は、メディア プロセッサとトランスポート リレーの違いをまとめた表です。

|    | メディア プロセッサ | トランスポート リレー|
| :--------------|:---------------|:------------|
エンド ユーザーのバイパスされていない呼び出しのメディア パス内 | いつも | クライアントがメディア プロセッサに直接到達できない場合 | 
エンド ユーザーのバイパス呼び出しのメディア パス | ぜんぜん | クライアントがパブリック IP アドレスで SBC に到達できない場合 | 
音声アプリケーションのメディア パス内 | いつも | ぜんぜん | 
コード変換を実行できる (B2BUA)\* | はい | いいえ、エンドポイント間のオーディオのみを中継します | 
世界中のインスタンスの数と場所 | 合計 10: 米国東部と西部で 2。2 in Dublin and Dublin;香港とシンガポールの 2。日本の 2 ;オーストラリア東部と東南部の 2 | 倍数

IP 範囲は次のとおりです。
- 52.112.0.0/14 (52.112.0.1 から 52.115.255.254 の IP アドレス)
- 52.120.0.0/14 (52.120.0.1 から 52.123.255.254 の IP アドレス)

\* コード変換の説明: 

- Media Processor は B2BUA です。つまり、コーデックを変更できます (たとえば、SILK を Teams クライアントから MP と G.711 に MP と SBC の間で変更できます)。

- トランスポート リレーは B2BUA ではありません。つまり、リレー経由でトラフィックが流れる場合でも、クライアントと SBC の間でコーデックが変更される必要はありません。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>トランクがメディア バイパス用に構成されている場合の Teams メディア プロセッサの使用

Teams Media Processors は、次のシナリオでは常にメディア パスに挿入されます。

- 通話は 1:1 からグループ通話にエスカレートされます
- フェデレーション Teams ユーザーへの通話の実行
- 通話が Skype for Business ユーザーに転送または転送される

以下で説明するように、SBC がメディア プロセッサとトランスポート リレーの範囲にアクセスできる必要があります。    


## <a name="sip-signaling-fqdns"></a>SIP シグナリング: FQDN

SIP シグナリングの場合、FQDN とファイアウォールの要件はバイパスされていないケースの場合と同じです。 

直接ルーティングは、次の Microsoft 365 または 365 環境Office提供されます。
- Microsoft 365 または Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD では、GCC、GCC High、DoD などの [Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) および米国政府機関の環境の詳細について確認できます。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。

- **sip.pstnhub.microsoft.com** – グローバル FQDN - 最初に試す必要があります。 SBC からこの名前を解決するための要求が送信された場合、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。 この割り当ては、データセンターのパフォーマンスメトリックと SBC への地理的近接性に基づいて行われます。 返される IP アドレスはプライマリ FQDN に対応します。

- **sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に第 2 の優先度の地域にマップされます。

- **sip3.pstnhub.microsoft.com** – 優先 FQDN – 第 3 の優先度の地域に地理的にマップされます。

次の 3 つの FQDN を配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込まれ少なく、最初の FQDN にクエリを実行して割り当てられた SBC データセンターに最も近い)。

- SBC から一時的な問題が発生しているデータセンターへの接続が確立された場合は、フェールオーバーを提供します。 詳細については、以下のフェールオーバー メカニズムを参照してください。


FQDN sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.comは、次のいずれかのIP アドレスに解決されます。
- 52.114.148.0
- 52.114.132.46
- 52.114.16.74
- 52.114.20.29
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。 ファイアウォールで DNS 名がサポートされている場合 **、FQDN** sip-all.pstnhub.microsoft.com すべての IP アドレスに解決されます。 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。 Office 365 DoD 環境は米国のデータ センターにのみ存在し、第 2 および第 3 の FQDN はありません。

FQDN – sip.pstnhub.dod.teams.microsoft.us 次のいずれかの IP アドレスに解決されます。

- 52.127.64.33
- 52.127.68.34

シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。  ファイアウォールが DNS 名をサポートしている場合、FQDN sip.pstnhub.dod.teams.microsoft.us これらの IP アドレスすべてに解決されます。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

ダイレクト ルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。 GCC High 環境は米国のデータ センターにのみ存在しますが、第 2 および第 3 の FQDN はありません。

FQDN – sip.pstnhub.gov.teams.microsoft.us 次のいずれかの IP アドレスに解決されます。

- 52.127.88.59
- 52.127.92.64

シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us IP アドレスはすべて解決されます。 

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

ポート要件は、ダイレクト ルーティングが提供Office 365 のすべての環境で同じです。
- Microsoft 365 または Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

次のポートを使用する必要があります。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP プロキシ | SBC | 1024 - 65535 | SBC で定義 |
| SIP/TLS | SBC | SIP プロキシ | SBC で定義 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>メディア トラフィック: IP とポートの範囲

直接接続が使用可能な場合、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合、メディア トラフィックは SBC と Teams クライアントの間で流れます。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>直接メディア トラフィックの要件 (Teams クライアントと SBC の間) 

クライアントは、SBC のパブリック IP アドレスで指定されたポート (表を参照) にアクセスできる必要があります。 

注: クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに流れます。 トラフィックがエンタープライズ ネットワーク機器から離れるのを決してしない、NAT デバイスでのヘア ピン留めを構成できます。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | クライアント | SBC | 50 000 – 50 019  | SBC で定義 |
| UDP/SRTP | SBC | クライアント | SBC で定義 | 50 000 – 50 019  |


> [!NOTE]
> クライアントのソース ポートを翻訳するネットワーク デバイスがある場合は、ネットワーク機器と SBC の間で翻訳されたポートが開いているか確認してください。 

### <a name="requirements-for-using-transport-relays"></a>トランスポート リレーを使用する場合の要件

トランスポート リレーはメディア プロセッサと同じ範囲内です (バイパス以外のケースの場合): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365、Office 365 GCC 環境

- 52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21


Teams トランスポート リレー (すべての環境に適用) のポート範囲を次の表に示します。


| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | トランスポート リレー | SBC | 50 000 -59 999    | SBC で定義 |
| UDP/SRTP | SBC | トランスポート リレー | SBC で定義 | 50 000 – 59 999, 3478, 3479     |


> [!NOTE]
> Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートを推奨しています。 Microsoft には 2 つのバージョンのトランスポート リレーが含まれていますので、次の手順が必要です。
> 
> - v4:ポート範囲 50 000 ~ 59 999 でのみ動作する
> 
> - v6(ポート 3478、3479 で動作)

現時点では、メディア バイパスは v4 バージョンのトランスポート リレーのみをサポートしています。 今後、v6 のサポートを導入する予定です。 

移行するには、ポート 3478 と 3479 を開く必要があります。 Microsoft がメディア バイパスを使用した v6 トランスポート リレーのサポートを導入する場合、ネットワーク機器や SBC を再構成する必要は一方で、必要な動作ではありません。 

### <a name="requirements-for-using-media-processors"></a>メディア プロセッサを使用する場合の要件

メディア プロセッサは、音声アプリケーションと Web クライアント (Edge や Google Chrome の Teams クライアントなど) のメディア パスに常にあります。 要件は、バイパス以外の構成の場合と同じです。


メディア トラフィックの IP 範囲は次の通り 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 および Office 365 GCC 環境

- 52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21

メディア プロセッサ (すべての環境に適用) のポート範囲を次の表に示します。

| トラフィック | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | メディア プロセッサ | SBC | 3478、3479、49 152 – 53 247    | SBC で定義 |
| UDP/SRTP | SBC | メディア プロセッサ | SBC で定義 | 3478、3479、49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>メディア バイパスと非メディア バイパス用に個別のトランクを構成する  

メディア バイパス以外からメディア バイパスに移行し、すべての使用をメディア バイパスに移行する前に機能を確認する場合は、個別のトランクを作成し、別のオンライン 音声ルーティング ポリシーを作成してメディア バイパス トランクにルーティングし、特定のユーザーに割り当てすることができます。 

高レベルの構成手順:

- メディア バイパスをテストするユーザーを特定します。

- 異なる FQDN を持つ 2 つの個別のトランクを作成します。1 つはメディア バイパスに対して有効です。もう 1 つではありません。 

  両方のトランクが同じ SBC を指します。 TLS SIP シグナリングのポートは異なる必要があります。 メディアのポートは同じである必要があります。

- 新しいオンライン 音声ルーティング ポリシーを作成し、このポリシーの PSTN 使用状況に関連付けられている対応するルートにメディア バイパス トランクを割り当てる。

- メディア バイパスをテストするために識別したユーザーに新しいオンライン音声ルーティング ポリシーを割り当てる。

次の例は、このロジックを示しています。

| 一連のユーザー | ユーザー数 | OVRP で割り当てられたトランク FQDN | メディア バイパス有効 |
| :------------ |:----------------- |:--------------|:--------------|
メディア以外のバイパス トランクを持つユーザー | 980 | sbc1.contoso.com:5060 | true
メディア バイパス トランクを使用するユーザー | 20 | sbc2.contoso.com:5061 | false | 

両方のトランクが、同じパブリック IP アドレスを持つ同じ SBC をポイントできます。 次の図に示すように、SBC 上の TLS シグナリング ポートは異なる必要があります。 証明書が両方のトランクをサポートしている必要があります。 SAN では、2 つの名前 **(sbc1.contoso.com** と **sbc2.contoso.com)** を持つか、ワイルドカード証明書を持っている必要があります。

> [!div class="mx-imgBorder"]
> ![両方のトランクが同じパブリック IP で同じ SBC をポイントできる](media/direct-routing-media-bypass-7.png)

同じ SBC で 2 つのトランクを構成する方法については、SBC ベンダーが提供するドキュメントを参照してください。

 - [AudioCodes 展開ドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle の展開に関するドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンコミュニケーションの展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) 展開ドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>メディア バイパスでサポートされるクライアント エンドポイント

メディア バイパスは、スタンドアロンのすべての Teams デスクトップ クライアント、Android および iOS クライアント、および Teams の電話デバイスでサポートされます。 

メディア バイパスをサポートしていない他のすべてのエンドポイントでは、バイパス呼び出しとして開始された場合でも、通話をバイパス以外に変換します。 これは自動的に行われます。管理者からの操作は必要とされません。 これには、Skype for Business 3PIP 電話機、および直接ルーティング呼び出しをサポートする Teams Web クライアント (Microsoft Edge、Google Chrome、Mozilla Firefox で実行されている WebRTC ベースのクライアント) が含まれます。 
 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングでメディア バイパスを構成する](direct-routing-configure-media-bypass.md)