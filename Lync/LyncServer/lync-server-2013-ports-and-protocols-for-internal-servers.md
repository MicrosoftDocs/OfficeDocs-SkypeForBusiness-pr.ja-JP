---
title: 'Lync Server 2013: 内部サーバー用のポートとプロトコル'
TOCTitle: 内部サーバー用のポートとプロトコル
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48273557
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の内部サーバー用のポートとプロトコル

 

_**トピックの最終更新日:** 2016-04-06_

ここでは、Lync Server 展開のサーバー、ロード バランサー、およびクライアントで使用されるポートおよびプロトコルの概要を示します。


> [!IMPORTANT]
> Lync クライアントと Communicator クライアントが 1 対 1 の通信に参加している場合、その通信は通常ピアツーピアと呼ばれます。技術的には、2 つのクライアントが 1 対 1 の会話で通信し、Instant Messaging Multipoint Control Unit (IMMCU) が間に存在します。IMMCU はフロント エンド サーバーのコンポーネントです。必要な通信ワークフローに IMMCU を配置すると、通話詳細記録や、フロント エンド サーバーで有効になるその他の機能を使用できます。通信は、クライアント上の動的ソース ポートからフロント エンド サーバーのポート TLS/TCP/5061 (推奨されるトランスポート層セキュリティの使用が前提) までの間で行われます。仕様により、ピアツーピア通信 (マルチパーティ IM も同様) は Lync Server と IMMCU がアクティブで使用できる状態のときにだけ実行できます。



## ポートとプロトコルの詳細

> [!NOTE]
> Lync Server は、サーバーで Lync Server サービスが開始されるときにファイアウォールで必要なポートを開くため、サービスを開始する前に Windows ファイアウォールが実行されているようにする必要があります。


エッジ コンポーネントのファイアウォール構成の詳細については、「[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。

次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。

### 必要なサーバー ポート (サーバー役割別)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>サーバーの役割</th>
<th>サービス名</th>
<th>ポート</th>
<th>プロトコル</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>すべてのサーバー</p></td>
<td><p>SQL ブラウザー</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>ローカルにレプリケートされた中央管理ストアのコピーに対する SQL ブラウザー。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server フロントエンド サービス</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>リモート通話コントロール サーバーなどの Standard Edition サーバーとフロントエンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server フロントエンド サービス</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロントエンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロントエンド プールで使用。監視サーバーとの通信でも使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server フロントエンド サービス</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>フォーカス (会議の状態を管理する Lync Server コンポーネント) と個別サーバーとの間の HTTPS 通信に使用。</p>
<p>このポートは、存続可能ブランチ アプライアンスとフロントエンド サーバーとの間の TCP 通信にも使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server フロントエンド サービス</p></td>
<td><p>135</p></td>
<td><p>DCOM およびリモート プロシージャ コール (RPC)</p></td>
<td><p>ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server IM 会議サービス</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server Web 会議サービス</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server Web 会議サービス互換性サービス</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Live Meeting クライアントおよび以前のバージョンの Lync Server からの永続共有オブジェクト モデル (PSOM) 接続をリッスンするために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 音声ビデオ会議サービス</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>音声ビデオ会議の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 音声ビデオ会議サービス</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>ビデオ会議で使用するメディア ポート範囲。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>HTTPS が使用されない場合の、フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>8080</p></td>
<td><p>TCP および HTTP</p></td>
<td><p>外部アクセスのために Web コンポーネントで使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Web サーバー コンポーネント</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Web サーバー コンポーネント</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Web サーバー コンポーネント</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Mobility Service コンポーネント</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Mobility Service の内部プロセスに使用される SIP ポート。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Mobility Service コンポーネント</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Mobility Service の内部プロセスに使用される SIP ポート。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Mobility Service コンポーネント</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 会議アテンダント サービス (ダイヤルイン会議)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>ダイヤルイン会議の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 会議アテンダント サービス (ダイヤルイン会議)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Attendant (ダイヤルイン会議) の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>併置された仲介サーバーも実行するフロントエンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>フロントエンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。</p></td>
</tr>
<tr class="odd">
<td><p>併置された仲介サーバーも実行するフロントエンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>併置された仲介サーバーも実行するフロントエンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>併置された仲介サーバーも実行するフロントエンド サーバー</p>
<p></p></td>
<td><p>Lync Server 仲介サービス</p>
<p></p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>併置された仲介サーバーも実行するフロントエンド サーバー</p>
<p></p></td>
<td><p>Lync Server 仲介サービス</p>
<p></p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server アプリケーション共有サービス</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>アプリケーション共有の SIP リッスン要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server アプリケーション共有サービス</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>アプリケーション共有で使用するメディア ポート範囲。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 会議アナウンス サービス</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Lync Server 会議アナウンス サービス (ダイヤルイン会議用) の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server コール パーク サービス</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>コール パーク アプリケーションの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server オーディオ テスト サービス</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>オーディオ テスト サービスの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>該当なし</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 応答グループ サービス</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>応答グループ アプリケーションの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 応答グループ サービス</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>応答グループ アプリケーションの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 帯域幅ポリシー サービス</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 帯域幅ポリシー サービス</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Lync Server 帯域幅ポリシー サービスによる通話受付管理で使用。</p></td>
</tr>
<tr class="odd">
<td><p>中央管理ストアが存在するフロントエンド サーバー</p></td>
<td><p>Lync Server マスター レプリケーター エージェント サービス</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>中央管理ストアから Lync Server が実行されているサーバーに構成データをプッシュするために使用。</p></td>
</tr>
<tr class="even">
<td><p>すべてのサーバー</p></td>
<td><p>SQL ブラウザー</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>SQL Server インスタンス内の 中央管理ストア データのローカルにレプリケートされたコピー用の SQL ブラウザー。</p></td>
</tr>
<tr class="odd">
<td><p>すべての内部サーバー</p></td>
<td><p>各種</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。オーディオを終端する次のすべてのサーバーで使用 (フロントエンド サーバー (Lync Server 会議アテンダント サービス、Lync Server 会議アナウンス サービス、および Lync Server 音声ビデオ会議サービス)、および仲介サーバー)。</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps サーバー</p></td>
<td><p></p></td>
<td><p>443</p></td>
<td><p></p></td>
<td><p>Office Web Apps サーバーに接続するために Lync Server 2013 で使用。</p></td>
</tr>
<tr class="odd">
<td><p>ディレクター</p></td>
<td><p>Lync Server フロントエンド サービス</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</p></td>
</tr>
<tr class="even">
<td><p>ディレクター</p></td>
<td><p>Lync Server フロントエンド サービス</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>フロントエンドとディレクターの間のサーバー間通信。さらに、クライアント証明書が既に公開されている場合にはクライアント証明書の (フロント エンド サーバーに対する) 公開または確認。</p></td>
</tr>
<tr class="odd">
<td><p>ディレクター</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</p></td>
</tr>
<tr class="even">
<td><p>ディレクター</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="odd">
<td><p>ディレクター</p></td>
<td><p>Lync Server フロントエンド サービス</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>サーバー間の内部通信とクライアント接続に使用。</p></td>
</tr>
<tr class="even">
<td><p>仲介サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>フロントエンド サーバーからの要求を受信するために仲介サーバーで使用。</p></td>
</tr>
<tr class="odd">
<td><p>仲介サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>PSTN ゲートウェイからの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>仲介サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>PSTN ゲートウェイからの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>仲介サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>フロントエンド サーバーからの SIP 要求で使用。</p></td>
</tr>
<tr class="even">
<td><p>常設チャット フロントエンド サーバー</p></td>
<td><p>常設チャット SIP</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>常設チャット フロントエンド サーバー</p></td>
<td><p>常設チャット Windows Communication Foundation (WCF)</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) および TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>常設チャット フロントエンド サーバー</p></td>
<td><p>常設チャット ファイル転送サービス</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> リモート通話コントロールのシナリオによっては、フロントエンド サーバーかディレクターと PBX の間で TCP 接続が必要になります。Lync Server が TCP ポート 5060 を使用することはなくなりましたが、リモート通話コントロールの展開時には信頼されたサーバー構成を作成します。それにより、RCC 回線サーバーの FQDN が、PBX システムに接続するためにフロントエンド サーバーまたはディレクターが使用する TCP ポートと関連付けられます。詳細については、Lync Server 管理シェルのドキュメントの「<strong>CsTrustedApplicationComputer</strong>」コマンドレットを参照してください。


次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。

### ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ロード バランサー</th>
<th>ポート</th>
<th>プロトコル</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>135</p></td>
<td><p>DCOM およびリモート プロシージャ コール (RPC)</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>8080</p></td>
<td><p>TCP - フロントエンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (リバース プロキシから)</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p>
<p></p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p>
<p></p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p>
<p></p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p>
<p></p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p>
<p></p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p>
<p></p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー (プールで仲介サーバーも稼働する場合)</p>
<p></p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー (プールで仲介サーバーも稼働する場合)</p>
<p></p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>ディレクターのロード バランサー</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>ディレクターのロード バランサー</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>ディレクターのロード バランサー</p>
<p></p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>ディレクターのロード バランサー</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (リバース プロキシから)</p></td>
</tr>
</tbody>
</table>


DNS 負荷分散を使用するフロントエンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。

### DNS 負荷分散を使用する場合のハードウェア ロード バランサー

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ロード バランサー</th>
<th>ポート</th>
<th>プロトコル</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>8080</p></td>
<td><p>TCP - フロントエンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (リバース プロキシから)</p></td>
</tr>
<tr class="odd">
<td><p>ディレクターのロード バランサー</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>ディレクターのロード バランサー</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (リバース プロキシから)</p></td>
</tr>
</tbody>
</table>


### 必要なクライアント ポート

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>ポート</th>
<th>プロトコル</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>レジストラーの FQDN を見つけるために Lync Server で使用 (つまり、DNS SRV で障害が発生し、手動設定が構成されていない場合)。</p></td>
</tr>
<tr class="even">
<td><p>クライアント</p>
<p></p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>Web 会議セッションへの外部ユーザー アクセスで使用。</p></td>
</tr>
<tr class="even">
<td><p>クライアント</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN)</p></td>
<td><p>音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用。</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>音声ビデオ セッションとメディアへの外部ユーザー アクセス (UDP) で使用。</p></td>
</tr>
<tr class="even">
<td><p>クライアント</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>6891-6901</p></td>
<td><p>TCP</p></td>
<td><p>Lync クライアントと以前のクライアント (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、および Live Communications Server 2005 のクライアント) の間のファイル転送で使用。</p></td>
</tr>
<tr class="even">
<td><p>クライアント</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>オーディオ ポート範囲 (少なくとも 20 個のポートが必要)。</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p>
<p></p></td>
<td><p>ビデオ ポート範囲 (少なくとも 20 個のポートが必要)。</p></td>
</tr>
<tr class="even">
<td><p>クライアント</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>アプリケーション共有。</p></td>
</tr>
<tr class="even">
<td><p>Aastra 6721ip 共通領域電話</p>
<p>Aastra 6725ip 卓上電話</p>
<p>HP 4110 IP 電話 (共通領域電話)</p>
<p>HP 4120 IP 電話 (卓上電話)</p>
<p>Polycom CX500 IP 共通領域電話</p>
<p>Polycom CX600 IP 卓上電話</p>
<p>Polycom CX700 IP 卓上電話</p>
<p>Polycom CX3000 IP 会議電話</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Lync Server 証明書、プロビジョニング FQDN、およびレジストラーの FQDN を見つけるために一覧のデバイスで使用。</p></td>
</tr>
</tbody>
</table>


**\*** これらのメディア種類用に特定のポートを構成するには、CsConferencingConfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、ClientMediaPortRange parameters) を使用します。

> [!NOTE]
> Lync クライアント用の設定プログラムは、必要なオペレーティング システム ファイアウォール例外をクライアント コンピューター上で自動的に作成します。


> [!NOTE]
> 外部ユーザー アクセス用に使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオにおいて必要です (たとえば、他の組織によってホストされる外部の通信や会議)。

