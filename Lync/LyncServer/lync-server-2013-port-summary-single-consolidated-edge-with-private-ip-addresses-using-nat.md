---
title: 'Lync Server 2013: ポートの概要 - NAT を使用したプライベート IP アドレスを含む単一統合エッジ'
TOCTitle: ポートの概要 - NAT を使用したプライベート IP アドレスを含む単一統合エッジ
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48271827
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ポートの概要 - Lync Server 2013 の NAT を使用したプライベート IP アドレスを含む単一統合エッジ

 

_**トピックの最終更新日:** 2015-03-09_

このシナリオ アーキテクチャで説明されている Lync Server 2013エッジ サーバー機能は、Lync Server 2010 で実装されていた機能とよく似ています。最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用のポート **5269/TCP** エントリが追加されたことです。Lync Server 2013 は、必要に応じて、XMPP プロキシを エッジ サーバーまたは エッジ プールに展開し、XMPP ゲートウェイ サーバーを フロント エンド サーバーまたは フロント エンド プールに展開します。

エッジ サーバーでは、IPv4 に加えて IPv6 もサポートされるようになりました。わかりやすいように、シナリオでは IPv4 のみを使用します。

**NAT を使用したプライベート IP アドレスを含む単一統合エッジ サーバーのネットワーク境界**

![単一統合エッジ サーバー](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "単一統合エッジ サーバー")

## ポートとプロトコルの詳細

外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。

エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。

### NAT を使用したプライベート IP アドレスを含む単一統合エッジのファイアウォールの概要: 外部インターフェイス

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
<td><p>XMPP プロキシ サービス (アクセス エッジ サービスと IP アドレスを共有)</p></td>
<td><p>XMPP プロキシ サービスは、定義済みの XMPP フェデレーションの XMPP 連絡先からのトラフィックを受け付ける</p></td>
</tr>
<tr class="even">
<td><p>アクセス/HTTP/TCP/80</p></td>
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>任意</p></td>
<td><p>証明書の失効/CRL のチェックおよび取得</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/DNS/TCP/53</p></td>
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>任意</p></td>
<td><p>TCP による DNS クエリ</p></td>
</tr>
<tr class="even">
<td><p>アクセス/DNS/UDP/53</p></td>
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>任意</p></td>
<td><p>UDP による DNS クエリ</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="even">
<td><p>Web 会議/PSOM (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー Web 会議エッジ サービス</p></td>
<td><p>Web 会議メディア</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/RTP/TCP/50,000 ～ 59,999</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行するパートナーとのフェデレーション時に必要です。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/RTP/UDP/50,000 ～ 59,999</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007 を実行するパートナーとのフェデレーションにのみ必要です。</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/RTP/TCP/50,000 ～ 59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>Office Communications Server 2007 を実行するパートナーとのフェデレーションにのみ必要です。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/RTP/UDP/50,000 ～ 59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>Office Communications Server 2007 を実行するパートナーとのフェデレーションにのみ必要です。</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>任意</p></td>
<td><p>3478 送信は、Lync Server が通信しているエッジ サーバーのバージョンの確認に使用され、エッジ サーバーと エッジ サーバーのメディア トラフィックにも使用されます。Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションで必要なほかに、社内に複数の エッジ プールが展開されている場合に必要です。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>STUN/UDP による候補の TURN ネゴシエーション/3478</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/STUN、MSTURN/TCP/443</p></td>
<td><p>エッジ サーバー音声ビデオ エッジ サービス</p></td>
<td><p>任意</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
</tbody>
</table>


### NAT を使用したプライベート IP アドレスを含む単一統合エッジのファイアウォールの概要: 内部インターフェイス

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
<td><p>任意 (XMPP ゲートウェイ サービスを実行している Standard Edition サーバー IP、Standard Edition サーバー IP アドレス、またはプール IP アドレスとして定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>フロント エンド サーバーまたは フロント エンド プールで実行されている XMPP ゲートウェイ サービスからの発信 XMPP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>任意 (ディレクター、ディレクター プール IP アドレス、フロント エンド サーバー、または フロント エンド プール IP アドレスとして定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>(ディレクター、ディレクター プール IP アドレス、フロント エンド サーバー、または フロント エンド プール IP アドレスから) エッジ サーバー内部インターフェイスへの送信 SIP トラフィック</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>任意 (ディレクター、ディレクター プール IP アドレス、フロント エンド サーバー、または フロント エンド プール IP アドレスとして定義可能)</p></td>
<td><p>エッジ サーバー内部インターフェイスから (ディレクター、ディレクター プール IP アドレス、フロント エンド サーバー、または フロント エンド プール IP アドレスへの) 受信 SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任意 (フロント エンド サーバー IP アドレス、または フロント エンド プール内の各 フロント エンド サーバー IP アドレスとして定義可能)</p>
<p></p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>フロント エンド サーバーまたは各 フロント エンド サーバー (プール内の場合) から エッジ サーバーの内部インターフェイスへの Web 会議トラフィック</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任意 (この エッジ サーバーを使用して、フロント エンド サーバーの IP アドレスまたは フロント エンド プールの IP アドレス、あるいは任意の 存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーとして定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>フロント エンド サーバーまたは フロント エンド プール IP アドレス、あるいはこの エッジ サーバーを使用した任意の 存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーからの音声ビデオ ユーザーの認証 (音声ビデオ認証サービス)</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>内部ユーザーと外部ユーザー、存続可能ブランチ アプライアンス、または 存続可能ブランチ サーバーとの間の音声ビデオ メディア転送の優先パス</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>UDP 通信を確立できない場合の、内部ユーザーと外部ユーザー、存続可能ブランチ アプライアンス、または 存続可能ブランチ サーバーとの間の音声ビデオ メディア転送のフォールバック パス、TCP はファイル転送およびデスクトップ共有に使用</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任意 (フロント エンド サーバー IP アドレス、または 中央管理ストアを保持するプールとして定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>中央管理ストアから エッジ サーバーへの変更のレプリケーション</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルおよび 集中ログ サービス コマンドレットを使用した 集中ログ サービス コントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルおよび 集中ログ サービス コマンドレットを使用した 集中ログ サービス コントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルおよび 集中ログ サービス コマンドレットを使用した 集中ログ サービス コントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
</tbody>
</table>


## フェデレーションのファイアウォールの概要


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
<td><p>アクセス エッジ サービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
</tbody>
</table>


## ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続


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
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>クライアント</p></td>
<td><p>エッジ サーバー アクセス エッジ サービス</p></td>
<td><p>外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/RTP/TCP/50,000 ～ 59,999</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続では必須</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービス</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続では必須</p></td>
</tr>
</tbody>
</table>


## XMPP のファイアウォールの概要


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
<td><p>エッジ サーバー  アクセス エッジ サービス インターフェイス IP アドレス</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。フェデレーション XMPP パートナーから エッジ サーバー XMPP プロキシへの通信を可能にします。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>エッジ サーバー  アクセス エッジ サービス インターフェイス IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。 エッジ サーバー XMPP プロキシからフェデレーション XMPP パートナーへの通信を可能にします。</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意</p></td>
<td><p>各内部 エッジ サーバー インターフェイス IP</p></td>
<td><p>フロント エンド サーバーまたは フロント エンド プールの XMPP ゲートウェイから エッジ サーバー内部 IP アドレスあるいは各 エッジ プール メンバーの内部 IP アドレスへの内部 XMPP トラフィック</p></td>
</tr>
</tbody>
</table>

