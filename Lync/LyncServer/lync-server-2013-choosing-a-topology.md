---
title: 'Lync Server 2013: トポロジの選択'
TOCTitle: トポロジの選択
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48271499
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのトポロジの選択

 

_**トピックの最終更新日:** 2015-03-09_

トポロジの選択では、次に示すサポートされるトポロジ オプションのいずれかを使用できます。

> [!NOTE]
> 特に注記がない限り、ここに示す指針の大部分は Microsoft Lync Server 2010 から変更されていません。


  - [Lync Server 2013 におけるプライベート IP アドレスと NAT を用いた単一統合エッジ](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)


> [!IMPORTANT]
> 内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。



次の表に、サポートされる Microsoft Lync Server 2013 トポロジで使用できる機能の概要を示します。列見出しは、該当するエッジ構成オプションで使用できる機能を示しています。たとえば、拡張エッジ (DNS 負荷分散) オプションでは、高可用性がサポートされること、エッジの外部インターフェイスに割り当てられたルーティング不可のプライベート IP アドレス (NAT を使用) またはルーティング可能なパブリック IP アドレスを使用できること、およびロード バランサー機器が必要ないのでコストが削減されることがわかります。

DNS 負荷分散でサポートされるエッジ フェールオーバーのシナリオは、Lync 対 Lync のポイントツーポイント セッション、Lync 会議セッション、Lync 対 PSTN セッションと Office 365 です。DNS 負荷分散による恩恵を受けないエッジ フェールオーバーのシナリオは、リモート ユーザー Exchange ユニファイド メッセージング (UM) (Exchange 2010 SP1 以前)、パブリック インスタント メッセージング (IM) 接続、および Office Communications Server を実行するサーバーとのフェデレーションのフェールオーバーです。

### エッジ サーバー トポロジ オプションの概要

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
<th>トポロジ</th>
<th>高可用性</th>
<th>エッジ プールにある外部エッジ サーバーの追加 DNS A レコードの必要性</th>
<th>Lync 対 Lync セッションのエッジ フェールオーバー</th>
<th>Lync 対 Lync EUM/PIC/OCS フェデレーション セッションのエッジ フェールオーバー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NAT を使用する単一エッジ</p></td>
<td><p>×</p></td>
<td><p>×</p></td>
<td><p>×</p></td>
<td><p>×</p></td>
</tr>
<tr class="even">
<td><p>パブリック IP を使用する単一エッジ</p></td>
<td><p>×</p></td>
<td><p>×</p></td>
<td><p>×</p></td>
<td><p>×</p></td>
</tr>
<tr class="odd">
<td><p>NAT を使用する拡張エッジ (DNS 負荷分散)</p></td>
<td><p>○</p></td>
<td><p>○</p></td>
<td><p>○</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>パブリック IP を使用する拡張エッジ (DNS 負荷分散)</p></td>
<td><p>○</p></td>
<td><p>○</p></td>
<td><p>○</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>拡張エッジ (ハードウェア負荷分散)</p></td>
<td><p>○</p></td>
<td><p>いいえ (VIP ごとに 1 つの DNS A レコード)</p></td>
<td><p>○</p></td>
<td><p>○</p></td>
</tr>
</tbody>
</table>


**\*** パブリック インスタント メッセージング (IM) 接続、および Office Communications Server を実行するサーバーとのフェデレーションのフェールオーバーは、DNS 負荷分散では利用できません。DNS 負荷分散を使用する Exchange UM (リモート ユーザー) のフェールオーバーには、Exchange Server 2010 SP1 以降が必要です。

> [!NOTE]  
> 単一エッジおよび拡張エッジ (DNS 負荷分散) トポロジでは、次のアドレスを使用できます。
> <ul><li><p>ルーティング可能なパブリック IP アドレス</p></li>
> <li><p>ルーティング不可のプライベート IP アドレス (対称ネットワーク アドレス変換 (NAT) を使用する場合)</p></li></ul>
>  
> パブリック IP アドレス、またはプライベート IP アドレスと NAT を使用する場合、トポロジ ビルダーの構成オプションに基づいて同じ数の IP アドレスを依然として使用します。1 つの IP アドレスおよびサービスごとの別々のポートを使用するか、サービスごとの別々の IP アドレスおよび 1 つのポート (既定では TCP 443) を使用するように エッジ サーバー を構成できます。
> 
> ルーティング不可のプライベート IP アドレスと NAT を使用する場合の注意点は次のとおりです。
> 
> <ul><li>3 つすべての外部インターフェイスでルーティング可能なプライベート IP アドレスを使用する必要があります。</li>
> <li>受信トラフィックと送信トラフィック用に対称 NAT を構成する必要があります。</li></ul>
> 
> 拡張エッジ (ハードウェア負荷分散) トポロジでは、パブリック IP アドレスを使用する必要があります。

Lync Server 2013 では、単一統合エッジ サーバー トポロジおよび拡張統合エッジ サーバー トポロジの両方で、ネットワーク アドレス変換 (NAT) を実行するルーターまたはファイアウォールの背後に、アクセス エッジ、Web 会議エッジ、および音声ビデオ エッジの外部インターフェイスを配置できます。

すべてのエッジ外部インターフェイスで NAT を使用する場合は、DNS 負荷分散を使用する必要があります。ロード バランサー機器を使用する場合に比べて、NAT を使わずに DNS 負荷分散を使用すると、次の一覧に示すとおり、エッジ プール内のエッジ サーバーごとのパブリック IP アドレス数を減らすことができます。

  - Lync Server 2013 拡張統合エッジ (DNS 負荷分散): エッジ プール内の各エッジ サーバーに 3 つのパブリック IP アドレスが必要。

  - Lync Server 2013 拡張統合エッジ (ハードウェア負荷分散): ロード バランサーの仮想 IP アドレス用に 3 つのパブリック IP アドレス (プールにエッジ サーバーを追加しても増えない、1 回限りの要件) と、プール内のエッジ サーバーごとに 3 つのパブリック IP アドレスが必要。

### 拡張統合エッジに必要な IP アドレス (役割ごとの IP アドレス)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プールごとのエッジ サーバー数</th>
<th>必要な IP アドレス数 Lync Server 2013 (DNS 負荷分散有効)</th>
<th>必要な IP アドレス数 Lync Server 2013 (ハードウェア負荷分散有効)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>6</p></td>
<td><p>3 (VIP ごとに 1 つ) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9</p></td>
<td><p>3 (VIP ごとに 1 つ) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (VIP ごとに 1 つ) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15</p></td>
<td><p>3 (VIP ごとに 1 つ) + 15</p></td>
</tr>
</tbody>
</table>


### 拡張統合エッジに必要な IP アドレス (すべての役割に対して 1 つの IP アドレス)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プールごとのエッジ サーバー数</th>
<th>必要な IP アドレス数 Lync Server 2013 (DNS 負荷分散有効)</th>
<th>必要な IP アドレス数 Lync Server 2013 (ハードウェア負荷分散有効)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
<td><p>1 (VIP ごとに 1 つ) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1 (VIP ごとに 1 つ) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>1 (VIP ごとに 1 つ) + 4</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>5</p></td>
<td><p>1 (VIP ごとに 1 つ) + 5</p></td>
</tr>
</tbody>
</table>


トポロジ選択を決定する上で最も優先されるポイントは、高可用性と負荷分散です。 高可用性の要件は、負荷分散の決定に影響を及ぼすことがあります。

  - **高可用性**   高可用性が必要な場合は、プールに少なくとも 2 台のエッジ サーバーを展開します。1 つのエッジ プールは、最大 12 台のエッジ サーバーをサポートします。処理能力を増やす必要がある場合は、複数のエッジ プールを展開できます。一般には、ユーザー ベースの 10％ は、外部アクセスを必要とします。
    

    > [!IMPORTANT]
    > トポロジ ビルダーでは、1 つの エッジ プールに最大 12 台の エッジ サーバーを構成できます。テスト済みでサポートされる、プール内の最大 エッジ サーバー数は 12 です。トポロジ ビルダーでは 12 を超える数が許容されますが、1 つの エッジ プールに 12 台を超える エッジ サーバーが暗黙的にサポートされると解釈されるものではありません。



  - **ハードウェア負荷分散**   ハードウェア負荷分散は、エッジの外部インターフェイス用にパブリック ルーティング可能な IP アドレスを使用する場合に、Lync Server 2013  エッジ サーバーの負荷を分散するためにサポートされます。たとえば、次のいずれかの用途でフェールオーバーが必要な状況でこのアプローチを使用します。
    
      - パブリック IM 接続
    
      - Microsoft Office Communications Server 2007 または Microsoft Office Communications Server 2007 R2 を実行する企業とのフェデレーション
    
      - Exchange 2007 Unified Messaging (UM) または Exchange 2010 UM への外部アクセス
        

        > [!IMPORTANT]
        > Exchange 2010 SP1 以降の DNS 負荷分散は Exchange UM でサポートされます。

    
    これら 3 つのアプリケーションは引き続き動作しますが、DNS 負荷分散に対応していないため、プール内の最初のエッジ サーバーだけに接続されます。 そのサーバーを使用できなくなると、接続は切断されます。 たとえば、フェデレーションされたトラフィックの負荷を処理するために、プールに複数のエッジ サーバーが展開されていても、実際には、1 台のアクセス プロキシだけがトラフィックを受信し、残りのサーバーはアイドル状態です。


> [!IMPORTANT]
> Lync Server 2010 および Microsoft Office 365 を使用する企業とフェデレーションしている場合は、DNS 負荷分散の使用をお勧めします。フェデレーション パートナーの多くが Office Communications Server 2007 または Office Communications Server 2007 R2 を使用している場合、パフォーマンスに大きな影響があることに注意してください。


