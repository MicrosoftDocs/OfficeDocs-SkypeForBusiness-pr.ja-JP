---
title: 'Lync Server 2013: トポロジの選択'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a75e1e829b59ff66df6b598c63b35f2f78981e4
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Lync Server 2013 でのトポロジの選択

</div>

<div id="mainSection">

<div id="mainBody">

_**トピックの最終更新日:** 2013-02-21_

トポロジの選択では、次に示すサポートされるトポロジ オプションのいずれかを使用できます。

<div>


> [!NOTE]
> 特に明記されていない限り、Microsoft Lync Server 2010 を使用している場合は、ここに示すガイダンスがほぼ変更されていないことがわかります。



</div>

  - [Lync Server 2013 でのプライベート IP アドレスと NAT を使用する単一統合エッジ](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 での拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 の拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 での拡張統合エッジとロードバランサー機器](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> 内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。



</div>

次の表に、サポートされている Microsoft Lync Server 2013 トポロジで使用可能な機能を示します。 列見出しは、該当するエッジ構成オプションで使用できる機能を示しています。 たとえば、拡張エッジ (DNS 負荷分散) オプションでは、高可用性がサポートされること、エッジの外部インターフェイスに割り当てられたルーティング不可のプライベート IP アドレス (NAT を使用) またはルーティング可能なパブリック IP アドレスを使用できること、およびロード バランサー機器が必要ないのでコストが削減されることがわかります。

DNS 負荷分散でサポートされているエッジフェールオーバーのシナリオには、Lync から Lync へのポイントツーポイントセッション、Lync 会議セッション、Lync から PSTN へのセッション、Office 365、および Microsoft 365 があります。 DNS 負荷分散の恩恵を受けられないエッジフェールオーバーのシナリオは、リモートユーザー Exchange ユニファイドメッセージング (UM) (Exchange 2010 SP1 以前)、パブリックインスタントメッセージング (IM) 接続、および Office Communications Server を実行しているサーバーとのフェデレーションのフェールオーバーです。

### <a name="summary-of-edge-server-topology-options"></a>エッジ サーバー トポロジ オプションの概要

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
<th>Lync 対 Lync セッションのエッジフェールオーバー</th>
<th>Lync 対 Lync EUM/PIC/OCS フェデレーションセッションのエッジフェールオーバー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NAT を使用する単一エッジ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>パブリック IP を使用する単一エッジ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>NAT を使用する拡張エッジ (DNS 負荷分散)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>パブリック IP を使用する拡張エッジ (DNS 負荷分散)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>拡張エッジ (ハードウェア負荷分散)</p></td>
<td><p>はい</p></td>
<td><p>いいえ (VIP ごとに 1 つの DNS A レコード)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
</tbody>
</table>


**\*** パブリックインスタントメッセージング (IM) 接続のフェールオーバー、および Office Communications Server を実行しているサーバーとのフェデレーションは、DNS 負荷分散では使用できません。 DNS 負荷分散を使用した exchange UM (リモートユーザー) のフェールオーバーには、Exchange Server 2010 SP1 以降が必要です。



> [!NOTE]
> 単一エッジおよび拡張エッジ (DNS 負荷分散) トポロジでは、次のアドレスを使用できます。
> <ul><li><p>ルーティング可能なパブリック IP アドレス</p></li>
> <li><p>対称ネットワークアドレス変換 (NAT) を使用している場合は、ルーティング可能でないプライベート IP アドレス</p></li>
>
> <ul><li> NAT でパブリック IP アドレスまたはプライベート IP アドレスを使用する場合でも、トポロジビルダーの構成選択に基づいて、同じ数の IP アドレスを使用することになります。 サービスごとに個別のポートを持つ単一の IP アドレスを使用するようにエッジサーバーを構成することも、サービスごとに個別の IP アドレスを使用することもできますが、同じポート (既定では TCP 443) を使用します。</li></ul>>
> NAT でルーティング不能なプライベート IP アドレスを使用する場合は、次のようにします。
> <ul><li><p>3つすべての外部インターフェイスで、ルーティング可能なプライベート IP アドレスを使用する必要があります。</p></li>
> <li><p>受信トラフィックと送信トラフィック用に対称 NAT を構成する必要があります。</p></li></ul>>
> 拡張エッジ (ハードウェア負荷分散) トポロジでは、パブリック IP アドレスを使用する必要があります。



Lync Server 2013 では、単一および拡張統合エッジサーバートポロジの両方でネットワークアドレス変換 (NAT) を実行する、ルーターまたはファイアウォールの背後にあるアクセス、Web 会議、および音声ビデオエッジ外部インターフェイスの配置をサポートしています。

すべてのエッジ外部インターフェイスで NAT を使用する場合は、DNS 負荷分散を使用する必要があります。ロード バランサー機器を使用する場合に比べて、NAT を使わずに DNS 負荷分散を使用すると、次の一覧に示すとおり、エッジ プール内のエッジ サーバーごとのパブリック IP アドレス数を減らすことができます。

  - Lync Server 2013 の拡張統合エッジ (DNS 負荷分散) には、エッジプールの各エッジサーバーに3つのパブリック IP アドレスが必要です。

  - Lync Server 2013 の拡張統合エッジ (ハードウェア負荷分散) は、ロードバランサーの仮想 IP アドレスに3つのパブリック IP アドレスを必要とします (プールに追加されたエッジサーバーの数が増えると増加しない1つの要件)、およびプール内のエッジサーバーごとの3つのパブリック IP アドレスが必要です。

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>拡張統合エッジに必要な IP アドレス (役割ごとの IP アドレス)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プールごとのエッジ サーバー数</th>
<th>必要な IP アドレスの数 Lync Server 2013 (DNS 負荷分散)</th>
<th>必要な IP アドレス数 Lync Server 2013 (ハードウェア負荷分散)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>6 </p></td>
<td><p>3 (VIP ごとに 1 つ) + 6</p></td>
</tr>
<tr class="even">
<td><p>3 </p></td>
<td><p>9 </p></td>
<td><p>3 (VIP ごとに 1 つ) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>12 </p></td>
<td><p>3 (VIP ごとに 1 つ) + 12</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>15 </p></td>
<td><p>3 (VIP ごとに 1 つ) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>拡張統合エッジに必要な IP アドレス (すべての役割に対して 1 つの IP アドレス)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プールごとのエッジ サーバー数</th>
<th>必要な IP アドレスの数 Lync Server 2013 (DNS 負荷分散)</th>
<th>必要な IP アドレス数 Lync Server 2013 (ハードウェア負荷分散)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>2 </p></td>
<td><p>1 (VIP ごとに 1 つ) + 2</p></td>
</tr>
<tr class="even">
<td><p>3 </p></td>
<td><p>3 </p></td>
<td><p>1 ( VIP ごとに 1 つ) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>4 </p></td>
<td><p>1 (VIP ごとに 1 つ) + 4</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>5</p></td>
<td><p>1 (VIP ごとに 1 つ) + 5</p></td>
</tr>
</tbody>
</table>


トポロジ選択を決定する上で最も優先されるポイントは、高可用性と負荷分散です。 高可用性の要件は、負荷分散の決定に影響を及ぼすことがあります。

  - **高可用性**  高可用性が必要な場合は、少なくとも2台のエッジサーバーをプールに展開します。 1つのエッジプールは最大12台のエッジサーバーをサポートします。 処理能力を増やす場合は、複数のエッジ プールを展開できます。 一般には、ユーザー ベースの 10％ は、外部アクセスを必要とします。
    
    <div>
    

    > [!IMPORTANT]
    > トポロジビルダーを使用すると、1つのエッジプールで最大20台のエッジサーバーを構成できます。 プール内のエッジサーバーのテスト済みおよびサポートされる最大数は12で、12より大きい数のトポロジビルダーは、1つのエッジプールに12台以上のエッジサーバーがあることを示す暗黙的なサポートとして解釈されないようにする必要があります。

    
    </div>

  - **ハードウェア負荷分散**  エッジの外部インターフェイスに対してパブリックルーティング可能な IP アドレスを使用している場合、Lync Server 2013 エッジサーバーの負荷分散は、ハードウェア負荷分散をサポートします。 たとえば、次のいずれかのアプリケーションでフェールオーバーが必要な状況でこのアプローチを使用します。
    
      - パブリック IM 接続
    
      - Microsoft Office Communications Server 2007 または Microsoft Office Communications Server 2007 R2 を実行している企業とのフェデレーション
    
      - Exchange 2007 Unified Messaging (UM) または Exchange 2010 UM への外部アクセス
        
        <div>
        

        > [!IMPORTANT]
        > Exchange UM では、Exchange 2010 SP1 以降の DNS 負荷分散がサポートされています。

        
        </div>
    
    これら 3 つのアプリケーションは引き続き動作しますが、DNS 負荷分散に対応していないため、プール内の最初のエッジ サーバーだけに接続されます。 そのサーバーを使用できなくなると、接続は切断されます。 たとえば、フェデレーションされたトラフィックの負荷を処理するために、プールに複数のエッジ サーバーが展開されていても、実際には、1 台のアクセス プロキシだけがトラフィックを受信し、残りのサーバーはアイドル状態です。

<div>


> [!IMPORTANT]
> Lync Server 2010 および Office 365 または Microsoft 365 を使用して企業とフェデレーションを行う場合は、DNS 負荷分散を使用することをお勧めします。 フェデレーションパートナーの大部分が Office Communications Server 2007 または Office Communications Server 2007 R2 を使用している場合は、パフォーマンスに著しい影響を与えることに注意してください。



</div>

</div>

<span> </span>

</div>

</div>

</div>

