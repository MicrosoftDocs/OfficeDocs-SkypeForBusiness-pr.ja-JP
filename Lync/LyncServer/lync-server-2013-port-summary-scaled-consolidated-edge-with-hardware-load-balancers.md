---
title: 'Lync Server 2013: ポートの概要 - 拡張統合エッジ (ロード バランサー機器を使用)'
TOCTitle: ポートの概要 - 拡張統合エッジ (ロード バランサー機器を使用)
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48272848
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ポートの概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)

 

_**トピックの最終更新日:** 2015-04-27_

このシナリオ アーキテクチャで説明されている Lync Server 2013 エッジ サーバー機能は、Lync Server 2010 で実装されていた機能とよく似ています。最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用のポート **5269/TCP** エントリが追加されたことです。Lync Server 2013 は、必要に応じて、XMPP プロキシを エッジ サーバーまたは エッジ プールに展開し、XMPP ゲートウェイ サーバーを フロント エンド サーバーまたは フロント エンド プールに展開します。

エッジ サーバーでは、IPv4 に加えて IPv6 もサポートされるようになりました。わかりやすいように、シナリオでは IPv4 のみを使用します。

**ロード バランサー機器を使用した拡張統合エッジ**

![エッジ サーバー境界ネットワークのポートおよびプロトコル](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "エッジ サーバー境界ネットワークのポートおよびプロトコル")

## ポートとプロトコルの詳細

外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。

エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、 アクセス エッジ サービスとの間で SIP メッセージングが実行されます。

### 拡張統合エッジ (ロード バランサー機器) のファイアウォールの概要: 外部インターフェイス - ノード 1 およびノード 2 (例)

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
<td><p>アクセス/HTTP/TCP/80</p></td>
<td><p>エッジ サーバー アクセス エッジ サービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>証明書の失効/CRL のチェックおよび取得</p></td>
</tr>
<tr class="even">
<td><p>アクセス/DNS/TCP/53</p></td>
<td><p>エッジ サーバー アクセス エッジ サービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>TCP による DNS クエリ</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/DNS/UDP/53</p></td>
<td><p>エッジ サーバー アクセス エッジ サービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>UDP による DNS クエリ</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/RTP/TCP/50,000 ～ 59,999</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービスの IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010、および Lync Server 2013 を実行するパートナーとのフェデレーション時に必要です。</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/RTP/UDP/50,000 ～ 59,999</p></td>
<td><p>エッジ サーバー音声ビデオ エッジ サービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>Office Communications Server 2007 を実行するパートナーとのフェデレーションにのみ必要です。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/RTP/TCP/50,000 ～ 59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー音声ビデオ エッジ サービスのパブリック IP アドレス</p></td>
<td><p>Office Communications Server 2007 を実行するパートナーとのフェデレーションにのみ必要です。</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/RTP/UDP/50,000 ～ 59,999</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー音声ビデオ エッジ サービスのパブリック IP アドレス</p></td>
<td><p>Office Communications Server 2007 を実行するパートナーとのフェデレーションにのみ必要です。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジ サーバー音声ビデオ エッジ サービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>3478 の発信は、 Lync Server の通信相手である エッジ サーバーのバージョンを判別するためと、 エッジ サーバーと エッジ サーバーのメディア トラフィックのために使用されます。 Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションで必要なほかに、社内に複数の エッジ プールが展開されている場合に必要です。</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー音声ビデオ エッジ サービスのパブリック IP アドレス</p></td>
<td><p>STUN/UDP による候補の TURN ネゴシエーション/3478</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー音声ビデオ エッジ サービスのパブリック IP アドレス</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/STUN、MSTURN/TCP/443</p></td>
<td><p>エッジ サーバー音声ビデオ エッジ サービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
</tbody>
</table>


### 拡張統合エッジ トポロジ (ロード バランサー機器) のファイアウォールの概要: 内部インターフェイス ノード 1 およびノード 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意 ( フロント エンド サーバー アドレス、または XMPP ゲートウェイ サービスを実行するプールの フロント エンド プール仮想 IP アドレスとして定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>フロント エンド サーバーまたは フロント エンド プールで実行されている XMPP ゲートウェイ サービスからの発信 XMPP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任意 ( 中央管理ストアを保持する フロント エンド サーバーのサーバー IP またはプールとして定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>中央管理ストアから エッジ サーバーへの変更のレプリケーション</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任意 ( ディレクター IP、 フロント エンド サーバー IP、またはプールの仮想 IP として定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>内部展開から内部 エッジ サーバー インターフェイスへの Web 会議トラフィック</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意 ( ディレクター IP、 フロント エンド サーバー IP、またはプールの仮想 IP として定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>内部ユーザーと外部ユーザー、 存続可能ブランチ アプライアンス、または 存続可能ブランチ サーバーとの間の音声ビデオ メディア転送の優先パス</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意 ( ディレクター IP、 フロント エンド サーバー IP、またはプールの仮想 IP として定義可能)</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>UDP 通信を確立できない場合の、内部ユーザーと外部ユーザー、 存続可能ブランチ アプライアンス、または 存続可能ブランチ サーバーとの間の音声ビデオ メディア転送のフォールバック パス、TCP はファイル転送およびデスクトップ共有に使用</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルおよび 集中ログ サービス コマンドレットを使用した 集中ログ サービス コントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルおよび 集中ログ サービス コマンドレットを使用した 集中ログ サービス コントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>Lync Server 管理シェルおよび 集中ログ サービス コマンドレットを使用した 集中ログ サービス コントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
</tbody>
</table>


ハードウェア ロード バランサーには、 Lync Server に可用性と負荷分散を提供する目的で展開する際に従う必要がある固有の要件があります。これらの要件を次の図と表に定義します。サード パーティ ベンダーでは、ここで定義する要件に別の用語を使用している場合があります。 Lync Server の要件を、ハードウェア ロード バランサーのベンダーが提供する機能と構成のオプションに対応付ける必要があります。

ハードウェア ロード バランサーを構成する場合は、以下の要件を考慮してください。

  - アクセス エッジ サービスと Web 会議エッジ サービス用のハードウェア ロード バランサー (HLB) で送信元ネットワーク アドレス変換 (SNAT) を構成できます。

  - 音声ビデオ エッジ サービスで SNAT を構成することはできません。Simple Traversal of UDP over NAT (STUN)/Traversal Using Relay NAT (TURN)/Federation TURN (FTURN) が正しく動作するためには、 音声ビデオ エッジ サービスが HLB の仮想 IP (VIP) ではなく実際のサーバー アドレスで応答する必要があります。

  - 各サーバー インターフェイスおよび HLB の VIP ではパブリック IP アドレスが使用されます。パブリック IP アドレスの要件は N+1 です。パブリック IP アドレスは、実際のサーバー インターフェイスごとに 1 つと、各 HLB VIP に 1 つ存在します。プール内のエッジ サーバーが 2 台の場合、パブリック IP アドレスは 9 つです。そのうちの 3 つは HLB VIP に使用され、エッジ サーバー インターフェイスごとに 1 つ (合計 6 つ) のアドレスが割り当てられます。

  - アクセス エッジ サービスと Web 会議エッジ サービスの場合、(および HLB では NAT を使用して) クライアントは VIP に接続し、VIP は送信元 IP アドレスをクライアントから固有の IP アドレスに変更します。サーバー インターフェイスは VIP への返信先アドレスを処理し、VIP は送信元アドレスをサーバー インターフェイスの IP アドレスから変更して、クライアントにパケットを送信します。

  - 音声ビデオ エッジ サービスの場合、VIP は送信元 IP アドレスを変更できません。実際のサーバー アドレスは直接クライアントに返されます。音声ビデオ トラフィック用の HLB で NAT を構成することはできません。

  - 音声ビデオの場合は、すべてのパケットについて、実際のサーバーのパブリック IP アドレスを外部ファイアウォールが保持します。

  - クライアントから 音声ビデオ エッジ サービスへの確立された通信は、HLB ではなく実際のサーバーに対する通信です。

  - 内部エッジから内部サーバーおよびクライアントへのルーティングを行う必要があります。サーバーまたはクライアントをホストするすべての内部ネットワークには固定ルートが設定されます。

  - HLB アクセス エッジ サービスの VIP は、各エッジ サーバー インターフェイスのデフォルト ゲートウェイとして機能します。

![エッジ サーバーのポートおよびプロトコルの詳細](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "エッジ サーバーのポートおよびプロトコルの詳細")

### 拡張統合エッジ (ロード バランサー機器) に必要な外部ポート設定: 外部インターフェイスの仮想 IP

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
<td><p>XMPP プロキシ サービス ( アクセス エッジ サービスと IP アドレスを共有)</p></td>
<td><p>XMPP プロキシ サービスは、定義済みの XMPP フェデレーションの XMPP 連絡先からのトラフィックを受け付ける</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP プロキシ サービス ( アクセス エッジ サービスと IP アドレスを共有)</p></td>
<td><p>任意</p></td>
<td><p>XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトにトラフィックを送信します</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>アクセス エッジ サービスのパブリック VIP アドレス</p></td>
<td><p>外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>アクセス エッジ サービスのパブリック VIP アドレス</p></td>
<td><p>SIP 信号、SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>アクセス エッジ サービスのパブリック VIP アドレス</p></td>
<td><p>フェデレーション パートナー</p></td>
<td><p>SIP 信号、SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
<tr class="even">
<td><p>Web 会議/PSOM (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー Web 会議エッジ サービスのパブリック IP アドレス</p></td>
<td><p>Web 会議メディア</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービスのパブリック VIP アドレス</p></td>
<td><p>STUN/UDP による候補の TURN ネゴシエーション/3478</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバー 音声ビデオ エッジ サービスのパブリック VIP アドレス</p></td>
<td><p>STUN/TCP による候補の TURN ネゴシエーション/443</p></td>
</tr>
</tbody>
</table>


### 拡張統合エッジ (ロード バランサー機器) のファイアウォールの概要: 内部インターフェイスの仮想 IP

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
<td><p>任意 ( ディレクター、 ディレクター プール仮想 IP アドレス、 フロント エンド サーバー、または フロント エンド プール仮想 IP アドレスとして定義可能)</p></td>
<td><p>エッジ サーバーの内部 VIP インターフェイス</p></td>
<td><p>( ディレクター、 ディレクター プール仮想 IP アドレス、 フロント エンド サーバー、または フロント エンド プール仮想 IP アドレスから) 内部エッジ VIP への送信 SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジ サーバーの内部 VIP インターフェイス</p></td>
<td><p>任意 ( ディレクター、 ディレクター プール仮想 IP アドレス、 フロント エンド サーバー、または フロント エンド プール仮想 IP アドレスとして定義可能)</p></td>
<td><p>エッジ サーバー内部インターフェイスから ( ディレクター、 ディレクター プール仮想 IP アドレス、 フロント エンド サーバー、または フロント エンド プール仮想 IP アドレスへの) 受信 SIP トラフィック</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任意 (この エッジ サーバーを使用して、 フロント エンド サーバーの IP アドレスまたは フロント エンド プールの IP アドレス、あるいは任意の 存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーとして定義可能)</p></td>
<td><p>エッジ サーバーの内部 VIP インターフェイス</p></td>
<td><p>フロント エンド サーバーまたは フロント エンド プール IP アドレス、あるいはこの エッジ サーバーを使用した任意の 存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーからの音声ビデオ ユーザーの認証 (音声ビデオ認証サービス)</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部 VIP インターフェイス</p></td>
<td><p>内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送の優先パス</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部 VIP インターフェイス</p></td>
<td><p>UDP 通信を確立できない場合の内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送のフォールバック パス、TCP はファイル転送およびデスクトップ共有に使用</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>エッジ サーバーの内部 VIP インターフェイス</p></td>
<td><p>任意</p></td>
<td><p>UDP 通信を確立できない場合の内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送のフォールバック パス、TCP はファイル転送およびデスクトップ共有に使用</p></td>
</tr>
</tbody>
</table>

