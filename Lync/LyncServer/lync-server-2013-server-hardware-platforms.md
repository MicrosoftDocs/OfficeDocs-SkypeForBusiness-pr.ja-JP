---
title: 'Lync Server 2013: サーバー ハードウェア プラットフォーム'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2682d0d8636c024dee4151842a143e65b11d48c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Lync Server 2013 のサーバー ハードウェア プラットフォーム

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-07-28_

Lync Server 2013 サーバーの役割と Lync Server 管理ツールを実行しているコンピューターには、64ビットのハードウェアが必要です。

Lync Server 2013 の展開に使用される特定のハードウェアは、サイズと使用状況の要件によって異なります。 ここでは、推奨ハードウェアについて説明します。 これらは推奨値であり、要件ではありませんが、推奨値を満たさないハードウェアを使用すると、重大なパフォーマンスの問題やその他の問題が発生する可能性があります。

<div>

## <a name="recommended-hardware-platform"></a>推奨されるハードウェア プラットフォーム

最高のパフォーマンスを得るには、次の表の要件を満たすハードウェアを備えたサーバーで Lync Server を実行することをお勧めします。 性能の低いハードウェアを使用している場合は、機能の問題が発生するか、パフォーマンスが低下することがあります。 これらのハードウェア要件は、以前のバージョンの Lync Server よりも高いことに注意してください。主に、Lync Server 2013 では、すべてのフロントエンドサーバーが SQL Server を実行するためです。

<div>


> [!NOTE]  
> NIC チーミングはサポートされているため、Lync Server には透過的である必要があります。 詳細について<A href="http://go.microsoft.com/fwlink/p/?linkid=389910">は、「通信サーバーまたは Lync server とネットワークアダプターチーミング</A>」を参照してください。



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>フロント エンド サーバー、バック エンド サーバー、Standard Edition サーバー、常設チャット サーバー、常設チャット ストアと常設チャット コンプライアンス ストア (常設チャット サーバーのバック エンド サーバーの役割) の推奨ハードウェア

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
<td><p>64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上。</p>
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
<li><p>1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</p>
<div>

> [!NOTE]  
> フロントエンドサーバー、バックエンドサーバー、標準エディションサーバー、常設チャットサーバーでは、デュアルホーム構成またはマルチホーム構成はサポートされません。<BR>ILO/DRAC/その他: オペレーティングシステムに公開されず、サーバーハードウェアを監視および管理するために使用される接続は、マルチホームサーバーではなく、サポートされます。


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>エッジ サーバー、スタンドアロン仲介サーバー、およびディレクターの推奨ハードウェア

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
<td><ul>
<li><p>64ビットデュアルプロセッサ、クアッドコア、2.0 ghz (GHz) 以上。</p>
<p>-/</p></li>
<li><p>64ビット4方向プロセッサ、デュアルコア、2.0 GHz 以上。</p></li>
</ul>
<p>Lync Server server の役割では、Intel Itanium プロセッサはサポートされていません。</p></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>16ギガバイト (GB)。</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>1万 RPM 以上のハードディスクドライブ (少なくとも 72 GB の空きディスク領域があります。</p>
<p>ディスクは 2 x RAID 1 構成である必要があります。</p>
<p>-/</p></li>
<li><p>10,000 RPM の機械的ディスク ドライブ 4 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要) 2ネットワークインターフェイスはエッジサーバーに必要であり、スタンドアロンの仲介サーバーでサポートされています。</p></li>
</ul>
<div>

> [!NOTE]  
> 2つまたは複数のホーム構成はディレクターに対してサポートされていません。<BR>ILO/DRAC/その他: オペレーティングシステムに公開されず、サーバーハードウェアを監視および管理するために使用される接続は、マルチホームサーバーではなく、サポートされます。


</div>
<p>エッジサーバーには、2つのネットワークインターフェイス、1 Gbps 以上 (または2つのペアリングされたネットワークアダプター、1つの MAC アドレスと1つの IP アドレスを持つ各ペア) が必要であり、合計で2組の場合があります。</p>
<p>特定の PSTN IP アドレスの構成を可能にするための追加のネットワークインターフェイスカード (Nic) のインストールは、スタンドアロンの仲介サーバーでサポートされています。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

