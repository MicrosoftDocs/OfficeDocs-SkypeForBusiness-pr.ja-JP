---
title: 'Lync Server 2013: トポロジの選択'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa98d479ca2bfeaf6214bbd1e66bb3f41b09782
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Lync Server 2013 でのトポロジの選択

</div>

<div id="mainSection">

<div id="mainBody">

_**最終更新日:** 2013-02-21_

トポロジを選択する場合は、次のサポートされているトポロジオプションのいずれかを使用できます。

<div>


> [!NOTE]
> 特に記載がない限り、Microsoft Lync Server 2010 を使用している場合は、次のガイダンスがほとんど変更されていないことがわかります。



</div>

  - [Lync Server 2013 におけるプライベート IP アドレスと NAT を用いた単一統合エッジ](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> 内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。 1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。



</div>

次の表は、サポートされている Microsoft Lync Server 2013 トポロジで利用できる機能をまとめたものです。 列見出しは、特定の Edge 構成オプションで使用できる機能を示します。 スケーリングされたエッジ (DNS load 均衡) オプションを使用すると、高可用性をサポートしていること、ルーティング可能ではないプライベート IP アドレス (NAT を含む)、またはエッジの外部インターフェイスに割り当てられているルーティング可能なパブリック IP アドレスを使用できることを確認できます。ハードウェアロードバランサーは必要ありません。

DNS の負荷分散でサポートされるエッジフェールオーバーのシナリオは、lync 間のポイントツーポイントセッション、Lync 会議セッション、Lync 間のセッション、および Office 365 です。 DNS 負荷分散のメリットが得られないエッジフェールオーバーのシナリオは、リモートユーザーの Exchange ユニファイドメッセージング (UM 2010)、パブリックインスタントメッセージング (IM) 接続、Office 通信を実行しているサーバーとのフェデレーションなどに対応しています。Server.

### <a name="summary-of-edge-server-topology-options"></a>エッジサーバーのトポロジオプションの概要

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
<th>追加 DNS A Edge プールの外部エッジサーバーに必要なレコード</th>
<th>Lync to Lync セッションのエッジフェールオーバー</th>
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
<td><p>パブリック IP を使った単一エッジ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>NAT を使用した拡張エッジ (DNS 負荷分散)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>パブリック IP を使った拡張エッジ (DNS 負荷分散)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>スケーリングされたエッジハードウェアの負荷分散)</p></td>
<td><p>はい</p></td>
<td><p>× (VIP ごとに 1 つの DNS A レコード)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
</tbody>
</table>


**\*** パブリックインスタントメッセージング (IM) 接続のフェールオーバーと、Office Communications Server を実行しているサーバーとのフェデレーションは、DNS の負荷分散では利用できません。 DNS 負荷分散を使用した exchange UM (リモートユーザー) のフェールオーバーには、Exchange Server 2010 SP1 以上が必要です。



> [!NOTE]
> 単一のエッジとスケーリングされたエッジ (DNS 負荷分散) には、次のような用途があります。
> <ul><li><p>ルーティング可能なパブリック IP アドレス</p></li>
> <li><p>対称ネットワークアドレス変換 (NAT) が使用されている場合、ルーティング可能ではないプライベート IP アドレス</p></li>
>
> <ul><li> NAT でパブリック IP アドレスまたはプライベート IP アドレスを使用している場合でも、トポロジビルダーの構成の選択に基づいて、同じ数の IP アドレスを使用します。 サービスごとに個別のポートを使用するようにエッジサーバーを構成することも、サービスごとに個別の IP アドレスを使用することもできますが、同じポート (既定では TCP 443) を使うことができます。</li></ul>>
> NAT でルーティング不能なプライベート IP アドレスを使用する場合は、次の操作を行います。
> <ul><li><p>ルーティング可能なプライベート IP アドレスは、すべての3つの外部インターフェイスで使用する必要があります。</p></li>
> <li><p>受信および送信トラフィック用に対称 NAT を構成する必要がある</p></li></ul>>
> スケーリングされたエッジ (ハードウェア負荷分散) トポロジでは、パブリック IP アドレスを使用する必要があります。



Lync Server 2013 は、ネットワークアドレス変換 (NAT) を実行するルーターまたはファイアウォールの背後にあるアクセス、Web 会議、および A/V Edge の外部インターフェイスの配置をサポートしています。統合されたエッジサーバートポロジの1つとスケーリングの両方に対応しています。

すべてのエッジに NAT を使用するには、DNS の負荷分散を使用する必要があります。 ハードウェアロードバランサーの使用と比較した場合、DNS の負荷分散を使用すると、次の一覧に示すように、エッジプールでエッジサーバーあたりのパブリック IP アドレスの数を減らすことができます。

  - Lync Server 2013 の統合エッジ (DNS 負荷分散) には、Edge プールのエッジサーバーごとに3つのパブリック IP アドレスが必要です。

  - Lync Server 2013 の統合されたエッジ (ハードウェア負荷分散) には、ロードバランサーの仮想 IP アドレスに対して3つのパブリック IP アドレスが必要です (プールに追加されたエッジサーバーが増加しないため1回限りの場合)。プール内のエッジサーバー。

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>スケーリングされた統合エッジの IP アドレス要件 (役割ごとの IP アドレス)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>1つのプールあたりのエッジサーバーの数</th>
<th>必要な IP アドレスの数 Lync Server 2013 (DNS 負荷分散)</th>
<th>必要な IP アドレスの数 Lync Server 2013 (ハードウェアの負荷分散)</th>
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
<td><p>ファイブ</p></td>
<td><p>3 (VIP ごとに 1 つ) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>以内</p></td>
<td><p>3 (VIP ごとに 1 つ) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>マート</p></td>
<td><p>3 (VIP あたり 1) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>スケーリングされた統合エッジの IP アドレス要件 (すべての役割の単一 IP アドレス)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>1つのプールあたりのエッジサーバーの数</th>
<th>必要な IP アドレスの数 Lync Server 2013 (DNS 負荷分散)</th>
<th>必要な IP アドレスの数 Lync Server 2013 (ハードウェアの負荷分散)</th>
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


トポロジ選択の主要な決定ポイントは、高可用性と負荷分散です。 高可用性の要件は、負荷分散の決定に影響を与える可能性があります。

  - **高可用性**  高可用性が必要な場合は、少なくとも2つのエッジサーバーをプールに展開します。 1つのエッジプールは、最大12台のエッジサーバーをサポートします。 さらに多くの容量が必要な場合は、複数のエッジプールを展開できます。 一般的な規則として、特定のユーザーベースの 10% には外部アクセスが必要です。
    
    <div>
    

    > [!IMPORTANT]
    > トポロジビルダーを使用すると、1つのエッジプールで最大20台のエッジサーバーを構成できます。 プール内のエッジサーバーのうち、テストおよびサポートされている最大数は12個とトポロジービルダーで、1つのエッジプールで12台以上のエッジサーバーに対して暗示的なサポートを行うことはできません。

    
    </div>

  - **ハードウェア負荷分散**  エッジ外部インターフェイスに対してパブリックルーティング可能な IP アドレスを使用している場合、ハードウェア負荷分散がサポートさ2013れます。 たとえば、次のいずれかのアプリケーションでフェールオーバーが必要な場合に、この方法を使用します。
    
      - パブリック IM 接続
    
      - Microsoft Office Communications Server 2007 または Microsoft Office Communications Server 2007 R2 を実行している企業とのフェデレーション
    
      - Exchange 2007 ユニファイドメッセージング (UM) または Exchange 2010 UM への外部アクセス
        
        <div>
        

        > [!IMPORTANT]
        > Exchange 2010 SP1 以降の DNS の負荷分散は、Exchange UM でサポートされています。

        
        </div>
    
    これら3つのアプリケーションは引き続き動作しますが、DNS の負荷分散に対応しておらず、プールの最初のエッジサーバーにのみ接続されます。 そのサーバーが利用できない場合、接続は失敗します。 たとえば、フェデレーションされたトラフィックの負荷を処理するために複数のエッジサーバーがプールに展開されている場合、他のユーザーがアイドル状態になっている間、実際にトラフィックを受信するのは1つのアクセスプロキシだけです。

<div>


> [!IMPORTANT]
> Lync Server 2010 および Microsoft Office 365 を使用して会社とフェデレーションする場合は、DNS の負荷分散を使用することをお勧めします。 フェデレーションパートナーの大半が Office Communications Server 2007 または Office Communications Server 2007 R2 を使用している場合、パフォーマンスへの影響が大きくなることに注意してください。



</div>

</div>

<span> </span>

</div>

</div>

</div>

