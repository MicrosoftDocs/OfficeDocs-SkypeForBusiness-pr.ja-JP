---
title: Lync Server 2013 のハードウェア ロード バランサーの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d5b10a91f469bf4688de06e836e0bdeffae1112
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Lync Server 2013 のハードウェア ロード バランサーの要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-05-11_

Lync Server 2013 スケーリングされた統合エッジトポロジは、新しい展開の場合、Lync Server を使用する他の組織との主な展開のために、DNS の負荷分散のために最適化されています。 次のシナリオのいずれかに対して高可用性が必要な場合は、次のように、エッジサーバープールでハードウェアロードバランサーを使用する必要があります。

  - Office Communications Server 2007 R2 または Office Communications Server 2007 を使用している組織とのフェデレーション

  - Exchange 2010 SP1 より前の exchange UM を使用しているリモートユーザーの exchange UM

  - パブリック IM ユーザーとの接続

<div>


> [!IMPORTANT]  
> 1 つのインターフェイスでハードウェア負荷分散を使用し、もう 1 つのインターフェイスで DNS 負荷分散を使用することはできません。両方のインターフェイスでハードウェア負荷分散を使用するか、両方で DNS 負荷分散を使用する必要があります。



</div>

<div>


> [!NOTE]  
> ロード バランサー機器を使用している場合は、内部ネットワークとの接続用に展開されているロード バランサーを構成して、アクセス エッジ サービスおよび音声ビデオ サービスを実行しているサーバーへのトラフィックのみを負荷分散する必要があります。内部の Web 会議エッジ サービスまたは内部 XMPP プロキシ サービスへのトラフィックを負荷分散することはできません。



</div>

<div>


> [!NOTE]  
> Direct server return (DSR) NAT は、Lync Server 2013 ではサポートされていません。



</div>

使用[http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)しているハードウェアロードバランサーが lync server 2013 に必要な機能をサポートしているかどうかを判断するには、の「lync Server 2010 ロードバランサーパートナー」を参照してください。

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>音声ビデオ エッジ サービスを実行するエッジ サーバーに対するロード バランサー機器の要件

A/V Edge サービスを実行しているエッジサーバーのハードウェアロードバランサーの要件を次に示します。

  - 内部と外部の両方のポート 443 に対して TCP のネーグル処理がオフになっていること。ネーグル処理はいくつかの小さなパケットを 1 つの大きなパケットにまとめて転送効率を向上させるプロセスです。

  - 外部ポート範囲 50000 ～ 59999 の TCP のネーグル処理がオフになっていること。

  - 内部または外部のファイアウォールで NAT が使用されていないこと。

  - Edge の内部インターフェイスは、エッジサーバーの外部インターフェイスとは異なるネットワーク上にあり、その間のルーティングを無効にする必要があります。

  - A/V Edge サービスを実行しているエッジサーバーの外部インターフェイスでは、公開ルーティング可能な IP アドレスを使用し、エッジ外部 IP アドレスには NAT やポートの変換を行わないようにする必要があります。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>ロード バランサー機器の要件

Cookie ベースのアフィニティ要件は、Web サービスの Lync Server 2013 で大幅に削減されます。 Lync server 2013 を展開していて、Lync Server 2010 フロントエンドサーバーまたはフロントエンドプールを保持していない場合は、cookie ベースの常設は必要ありません。 ただし、Lync Server 2010 のフロントエンドサーバーまたはフロントエンドプールを一時的または完全に保持する場合でも、Lync Server 2010 用に展開して構成すると、cookie ベースの常設が使用されます。

<div>


> [!NOTE]  
> <STRONG>展開では不要だが、Cookie ベースのアフィニティを使用する場合でも</STRONG>、悪影響はありません。



</div>

Cookie ベースのアフィニティを**使用しない**展開の場合

  - リバース プロキシのポート 4443 に対する公開ルールで、[**ホスト ヘッダーを転送する**] を True に設定します。 これにより、元の URL が確実に転送されます。

Cookie ベースのアフィニティを**使用する**展開の場合

  - リバース プロキシのポート 4443 に対する公開ルールで、[**ホスト ヘッダーを転送する**] を True に設定します。これにより、元の URL が確実に転送されます。

  - ロード バランサー機器 Cookie が httpOnly とマークされていないこと

  - ロード バランサー機器 Cookie に有効期限がないこと

  - ロード バランサー機器 Cookie の名前が **MS-WSMAN** であること (これは Web サービスが受け取ることを想定している値であり、変更できません)

  - ロード バランサー機器着信 HTTP 要求に Cookie が含まれていなかったすべての HTTP 応答に Cookie が設定されていること。同じ TCP 接続での以前の HTTP 応答で Cookie が既に取得されているかどうかは関係ありません。ロード バランサーによって、Cookie の挿入が TCP 接続ごとに 1 回のみ行われるように最適化されている場合は、その最適化を使用しないでください。

<div>


> [!NOTE]  
> 一般的なハードウェアロードバランサー構成では、ソースアドレスのアフィニティと20分の TCP セッションの有効期限が使用されます。これは、クライアントの使用状況やアプリケーションの操作によってセッションの状態が維持されるため、Lync Server と Lync 2013 クライアントにとって適切です。



</div>

モバイル デバイスを展開する場合、ロード バランサー機器で、TCP セッション内の個々の要求を負荷分散できるようにする必要があります (実際には、ターゲット IP アドレスに基づいて個々の要求を負荷分散できる必要があります)。

<div>


> [!WARNING]  
> F5 ロード バランサー機器には、OneConnect と呼ばれる機能があります。この機能を使用すると、TCP 接続内の各要求が個々に負荷分散されます。モバイル デバイスを展開する場合、ロード バランサー機器のベンダーが同じ機能をサポートしていることを確認してください。最新の Apple iOS モバイル アプリでは、トランスポート層セキュリティ (TLS) v1.2 が必要です。F5 は、その固有の設定を備えています。<BR>サードパーティのハードウェアロードバランサーの詳細については、<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

ディレクターおよびフロントエンド プールの Web サービスに対するロード バランサー機器の要件は次のとおりです。

  - 内部の Web サービス Vip では、\_ハードウェアのロードバランサーでソースアドレスの常設 (内部ポート80、443) を設定します。 Lync Server 2013 の場合、\_ソースアドレス常設は、1つの IP アドレスからの複数の接続が常に1つのサーバーに送信され、セッションの状態を維持することを意味します。

  - TCP アイドル タイムアウトが 1800 秒に設定されていること

  - リバース プロキシと次ホップ プールのロード バランサー機器間のファイアウォールで、リバース プロキシからロード バランサー機器へのポート 4443 に対する https: トラフィックを許可するルールが作成されていること。ポート 80、443、および 4443 をリッスンするようにロード バランサー機器を構成する必要があります。

<div>


> [!IMPORTANT]  
> ハードウェアロードバランサーの構成の詳細については、「<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">ポートの概要-Lync Server 2013 でハードウェアロードバランサーを使用して拡大縮小されたエッジを</A>確認する」を参照してください。



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>ロード バランサー機器のアフィニティ要件の概要


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント/ユーザーの場所</th>
<th>外部 Web サービスの FQDN のアフィニティ要件</th>
<th>内部 Web サービスの FQDN のアフィニティ要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (内部と外部のユーザー)</p>
<p>モバイル デバイス (内部および外部ユーザー)</p></td>
<td><p>アフィニティなし</p></td>
<td><p>送信元アドレスのアフィニティ</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (外部ユーザーのみ)</p>
<p>モバイル デバイス (内部および外部ユーザー)</p></td>
<td><p>アフィニティなし</p></td>
<td><p>送信元アドレスのアフィニティ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (内部ユーザーのみ)</p>
<p>モバイル デバイス (展開しない)</p></td>
<td><p>アフィニティなし</p></td>
<td><p>送信元アドレスのアフィニティ</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>ロード バランサー機器のポート監視

特定のサービスがハードウェアまたは通信障害によって使用できないような状況を確認する目的で、ロード バランサー機器に対してポート監視を定義します。 たとえば、フロントエンドサーバーまたはフロントエンドプールに障害が発生したために、フロントエンドサーバーサービス (RTCSRV) が停止した場合、HLB の監視でも Web サービスのトラフィックの受信を停止する必要があります。 以下を監視する目的で、HLB にポート監視を実装します。

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>フロントエンドサーバーのユーザープール– HLB 内部インターフェイス

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
<th>仮想 IP/ポート</th>
<th>ノード ポート</th>
<th>ノード コンピューター/モニター</th>
<th>保存プロファイル</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>フロントエンド</p>
<p>5061</p></td>
<td><p>ソース</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>フロントエンド</p>
<p>5061</p></td>
<td><p>ソース</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>フロントエンドサーバーのユーザープール– HLB 外部インターフェイス

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
<th>仮想 IP/ポート</th>
<th>ノード ポート</th>
<th>ノード コンピューター/モニター</th>
<th>保存プロファイル</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;プール&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>フロントエンド</p>
<p>5061</p></td>
<td><p>なし</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;プール&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>フロントエンド</p>
<p>5061</p></td>
<td><p>なし</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

