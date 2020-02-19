---
title: 'Lync Server 2013: フロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2865d1a4169491751643e7b16601a5ed3efcded
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-10-24_

インスタントメッセージング (IM) とプレゼンスに必要なコンポーネントは、次のものだけです。

  - 組織のフロントエンドサーバーまたは Standard Edition サーバー。 IM とプレゼンスの機能は、これらのサーバー上で常に有効になります。

  - エンタープライズエディションのフロントエンドプールを使用している場合は、ロードバランサー。 詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>フロントエンドプールの展開の計画

Lync Server 2013 では、フロントエンドプールのアーキテクチャが変更され、これらの変更によってフロントエンドプールを計画および管理する方法が変わります。

すべての Enterprise Edition フロントエンドプールに、少なくとも3台のフロントエンドサーバーが含まれるようにすることをお勧めします。 Lync Server では、フロントエンドプールのアーキテクチャは分散システムモデルを使用しており、各ユーザーのデータはプール内の3つのフロントエンドサーバー上に保持されます。 この新しいアーキテクチャの詳細については、「 [Lync Server 2013 のトポロジの変更](lync-server-2013-topology-changes.md)」を参照してください。

3つの Enterprise Edition フロントエンドサーバーを展開せず、障害復旧を必要とする場合は、Lync Server Standard Edition を使用して、バックアップ関係がペアになった2つのプールを作成することをお勧めします。 これにより、2台のサーバーのみの障害復旧ソリューションが提供されます。 高可用性と障害復旧のトポロジおよび機能の詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>フロントエンドプールの管理の計画

フロントエンドプールの場合は、このセクションのガイドラインに従ってください。

<div>

## <a name="ensuring-that-pools-are-functional"></a>プールが機能していることを確認する

フロントエンドプール用の新しい分散モデルでは、プールが機能するためには特定の数のプールのサーバーが実行されている必要があります。 プールには2つの損失モードがあります。

  - 特定のルーティンググループに十分な数のレプリカサーバーがないことによって発生した、ルーティンググループレベルのクォーラム損失。 ルーティンググループとは、プールに所属する一連のユーザーの集合です。 各ルーティンググループには、プールに3つのレプリカがあります。1つはプライマリ、2つはセカンダリです。

  - プールレベルのクォーラム損失。プール内で十分な数のシードサーバーが実行されていない場合に発生します。

<div>

## <a name="routing-group-level-quorum-loss"></a>ルーティンググループレベルのクォーラム損失

新しいフロントエンドプールを初めて起動するときは、次の表に示すように、サーバーの85% が稼働していることが重要です。 実行されているサーバーの数が少ない場合、サービスが開始状態になり、プールが開始されない可能性があります。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>プール内のサーバーの合計数</th>
<th>プールを初めて起動するために実行する必要があるサーバーの数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pbm-2</p></td>
<td><p>1-d</p></td>
</tr>
<tr class="even">
<td><p>1/3</p></td>
<td><p>1/3</p></td>
</tr>
<tr class="odd">
<td><p>2/4</p></td>
<td><p>1/3</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>2/4</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10 </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>11 </p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>10 </p></td>
</tr>
</tbody>
</table>


今後プールが起動されるたびに、サーバーの85% が開始されます (前の表に示すように)。 この数のサーバーを開始できない (ただし、プールレベルのクォーラム損失が発生しないように、十分な数のサーバーを開始できる) 場合は、 **reset-cspoolregistrarstate – ResetType QuorumLossRecovery**コマンドレットを使用して、このルーティンググループレベルのクォーラム損失から回復できるようにプールを有効にし、進行状況を確認できます。 このコマンドレットの使用方法の詳細については、「 [reset-cspoolregistrarstate](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)」を参照してください。

<div>


> [!NOTE]  
> Lync Server はプライマリ SQL データベースをミラーリング監視として使用しているため、プライマリデータベースをシャットダウンして、ミラーコピーに切り替え、十分な数のフロントエンドサーバーをシャットダウンして、前の表に従って十分でない場合は、プール全体がダウンします。 詳細については、「<A href="https://go.microsoft.com/fwlink/?linkid=393672">データベースミラーリング監視</A>」を参照してください。



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>プールレベルのクォーラム損失

フロントエンドプールが完全に機能するために、プールレベルのクォーラム損失になることはありません。 次の表に示すように、実行しているサーバーの数が機能レベルの下にある場合は、プール内の残りのサーバーがすべての Lync Server サービスを停止します。 次の表の番号は、プール内のバックエンドサーバーが動作していることを前提としています。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>プール内のフロントエンド サーバーの総数</th>
<th>プールが機能するために実行されている必要のあるサーバーの数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pbm-2</p></td>
<td><p>1-d</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>任意の2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>任意の3つ</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>任意4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>最初の7台のサーバーのうち4台</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>最初の9台のサーバーのうち5台</p></td>
</tr>
</tbody>
</table>


上記の表では、最初にプールが開始されたときに、最初に開始されたサーバーが "最初のサーバー" です。 これらのサーバーを決定するには、 **-** **poolfqdn**オプションを指定して、コマンドレットを使用できます。 このコマンドレットでは、トポロジに表示される順序でサーバーが表示され、一覧の一番上にあるサーバーが最初のサーバーになります。

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>フロントエンドサーバーが2台のフロントエンドプール

2台のフロントエンドサーバーのみが含まれるフロントエンドプールを展開することはお勧めしません。 このようなプールを展開する必要が生じた場合は、次のガイドラインに従ってください。

  - 2台のフロントエンドサーバーのうち1台がダウンした場合は、障害が発生したサーバーをできるだけ早く復旧するようにしてください。 同様に、2台のサーバーのいずれかをアップグレードする必要がある場合は、アップグレードが完了したらすぐにオンラインに戻します。

  - 何らかの理由で両方のサーバーを同時に停止する必要がある場合は、プールのダウンタイムが終了したら、次の手順を実行します。
    
      - ベストプラクティスは、両方のフロントエンドサーバーを同時に再起動することです。
    
      - 2台のサーバーを同時に再起動できない場合は、停止した順序とは逆の順序でバックアップする必要があります。
    
      - その順序で復元できない場合は、プールを復旧する前に、次のコマンドレットを使用してください。
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>プールが機能していることを確認するための追加の手順

フロントエンドプールが機能していることを確認するには、他にもいくつかの要因を監視する必要があります。

  - ユーザーをプールに初めて移動するときは、少なくとも3台のフロントエンドサーバーが稼働していることを確認してください。

  - このプールと障害復旧のために別のプールとの間にペアリング関係を確立した場合は、その関係を確立した後に、このプールに、同時に実行されている3台のフロントエンドサーバーが存在することを確認する必要があります。バックアッププールを使用したデータ。 プールのペアリングと障害復旧機能の詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>プールのアップグレードの信頼性を向上させる

フロントエンドプール内のサーバーをアップグレードまたは更新する必要がある場合は、「 [Lync Server 2013 でのフロントエンドサーバーのアップグレードまたは更新](lync-server-2013-upgrade-or-update-front-end-servers.md)」に示されているワークフローに従って、次のガイドラインを参照してください。

  - アップグレードドメイン間を移行するために ([アップグレード時または Lync Server 2013 でのフロントエンドサーバーの更新](lync-server-2013-upgrade-or-update-front-end-servers.md)時にワークフローに従って) 別のアップグレードドメインに移動する場合は、 **get-cspoolupgradereadinessstate 戻し**コマンドレットを使用して、レディ状態をチェックします。 「Ready」に達した後、各アップグレードドメインの間に20分間の待ち時間を追加すると、アップグレードの信頼性が向上します。 この20分間の準備ができ**ない状態**になった場合は、20分のタイマーを再起動します。 また、20分間隔を開始する前と後に**get-cspoolfabricstate**コマンドレットを実行して、ルーティンググループのプライマリとセカンダリが変更されていないことを確認することもできます。

  - 最後にパッチが適用されたアップグレードドメイン内のサーバーが停止または再起動しない場合は、次のアップグレードドメインに移動しないでください。 これは、アップグレード中のいずれかのサーバーが開始できない場合にも適用されます。 **Get-cspoolfabricstate**を実行して、すべてのルーティンググループにプライマリおよび少なくとも1つのセカンダリがあることを確認します。これにより、すべてのユーザーがサービスを利用できるかどうかが確認されます。

  - 一部のユーザーがサービスを所有していて、他のユーザーがいない場合は、-Verbose オプションを指定して**get-cspoolfabricstate**を実行し、レプリカがないルーティンググループを確認します。 最初のトラブルシューティング手順として、プール全体を再起動しないでください。 このコマンドレットの詳細については、「 [get-cspoolfabricstate](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)」を参照してください。

  - Windows fabric のインストール/アンインストールの際に、イベントビューアまたはパフォーマンスモニターウィンドウのすべてのインスタンスが閉じていることを確認してください。

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>フロントエンドプールの構成の変更

フロントエンドサーバーをプールに追加、またはプールから削除した後、新しいトポロジを公開する場合は、次のガイドラインに従ってください。

  - 新しいトポロジが公開されたら、プール内の各フロントエンドサーバーを再起動する必要があります。 一度に1つずつ再起動します。

  - 構成の変更中にプール全体がダウンしていた場合は、新しいトポロジが公開された後、次のコマンドレットを実行します。
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

フロントエンドサーバーに障害が発生した場合、数日間またはそれ以上の交換が必要になる可能性がある場合は、サーバーをトポロジから削除します。 再び使用できるようになったら、新しいフロントエンドサーバーをトポロジに追加します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

