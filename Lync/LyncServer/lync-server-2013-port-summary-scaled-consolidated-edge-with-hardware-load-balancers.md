---
title: ポートの概要-拡張統合エッジ (ロードバランサー機器を使用)
description: ポートの概要-拡張統合エッジ (ロードバランサー機器を使用)。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564593"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>ポートの概要-Lync Server 2013 の拡張統合エッジ (ロードバランサー機器を含む)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-04-27_

このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。 最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。 Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。

IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。 わかりやすいように、シナリオでは IPv4 のみを使用します。

**ハードウェア負荷分散を使用する拡張統合エッジ**

![エッジサーバー境界ネットワークのポートとプロトコル](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "エッジサーバー境界ネットワークのポートとプロトコル")

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。

エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>拡張統合エッジのファイアウォールの概要 (ハードウェア負荷分散): 外部インターフェイス–ノード1およびノード 2 (例)

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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>エッジサーバーアクセスエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>証明書の失効/CRL のチェックおよび取得</p></td>
</tr>
<tr class="even">
<td><p>アクセス/DNS/TCP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>TCP による DNS クエリ</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/DNS/UDP/53</p></td>
<td><p>エッジサーバーアクセスエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>UDP による DNS クエリ</p></td>
</tr>
<tr class="even">
<td><p>音声/V/RTP/TCP/50,000-59999</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスの IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</p></td>
</tr>
<tr class="even">
<td><p>音声/V/RTP/TCP/50,000-59999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</p></td>
<td><p>Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。 Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</p></td>
<td><p>STUN/UDP による候補の TURN ネゴシエーション/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>拡張統合エッジのファイアウォールの概要ハードウェア負荷分散: ノード1およびノード2の内部インターフェイス

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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意 (フロントエンドサーバーのアドレス、または XMPP ゲートウェイサービスを実行しているフロントエンドプールの仮想 IP アドレスとして定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任意 (中央管理ストアを保持するフロントエンドサーバーサーバーの IP またはプールとして定義可能)</p></td>
<td><p>エッジ サーバー内部インターフェイス</p></td>
<td><p>中央管理ストアからエッジ サーバーへの変更のレプリケーション</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任意 (ディレクター IP、フロントエンドサーバー IP またはプールの仮想 IP として定義可能)</p></td>
<td><p>エッジ サーバー内部インターフェイス</p></td>
<td><p>内部展開から内部エッジ サーバー インターフェイスへの Web 会議トラフィック</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意 (ディレクター IP、フロントエンドサーバー IP またはプールの仮想 IP として定義可能)</p></td>
<td><p>エッジ サーバー内部インターフェイス</p></td>
<td><p>内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意 (ディレクター IP、フロントエンドサーバー IP またはプールの仮想 IP として定義可能)</p></td>
<td><p>エッジ サーバー内部インターフェイス</p></td>
<td><p>内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</p></td>
</tr>
</tbody>
</table>


ハードウェアロードバランサーを展開する場合は、Lync Server の可用性と負荷分散を実現するための特定の要件があります。 要件は、次の図と表で定義されています。 サードパーティベンダーは、ここで定義されている要件に関して異なる用語を使用する場合があります。 Lync Server の要件を、ロードバランサー機器ベンダーが提供する機能および構成オプションにマップする必要があります。

ロードバランサー機器を構成する場合は、次の要件を考慮してください。

  - ソースネットワークアドレス変換 (SNAT) は、アクセスエッジサービスと Web 会議エッジサービスのハードウェアロードバランサー (HLB) で構成できます。

  - 音声ビデオエッジサービスで SNAT を構成することはできません。音声ビデオエッジサービスは、UDP over NAT (STUN) を使用した実際のサーバーアドレスではなく、(仮想 IP) を使用して応答する必要があります。これは、リレー NAT (TURN) と federation TURN (FTURN) を使用して正しく動作します。
    
      - クライアントが HLB に要求を送信する場合、応答は HLB VIP から返される必要があります。
    
      - クライアントがエッジに要求を送信する場合、応答はエッジ IP から返される必要があります。

  - パブリック IP アドレスは、各サーバーインターフェイスおよび HLB の Vip で使用され、パブリック ip アドレスの要件は、各 real サーバーインターフェイスにパブリック IP アドレスがあり、各 HLB VIP に対して1つずつ使用される N + 1 です。 プールに2台のエッジサーバーがある場合、この値は9個のパブリック IP アドレスになります。ここでは、HLB Vip に3を使用し、各エッジサーバーインターフェイス (サーバーの合計 6) に対して1つを使用します。

  - アクセスエッジサービスと Web 会議エッジサービス (および HLB で NAT を使用して) は、クライアントが VIP に接続するため、VIP はクライアントの送信元 IP アドレスを自身の IP アドレスに変更します。 サーバーインターフェイスは、VIP への復帰アドレスに対応します。 VIP は、サーバーインターフェイスの IP アドレスから送信元のアドレスを変更して、クライアントにパケットを送信します。

  - 音声ビデオエッジサービスでは、VIP がソース IP アドレスを変更しないで、実際のサーバーアドレスが直接クライアントに返されるので、AV トラフィック用に HLB で NAT を構成することはできません
    
      - クライアントが HLB VIP に要求を送信する場合、応答は HLB VIP から返される必要があります。
    
      - クライアントがエッジ IP に要求を送信する場合、応答はエッジ IP から返される必要があります。

  - AV の場合、外部ファイアウォールはすべてのパケットに対して実際のサーバーのパブリック IP アドレスを保持します。

  - 確立されると、HLB ではなく、クライアントから音声ビデオエッジサービスの通信が実際のサーバーに対して行われます。

  - 内部エッジから内部サーバーとクライアントをルーティングする必要があり、サーバーまたはクライアントをホストするすべての内部ネットワークに対して固定ルートが設定されている。

  - HLB アクセスエッジサービス VIP は、各エッジサーバーインターフェイスの既定のゲートウェイとして機能します。

<div>


> [!NOTE]
> NAT の計画および機能の詳細については、「 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 のハードウェアロードバランサーの要件</A>」を参照してください。



</div>

![エッジサーバーのポートとプロトコルの詳細](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "エッジサーバーのポートとプロトコルの詳細")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>拡張統合エッジに必要な外部ポートの設定: ハードウェア負荷分散: 外部インターフェイスの仮想 Ip

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
<th>Notes</th>
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
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>アクセスエッジサービスのパブリック VIP アドレス</p></td>
<td><p>外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>アクセスエッジサービスのパブリック VIP アドレス</p></td>
<td><p>Sip を使用した SIP 信号、フェデレーション、パブリック IM 接続</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>アクセスエッジサービスのパブリック VIP アドレス</p></td>
<td><p>フェデレーションパートナー</p></td>
<td><p>Sip を使用した SIP 信号、フェデレーション、パブリック IM 接続</p></td>
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
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック VIP アドレス</p></td>
<td><p>STUN/UDP による候補の TURN ネゴシエーション/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの音声ビデオエッジサービスのパブリック VIP アドレス</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>拡張統合エッジのファイアウォールの概要ハードウェア負荷分散: 内部インターフェイスの仮想 Ip

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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意 (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレスとして定義可能)</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>送信 SIP トラフィック (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバーまたはフロントエンドプールの仮想 IP アドレス) から内部エッジ VIP へ</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>任意 (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレスとして定義可能)</p></td>
<td><p>エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレス)</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送の優先パス</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>UDP 通信を確立できない場合の内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送のフォールバック パス、TCP はファイル転送およびデスクトップ共有に使用</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>エッジサーバーの内部 VIP インターフェイス</p></td>
<td><p>任意</p></td>
<td><p>UDP 通信を確立できない場合の内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送のフォールバック パス、TCP はファイル転送およびデスクトップ共有に使用</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

