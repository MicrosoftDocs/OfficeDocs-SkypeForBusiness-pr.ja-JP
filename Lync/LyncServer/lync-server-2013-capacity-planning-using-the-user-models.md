---
title: ユーザーモデルを使用した Lync Server 2013 キャパシティ計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>ユーザーモデルを使用した Lync Server 2013 のキャパシティ計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-01-14_

このセクションでは、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で説明されている使用法に従って、そのサイトのユーザー数に応じてサイトで必要なサーバー数について説明します。

<div>

## <a name="tested-hardware-platform"></a>テスト済みのハードウェア プラットフォーム

このセクションのパフォーマンスの結果と展開に関する推奨事項はすべて、次の表で説明されているハードウェアを実行しているサーバーでのパフォーマンステストに基づいています。 同様のハードウェアを使用することをお勧めします。 性能の低いハードウェアを使用している場合は、機能の問題が発生するか、パフォーマンスが低下することがあります。 これらのハードウェアの推奨事項は、以前のバージョンの Lync Server よりも高いことに注意してください。

### <a name="hardware-used-in-performance-testing"></a>パフォーマンス テストで使用するハードウェア

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
<p>Lync Server server の役割では、Intel Itanium プロセッサはサポートされていません。</p></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>32 ギガバイト (GB)</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 8 台以上。</p>
<p>ディスクのうち 2 台で RAID 1 を使用し、6 台で RAID 10 を使用する必要があります。</p>
<p>-/</p></li>
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

次の表は、これらの推奨事項をまとめたものです。


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
<td><p>12個のフロントエンドサーバーと1つのバックエンドサーバー、またはバックエンドサーバーのミラーされたペアのフロントエンドプール。</p></td>
<td><p>エンドポイントの合計 152,000 に対し、同時にログインする 80,000 の一意ユーザー、および非モバイル インスタンスを表す 50% の複数の MPOP (Multiple Point of Presence)、モビリティが有効な 40% のユーザー。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ会議</p></td>
<td><p>フロントエンドプールによって提供される A/V 会議サービスは、最大会議サイズが250ユーザーであり、その大人数の会議は一度に1つだけ実行されることを前提とした、プールの会議をサポートしています。</p>
<div>

> [!NOTE]  
> さらに、250と1000ユーザーの間の大規模な会議をサポートするには、2つのフロントエンドサーバーと、大きな会議をホストするための、別々のフロントエンドプールを展開します。 詳細については、「 <A href="lync-server-2013-supporting-large-meetings.md">Lync Server 2013 を使用した大規模な会議のサポート</A>」を参照してください。


</div></td>
</tr>
<tr class="odd">
<td><p>1つのエッジサーバー</p></td>
<td><p>12000同時リモートユーザー</p></td>
</tr>
<tr class="even">
<td><p>1人のディレクター</p></td>
<td><p>12000同時リモートユーザー</p></td>
</tr>
<tr class="odd">
<td><p>監視およびアーカイブ</p></td>
<td><p>Lync Server 2013 では、個別のサーバーの役割ではなく、フロントエンドサーバーごとに、監視およびアーカイブのフロントエンドサービスが実行されるようになりました。</p>
<p>監視とアーカイブにはそれぞれ専用のデータベース ストアが必要です。 Exchange 2013 も実行している場合は、専用の SQL データベースではなく、Exchange でアーカイブデータを保持することができます。</p></td>
</tr>
<tr class="even">
<td><p>1つの仲介サーバー</p></td>
<td><p>フロントエンドサーバーと併置されている仲介サーバーは、プール内のすべてのフロントエンドサーバー上で実行され、プール内のユーザーに十分な容量を提供する必要があります。 スタンドアロンの仲介サーバーの場合は、このトピックで後述する「仲介サーバー」のセクションを参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>Standard Edition server 1 台</p></td>
<td><p>Standard Edition サーバーを使用してユーザーをホストする場合は、常に2つのサーバーを使用し、<a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">高可用性と障害回復の計画</a>に関する推奨事項を Lync Server 2013 で使用することを強くお勧めします。 ペアの中の各サーバーは、最大 2,500 ユーザーをホストすることができ、フェールオーバー シナリオでは、1 台のサーバーに障害が発生した場合は残りの 1 台で 5,000 ユーザーをサポートできます。</p>
<p>展開に大量のオーディオまたは動画トラフィックがある場合、サーバーあたりのユーザー数が 2,500 名を超えるとサーバー パフォーマンスが低下することがあります。 この場合は、Standard Edition サーバーの追加または Lync Server Enterprise Edition への移行を検討してください。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>フロントエンド サーバー

<div>


> [!NOTE]  
> ストレッチプールは、このサーバーの役割ではサポートされていません。



</div>

フロントエンドプールでは、プール内のすべてのサーバーでハイパースレッディングが有効であり、サーバーハードウェアが[Lync のサーバーハードウェアプラットフォームで推奨事項を満たしていることを前提として、すべての6660ユーザーに対して1つのフロントエンドサーバーを用意する必要があります。サーバー 2013](lync-server-2013-server-hardware-platforms.md)。 1つのフロントエンドプール内のユーザーの最大数は8万で、そのプール内のすべてのサーバーでハイパースレッディングが有効になっていることを前提としています。 1つのサイトで8万を超えるユーザーがいる場合は、複数のフロントエンドプールを展開できます。

フロントエンドプールのユーザー数を考慮している場合は、このフロントエンドプールに関連付けられている支社で、Survivable Branch アプライアンスと Survivable ブランチサーバーを含むユーザーを含めます。

アクティブなサーバーが使用できなくなると、その接続はプール内にある他のサーバーに自動的に転送されます。 たとえば、3万ユーザーと5台のフロントエンドサーバーがある場合、1つのサーバーを使用できない場合は、6000ユーザーの接続を他の4台のサーバーに移行する必要があります。 残りの4台のサーバーにはそれぞれ7500ユーザーが含まれています。これは推奨されるよりも大きい数値です。

代わりに、3万ユーザー用に6つのフロントエンドサーバーを使い始めた後で、そのサーバーが利用できなくなった場合は、合計5000ユーザーが残りの5台のサーバーに移動されます。 これら5つのサーバーはそれぞれ、6000ユーザーをホストします。これらは、推奨される範囲内にあります。

フロントエンドプールのユーザーの最大数は8万です。 プール内のフロントエンドサーバーの最大数は12です。

8万ユーザーを含むフロントエンドプールの場合、パフォーマンスを向上させるには、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)に従った通常の展開で、12個のフロントエンドサーバーで十分です。 障害回復フェールオーバーをサポートするように設計された展開では、2つのペアのフロントエンドプールのそれぞれに最大4万ユーザーをホストできます。各プールには、両方のプールのユーザーに対応するための十分なフロントエンドサーバーがあることを前提としています。1つのプールは失敗する必要があります。他へ。

特定のフロントエンドプールによる良好なパフォーマンスでサポートされるユーザーの数は、次のような理由により、これらの数値とは異なる場合があります。

  - フロントエンドサーバーのハードウェアは、 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていません。

  - 組織の使用状況は、多くの会議トラフィックなど、ユーザーモデルとは大きく異なります。

<div>


> [!IMPORTANT]  
> Lync Server 2013 では、バックエンドサーバーでホストされていた Lync Server 2010 ではなく、フロントエンドサーバーでプレゼンスデータベースがホストされるようになりました。 つまり、フロントエンドサーバーのディスクパフォーマンスと容量は、このセクションで説明した推奨事項、および<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 のサーバーハードウェアプラットフォーム</A>では、ユーザーがホストしているユーザーの数に関係なく、このセクションに記載されている推奨事項から侵害されないことを意味します。フロントエンドサーバー。



</div>

次の表は、 [Lync Server 2013 のユーザー](lync-server-2013-user-models.md)モデルで定義されているユーザーモデルに基づいて、IM とプレゼンスの平均帯域幅を示しています。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ユーザー単位の平均帯域幅</th>
<th>6660ユーザーとのフロントエンドサーバーあたりの帯域幅要件</th>
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
> フロントエンドサーバー上の併置された A/V 会議および仲介サーバー機能のメディアパフォーマンスを向上させるには、フロントエンドサーバー上のネットワークアダプターで受信側スケーリング (RSS) を有効にする必要があります。 RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。 詳細については、「Windows Server 2008 の受信側スケーリングの拡張<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>機能」を参照してください。 RSS を有効にする方法の詳細については、ネットワーク アダプターのドキュメントを参照してください。



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>最大会議数

プール内のユーザーの 5% が1つの会議に参加している可能性がある場合、8万ユーザーのプールは、一度に1人の会議で4000ユーザーを持つことがあります。 これらの会議は、メディアが混在していることを前提としています (一部の IM のみ、音声での IM、一部の音声/ビデオなど)、参加者の数が含まれます。 許可されている電話会議の実際の数には制限はありません。実際の使用状況によって実際のパフォーマンスが決まります。 たとえば、組織にユーザーモデルで想定されているよりも多くの混在モードの会議がある場合は、このドキュメントの推奨事項よりも多くのフロントエンドサーバーまたは A/V の会議サーバーを展開する必要がある場合があります。 ユーザーモデルの前提条件の詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。

定期的な Lync Server 2013 フロントエンドプールによってホストされる最大サポートされている会議サイズであり、ユーザーは、250の参加者でもあります。 250 ユーザーが参加する会議が行われている場合、プールは同時に他の会議もサポートします (同時に行われる会議にプール ユーザーのうちの 5% が参加している場合など)。 たとえば、12台のフロントエンドサーバーと8万ユーザーのプールでは、250ユーザーの会議が行われている間、Lync Server は小規模の会議に参加している3750他のユーザーをサポートします。

フロントエンドプールまたは Standard Edition サーバーに所属しているユーザー数にかかわらず、Lync Server は、250ユーザー会議をホストしている同一のプールまたはサーバー上の小さい会議に参加している、少なくとも125の他のユーザーをサポートします。

250と1000のユーザーの間で会議を有効にするには、個別のフロントエンドプールをセットアップして、会議を主催することができます。 このフロントエンドプールでは、ユーザーはホストされません。 詳細については、「 [Lync Server 2013 を使用した大規模な会議のサポート](lync-server-2013-supporting-large-meetings.md)」を参照してください。

組織で、ユーザーモデルで想定されているよりも多くの混在モードの会議がある場合は、このドキュメントの推奨事項よりも多くのフロントエンドサーバーを展開する必要がある場合があります (上限は 12 FEs)。 ユーザーモデルの前提条件の詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。

</div>

<div>

## <a name="edge-server"></a>エッジ サーバー

<div>


> [!NOTE]  
> ストレッチプールは、このサーバーの役割ではサポートされていません。



</div>

サイトに同時にアクセスするすべての12000リモートユーザーに対して、1つのエッジサーバーを展開する必要があります。 少なくとも、高可用性を実現するには、2台のエッジサーバーをお勧めします。 これらの推奨事項は、エッジサーバーのハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提としています。

エッジサーバーのユーザー数を考慮する場合は、このサイトのフロントエンドプールに関連付けられている支社で、Survivable Branch アプライアンスと Survivable ブランチサーバーを含むユーザーを含めます。

<div>


> [!NOTE]  
> エッジサーバー上の A/V 会議エッジサービスのパフォーマンスを向上させるには、エッジサーバーのネットワークアダプターで受信側スケーリング (RSS) を有効にする必要があります。 RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。 詳細については、「Windows Server 2008 の受信側スケーリングの拡張<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>機能」を参照してください。 RSS を有効にする方法の詳細については、ネットワーク アダプターのドキュメントを参照してください。



</div>

</div>

<div>

## <a name="director"></a>ディレクター

<div>


> [!NOTE]  
> ストレッチプールは、このサーバーの役割ではサポートされていません。



</div>

ディレクターサーバーの役割を展開する場合は、サイトに同時にアクセスするすべての12000リモートユーザーに対してディレクターを1つ展開することをお勧めします。 少なくとも、高可用性を実現するために2つのディレクターをお勧めします。 これらの推奨事項は、エッジサーバーのハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提としています。

ディレクターのユーザー数を考慮する場合は、このサイトのフロントエンドプールに関連付けられている支社で、Survivable Branch アプライアンスと Survivable ブランチサーバーを使用しているユーザーを含めます。

</div>

<div>

## <a name="mediation-server"></a>仲介サーバー

<div>


> [!NOTE]  
> ストレッチプールは、このサーバーの役割ではサポートされていません。



</div>

フロントエンドサーバーで仲介サーバーを使用している場合、仲介サーバーはプール内の各フロントエンドサーバー上で実行され、プール内のユーザーに十分な容量を提供する必要があります。

スタンドアロンの仲介サーバープールを展開する場合、展開する仲介サーバーの数は、仲介サーバーに使用されるハードウェア、使用している VoIP ユーザーの数、各仲介サーバープールのゲートウェイピアの数など、さまざまな要因によって異なります。コントロール、それらのゲートウェイ経由でのビジー時間のトラフィック、および仲介サーバーをバイパスするメディアでの通話の割合。

次の表では、仲介サーバーのハードウェアが[Lync server 2013 用のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の要件を満たしていること、およびそのハイパースレッディングに対応していることを前提として、仲介サーバーが処理できる同時呼び出しの数に関するガイドラインを提供します。が有効になります。 仲介サーバーのスケーラビリティの詳細については、「 [Lync server 2013 の音声使用量とトラフィックの見積もり](lync-server-2013-estimating-voice-usage-and-traffic.md)」および「 [lync server 2013 での仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」を参照してください。

次の表では、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)での使用状況を想定しています。

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>スタンドアロンの仲介サーバー容量:70% 内部ユーザー、非バイパス通話容量を持つ外部ユーザー 30% (仲介サーバーによって実行されるメディアのトランスコード)

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
<td><p>デュアル プロセッサ、6 コア、2.26 GHz ハイパースレッディング CPU (<strong>ハイパースレッディング無効</strong>)、32 GB メモリ、デュアルポート ネットワーク アダプター カード 1 つ</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>デュアル プロセッサ、6 コア、2.26 GHz ハイパースレッディング CPU、32 GB メモリ、デュアルポート ネットワーク アダプター カード 1 つ</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 32 GB のメモリを搭載したサーバーはパフォーマンステストに使用されていますが、16 GB のメモリを持つサーバーは、スタンドアロンの仲介サーバーでサポートされており、この表に示すパフォーマンスを提供するのに十分な方法です。



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>仲介サーバーの容量 (フロントエンドサーバーと連携している仲介サーバー) 70% 内部ユーザー、30% の外部ユーザー、非バイパス通話キャパシティ (仲介サーバーによって実行されるメディア処理)

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
<td><p>デュアル プロセッサ、6 コア、2.26 GHz ハイパースレッディング CPU、32 GB メモリ、1 GB ネットワーク アダプター カード × 2</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> この数値は、スタンドアロンの仲介サーバーの数値よりもかなり小さいです。フロントエンドサーバーでは、ホームに必要な6600ユーザーのその他の機能や機能を処理する必要があります。また、音声通話に必要なトランスコードを使用する必要があります。



</div>

<div>


> [!NOTE]  
> 仲介サーバーのパフォーマンスを向上させるには、仲介サーバーのネットワークアダプターで受信側スケーリング (RSS) を有効にする必要があります。 RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。 詳細については、「Windows Server 2008 の受信側スケーリングの拡張<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>機能」を参照してください。 RSS を有効にする方法の詳細については、ネットワーク アダプターのドキュメントを参照してください。



</div>

</div>

<div>

## <a name="back-end-server"></a>バック エンド サーバー

Lync Server 2013 では、プレゼンスデータベースはバックエンドサーバーではなく、フロントエンドサーバー上に配置されています。 このため、Lync Server 2013 のバックエンドサーバーごとに、フロントエンドサーバーのハードウェア要件と同等の要件が大幅に簡素化されています。 この点2010について、バックエンドサーバーは、25ディスクでより高いグレードのサーバーである必要がありました。 ただし、バックエンドサーバーの作業負荷は依然としているため、このセクションで説明したハードウェア推奨事項、および[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)には合格しない必要があります。

バックエンドサーバーの高可用性を実現するには、サーバーのミラーリングを展開することをお勧めします。 詳細については、「 [Lync Server 2013 のバックエンドサーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。

</div>

<div>

## <a name="monitoring-and-archiving"></a>監視およびアーカイブ

Lync Server 2013 では、監視またはアーカイブを展開した場合、これらのサービスのフロントエンド機能は、個別のサーバーの役割ではなく、フロントエンドサーバー上で実行されます。 監視とアーカイブの各機能は、バックエンドストアとは別に、独自のデータベースストアを使用します。 また、Exchange 2013 が展開されている場合は、専用の SQL ストアではなく、インスタントメッセージのアーカイブデータを Exchange に保存することもできます。

次の表は、監視およびアーカイブのデータに必要な、ユーザーごとの 1 日あたりのデータベース記憶域 (概算) を示します。


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
<td><p>ユーザーごとに 1 日に必要なディスク容量</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft では、パフォーマンス テストの際に、次の表に示すハードウェアを監視およびアーカイブ用のデータベース サーバーとして使用しました。 テストでは、2つのフロントエンドプールのデータが収集されます。各データには8万ユーザーが含まれています。

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>監視およびアーカイブのパフォーマンス テストで使用したハードウェア

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
<td><p>48 ギガバイト (GB)</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><p>次の構成を持つ 10,000 RPM のハード ディスク ドライブ × 25 (各ディスクのサイズは 300 GB)</p>
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
<td><p><strong>ドライブ</strong></p></td>
<td><p><strong>RAID 構成</strong></p></td>
<td><p><strong>ディスク数</strong></p></td>
</tr>
<tr class="even">
<td><p>CDR、QoE、およびアーカイブ データベースのデータ ファイル (単一のドライブ上)</p></td>
<td><p>1+0</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>CDR データベースのログ ファイル</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>QoE データベースのログ ファイル</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>アーカイブ データベースのログ ファイル</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
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

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の音声の利用状況とトラフィックの予測](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Lync Server 2013 での仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

