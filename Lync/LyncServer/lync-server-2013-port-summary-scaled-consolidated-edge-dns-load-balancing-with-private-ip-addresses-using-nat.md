---
title: 'Lync Server 2013: ポートの概要 - 拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>ポートの概要 - Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-04_

このシナリオアーキテクチャで説明されている Lync Server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されたものとよく似ています。 最も顕著な追加機能は、拡張メッセージングとプレゼンスプロトコル (XMPP) の TCP エントリのポート**5269**です。 Lync Server 2013 では、必要に応じて、microsoft Edge サーバーまたはエッジプールに XMPP プロキシを展開し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイサーバーを配置します。

IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。 わかりやすくするために、シナリオでは IPv4 のみが使用されます。

**NAT を使用する統合エッジ用のエンタープライズ境界ネットワークとプライベート IP アドレス**

![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

外部アクセスを提供する機能をサポートするために必要なポートのみを開くことをお勧めします。

エッジサービスに対してリモートアクセスを使用するには、受信/送信エッジトラフィックの図に示すように、SIP トラフィックが双方向に流れるようにすることが必須です。 別の方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声/ビデオ (A/V)、およびフェデレーションに関連しています。

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a>拡張統合エッジの場合のファイアウォールの概要、NAT を使用したプライベート IP アドレスを使った DNS 負荷分散: ノード1とノード 2 (例)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>証明書の失効/CRL の確認と取得</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>TCP 経由の DNS クエリ</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>UDP 経由の DNS クエリ</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続の場合</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続の場合</p></td>
</tr>
<tr class="odd">
<td><p>Web 会議/PSOM (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバー Web 会議エッジサービス</p></td>
<td><p>Web 会議メディア</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/59,999</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行しているパートナーとのフェデレーションに必要。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/59,999</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>任意</p></td>
<td><p>3478送信は、Lync Server が通信するエッジサーバーのバージョンと、エッジサーバーからエッジサーバーへのメディアトラフィックも確認するために使用されます。 Lync Server 2010、Windows Live Messenger、Office Communications Server 2007 R2 とのフェデレーション、および複数のエッジプールが会社内に展開されている場合に必要です。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>TCP/443 経由での候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/443</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>任意</p></td>
<td><p>TCP/443 経由での候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a>拡大縮小された統合エッジのファイアウォールの概要: 内部インターフェイス–ノード1とノード 2 (例) のプライベート IP アドレスを使った DNS 負荷分散

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (フロントエンドサーバーアドレスとして定義可能、または XMPP ゲートウェイサービスを実行するフロントエンドプール IP アドレス)</p></td>
<td><p>エッジサーバーの内部インターフェイス IP アドレス</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>送信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレス) からエッジサーバーの内部インターフェイスへ</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</p></td>
<td><p>エッジサーバーの内部インターフェイスから受信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレス)</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (フロントエンドサーバーの IP アドレス、またはフロントエンドプールの各フロントエンドサーバー IP アドレスとして定義できます)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>フロントエンドサーバーからの Web 会議トラフィック、またはプール内の各フロントエンドサーバーから Edge Server の内部インターフェイスへの Web 会議トラフィック</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (フロントエンドサーバーの IP アドレス、またはこのエッジサーバーを使用している Survivable Branch Appliance または Survivable ブランチサーバー) として定義することができます。</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>このエッジサーバーを使用して、フロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは Survivable Branch Appliance または Survivable ブランチサーバーからの、A/V ユーザー (A/V 認証サービス) の認証</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>内部と外部のユーザー、Survivable Branch Appliance または Survivable ブランチサーバー間の A/V メディア転送の優先パス</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>内部と外部のユーザーとの間でのメディア転送のフォールバックパス Survivable Branch Appliance または Survivable Branch Server (UDP 通信が確立できない場合は、TCP を使ってファイル転送とデスクトップ共有を行う)</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (任意) (フロントエンドサーバーの IP アドレス、または全体管理ストアを保持するプールとして定義できます)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>中央管理ストアからエッジサーバーへの変更のレプリケーション</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>フェデレーションのためのファイアウォールの概要


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
<td><p>アクセスエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続の場合</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>ファイアウォールの概要–パブリックインスタントメッセージング接続


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
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続の場合</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続の場合</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>クライアント</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/59,999</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>パブリック IM 接続が構成されている場合、Windows Live Messenger でのセッションに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続に必要</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続に必要</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>拡張メッセージングとプレゼンスプロトコルのファイアウォールの概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol/TCP または UDP/ポート</th>
<th>ソース (IP アドレス)</th>
<th>宛先 (IP アドレス)</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</p></td>
<td><p>XMPP 向けの標準的なサーバー間通信ポート。 フェデレーションされた XMPP パートナーからエッジサーバーの XMPP プロキシへの通信を許可します。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>XMPP 向けの標準的なサーバー間通信ポート。 エッジサーバーの XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意</p></td>
<td><p>各内部エッジサーバーインターフェイス IP</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから Edge Server 内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部の XMPP トラフィック</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

