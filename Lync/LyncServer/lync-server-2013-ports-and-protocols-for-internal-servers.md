---
title: 'Lync Server 2013: 内部サーバーのポートとプロトコル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 の内部サーバーのポートとプロトコル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-04-06_

このセクションでは、Lync Server 展開のサーバー、ロードバランサー、クライアントで使用されるポートとプロトコルについて概要を説明します。

<div>


> [!IMPORTANT]  
> Lync と Communicator クライアントが1対1の通信に関わる場合、ピアツーピアと呼ばれることがよくあります。 技術的には、2つのクライアントは1つの会話と1つの会話の間でやり取りされ、中央にはインスタントメッセージング multipoint コントロールユニット (IMMCU) が含まれます。 IMMCU は、フロントエンドサーバーのコンポーネントです。 必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話の詳細の記録とその他の機能を使用できます。 通信は、クライアント上の動的ソースポートからフロントエンドサーバーポート TLS/TCP/5061 に送信されます (推奨トランスポート層セキュリティを使用していることを前提としています)。 設計上、ピアツーピア通信 (およびマルチパーティの IM) は、Lync Server と IMMCU がアクティブで利用可能な場合にのみ可能です。



</div>

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

<div>


> [!NOTE]  
> サーバー上で Lync Server サービスを開始する前に、Windows ファイアウォールが実行されている必要があります。そのため、Lync Server はファイアウォールで必要なポートを開くことになります。



</div>

エッジコンポーネントのファイアウォール構成の詳細については、「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。

次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。

### <a name="required-server-ports-by-server-role"></a>必要なサーバー ポート (サーバー役割別)

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
<td><p>中央管理ストアデータベースのローカルでレプリケートされたコピーの SQL ブラウザー。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server のフロントエンドサービス</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>リモート通話コントロール サーバーなどの Standard Edition サーバーとフロントエンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server のフロントエンドサービス</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロントエンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロントエンド プールで使用。 監視サーバーとの通信にも使用されます。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server のフロントエンドサービス</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>フォーカス (会議の状態を管理する Lync Server コンポーネント) と個々のサーバーの間の HTTPS 通信に使用されます。</p>
<p>このポートは、Survivable Branch アプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server のフロントエンドサービス</p></td>
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
<td><p>Lync Server Web 会議互換サービス</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Live Meeting クライアントと以前のバージョンの Lync Server からの永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server の音声/ビデオ会議サービス</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>音声ビデオ会議の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server の音声/ビデオ会議サービス</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>ビデオ会議で使用するメディア ポート範囲。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server Web 互換サービス</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>HTTPS が使用されない場合の、フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server Web 互換サービス</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server Web 互換サービス</p></td>
<td><p>8080</p></td>
<td><p>TCP および HTTP</p></td>
<td><p>外部アクセスのために Web コンポーネントで使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Web サーバー コンポーネント</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>Autodiscover サインインのための HTTPS (リバース プロキシから) および HTTPS フロント エンドのプール間通信。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Web サーバー コンポーネント</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Web サーバー コンポーネント</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
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
<td></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 会議アテンダントサービス (ダイヤルイン会議)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>ダイヤルイン会議の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 会議アテンダントサービス (ダイヤルイン会議)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>応答の受信 SIP 要求 (ダイヤルイン会議) に使用されます。</p></td>
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
<td><p>併置された仲介サーバーも実行するフロントエンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>併置された仲介サーバーも実行するフロントエンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
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
<td><p>Lync Server 会議のアナウンスメントサービス</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Lync Server 会議のアナウンスメントサービス (ダイヤルイン会議) の受信 SIP 要求に使用されます。</p></td>
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
<td><p>Lync Server の音声テストサービス</p></td>
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
<td><p>Lync Server 帯域幅ポリシーサービス</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバー</p></td>
<td><p>Lync Server 帯域幅ポリシーサービス</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Lync Server 帯域幅ポリシーサービスによる通話受付制御に使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>中央管理ストアが配置されているフロントエンドサーバー</p></td>
<td><p>Lync Server マスターレプリケーターエージェントサービス</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Lync Server を実行しているサーバーに、中央の管理ストアから構成データをプッシュするために使用されます。</p></td>
</tr>
<tr class="even">
<td><p>すべてのサーバー</p></td>
<td><p>SQL ブラウザー</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピー用の SQL ブラウザー</p></td>
</tr>
<tr class="odd">
<td><p>すべての内部サーバー</p></td>
<td><p>各種</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 オーディオを終了するすべてのサーバーで使用されます。フロントエンドサーバー (Lync Server 会議アテンダントサービス、Lync Server 会議のアナウンスメントサービス、Lync Server Audio/ビデオ会議サービス、および仲介サーバー)。</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps サーバー</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Lync Server 2013 で Office Web Apps サーバーに接続するために使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>ディレクター</p></td>
<td><p>Lync Server のフロントエンドサービス</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</p></td>
</tr>
<tr class="even">
<td><p>ディレクター</p></td>
<td><p>Lync Server のフロントエンドサービス</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>フロントエンドとディレクターの間のサーバー間通信。 さらに、クライアント証明書公開 (フロントエンドサーバー) またはクライアント証明書が既に公開されているかどうかを確認します。</p></td>
</tr>
<tr class="odd">
<td><p>ディレクター</p></td>
<td><p>Lync Server Web 互換サービス</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</p></td>
</tr>
<tr class="even">
<td><p>ディレクター</p></td>
<td><p>Lync Server Web 互換サービス</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="odd">
<td><p>ディレクター</p></td>
<td><p>Lync Server のフロントエンドサービス</p></td>
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
<td></td>
</tr>
<tr class="odd">
<td><p>常設チャット フロントエンド サーバー</p></td>
<td><p>常設チャット Windows Communication Foundation (WCF)</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) および TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>常設チャット フロントエンド サーバー</p></td>
<td><p>常設チャット ファイル転送サービス</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 一部のリモート通話コントロールシナリオでは、フロントエンドサーバーまたはディレクターと PBX の間に TCP 接続が必要です。 Lync Server は TCP ポート5060を使用しなくなりましたが、リモートコールコントロールの展開時には、RCC Line Server の FQDN と、フロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートを関連付ける信頼されたサーバー構成を作成します。 詳細については、「Lync Server 管理シェルドキュメントの<STRONG>CsTrustedApplicationComputer</STRONG>コマンドレット」を参照してください。



</div>

次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー

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
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>仲介サーバーのロード バランサー</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンド サーバーのロード バランサー (プールで仲介サーバーも稼働する場合)</p></td>
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
<td><p>ディレクターのロード バランサー</p></td>
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

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>DNS 負荷分散を使用する場合のハードウェア ロード バランサー

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


### <a name="required-client-ports"></a>必要なクライアント ポート

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
<td><p>Lync Server によってレジストラーの FQDN が検索されます (つまり、DNS SRV に障害が発生した場合は、手動の設定が構成されていない場合)。</p></td>
</tr>
<tr class="even">
<td><p>クライアント</p></td>
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
<td><p>Lync クライアントと以前のクライアント (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、Live Communications Server 2005) の間でのファイル送信に使用されます。</p></td>
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
<td><p>TCP/UDP</p></td>
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
<td><p>リストされているデバイスで使用され、Lync Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索します。</p></td>
</tr>
</tbody>
</table>


**\*** これらのメディアの種類に対して特定のポートを構成するには、CsConferencingConfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、ClientMediaPortRange parameters) を使用します。

<div>


> [!NOTE]  
> Lync クライアント用のプログラムを設定すると、必要なオペレーティングシステムファイアウォール例外がクライアントコンピューターに自動的に作成されます。



</div>

<div>


> [!NOTE]  
> 外部ユーザー アクセス用に使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオにおいて必要です (たとえば、他の組織によってホストされる外部の通信や会議)。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

