---
title: 'Lync Server 2013: フロントエンド サーバー、インスタント メッセージングおよびプレゼンスのトポロジおよびコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 フロントエンド サーバー、インスタント メッセージングおよびプレゼンスのトポロジおよびコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-10-24_

インスタント メッセージング (IM) とプレゼンスに必要なコンポーネントは、次に示すものだけです。

  - 組織のフロントエンドサーバーまたは Standard Edition サーバー。 これらのサーバーで、IM およびプレゼンス機能は常にオンになっています。

  - ロード バランサー (Enterprise Edition フロントエンド プールがある場合) 詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>フロントエンドプールの展開を計画する

Lync Server 2013 では、フロントエンドプールのアーキテクチャが変更され、これらの変更が、フロントエンドプールの計画と維持の方法に影響します。

すべての Enterprise Edition フロントエンドプールには、少なくとも3台のフロントエンドサーバーが含まれていることをお勧めします。 Lync Server では、フロントエンドプールのアーキテクチャで分散システムモデルが使用され、各ユーザーのデータはプール内の3つのフロントエンドサーバー上に保持されます。 この新しいアーキテクチャの詳細については、「 [Lync Server 2013 でのトポロジの変更](lync-server-2013-topology-changes.md)」を参照してください。

3つの Enterprise Edition フロントエンドサーバーを展開したくない場合、および障害回復が必要な場合は、Lync Server Standard Edition を使用して、ペアのバックアップリレーションシップを持つ2つのプールを作成することをお勧めします。 これにより、2台のサーバーのみを含む障害回復ソリューションが提供されます。 高可用性と障害回復のトポロジと機能の詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>フロントエンドプールの管理の計画

フロントエンドプールの場合は、このセクションのガイドラインに従ってください。

<div>

## <a name="ensuring-that-pools-are-functional"></a>プールが機能していることを確認する

フロントエンドプール用の新しい分散モデルを使用すると、プールを機能させるには、プールのサーバーの特定の数を実行しておく必要があります。 プールには2つの損失モードがあります。

  - 特定のルーティンググループの十分なレプリカサーバーがないために、ルーティンググループレベルのクォーラム損失が発生しました。 ルーティンググループは、プールに所属している一連のユーザーの集合体です。 各ルーティンググループには、1つのプライマリと2つのセカンダリという3つの複製がプールにあります。

  - プール レベル クォーラム損失。プールで十分な数のシード サーバーが実行されていない場合に発生します。

<div>

## <a name="routing-group-level-quorum-loss"></a>ルーティング グループ レベル クォーラム損失

新しいフロント エンド プールを初めて起動するときには、次の表に示すように、サーバーの 85% が実行されていることが必要です。実行されているサーバーの数がそれより少ないと、サービスが起動状態で行き詰まり、プールが起動されないことがあります。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>プール内のサーバーの合計数</th>
<th>プールを初めて起動させるために実行する必要があるサーバー数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>個</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>ファイブ</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>常用</p></td>
<td><p>個</p></td>
</tr>
<tr class="even">
<td><p>折り</p></td>
<td><p>ファイブ</p></td>
</tr>
<tr class="odd">
<td><p>以内</p></td>
<td><p>常用</p></td>
</tr>
</tbody>
</table>


その後もプールが起動されるたびに、サーバーの 85% が起動されている必要があります (前出の表を参照)。 この数のサーバーを起動できない (ただし、プール レベル クォーラム損失にはならない数のサーバーが起動されている) 場合は、**Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** コマンドレットを使用して、プールをルーティング グループ レベル クォーラム損失から復旧させ、処理を続行させることができます。 このコマンドレットの使い方の詳細については、「 [CsPoolRegistrarState をリセット](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)する」を参照してください。

<div>


> [!NOTE]  
> Lync Server ではプライマリ SQL データベースが監視として使用されるため、プライマリデータベースをシャットダウンし、ミラーコピーに切り替えて、前の表に従っても十分に動作しない場合には、プール全体がダウンします。 詳細については、「<A href="http://go.microsoft.com/fwlink/?linkid=393672">データベースミラーリング監視</A>」を参照してください。



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>プール レベル クォーラム損失

フロントエンドプールをまったく機能させるには、プールレベルのクォーラム損失にすることはできません。 次の表に示すように、実行しているサーバーの数が機能レベルを下回っている場合は、プール内の残りのサーバーによって、すべての Lync Server サービスが停止されます。 次の表の数値は、プール内のバックエンドサーバーが実行されていることを前提としています。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>プール内のフロントエンドサーバーの合計数</th>
<th>プールを機能させるために実行する必要があるサーバーの数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3 ～ 4</p></td>
<td><p>任意の 2 台</p></td>
</tr>
<tr class="odd">
<td><p>5 ～ 6</p></td>
<td><p>任意の 3 台</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>任意の 4 台</p></td>
</tr>
<tr class="odd">
<td><p>8 ～ 9</p></td>
<td><p>最初の 7 台のうちの任意の 4 台</p></td>
</tr>
<tr class="even">
<td><p>10 ～ 12</p></td>
<td><p>最初の 9 台のうちの任意の 5 台</p></td>
</tr>
</tbody>
</table>


この表でいう最初のサーバーとは、プールが初めて起動されたとき先に立ち上げられたものから順に数えたサーバーです。 これらのサーバーを確認するには、 **– Poolfqdn**オプションを使用して、**コンピューターの購入**コマンドレットを使用します。 このコマンドレットはサーバーをトポロジ内に出現した順に表示するので、そのリストの先頭にある方が最初のサーバーです。

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>フロントエンドサーバーが2台あるフロントエンドプール

2台のフロントエンドサーバーのみを含むフロントエンドプールの展開はお勧めしません。 このようなプールを展開する必要がある場合は、次のガイドラインに従ってください。

  - 2台のフロントエンドサーバーのいずれかがダウンしている場合は、可能な限り早く、障害が発生したサーバーをバックアップしておく必要があります。 同様に、2 台のサーバーのうち 1 台をアップグレードする必要がある場合は、アップグレードが終わり次第、オンラインにします。

  - 何らかの理由で両方のサーバーを同時に停止する必要がある場合は、プールのダウンタイムが終わったら次のことをします。
    
      - ベストプラクティスとして、フロントエンドサーバーの両方を同時に再起動することをお勧めします。
    
      - 2 台のサーバーを同時に再起動できない場合は、停止した順序とは逆の順序で復旧する必要があります。
    
      - この順序で元の状態に戻すことができない場合は、プールを復元する前に、次のコマンドレットを使用します。
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>プールを機能させるための追加の手順

フロント エンド プールを確実に機能させておくために、他にもいくつかの要因を監視する必要があります。

  - ユーザーをプールに初めて移動する場合は、少なくとも3台のフロントエンドサーバーが実行されていることを確認します。

  - このプールと障害回復目的のために別のプールとの間にペアリング関係を確立した場合は、リレーションシップを設定した後に、リレーションシップを確立した後に、このプールに3つのフロントエンドサーバーが同時に実行されていることを確認する必要があります。バックアッププールのあるデータ。 プールのペアリングと障害回復機能の詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>プールのアップグレードの信頼性を向上させる

フロントエンドプールのサーバーをアップグレードまたは更新する必要がある場合は、「 [Lync Server 2013 のフロントエンドサーバーのアップグレードまたは更新](lync-server-2013-upgrade-or-update-front-end-servers.md)に関するワークフロー」と次のガイドラインに従ってください。

  - アップグレードのために1つのアップグレードドメインから別のドメインに移動する場合 ([アップグレードまたは Lync Server 2013 のフロントエンドサーバーの更新](lync-server-2013-upgrade-or-update-front-end-servers.md)でワークフローに従います)、 **CsPoolUpgradeReadinessState**コマンドレットを使用して、[準備完了] 状態を確認します。 "準備完了" になった後の各ドメイン間で20分間の待機を追加すると、アップグレードの信頼性が向上します。 この20分間に準備ができ**ない**場合は、20分のタイマーを再起動してください。 また、 **CsPoolFabricState**コマンドレットを実行してから20分間隔を開始してから、ルーティンググループのプライマリとセカンダリを変更しないようにすることもできます。

  - 最後に修正されたアップグレードドメイン内のいずれかのサーバーが停止しているか、再開されていない場合は、次のアップグレードドメインに移動しないでください。 これは、アップグレード内のいずれかのサーバーが起動できない場合にも適用されます。 **CsPoolFabricState**を実行して、すべてのルーティンググループにプライマリと少なくとも1つのセカンダリが含まれていることを確認します。これにより、すべてのユーザーがサービスを利用できるかどうかが確認されます。

  - 一部のユーザーがサービスを利用していない場合は、– Verbose オプションを指定して**CsPoolFabricState**を実行し、レプリカが存在しないルーティンググループを確認します。 最初のトラブルシューティング手順として、プール全体を再起動しないでください。 このコマンドレットの詳細については、「 [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)」を参照してください。

  - Windows fabric のインストール/アンインストールのため、イベントビューアーまたはパフォーマンスモニターのウィンドウのすべてのインスタンスが閉じていることを確認します。

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>フロントエンドプールの構成を変更する

フロントエンドサーバーをプールに追加するか、またはプールから削除して、新しいトポロジを公開する場合は、次のガイドラインに従ってください。

  - 新しいトポロジが公開されたら、プール内の各フロントエンドサーバーを再起動する必要があります。 1 台ずつ再起動してください。

  - 構成の変更中にプール全体が停止している場合は、新しいトポロジが公開された後に次のコマンドレットを実行します。
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

フロントエンドサーバーに障害が発生し、数日以上に置き換えられない場合は、トポロジからサーバーを削除します。 再利用可能な場合は、新しいフロントエンドサーバーをトポロジに追加します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

