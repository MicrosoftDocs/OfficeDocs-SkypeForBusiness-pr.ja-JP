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
ms.openlocfilehash: 42f40265cf7b8fff7fd6cbf3d4f67a2fb9f558fa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 の内部サーバーのポートとプロトコル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-04-06_

このセクションでは、Lync Server 展開のサーバー、ロードバランサー、およびクライアントで使用されるポートとプロトコルの概要について説明します。

<div>


> [!IMPORTANT]  
> 1対1の通信に関係する Lync および Communicator クライアントは、ピアツーピアと呼ばれることがよくあります。 技術的には、2つのクライアントは1つの会話に、インスタントメッセージング multipoint control unit (IMMCU) を中央に持つ1つの会話と通信します。 IMMCU はフロントエンドサーバーのコンポーネントです。 必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話詳細記録およびその他の機能を使用できるようになります。 クライアント上の動的送信元ポートからフロントエンドサーバーポート TLS/TCP/5061 への通信です (推奨トランスポート層セキュリティを使用していることを前提としています)。 設計上、Lync Server と IMMCU がアクティブで利用可能な場合にのみ、ピアツーピア通信 (およびマルチパーティ IM) を使用できます。



</div>

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

<div>


> [!NOTE]  
> Lync server がファイアウォールで必要なポートを開くときに、サーバー上で Lync Server サービスを開始する前に、Windows ファイアウォールを実行しておく必要があります。



</div>

エッジコンポーネントのファイアウォール構成の詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。

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
<td><p>受信</p></td>
<td><p>中央管理ストアデータベースのローカルにレプリケートされたコピーの SQL ブラウザー。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server フロントエンドサービス</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>リモート通話コントロール サーバーなどの Standard Edition サーバーとフロント エンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server フロントエンドサービス</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロント エンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロント エンド プールで使用。 監視サーバーとの通信でも使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server フロントエンドサービス</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>フォーカス (会議の状態を管理する Lync Server コンポーネント) と個々のサーバーとの間の HTTPS 通信に使用されます。</p>
<p>このポートは、存続可能ブランチアプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server フロントエンドサービス</p></td>
<td><p>135</p></td>
<td><p>DCOM およびリモート プロシージャ コール (RPC)</p></td>
<td><p>ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server IM 会議サービス</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server Web 会議サービス</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server Web 会議互換性サービス</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Live Meeting クライアントおよび以前のバージョンの Lync Server からの、永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 音声ビデオ会議サービス</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>音声ビデオ会議の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 音声ビデオ会議サービス</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>ビデオ会議で使用するメディア ポート範囲。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>HTTPS が使用されない場合の、フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>8080</p></td>
<td><p>TCP および HTTP</p></td>
<td><p>外部アクセスのために web コンポーネントによって使用されます。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Web サーバーコンポーネント</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>自動検出サインインの HTTPS (リバースプロキシから) および HTTPS フロントエンドプール間通信。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Web サーバーコンポーネント</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Web サーバーコンポーネント</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Mobility Services コンポーネント</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Mobility Services 内部プロセスで使用される SIP ポート</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Mobility Services コンポーネント</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Mobility Services 内部プロセスで使用される SIP ポート</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Mobility Services コンポーネント</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 会議アテンダントサービス (ダイヤルイン会議)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>ダイヤルイン会議の SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 会議アテンダントサービス (ダイヤルイン会議)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>アテンダント (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</p></td>
</tr>
<tr class="even">
<td><p>併置された仲介サーバーも実行するフロント エンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>フロント エンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。</p></td>
</tr>
<tr class="odd">
<td><p>併置された仲介サーバーも実行するフロント エンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>併置された仲介サーバーも実行するフロント エンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>併置された仲介サーバーも実行するフロント エンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>併置された仲介サーバーも実行するフロント エンド サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server アプリケーション共有サービス</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>アプリケーション共有の SIP リッスン要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server アプリケーション共有サービス</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>アプリケーション共有で使用するメディア ポート範囲。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 会議アナウンスサービス</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Lync Server 会議アナウンスサービス (ダイヤルイン会議) の SIP 要求を受信するために使用されます。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server コール パーク サービス</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>コール パーク アプリケーションの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server Audio Test service</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>オーディオ テスト サービスの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>該当なし</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 応答グループ サービス</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>応答グループ アプリケーションの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 応答グループ サービス</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>応答グループ アプリケーションの SIP 要求を受信するために使用。</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 帯域幅ポリシーサービス</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバー</p></td>
<td><p>Lync Server 帯域幅ポリシーサービス</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Lync Server 帯域幅ポリシーサービスによる通話受付管理に使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>中央管理ストアが存在するフロントエンドサーバー</p></td>
<td><p>Lync Server マスター レプリケーター エージェント サービス</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>中央管理ストアから Lync Server を実行しているサーバーに構成データをプッシュするために使用されます。</p></td>
</tr>
<tr class="even">
<td><p>すべてのサーバー</p></td>
<td><p>SQL ブラウザー</p></td>
<td><p>1434</p></td>
<td><p>受信</p></td>
<td><p>ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピーのための SQL ブラウザー</p></td>
</tr>
<tr class="odd">
<td><p>すべての内部サーバー</p></td>
<td><p>各種</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 オーディオを終了するすべてのサーバーで使用します。フロントエンドサーバー (Lync Server 会議アテンダントサービス、lync Server 会議アナウンスサービス、および Lync Server 音声ビデオ会議サービスの場合)、および仲介サーバー。</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps サーバー</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Lync Server 2013 が Office Web Apps サーバーに接続するために使用します。</p></td>
</tr>
<tr class="odd">
<td><p>レ</p></td>
<td><p>Lync Server フロントエンドサービス</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。</p></td>
</tr>
<tr class="even">
<td><p>レ</p></td>
<td><p>Lync Server フロントエンドサービス</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>フロントエンドとディレクターの間のサーバー間通信。 さらに、クライアント証明書を (フロントエンドサーバーに) 公開するか、クライアント証明書が既に公開されているかどうかを確認します。</p></td>
</tr>
<tr class="odd">
<td><p>レ</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。</p></td>
</tr>
<tr class="even">
<td><p>レ</p></td>
<td><p>Lync Server Web 互換性サービス</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。</p></td>
</tr>
<tr class="odd">
<td><p>レ</p></td>
<td><p>Lync Server フロントエンドサービス</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>サーバー間の内部通信とクライアント接続に使用。</p></td>
</tr>
<tr class="even">
<td><p>仲介サーバー</p></td>
<td><p>Lync Server 仲介サービス</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>フロント エンド サーバーからの要求を受信するために仲介サーバーで使用。</p></td>
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
<td><p>フロント エンド サーバーからの SIP 要求で使用。</p></td>
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
<td><p>TCP (TLS) と TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>常設チャット フロントエンド サーバー</p></td>
<td><p>常設チャットのファイル転送サービス</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> リモート通話コントロールのシナリオによっては、フロントエンドサーバーまたはディレクターと PBX との間に TCP 接続が必要な場合があります。 Lync Server は TCP ポート5060を使用しなくなりましたが、リモート通話コントロールの展開時には、RCC Line サーバーの FQDN を、フロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートに関連付ける信頼できるサーバー構成を作成します。 詳細については、「Lync Server Management Shell」のドキュメントの「 <STRONG>CsTrustedApplicationComputer</STRONG>コマンドレット」を参照してください。



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
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>135</p></td>
<td><p>DCOM およびリモート プロシージャ コール (RPC)</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>8080</p></td>
<td><p>TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (リバース プロキシから)</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>仲介サーバーのロードバランサー</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>フロントエンドサーバーのロードバランサー (プールが仲介サーバーも実行している場合)</p></td>
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


DNS 負荷分散を使用するフロント エンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。 次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。

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
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
<td><p>8080</p></td>
<td><p>TCP - フロント エンド サーバーからのクライアントとデバイスのルート証明書取得 - NTLM で認証されたクライアントとデバイス</p></td>
</tr>
<tr class="even">
<td><p>フロント エンド サーバーのロード バランサー</p></td>
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
<td><p>Lync Server によって、レジストラーの FQDN を検索するために使用されます (つまり、DNS SRV に障害が発生し、手動設定が構成されていない場合)。</p></td>
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
<td><p>音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>音声ビデオセッションおよびメディアへの外部ユーザーアクセスに使用されます (UDP)</p></td>
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
<td><p>Lync クライアントと以前のクライアントの間のファイル転送に使用されます (Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007、および Live Communications Server 2005)。</p></td>
</tr>
<tr class="even">
<td><p>クライアント</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>オーディオ ポート範囲 (少なくとも 20 個のポートが必要)</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>ビデオ ポート範囲 (少なくとも 20 個のポートが必要)</p></td>
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
<td><p>Lync Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索するために、リストされているデバイスによって使用されます。</p></td>
</tr>
</tbody>
</table>


**\*** これらのメディアの種類に対して特定のポートを構成するには、Get-csconferencingconfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、および ClientMediaPortRange パラメーター) を使用します。

<div>


> [!NOTE]  
> Lync クライアント用のプログラムを設定すると、クライアントコンピューターに必要なオペレーティングシステムファイアウォールの例外が自動的に作成されます。



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

