---
title: ポートの概要 - 拡張統合エッジ (ロード バランサー機器を使用)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>ポートの概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-04-27_

このシナリオアーキテクチャで説明されている Lync Server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されたものとよく似ています。 最も顕著な追加機能は、拡張メッセージングとプレゼンスプロトコル (XMPP) の TCP エントリのポート**5269**です。 Lync Server 2013 では、必要に応じて、microsoft Edge サーバーまたはエッジプールに XMPP プロキシを展開し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイサーバーを配置します。

IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。 わかりやすくするために、シナリオでは IPv4 のみが使用されます。

**ハードウェア負荷分散を使用した拡大縮小エッジ**

![エッジサーバーの境界ネットワークのポートとプロトコル](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "エッジサーバーの境界ネットワークのポートとプロトコル")

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

外部アクセスを提供する機能をサポートするために必要なポートのみを開くことをお勧めします。

エッジサービスに対してリモートアクセスを使用するには、受信/送信エッジトラフィックの図に示すように、SIP トラフィックが双方向に流れるようにすることが必須です。 別の方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声/ビデオ (A/V)、およびフェデレーションに関連しています。

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>スケーリングされた統合エッジのファイアウォールの概要: ハードウェア負荷分散: ノード1とノード 2 (例)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>エッジサーバーアクセスエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>証明書の失効/CRL の確認と取得</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>TCP 経由の DNS クエリ</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>UDP 経由の DNS クエリ</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/59,999</p></td>
<td><p>エッジサーバー A/V Edge サービス IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行しているパートナーとのフェデレーションに必要。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/59,999</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック IP アドレス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック IP アドレス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>3478送信は、Lync Server が通信するエッジサーバーのバージョンと、エッジサーバーからエッジサーバーへのメディアトラフィックも確認するために使用されます。 Lync Server 2010、Windows Live Messenger、Office Communications Server 2007 R2 とのフェデレーション、および複数のエッジプールが会社内に展開されている場合に必要です。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック IP アドレス</p></td>
<td><p>UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック IP アドレス</p></td>
<td><p>TCP/443 経由での候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/443</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>TCP/443 経由での候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>スケーリングされた統合エッジのファイアウォールの概要、ハードウェア負荷分散: 内部インターフェイスノード1とノード2

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (フロントエンドサーバーアドレスとして定義可能、または XMPP ゲートウェイサービスを実行するフロントエンドプール仮想 IP アドレス)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (任意) (中央管理ストアを保持するフロントエンドサーバーサーバーの IP またはプールとして定義できます)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>中央管理ストアからエッジサーバーへの変更のレプリケーション</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (ディレクター IP、フロントエンドサーバー IP またはプール仮想 IP として定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>内部展開から内部のエッジサーバーインターフェイスへの Web 会議トラフィック</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Any (ディレクター IP、フロントエンドサーバー IP またはプール仮想 IP として定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>内部と外部のユーザー、Survivable Branch Appliance または Survivable ブランチサーバー間の A/V メディア転送の優先パス</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/443</p></td>
<td><p>Any (ディレクター IP、フロントエンドサーバー IP またはプール仮想 IP として定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>内部と外部のユーザーとの間でのメディア転送のフォールバックパス Survivable Branch Appliance または Survivable Branch Server (UDP 通信が確立できない場合は、TCP を使ってファイル転送とデスクトップ共有を行う)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</p></td>
</tr>
</tbody>
</table>


ハードウェアロードバランサーを展開するときに、Lync Server の可用性と負荷分散を提供するための特定の要件があります。 要件は、次の図と表で定義されています。 サードパーティベンダーは、ここで定義されている要件について別の用語を使用する場合があります。 Lync Server の要件を、ハードウェアロードバランサーのベンダーから提供されている機能と構成オプションにマップする必要があります。

ハードウェアロードバランサーを構成する場合は、次の要件を考慮してください。

  - ソースネットワークアドレス変換 (SNAT) を、Access Edge サービスおよび Web 会議エッジサービスのハードウェアロードバランサー (HLB) で構成することができます。

  - SNAT を A/V Edge サービスで構成することはできません。 A/V Edge サービスは、UDP 経由の単純なトラバーサル (STUN)、または relay NAT (TURN) を使用したトラバーサル (FTURN) で正常に動作するように、実際のサーバーアドレスに応答する必要があります。
    
      - クライアントが HLB に要求を送信した場合、応答は HLB VIP から返される必要があります。
    
      - クライアントが要求をエッジに送信した場合、応答はエッジ IP から返される必要があります。

  - パブリック IP アドレスは、各サーバーインターフェイスと HLB の Vip で使用され、パブリック ip アドレスの要件は、それぞれの実際のサーバーインターフェイスのパブリック IP アドレスと、各 HLB VIP 用に1つずつ使用されます。 プール内に2台のエッジサーバーがある場合、この結果、3つのパブリック IP アドレスが作成されます。ここでは、3は HLB Vip として、3は各エッジサーバーインターフェイスに対して使います (サーバーの場合は合計 6)。

  - クライアントは、アクセスエッジサービスおよび Web 会議エッジサービス (および HLB で NAT を使う) について、VIP に接続して、クライアントのソース IP アドレスをクライアントの IP アドレスに変更します。 サーバーインターフェイスは、VIP に対して差出人住所を解決し、VIP によってサーバーインターフェイスの IP アドレスからソースアドレスが変更され、パケットがクライアントに送信されます。

  - A/V Edge サービスの場合、VIP はソースの IP アドレスを変更してはなりません。実際のサーバーのアドレスはクライアントに直接返され、AV トラフィック用に HLB で NAT を構成することはできません。
    
      - クライアントが HLB VIP に要求を送信した場合、応答は HLB VIP から返される必要があります。
    
      - クライアントが要求をエッジ IP に送信した場合、応答はエッジ IP から返される必要があります。

  - AV の場合、外部ファイアウォールは、すべてのパケットに対して実際のサーバーのパブリック IP アドレスを保持します。

  - 確立されたクライアントから A/V Edge サービス通信は、HLB ではなく、実際のサーバーに対して行われます。

  - 内部サーバーとクライアント間の内部境界はルーティングされる必要があり、サーバーまたはクライアントをホストするすべての内部ネットワークに対して固定ルートが設定されます。

  - HLB Access Edge service VIP は、各エッジサーバーインターフェイスの既定のゲートウェイとして機能します。

<div>


> [!NOTE]
> NAT の計画と機能の詳細については、「 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 のハードウェアロードバランサーの要件</A>」を参照してください。



</div>

![エッジサーバーのポートとプロトコルの詳細](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "エッジサーバーのポートとプロトコルの詳細")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>スケーリングされた統合エッジに必要な外部ポート設定、ハードウェア負荷分散: 外部インターフェイス仮想 Ip

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</p></td>
<td><p>XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先からのトラフィックを受け入れます。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</p></td>
<td><p>任意</p></td>
<td><p>XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP の連絡先にトラフィックを送信します。</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>アクセスエッジサービスのパブリック VIP アドレス</p></td>
<td><p>外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>アクセスエッジサービスのパブリック VIP アドレス</p></td>
<td><p>Sip を使用した SIP シグナリング、フェデレーションおよびパブリック IM 接続</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>アクセスエッジサービスのパブリック VIP アドレス</p></td>
<td><p>フェデレーションパートナー</p></td>
<td><p>Sip を使用した SIP シグナリング、フェデレーションおよびパブリック IM 接続</p></td>
</tr>
<tr class="even">
<td><p>Web 会議/PSOM (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバー Web 会議エッジサービスのパブリック VIP アドレス</p></td>
<td><p>Web 会議メディア</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック VIP アドレス</p></td>
<td><p>UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V エッジサービスのパブリック VIP アドレス</p></td>
<td><p>TCP/443 経由での候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>スケーリングされた統合エッジのファイアウォールの概要: ハードウェア負荷分散: 内部インターフェイス仮想 Ip

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>Any (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレスとして定義できます)</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>送信 SIP トラフィック (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバーまたはフロントエンドプールの仮想 IP アドレス) から内部エッジ VIP へ</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>Any (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレスとして定義できます)</p></td>
<td><p>エッジサーバーの内部インターフェイスから受信 SIP トラフィック (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレス)</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (フロントエンドサーバーの IP アドレス、またはこのエッジサーバーを使用している Survivable Branch Appliance または Survivable ブランチサーバー) として定義することができます。</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>このエッジサーバーを使用して、フロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは Survivable Branch Appliance または Survivable ブランチサーバーからの、A/V ユーザー (A/V 認証サービス) の認証</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>内部と外部のユーザー間の A/V メディア転送の優先パス</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>内部と外部のユーザーとの間でのメディア転送のフォールバックパス UDP 通信を確立できない場合、TCP がファイル転送とデスクトップ共有に使用されます。</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/443</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>任意</p></td>
<td><p>内部と外部のユーザーとの間でのメディア転送のフォールバックパス UDP 通信を確立できない場合、TCP がファイル転送とデスクトップ共有に使用されます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

