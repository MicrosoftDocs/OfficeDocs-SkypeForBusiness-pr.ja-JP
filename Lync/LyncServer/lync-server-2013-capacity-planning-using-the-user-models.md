---
title: Lync Server 2013 ユーザーモデルを使用した処理能力の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab2b7026ca49f8e12a5f8b67aa0780996feaebe1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>ユーザーモデルを使用した Lync Server 2013 の容量計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-01-14_

このセクションでは、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で説明されている使用法に従って、サイトで必要なサーバーの数についてのガイダンスを提供します。

<div>

## <a name="tested-hardware-platform"></a>テスト済みのハードウェアプラットフォーム

このセクションのパフォーマンスの結果と展開に関する推奨事項はすべて、次の表に示すハードウェアを実行しているサーバーのパフォーマンステストに基づいています。 同様のハードウェアを使用することをお勧めします。 より強力なハードウェアを使用すると、機能に問題が発生したり、パフォーマンスが低下したりする可能性があります。 これらの推奨ハードウェアは、以前のバージョンの Lync Server よりも高いことに注意してください。

### <a name="hardware-used-in-performance-testing"></a>パフォーマンステストで使用されるハードウェア

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ハードウェア コンポーネント</th>
<th>推奨</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上</p>
<p>Lync Server のサーバーの役割では、Intel Itanium プロセッサはサポートされていません。</p></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>32 ギガバイト (GB)</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>1万 RPM のハードディスクドライブのうち、少なくとも 72 GB の空きディスク領域があるものを8台以上。</p>
<p>ディスクのうち 2 台で RAID 1 を使用し、6 台で RAID 10 を使用する必要があります。</p>
<p>-や</p></li>
<li><p>10,000 RPM の機械的ディスク ドライブ 8 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>結果の概要

次の表は、これらの推奨事項を要約したものです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>サーバーの役割</th>
<th>サポートされる最大ユーザー数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>12台のフロントエンドサーバーと1つのバックエンドサーバー、またはバックエンドサーバーのミラー化されたペアのフロントエンドプール。</p></td>
<td><p>8万ユーザーが同時にログインし、50% 複数のプレゼンスポイント (MPOP) が表示されます。これには、非モバイルインスタンスが表示されます。さらに、合計152000エンドポイントのモビリティが有効になっているユーザーの40%。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ会議</p></td>
<td><p>フロントエンドプールによって提供される音声ビデオ会議サービスは、最大会議サイズ250ユーザーを想定し、一度に実行する大規模な会議を1つだけ持つプールの会議をサポートします。</p>
<div>

> [!NOTE]  
> さらに、大規模な会議をホストするために2台のフロントエンドサーバーを使用する独立したフロントエンドプールを展開することで、250と1000ユーザーの間の大規模な会議をサポートすることができます。 詳細については、「 <A href="lync-server-2013-supporting-large-meetings.md">Lync Server 2013 を使用した大規模会議のサポート</A>」を参照してください。


</div></td>
</tr>
<tr class="odd">
<td><p>1 台のエッジ サーバー</p></td>
<td><p>12000同時リモートユーザー</p></td>
</tr>
<tr class="even">
<td><p>1 台のディレクター</p></td>
<td><p>12000同時リモートユーザー</p></td>
</tr>
<tr class="odd">
<td><p>監視およびアーカイブ</p></td>
<td><p>Lync Server 2013 では、監視およびアーカイブのフロントエンドサービスが、個別のサーバーの役割ではなく、各フロントエンドサーバーで実行されるようになりました。</p>
<p>監視とアーカイブには、それぞれ独自のデータベースストアが必要です。 Exchange 2013 も実行している場合は、専用の SQL データベースではなく、Exchange にアーカイブデータを保持できます。</p></td>
</tr>
<tr class="even">
<td><p>1 台の仲介サーバー</p></td>
<td><p>フロントエンドサーバーと併置された仲介サーバーは、プール内のすべてのフロントエンドサーバーで実行され、プール内のユーザーに十分な容量を提供する必要があります。 スタンドアロンの仲介サーバーの場合は、このトピックで後述する「仲介サーバー」のセクションを参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>1 台の Standard Edition サーバー</p></td>
<td><p>Standard Edition サーバーを使用してユーザーをホストする場合は、「 <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 での高可用性と障害復旧の計画</a>」の推奨事項を使用して、常に2台のサーバーを使用することを強くお勧めします。 ペア内の各サーバーは最大2500ユーザーをホストでき、1台のサーバーが障害を発生した場合、残りのサーバーはフェールオーバーシナリオで5000ユーザーをサポートできます。</p>
<p>展開に大量のオーディオまたはビデオトラフィックが含まれている場合、サーバーあたりのユーザー数が2500を超えると、サーバーのパフォーマンスが低下することがあります。 この場合は、より多くの Standard Edition サーバーを追加するか、Lync Server Enterprise Edition に移行することを検討する必要があります。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>フロント エンド サーバー

<div>


> [!NOTE]  
> 拡張されたプールは、このサーバーの役割ではサポートされていません。



</div>

フロントエンドプールには、プール内のすべてのサーバーでハイパースレッディングが有効になっており、サーバーハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提として、プールに所属する6660ユーザーごとに1台のフロントエンドサーバーが必要です。 1つのフロントエンドプール内のユーザーの最大数は、ハイパースレッディングがプール内のすべてのサーバーで有効になっていることを前提としています (8万)。 サイトに 80,000 を超えるユーザーが存在する場合、複数のフロント エンド プールを展開できます。

フロント エンド プール内のユーザー数を考慮する際は、このフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。

アクティブなサーバーが使用できなくなると、その接続はプール内にある他のサーバーに自動的に転送されます。 たとえば、3万ユーザーと5台のフロントエンドサーバーがある場合、1台のサーバーを使用できない場合は、6000ユーザーの接続を他の4台のサーバーに転送する必要があります。 残りの4台のサーバーはそれぞれ7500ユーザーを持ち、推奨されるよりも大きな数です。

その代わりに、3万ユーザーの6台のフロントエンドサーバーを使用していて、その後で使用できなくなった場合は、合計で5000ユーザーが残りの5台のサーバーに移動されます。 これら5台のサーバーはそれぞれ6000ユーザーをホストしますが、これは推奨範囲になっています。

1 フロント エンド プール内の最大ユーザー数は 80,000 です。 プール内のフロントエンドサーバーの最大数は12です。

8万ユーザーが含まれるフロントエンドプールの場合、通常、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)に準拠する展開では、12台のフロントエンドサーバーでパフォーマンスを十分に確保できます。 障害復旧フェールオーバーをサポートするように設計されている展開では、2つのペアのフロントエンドプールのそれぞれで最大4万ユーザーをホストすることができます。各プールには、両方のプールのユーザーに対応する十分な数のフロントエンドサーバーがあり、1つのプールに障害が発生する必要があります。になります。

特定のフロントエンドプールでサポートされているユーザーの数は、次の理由から、これらの値と異なる場合があります。

  - フロントエンドサーバーのハードウェアは、 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていません。

  - ユーザー モデルよりもかなり多い会議トラフィックの場合など、組織の使用法がユーザー モデルのそれと著しく異なります。

<div>


> [!IMPORTANT]  
> Lync Server 2013 では、プレゼンスデータベースは、バックエンドサーバーでホストされていた Lync Server 2010 とは異なり、フロントエンドサーバーでホストされるようになりました。 これは、フロントエンドサーバーによってホストされているユーザーの数に関係なく、このセクションおよび<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 のサーバーハードウェアプラットフォーム</A>で前述した推奨事項から、フロントエンドサーバーのディスクのパフォーマンスと容量を侵害してはならないことを意味します。



</div>

次の表に、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で定義されているように、ユーザーモデルを使用して IM とプレゼンスの平均帯域幅を示します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ユーザー単位の平均帯域幅</th>
<th>6660ユーザーのフロントエンドサーバーごとの帯域幅要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.3 Kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> フロントエンドサーバーで併置された音声ビデオ会議と仲介サーバーの機能のメディアパフォーマンスを向上させるには、フロントエンドサーバーのネットワークアダプターで受信側の拡大/縮小 (RSS) を有効にする必要があります。 RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。 詳細については、「」の「Windows Server 2008 の受信側<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>スケーリングの拡張機能」を参照してください。 RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>最大会議数

ユーザーモデルでは、プール内のユーザーの5% が一度に会議に参加している可能性があるため、8万のユーザーのプールは、一度に1人の電話会議に約4000ユーザーを持つことができます。 これらの電話会議は、メディアが混在していることが予想されます (一部の IM のみ、一部の IM、オーディオ/ビデオなど)、参加者の数です。 許可されている実際の電話会議数に対するハードリミットはありません。実際の使用量によって実際のパフォーマンスが決まります。 たとえば、組織にユーザーモデルで想定されているよりも多くの混在モードの会議がある場合は、このドキュメントの推奨事項より多くのフロントエンドサーバーまたは音声ビデオ会議サーバーを展開する必要がある場合があります。 ユーザーモデルの前提条件の詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。

通常の Lync Server 2013 フロントエンドプールでホストされている、サポートされている会議の最大サイズは、ユーザーが250参加者であることを示しています。 250ユーザーの会議が発生している間も、プールは引き続き他の会議をサポートしています。これには、プールユーザーの合計5% が同時会議に含まれます。 たとえば、12台のフロントエンドサーバーと8万ユーザーのプールでは、250ユーザーの会議が発生している間、Lync Server は、小規模の電話会議に参加している他のユーザーの3750をサポートします。

Lync Server は、フロントエンドプールまたは Standard Edition サーバーに所属しているユーザー数に関係なく、250ユーザーの会議をホストしている同じプールまたはサーバー上の小さな会議に参加する、少なくとも125の他のユーザーをサポートします。

250ユーザーと1000ユーザーの間で会議を有効にするには、これらの会議をホストするためだけに別のフロントエンドプールをセットアップできます。 このフロントエンドプールでは、ユーザーはホストされません。 詳細については、「 [Lync Server 2013 を使用した大規模会議のサポート](lync-server-2013-supporting-large-meetings.md)」を参照してください。

ユーザーモデルで想定されているよりも多くの混合モード会議が組織にある場合は、このドキュメントの推奨事項 (上限は 12 FEs) より多くのフロントエンドサーバーを展開する必要がある場合があります。 ユーザーモデルの前提条件の詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。

</div>

<div>

## <a name="edge-server"></a>エッジ サーバー

<div>


> [!NOTE]  
> 拡張されたプールは、このサーバーの役割ではサポートされていません。



</div>

サイトに同時にアクセスする12000リモートユーザーごとに1つのエッジサーバーを展開する必要があります。 高可用性を実現するために 2 つ以上のエッジ サーバーを用意することをお勧めします。 これらの推奨事項は、エッジサーバーのハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提としています。

エッジ サーバーのユーザー数を考慮する際は、このサイトのフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。

<div>


> [!NOTE]  
> エッジ サーバーの音声ビデオ会議エッジ サービスのパフォーマンスを改善するには、エッジ サーバーのネットワーク アダプターの Receive-side Scaling (RSS) を有効にする必要があります。 RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。 詳細については、「」の「Windows Server 2008 の受信側<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>スケーリングの拡張機能」を参照してください。 RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。



</div>

</div>

<div>

## <a name="director"></a>ディレクター

<div>


> [!NOTE]  
> 拡張されたプールは、このサーバーの役割ではサポートされていません。



</div>

ディレクターサーバーの役割を展開する場合は、サイトに同時にアクセスするすべての12000リモートユーザーに対して1つのディレクターを展開することをお勧めします。 高可用性を実現するために 2 つ以上のディレクターを用意することをお勧めします。 これらの推奨事項は、エッジサーバーのハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提としています。

ディレクターのユーザー数を考慮する際は、このサイトのフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。

</div>

<div>

## <a name="mediation-server"></a>仲介サーバー

<div>


> [!NOTE]  
> 拡張されたプールは、このサーバーの役割ではサポートされていません。



</div>

仲介サーバーをフロントエンドサーバーと併置する場合、仲介サーバーはプール内のすべてのフロントエンドサーバー上で実行され、プール内のユーザーに十分な容量を提供する必要があります。

スタンドアロンの仲介サーバープールを展開する場合、展開する仲介サーバーの数は、仲介サーバーに使用されるハードウェア、使用する VoIP ユーザーの数、各仲介サーバープールのゲートウェイピアの数など、さまざまな要因によって異なります。制御、それらのゲートウェイを通過する時間内のトラフィック、および仲介サーバーをバイパスするメディアを使用した通話の割合。

次の表は、仲介サーバーのハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の要件を満たしており、ハイパースレッディングが有効になっている場合に、仲介サーバーが処理できる同時呼び出し数に関するガイドラインを提供します。 仲介サーバーのスケーラビリティの詳細については、「lync server [2013 の音声使用率とトラフィックの見積もり](lync-server-2013-estimating-voice-usage-and-traffic.md)」および「 [lync Server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」を参照してください。

次の表はすべて、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で要約された使用法を前提としています。

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>スタンドアロン仲介サーバーの容量: 70% 内部ユーザー、30% の外部ユーザー (仲介サーバーによって実行されるメディアトランスコーディング)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>サーバー ハードウェア</th>
<th>最大通話数</th>
<th>T1 回線の最大数</th>
<th>E1 回線の最大数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>デュアルプロセッサ、16コア、2.26 GHz ハイパースレッディング CPU (<strong>ハイパースレッディング無効</strong>)、32 GB メモリ、および1つのデュアルポートネットワークアダプターカード。</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>デュアルプロセッサ、16コア、2.26 GHz ハイパースレッディング CPU (32 GB メモリと1つのデュアルポートネットワークアダプターカードを使用)。</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> パフォーマンス テストにはメモリが 32 GB のサーバーを使用しましたが、スタンドアロンの仲介サーバーにはメモリが 16 GB のサーバーがサポートされており、その条件のサーバーでもこの表に示されるパフォーマンスを十分実現できます。



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>仲介サーバーの処理能力 (フロントエンドサーバーと併置された仲介サーバー) 70% 内部ユーザー、30% の外部ユーザー、非バイパス通話の容量 (仲介サーバーによって実行されるメディア処理)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>サーバー ハードウェア</th>
<th>最大通話数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>デュアルプロセッサ、16進コア、2.26 GHz ハイパースレッディング CPU (32 GB メモリと 2 GB ネットワークアダプターカード)。</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> この数は、フロントエンドサーバーが、音声呼び出しに必要なトランスコーディングだけでなく、それに所属する6600ユーザーの他の機能や機能を処理する必要があるため、スタンドアロンの仲介サーバーの数よりもはるかに小さくなります。



</div>

<div>


> [!NOTE]  
> 仲介サーバーのパフォーマンスを向上させるには、仲介サーバーのネットワークアダプターで受信側の拡大/縮小 (RSS) を有効にする必要があります。 RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。 詳細については、「」の「Windows Server 2008 の受信側<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>スケーリングの拡張機能」を参照してください。 RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。



</div>

</div>

<div>

## <a name="back-end-server"></a>バック エンド サーバー

Lync Server 2013 では、プレゼンスデータベースはバックエンドサーバーではなくフロントエンドサーバーに配置されます。 これにより、Lync Server 2013 のバックエンドサーバーごとに、フロントエンドサーバーのハードウェア要件と同等の要件が大幅に簡略化されました。 これを Lync Server 2010 と比較します。これは、バックエンドサーバーが25台のディスクを使用した、より高いグレードのサーバーでなければならないということです。 ただし、バックエンドサーバーのワークロードについては、このセクションで前述したハードウェアの推奨事項や、 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の要件を満たすことができない場合があります。

バックエンドサーバーの高可用性を実現するには、サーバーミラーリングを展開することをお勧めします。 詳細については、「 [Lync server 2013 のバックエンドサーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。

</div>

<div>

## <a name="monitoring-and-archiving"></a>監視およびアーカイブ

Lync Server 2013 では、監視またはアーカイブを展開する場合、これらのサービスのフロントエンド機能は、個別のサーバーの役割ではなくフロントエンドサーバーで実行されます。 監視とアーカイブは、バックエンドストアから切り離された独自のデータベースストアを使用します。 または、Exchange 2013 を展開している場合は、専用の SQL ストアではなく、インスタントメッセージのアーカイブデータを Exchange に格納できます。

次の表は、データを監視およびアーカイブするために、ユーザーごとに1日あたりに必要なデータベース記憶域のおおよその量を示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>CDR (監視)</strong></p></td>
<td><p><strong>QoE (監視)</strong></p></td>
<td><p><strong>アーカイブ</strong></p></td>
</tr>
<tr class="even">
<td><p>ユーザーごとに1日あたり必要なディスク領域</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft では、データベースサーバーのパフォーマンステスト中に監視およびアーカイブするために、次の表に示すハードウェアを使用しています。 このテストでは、2つのフロントエンドプールのデータが収集され、それぞれに8万のユーザーが含まれていました。

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>監視およびアーカイブのパフォーマンステストで使用されるハードウェア

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ハードウェア コンポーネント</th>
<th>推奨</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上</p></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>48ギガバイト (GB)</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><p>25 1万 RPM のハードディスクドライブ、各ディスク上の 300 GB、次の構成</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Drive</strong></p></td>
<td><p><strong>RAID 構成</strong></p></td>
<td><p><strong>ディスク数</strong></p></td>
</tr>
<tr class="even">
<td><p>CDR、QoE、およびアーカイブデータベースのデータファイル、1台のドライブ</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>CDR データベースのログ ファイル</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
<tr class="even">
<td><p>QoE データベースのログ ファイル</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
<tr class="odd">
<td><p>アーカイブデータベースのログファイル</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の音声の使用状況とトラフィックの予測](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Lync Server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

