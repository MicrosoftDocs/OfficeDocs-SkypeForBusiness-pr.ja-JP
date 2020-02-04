---
title: ポートの概要 - NAT を使用したプライベート IP アドレスを含む単一統合エッジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a425a07bf5ff615fb4766d50f21c6467512d110e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>ポートの概要 - Lync Server 2013 の NAT を使用したプライベート IP アドレスを含む単一統合エッジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-04-03_

このシナリオアーキテクチャで説明されている Lync Server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されたものとよく似ています。 最も顕著な追加機能は、拡張メッセージングとプレゼンスプロトコル (XMPP) の TCP エントリのポート**5269**です。 Lync Server 2013 では、必要に応じて、microsoft Edge サーバーまたはエッジプールに XMPP プロキシを展開し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイサーバーを配置します。

IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。 わかりやすくするために、シナリオでは IPv4 のみが使用されます。

**NAT を使用するプライベート IP アドレスが指定された単一の統合エッジサーバーのネットワーク境界線**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

外部アクセスを提供する機能をサポートするために必要なポートのみを開くことをお勧めします。

エッジサービスに対してリモートアクセスを使用するには、受信/送信エッジトラフィックの図に示すように、SIP トラフィックが双方向に流れるようにすることが必須です。 別の方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声/ビデオ (A/V)、およびフェデレーションに関連しています。

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a>NAT を使用してプライベート IP アドレスを持つ単一の統合エッジのファイアウォールの概要: 外部インターフェイス

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>証明書の失効/CRL の確認と取得</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>TCP 経由の DNS クエリ</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>UDP 経由の DNS クエリ</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続の場合</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーアクセスエッジサービス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続の場合</p></td>
</tr>
<tr class="even">
<td><p>Web 会議/PSOM (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバー Web 会議エッジサービス</p></td>
<td><p>Web 会議メディア</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/59,999</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行しているパートナーとのフェデレーションに必要。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/59,999</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>任意</p></td>
<td><p>3478送信は、Lync Server が通信するエッジサーバーのバージョンと、エッジサーバーからエッジサーバーへのメディアトラフィックも確認するために使用されます。 Lync Server 2010、Windows Live Messenger、Office Communications Server 2007 R2 とのフェデレーション、および複数のエッジプールが会社内に展開されている場合に必要です。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>TCP/443 経由での候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/443</p></td>
<td><p>エッジサーバーの A/V Edge サービス</p></td>
<td><p>任意</p></td>
<td><p>TCP/443 経由での候補のネゴシエーションをオフ/オンにする</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a>NAT を使用してプライベート IP アドレスを持つ単一の統合エッジのファイアウォールの概要: 内部インターフェイス

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
<td><p>Any (標準エディションサーバー IP、Standard Edition server IP アドレス、または XMPP ゲートウェイサービスを実行しているプール IP アドレスとして定義できます)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
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

