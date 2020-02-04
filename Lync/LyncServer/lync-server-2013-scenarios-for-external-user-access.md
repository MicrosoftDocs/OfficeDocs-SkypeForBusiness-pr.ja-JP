---
title: 'Lync Server 2013: 外部ユーザー アクセスのシナリオ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 の外部ユーザー アクセスのシナリオ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

Lync Server 2013 の外部ユーザーアクセスを提供するには、境界ネットワークに少なくとも1つのエッジサーバーと1つの逆プロキシを展開する必要があります。 必要に応じて、内部ネットワークにディレクターまたはディレクタープールを展開することができます。

1つのエッジサーバーでは提供できないキャパシティを確保する必要がある場合、またはエッジサーバーの展開に高可用性が必要な場合は、負荷分散プールで複数のエッジサーバーを構成することができます。 組織に複数のデータセンターがある場合は、複数の場所でエッジサーバーまたはエッジプールの展開を行うことができます。 ただし、1エッジサーバーの展開のみをフェデレーションルートとして指定できます。

このセクションでは、Edge Server の展開のシナリオを定義し、計画セクションを考えられるシナリオにマップします。 たとえば、高い可用性、拡張可能なメッセージングとプレゼンス (XMPP) の連絡先とのフェデレーション、および Lync のモバイル機能が必要な場合は、次の表で、これらの要件を満たす対応エントリを選択して、次のフローチャートに示すように、参照計画セクションで展開を定義します。

**エッジサーバーの展開シナリオの選択プロセス**

![展開例フローチャート](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "展開例フローチャート")

このプロセスを使用することで、ユーザーに展開する可能性があるすべての機能の構成を計画し、文書化することができます。 ただし、エッジサーバーを展開して、他の機能を追加する前に適切な操作を確認した後で、フェデレーションサービスとモバイルサービスを追加することができます。 既存のエッジサーバー展開に機能を追加するプロセスについては、「展開」セクションを参照してください。 展開の詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。最初の計画プロセスでこれらの機能の計画を含めることによって、証明書を取得し、dns およびポート/プロトコルの要件を事前に構成できるようになりました。

<div>


> [!TIP]  
> エッジサーバーとリバースプロキシをインストールし、後で機能を追加することを計画している場合 (たとえば、フェデレーションとモビリティ)、展開後にすべてのサービスに必要な証明書を決定します。 事前にすべての機能の証明書を計画して取得する場合は、最初に展開されたかどうかにより、新しい証明書の順序を設定して、フェデレーション (つまりエッジサーバー上) またはリバースプロキシ (つまり、モビリティ) の要件を満たす必要があります。サービス)。



</div>

<div>


> [!NOTE]  
> エッジサービスは、各エッジサーバー上で実行されます。 サービスは、2つの異なるエッジサーバー間で分割することはできません。 スケーラビリティのためにエッジプールを展開すると、すべてのエッジサービスがプールの各エッジサーバーに展開されます。 XMPP フェデレーション、Office Communications Server、Lync Server federation、パブリック IM 接続、クライアントモビリティは、最初のエッジサーバーまたはエッジプールの展開後に展開できる追加サービスです。 モビリティーサービスは、リバースプロキシを使用する機能です。 モバイルサービスをインストールしても、エッジサーバーに機能は追加されませんが、リバースプロキシの再構成が必要になります。 これらの機能を記載した [<STRONG>インストールの目標</STRONG>] 列では、エッジサーバーのインストールと構成時にこれらの機能が展開されるように、これらの機能を同時に計画<STRONG>するための</STRONG>、関連する列にある関連列の計画ガイダンスを示しています。



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>展開目標の特定とマッピング


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>インストールの目標</th>
<th>エッジサーバー計画のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>お客様は、インフラストラクチャのエッジサービスには1台のサーバーのみで十分であると判断しました。 また、インターネットに NAT を使用して、エッジサーバーの外部インターフェイスに対してもプライベート IP アドレスを使用することを意図しています。</p>
<p>この計画セクションは、境界に単一エッジサーバーを展開する場合に使用します。 エッジサーバーに、プライベート IP アドレスが割り当てられたエッジサーバーを展開し、インターネット上の外部ユーザーに対して NAT を使用してパブリック IP アドレスを提供します。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 におけるプライベート IP アドレスと NAT を用いた単一統合エッジ</a></p></td>
</tr>
<tr class="even">
<td><p>お客様は、インフラストラクチャのエッジサービスには1台のサーバーのみで十分であると判断しました。 また、エッジサーバーのインターネットへの外部インターフェイスにパブリック IP アドレスを使いたいと考えています。</p>
<p>この計画セクションは、境界に単一エッジサーバーを展開する場合に使用します。 エッジサーバーにパブリック IP アドレスが割り当てられたエッジサーバーを展開します。 NAT の代わりに、このシナリオでルーティングを使います。 エッジサーバーの実際のパブリック IP アドレスは、外部ユーザー接続に対して利用可能になります。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ</a></p></td>
</tr>
<tr class="odd">
<td><p>エッジサービスの高可用性がユーザーにとって重要であり、このプールに2つ以上のエッジサーバーを展開することを決定しました。 また、インターネットに NAT を使用して、エッジサーバーの外部インターフェイスに対してもプライベート IP アドレスを使用することを意図しています。</p>
<p>境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。 DNS の負荷分散を使ってプール間で通信を分散する、エッジサーバーに割り当てられているプライベート IP アドレスを持つエッジサーバーを展開します。 インターネット上の外部ユーザーに対してパブリック IP アドレスを提供するには、NAT を使用します。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</a></p></td>
</tr>
<tr class="even">
<td><p>エッジサービスの高可用性がユーザーにとって重要であり、このプールに2つ以上のエッジサーバーを展開することを決定しました。 また、エッジサーバーのインターネットへの外部インターフェイスにパブリック IP アドレスを使いたいと考えています。</p>
<p>境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。 DNS の負荷分散を使ってプール間で通信を分散する、エッジサーバーに割り当てられたパブリック IP アドレスを持つエッジサーバーを展開します。 NAT の代わりに、ルーティングを使用して、インターネット上の外部ユーザーに対してパブリック IP アドレスを提供します。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</a></p></td>
</tr>
<tr class="odd">
<td><p>エッジサービスの高可用性がユーザーにとって重要であると判断し、ハードウェアロードバランサーを使って、このプールに2つ以上のエッジサーバーを展開します。</p>
<p>境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。 ハードウェアロードバランサーを使ってプール間で通信を分散するエッジサーバーを、エッジサーバーに割り当てられたパブリック IP アドレスを使って展開します。 NAT の代わりに、ルーティングを使用して、インターネット上の外部ユーザーに対してパブリック IP アドレスを提供します。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ</a></p></td>
</tr>
<tr class="even">
<td><p>フェデレーションシナリオでは、ユーザーが通信できるパートナーの種類を拡張する機能を計画することができます。</p>
<ul>
<li><p>Lync Server フェデレーション</p></li>
<li><p>Office Communications Server フェデレーション</p></li>
<li><p>パブリック IM 接続</p></li>
<li><p>XMPP フェデレーション</p></li>
</ul></td>
<td><p>フェデレーションシナリオの計画</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Lync Server 2013 と Office Communications Server フェデレーションの計画</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセージング接続の計画</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Lync Server 2013 での拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションの計画</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>モビリティーサービスはリバースプロキシを通じて提供されます。 外部ユーザーに対するモビリティを有効にするサービスは、フロントエンドサーバーまたはフロントエンドプールに展開されます。 リバースプロキシで既存の公開ルールを作成または変更して、外部ユーザーのモビリティサービスを有効にします。</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 次のシナリオでは、リファレンスアーキテクチャ、DNS、ポート/プロトコル定義、証明書の要件などについて説明します。 DNS、ポート/プロトコル定義、証明書のニーズに関する図も含まれています。 この図では、他のチーム (たとえば、組織のネットワークチーム、公開キー基盤チーム、サーバー展開チーム) に入力して配布するためのテンプレートを提供します。 図の目的は、コミュニケーションを強化し、必要なエッジサーバー構成要素を実際の構成作業を行うユーザーに伝えるときの成功を確実にすることです。 図と関連付けられた参照アーキテクチャを使用して展開を計画することをお勧めします。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

