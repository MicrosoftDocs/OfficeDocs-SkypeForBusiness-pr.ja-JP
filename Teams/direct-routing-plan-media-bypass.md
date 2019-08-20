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
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: このトピックでは、電話システムのダイレクトルーティングを使用してメディアのバイパスを計画する方法について説明します。
ms.openlocfilehash: a6f13b8f7db767d8a6a16f8f4493f15aeed9af38
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464592"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>ダイレクト ルーティングでメディア バイパスを計画する

## <a name="about-media-bypass-with-direct-routing"></a>ダイレクトルーティングによるメディアのバイパスについて

メディアのバイパスにより、メディアトラフィックのパスを短縮し、転送中のホップの数を減らしてパフォーマンスを向上させることができます。 メディアをバイパスすると、メディアは、Microsoft 電話システム経由で送信されるのではなく、セッション境界コントローラー (SBC) とクライアントの間で保持されます。 メディアバイパスを構成するには、SBC とクライアントが同じ場所またはネットワーク内にある必要があります。

**Mediabypass**コマンドを使用して、各**** SBC のメディアのバイパスを制御することができます。 メディアのバイパスを有効にすると、すべてのメディアトラフィックが企業ネットワーク内に収まるというわけではありません。 この記事では、さまざまなシナリオでのコールフローについて説明します。    

以下の図は、メディアのバイパスを含む、または含まれていない通話フローの違いを示しています。

メディアのバイパスがない場合、クライアントが通話を発信または受信したときに、次の図に示すように、SBC、Microsoft 電話システム、および Teams クライアント間のシグナリングとメディアフローの両方が行われます。

![メディアバイパスのないシグナリングとメディアフローを示す](media/direct-routing-media-bypass-1.png)


ただし、ユーザーが SBC と同じ建物またはネットワーク内にあることを前提としてみましょう。 たとえば、Frankfurt で建物内にいるユーザーが PSTN ユーザーに電話をかけるとします。 

- メディアがバイパスされて**いない**場合、メディアはアムステルダムまたはダブリン (Microsoft データセンターが展開されている場所) で、FRANKFURT の SBC に戻ります。 

  ヨーロッパのデータセンターが選択されているため、Microsoft は SBC に最も近いデータセンターを使用しています。 ほとんどの地域では、Microsoft ネットワーク内でのトラフィックフローの最適化による通話品質には影響ありませんが、トラフィックには不要なループがあります。     

- **メディアをバイパスすると**、次の図に示すように、Teams ユーザーと SBC の間でメディアが直接保持されます。

![メディアバイパスによるシグナリングとメディアフローを示しています](media/direct-routing-media-bypass-2.png)

メディアのバイパスでは、SBC の Teams クライアントと ICE lite で対話型接続確立 (ICE) と呼ばれるプロトコルを使用します。 これらのプロトコルでは、最適な音質を実現するために、ダイレクトルーティングで最も直接的なメディアパスを使うことができます。 ICE および ICE Lite は WebRTC 標準です。 これらのプロトコルの詳細については、RFC 5245 を参照してください。


## <a name="call-flow-and-firewall-planning"></a>コールフローとファイアウォールの計画

コールフローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうか、およびユーザーがネットワークの内外にいるかどうかによって異なります。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合のコールフロー

ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、通話フローは次のようになります。

- メディアバイパスの場合、チームクライアントは、内部ネットワークからでも、SBC のパブリック IP アドレスにアクセスできる必要があります。 ダイレクトメディアが必要でない場合、メディアはトランスポートリレー経由で流れることができます。

- これは、ユーザーが同じ建物またはネットワークにあるときに、SBC –メディアパスから Microsoft Cloud コンポーネントを削除する場合に推奨される解決策です。

- シグナリングは、常に Microsoft cloud 経由でフローします。

次の図は、メディアのバイパスが有効になっている場合、クライアントが内部であり、クライアントが SBC (ダイレクトメディア) のパブリック IP アドレスに到達した場合のコールフローを示しています。 

- パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)の記事に従っています。

- SIP シグナリングには、常にパス4と 4 (トラフィックの方向によって異なります) があります。 メディアはローカルのままでパス5b を受け取ります。

![メディアのバイパスが有効になっている、クライアントが内部のコールフローを示しています](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコールフロー

次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコールフローについて説明します。 

たとえば、ユーザーが外部であることを前提としていますが、テナント管理者は、インターネット上のすべてのユーザーに、SBC のパブリック IP アドレスを開くことはできません。ただし、Microsoft Cloud のみです。 トラフィックの内部コンポーネントは、Teams トランスポートリレー経由で流れることができます。 これは、企業ネットワークの外部のユーザーに推奨される構成です。 次の点に注意してください。

- Teams トランスポートリレーが使用されます。

- メディアのバイパスの場合、Microsoft は、チームトランスポートリレーと SBC の間でポート 50 000 59 999 を開く必要があるトランスポートリレーのバージョン (将来は、3478と3479のポートのみを必要とするバージョンに移行する予定です) を使用しています。

- メディアの最適化のため、Microsoft は、SBC のパブリック IP アドレスを Teams トランスポートリレーにのみ開くことをお勧めします。 企業ネットワークの外部にいるクライアントの場合、Microsoft は、SBC のパブリック IP アドレスに直接アクセスする代わりに、トランスポートリレーを使用することをお勧めします。

次の図は、メディアのバイパスが有効になっている場合、クライアントは外部であり、クライアントはセッションの境界コントローラーのパブリック IP アドレスに到達できないことを示しています (メディアは Teams トランスポートリレーによって中継されます)。

- パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)の記事に従っています。

- メディアは、3、3、4、4というパスで中継されます。

![ユーザーが SBC のパブリック IP へのアクセス権を持っていない場合のコールフローを示します。](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>ユーザーがネットワーク外であり、SBC のパブリック IP にアクセスできる場合のコールフロー

> [!NOTE]
> これは、Teams トランスポートリレーを利用していないため、推奨される構成ではありません。 代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを考慮する必要があります。 

次の図は、メディアのバイパスが有効になっている場合、クライアントが外部であり、クライアントが SBC (ダイレクトメディア) のパブリック IP アドレスに到達できる場合のコールフローを示しています。

- パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)の記事に従っています。

- SIP シグナリングは、常にパス3と 3 (トラフィックの方向によって異なります) を受け取ります。 パス2を使用したメディアフロー。

![ユーザーが SBC のパブリック IP へのアクセス権を持っていない場合のコールフローを示します。](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>メディアプロセッサとトランスポートリレーの使用

メディアトラフィックのパスには、メディアプロセッサとトランスポートリレーという2つのコンポーネントがあります。 

- メディアプロセッサは、非バイパスのケースでメディアを処理し、ボイスアプリケーションのメディアを処理するパブリックなフェーシングコンポーネントです。

   メディアプロセッサは、常にエンドユーザーの非バイパス呼び出しのパスにありますが、バイパス呼び出しのパスには含まれません。 メディアプロセッサは、コールパーク、組織の自動応答、通話キューなど、すべての音声アプリケーションのパスに常に含まれています。

- トランスポートリレーは、リアルタイムトラフィックを送信するために最も近いトランスポートサービスに接続するために使われます。

   トランスポート中継は、ユーザーがどこにいるかによって、またはエンドユーザーがどのように構成されているかに応じて、バイパスされた通話のパスに含まれている場合とできない場合があります。

次の図は、2つのコールフローを示しています。メディアのバイパスが有効で、もう1つはメディアバイパスが無効になっています。 注図には、エンドユーザーからのトラフィックのみが示されます。  
- メディアコントローラーは、メディアプロセッサを割り当て、セッション記述プロトコル (SDP) オファーを作成する Azure のマイクロサービスです。

- SIP プロキシは、チームで使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。    

![メディアバイパスを有効または無効にしたコールフローを表示します](media/direct-routing-media-bypass-6.png)


以下の表は、メディアプロセッサとトランスポートリレーの違いをまとめたものです。

|    | メディアプロセッサ | トランスポートリレー|
| :--------------|:---------------|:------------|
エンドユーザーへの非バイパス呼び出しのメディアパス | いつも | ぜんぜん | 
エンドユーザーに対してバイパスされる通話のメディアパス | ぜんぜん | クライアントがパブリック IP アドレスの SBC に到達できない場合 | 
ボイスアプリケーションのメディアパス | いつも | ぜんぜん | 
コード変換を実行できる (B2BUA)\* | はい | いいえ、エンドポイント間の音声のみを中継します | 
ワールドワイドおよび場所のインスタンス数 | 8合計: 米国東部および西での22 (アムステルダムとダブリン)香港およびシンガポールでの2日本の 2 (Q1CY2019 に追加されています)  | 多数

IP 範囲は 52.112.0.0/14 (IP アドレスは52.112.0.1 から 52.115.255.254) です。 

\*コード変換の説明: 

- メディアプロセッサは B2BUA であることを意味します。つまり、SILK (Teams クライアントの場合は、MP と SBC の間の mp と G) に変更できます。

- トランスポートリレーは B2BUA ではありません。つまり、リレー経由でトラフィックが流れる場合でも、クライアントと SBC の間でコーデックが変更されることはありません。

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>メディアバイパス用にトランクが構成されている場合のエスカレーションシナリオでの Teams トランスポートリレーの使用

Teams トランスポートリレーは、次のシナリオでは常にメディアパスにあります。

- 通話は1:1 からグループ通話にエスカレートされます
- フェデレーションされた Teams ユーザーに通話を発信する
- 通話が Skype for Business ユーザーに転送または転送される

以下で説明するように、SBC がトランスポートリレーにアクセスできることを確認します。    


## <a name="sip-signaling-fqdns"></a>SIP シグナリング: Fqdn

SIP シグナリングの場合、FQDN とファイアウォールの要件は、非バイパスのケースと同じです。 

直接ルーティングは、次の Office 365 環境で提供されます。
- Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD の詳細については、「GCC、GCC 高、DoD などの[office 365 および米国政府機関向けの環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)」を参照してください。

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 および Office 365 の GCC 環境

直接ルーティングの接続ポイントは、次の3つの Fqdn です。

- **sip.pstnhub.microsoft.com** –グローバル FQDN –最初に試す必要があります。 SBC がこの名前を解決するための要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure datacenter をポイントしている IP アドレスを返します。 課題は、データセンターのパフォーマンスメトリックと SBC への地理的な距離に基づいています。 返される IP アドレスは、プライマリ FQDN に対応しています。

- **sip2.pstnhub.microsoft.com** –セカンダリ FQDN –地理的に2番目の優先度の地域にマップされます。

- **sip3.pstnhub.microsoft.com** –第3の FQDN –地理的に3番目の優先度の地域にマップされます。

次のために、これらの3つの Fqdn を配置する必要があります。

- 最適なエクスペリエンスを提供します (読み込みが少なく、最初の FQDN を照会することによって割り当てられた SBC データセンターに最も近い)。

- 一時的な問題が発生しているデータセンターに対して SBC からの接続が確立された場合のフェールオーバーを提供します。 詳細については、以下の「フェールオーバーのメカニズム」をご覧ください。


Fqdn **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**、および**sip3.pstnhub.microsoft.com**は、次のいずれかの IP アドレスに解決されます。
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。 ファイアウォールで DNS 名がサポートされている場合、FQDN **sip-all.pstnhub.microsoft.com**はこれらのすべての IP アドレスに解決されます。 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

ダイレクトルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.dod.teams.microsoft.us** –グローバル FQDN。 Office 365 DoD 環境は US データセンターにのみ存在するため、第2および第3の Fqdn はありません。

Fqdn – sip.pstnhub.dod.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。

- 52.127.64.33
- 52.127.68.34

シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.dod.teams.microsoft.us はこれらのすべての IP アドレスに解決されます。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高環境

ダイレクトルーティングの接続ポイントは、次の FQDN です。

**sip.pstnhub.gov.teams.microsoft.us** –グローバル FQDN。 GCC 高環境は US データセンターにのみ存在するため、第2の Fqdn はありません。

Fqdn – sip.pstnhub.gov.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。

- 52.127.88.59
- 52.127.92.64

シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。  ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us はこれらのすべての IP アドレスに解決されます。 

## <a name="sip-signaling-ports"></a>SIP シグナリング: ポート

ダイレクトルーティングが提供されているすべての Office 365 環境では、ポート要件は同じです。
- Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

次のポートを使用する必要があります。

| 通過 | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP プロキシ | SBC | 1024-65535 | SBC で定義 |
| SIP/TLS | SBC | SIP プロキシ | SBC で定義 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>メディアトラフィック: IP とポートの範囲

直接接続が利用できるか、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合は、SBC と Teams クライアント間でメディアトラフィックが流れます。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>ダイレクトメディアトラフィック (Teams クライアントと SBC の間) の要件 

クライアントは、SBC のパブリック IP アドレスで指定されたポート (表を参照) にアクセスする必要があります。 

注: クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに送られます。 NAT デバイスで hairpinning を構成して、トラフィックが企業ネットワーク機器を離れることがないようにすることができます。

| 通過 | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | クライアント | SBC | 50 000 – 50 019  | SBC で定義 |
| UDP/SRTP | SBC | クライアント | SBC で定義 | 50 000 – 50 019  |


注: クライアントのソースポートを変換するネットワークデバイスがある場合は、ネットワーク機器と SBC の間で変換されたポートが開かれていることを確認してください。 

### <a name="requirements-for-using-transport-relays"></a>トランスポートリレーを使用するための要件

トランスポートリレーは、メディアプロセッサ (バイパス以外のケース) と同じ範囲にあります。 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 および Office 365 の GCC 環境

-52.112.0.0/14 (52.112.0.1 から52.115.255.254 への IP アドレス)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高環境

- 52.127.88.0/21


Teams トランスポートリレーのポート範囲 (すべての環境に適用されます) については、次の表を参照してください。


| 通過 | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | トランスポートリレー | SBC | 50 000-59 999    | SBC で定義 |
| UDP/SRTP | SBC | トランスポートリレー | SBC で定義 | 50 000 – 59 999、3478、3479     |


注: SBC では、同時通話ごとに少なくとも2つのポートが推奨されます。 Microsoft にはトランスポートリレーの2つのバージョンがあるため、次のものが必要です。

- v4 (ポート範囲 59 999 50 000 でのみ使用可能)

- v6 (ポート3478、3479と連携)

現時点では、メディアバイパスは、トランスポートリレーの v4 バージョンのみをサポートしています。 今後、v6 のサポートが導入される予定です。 

移行するには、ポート3478と3479を開く必要があります。 Microsoft がメディアバイパスでの v6 トランスポートリレーのサポートを導入する場合、ネットワーク機器または SBCs を再設定する必要はありません。 

### <a name="requirements-for-using-media-processors"></a>メディアプロセッサを使うための要件

メディアプロセッサは、常にボイスアプリケーションおよび Web クライアント (たとえば、エッジまたは Google Chrome の Teams クライアント) のメディアパスにあります。 要件は、非バイパス構成の場合と同じです。


メディアトラフィックの IP 範囲は 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 および Office 365 の GCC 環境

-52.112.0.0/14 (52.112.0.1 から52.115.255.254 への IP アドレス)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高環境

- 52.127.88.0/21

メディアプロセッサのポート範囲 (すべての環境に該当) を次の表に示します。

| 通過 | 開始 | 終了 | 送信元ポート | 宛先ポート|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | メディアプロセッサ | SBC | 49 152 – 53 247    | SBC で定義 |
| UDP/SRTP | SBC | メディアプロセッサ | SBC で定義 | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>ネットワークで Skype for Business 電話を使用している場合の考慮事項  

直接ルーティングを使用しているネットワーク内の Skype for Business エンドポイントがある場合、チームユーザーは、Skype for Business クライアントに基づく3PIP 電話を持つことができます。これらのユーザーに対応しているトランクでのメディアのバイパスは、無効にする必要があります。

これらのユーザーに対して個別のトランクを作成し、オンラインボイスルーティングポリシーを割り当てることができます。

高レベルの構成手順:

- ユーザーが3PIP 電話を使っているかどうかに応じて、種類によってユーザーを分割します。

- 異なる Fqdn を使用して2つの別個の trunks を作成します。1つはメディアバイパス用です。それ以外の場合は、 

  どちらの trunks も、同じ SBC をポイントします。 TLS SIP シグナリングのポートは異なっている必要があります。 メディアのポートは同じである必要があります。

- オンラインボイスルーティングポリシーのユーザのタイプに応じて、正しいトランクを割り当てます。

次の例は、このロジックを示しています。

| ユーザーのセット | ユーザー数 | "の順番で割り当てられたトランクの FQDN | メディアのバイパスを有効にする |
| :------------ |:----------------- |:--------------|:--------------|
Teams クライアントと3PIP 電話を使用するユーザー | 超える | sbc1.contoso.com:5061 | false | 
チームのエンドポイントのみを持つユーザー (Teams で認定された新しい電話を含む) | 980 | sbc2.contoso.com:5060 | true

どちらの trunks も、同じ SBC を同じパブリック IP アドレスで指すことができます。 次の図に示すように、SBC の TLS シグナリングポートは異なっている必要があります。 注: 証明書で trunks の両方がサポートされていることを確認する必要があります。 SAN では、2つの名前 (**sbc1.contoso.com**と**sbc2.contoso.com**) を使用するか、ワイルドカード証明書を持っている必要があります。


![両方の trunks が同じ SBC をポイントし、同じパブリック IP アドレスを持つことを示します。](media/direct-routing-media-bypass-7.png)

同じ SBC で2つの trunks を構成する方法については、SBC ベンダーから提供されているドキュメントを参照してください。

 - [AudioCodes の展開に関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 展開に関するドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンの通信展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE システム (anynode) の展開ドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>メディアバイパスでサポートされているクライアントエンドポイント

メディアのバイパスは、すべてのチームのエンドポイントでサポートされています。

注 web クライアント (Microsoft Edge、Google Chrome、Mozilla Firefox の Teams Web アプリ) では、バイパス呼び出しとして開始された場合でも、呼び出しを非バイパスに変換します。 これは自動的に行われるため、管理者からの操作は必要ありません。 
 
## <a name="see-also"></a>関連項目

[ダイレクト ルーティングでメディア バイパスを構成する](direct-routing-configure-media-bypass.md)



