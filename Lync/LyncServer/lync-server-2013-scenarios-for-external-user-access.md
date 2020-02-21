---
title: 'Lync Server 2013: 外部ユーザーアクセスのシナリオ'
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
ms.openlocfilehash: 3e9a2f60b2273cf8d43833226ede66a2a90478a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザーアクセスのシナリオ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

Lync Server 2013 の外部ユーザーアクセスを提供するには、境界ネットワークに少なくとも1つのエッジサーバーと1つのリバースプロキシを展開する必要があります。 必要に応じて、ディレクターまたはディレクタープールを内部ネットワークに展開することもできます。

1台のエッジサーバーが提供できるよりも多くの容量が必要な場合や、エッジサーバーの展開に高可用性が必要な場合は、負荷分散を構成し、複数のエッジサーバーを負荷分散プールに展開することができます。 組織に複数のデータセンターがある場合は、複数の場所にエッジサーバーまたはエッジプールを展開することができます。 ただし、1つのエッジサーバー展開のみをフェデレーションルートとして指定できます。

このセクションでは、エッジサーバー展開のシナリオを定義し、計画セクションを考えられるシナリオにマップします。 たとえば、高可用性、拡張可能なメッセージングとプレゼンス (XMPP) 連絡先、および Lync モビリティを必要とする展開では、次の表の一致するエントリを選択して、これらの要件を満たすことができます。次のフローチャートに示されているように、展開を定義するための計画セクションを参照してください。

**エッジ サーバー展開シナリオの選択プロセス**

![展開のフローチャートの例](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "展開のフローチャートの例")

このプロセスを使用すると、ユーザー用に展開する可能性があるすべての機能の構成を計画し、文書化することができます。 ただし、エッジサーバーを展開して、他の機能を追加する前に正しい操作を確認した後に、フェデレーションサービスとモビリティサービスを追加することができます。 既存のエッジサーバー展開に機能を追加するプロセスについては、「展開」のセクションを参照してください。 展開の詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。初期計画プロセスの際に、dns、ファイアウォール、および証明書の要件を計画することによって、追加された機能の dns、ファイアウォール、および証明書の要件を事前に準備できます。

<div>


> [!TIP]  
> エッジサーバーとリバースプロキシのインストールを計画していて、後で機能を追加する (たとえば、フェデレーションとモビリティ) 場合は、展開後にすべてのサービスに必要な証明書を決定します。 事前に展開されているすべての機能の証明書を計画し、取得することにより、最初に展開したかしないかには、フェデレーションの要件 (つまりエッジサーバー) またはリバースプロキシ (つまりモビリティの場合) を満たす新しい証明書を注文する必要がなくなります。サービス)。



</div>

<div>


> [!NOTE]  
> 各エッジサーバーですべてのエッジサービスが実行されます。 2つの異なるエッジサーバー間でサービスを分割することはできません。 スケーラビリティを確保するためにエッジプールを展開する場合は、すべてのエッジサービスがプール内の各エッジサーバーに展開されます。 XMPP フェデレーション、Office Communications Server、Lync Server フェデレーション、パブリック IM 接続、およびクライアントモビリティは、最初のエッジサーバーまたはエッジプールを展開した後に展開できる追加のサービスです。 モビリティ サービス機能では、リバース プロキシが使用されます。 Mobility service をインストールしても、エッジサーバーに機能は追加されませんが、リバースプロキシの再構成が必要になります。 これらの機能を一覧表示する [<STRONG>インストールの目標</STRONG>] 列には、エッジサーバーをインストールして構成したときにこれらの機能を展開するための、<STRONG>エッジサーバーの計画セクションまたはセクション</STRONG>の下にある関連する列の計画ガイダンスが記載されています。



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>展開の目標を見極めて対応付ける


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>インストールの目標</th>
<th>エッジ サーバーの「計画」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>現在のインフラストラクチャのエッジ サービスには、単一のサーバーで十分であると判断しました。また、エッジ サーバーの外部インターフェイスにはプライベート IP アドレスを使用し、NAT 経由でインターネットに接続する予定です。</p>
<p>境界に単一エッジサーバーを展開する場合は、この計画セクションを使用します。 エッジサーバーには、エッジサーバーに割り当てられたプライベート IP アドレスを使用してエッジサーバーを展開し、インターネット上の外部ユーザーのパブリック IP アドレスを提供するために NAT を使用します。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 でのプライベート IP アドレスと NAT を使用する単一統合エッジ</a></p></td>
</tr>
<tr class="even">
<td><p>現在のインフラストラクチャのエッジ サービスには、単一のサーバーで十分であると判断しました。また、エッジ サーバーの外部インターフェイスにはパブリック IP アドレスを使用してインターネットに接続する予定です。</p>
<p>境界に単一エッジサーバーを展開する場合は、この計画セクションを使用します。 エッジサーバーには、パブリック IP アドレスが割り当てられているエッジサーバーを展開します。 NAT の代わりに、このシナリオではルーティングを使用します。 エッジサーバーの実際のパブリック IP アドレスは、外部ユーザー接続に対して使用可能になります。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ</a></p></td>
</tr>
<tr class="odd">
<td><p>ユーザーにとってエッジ サービスの高可用性が重要であると判断し、このプールに複数のエッジ サーバーを展開することにしました。また、エッジ サーバーの外部インターフェイスにはプライベート IP アドレスを使用し、NAT 経由でインターネットに接続する予定です。</p>
<p>境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。 DNS 負荷分散を使用してプール間で通信を分散させるために、エッジサーバーに割り当てられたプライベート IP アドレスを使用してエッジサーバーを展開します。 インターネット上の外部ユーザーには NAT を使用してパブリック IP アドレスを提供します。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 での拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散</a></p></td>
</tr>
<tr class="even">
<td><p>ユーザーにとってエッジ サービスの高可用性が重要であると判断し、このプールに複数のエッジ サーバーを展開することにしました。 また、エッジサーバーの外部インターフェイスのパブリック IP アドレスをインターネットにも使用することを目的としています。</p>
<p>境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。 DNS 負荷分散を使用してプール間で通信を分散させるために、エッジサーバーに割り当てられたパブリック IP アドレスを使用してエッジサーバーを展開します。 NAT の代わりにルーティングを使用して、インターネット上の外部ユーザーにパブリック IP アドレスを提供します。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 の拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</a></p></td>
</tr>
<tr class="odd">
<td><p>エッジサービスの高可用性がユーザーにとって重要であると判断したため、このプールには、ロードバランサー機器を使用して2台以上のエッジサーバーを展開します。</p>
<p>境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。 エッジサーバーには、ハードウェアロードバランサーを使用してプール間で通信を分散させるパブリック IP アドレスを使用して、エッジサーバーを展開します。 NAT の代わりにルーティングを使用して、インターネット上の外部ユーザーにパブリック IP アドレスを提供します。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 での拡張統合エッジとロードバランサー機器</a></p></td>
</tr>
<tr class="even">
<td><p>フェデレーションのシナリオを使用すると、ユーザーが通信できるパートナーの種類を拡大する機能の計画を立てることができます。</p>
<ul>
<li><p>Lync Server フェデレーション</p></li>
<li><p>Office Communications Server のフェデレーション</p></li>
<li><p>パブリック IM 接続</p></li>
<li><p>XMPP フェデレーション</p></li>
</ul></td>
<td><p>フェデレーションのシナリオの計画</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Lync Server 2013 および Office Communications Server のフェデレーションの計画</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセージング接続の計画</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Lync Server 2013 での拡張メッセージングおよびプレゼンスプロトコル (XMPP) フェデレーションの計画</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>モビリティ サービスはリバース プロキシを通じて提供されます。 外部ユーザーのモビリティを有効にするサービスは、フロントエンドサーバーまたはフロントエンドプールに展開されます。 リバース プロキシの公開ルールを作成または変更し、外部ユーザーに対してモビリティ サービスを有効にします。</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 以下の「シナリオ」のセクションには、関連アーキテクチャ、DNS の例、ポート/プロトコルの定義、および証明書要件が記載されています。 また、DNS、ポート/プロトコルの定義、および証明書要件用の図表も含まれています。 この図表は、記入して他のチーム (組織のネットワーク チーム、公開キー基盤チーム、サーバー展開チームなど) に配布するためのテンプレートになります。 図の目的は、コミュニケーションを強化し、必要なエッジサーバー構成要素を実際の構成作業を行うユーザーに伝える際の成功を確実にすることです。 展開を計画する際にはこの図表と関連アーキテクチャを使用することをお勧めします。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

