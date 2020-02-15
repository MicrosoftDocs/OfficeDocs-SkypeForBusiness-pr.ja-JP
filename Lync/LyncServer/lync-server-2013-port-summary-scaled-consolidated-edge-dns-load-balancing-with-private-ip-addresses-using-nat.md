---
title: 'Lync Server 2013: ポートの概要-拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96bf91dfaf4d231ec64ce1b385983f63b15ee0b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>ポートの概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-04_

このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。 最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。 Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。

IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。 わかりやすいように、シナリオでは IPv4 のみを使用します。

**NAT を使用して拡張統合エッジとプライベート IP アドレスを使用するためのエンタープライズ境界ネットワーク**

![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。

エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a>拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 外部インターフェイス–ノード1およびノード 2 (例)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>役割/プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</p></td>
<td><p>XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</p></td>
<td><p>任意</p></td>
<td><p>XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先にトラフィックを送信します。</p></td>
</tr>
<tr class="odd">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>証明書の失効/CRL のチェックおよび取得</p></td>
</tr>
<tr class="even">
<td><p>アクセス/DNS/TCP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>TCP による DNS クエリ</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/DNS/UDP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>UDP による DNS クエリ</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="odd">
<td><p>Web 会議/PSOM (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバー Web 会議エッジサービス</p></td>
<td><p>Web 会議メディア</p></td>
</tr>
<tr class="even">
<td><p>音声/V/RTP/TCP/50,000-59999</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</p></td>
</tr>
<tr class="even">
<td><p>音声/V/RTP/TCP/50,000-59999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。 Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>STUN/UDP による候補の TURN ネゴシエーション/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a>拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 内部インターフェイス–ノード1およびノード 2 (例)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意 (フロントエンドサーバーのアドレス、または XMPP ゲートウェイサービスを実行しているフロントエンドプールの IP アドレスとして定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイスの IP アドレス</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>(ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレスからの) エッジサーバーの内部インターフェイスへの送信 SIP トラフィック</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの ip アドレス)</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任意 (フロントエンドサーバーの IP アドレスとして、またはフロントエンドプール内の各フロントエンドサーバーの IP アドレスとして定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>フロントエンドサーバーまたはプール内の各フロントエンドサーバーからエッジサーバーの内部インターフェイスへの Web 会議トラフィック</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任意 (フロントエンドサーバーの IP アドレス、または中央管理ストアを保持するプールとして定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>中央管理ストアからエッジ サーバーへの変更のレプリケーション</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>フェデレーションのファイアウォールの概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>役割/プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>アクセス エッジ サービス パブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>役割/プロトコル/TCP または UDP/ポート</th>
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
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>クライアント</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>音声/V/RTP/TCP/50,000-59999</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続では必須</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービス</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続では必須</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>XMPP のファイアウォールの概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/TCP または UDP/ポート</th>
<th>送信元 (IP アドレス)</th>
<th>宛先 (IP アドレス)</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。 フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。 エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意</p></td>
<td><p>各内部エッジサーバーインターフェイス IP</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから、エッジサーバーの内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部 XMPP トラフィック</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

