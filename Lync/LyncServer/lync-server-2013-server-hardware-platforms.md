---
title: Lync Server 2013 サーバーハードウェアプラットフォーム
description: Lync Server 2013 サーバーハードウェアプラットフォーム
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d55deec50994d70cf305b794662a630c16c3af14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551383"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a>Lync Server 2013 のサーバーハードウェアプラットフォーム

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-07-28_

Lync Server 2013 のサーバーの役割と Lync Server 管理ツールを実行しているコンピューターには、64ビットのハードウェアが必要です。

Lync Server 2013 の展開に使用される特定のハードウェアは、サイズと使用要件に応じて異なる場合があります。 ここでは、推奨ハードウェアについて説明します。 これらは推奨値であり、要件ではありませんが、推奨値を満たさないハードウェアを使用すると、重大なパフォーマンスの問題やその他の問題が発生する可能性があります。

<div>

## <a name="recommended-hardware-platform"></a>推奨されるハードウェア プラットフォーム

最適なパフォーマンスを得るために、次の表の要件を満たすハードウェアを備えたサーバーで Lync Server を実行することをお勧めします。 より強力なハードウェアを使用すると、機能に問題が発生したり、パフォーマンスが低下したりする可能性があります。 これらのハードウェア要件は、以前のバージョンの Lync Server よりも高いものであることに注意してください。主に Lync server 2013 では、すべてのフロントエンドサーバーが SQL Server を実行するからです。

<div>


> [!NOTE]  
> NIC チーミングはサポートされており、Lync Server に対して透過的である必要があります。 詳細については、「 <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications server または Lync Server とネットワークアダプターチーミング</A>」を参照してください。



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>フロントエンドサーバー、バックエンドサーバー、Standard Edition サーバー、常設チャットサーバー、および常設チャットストアと常設チャットコンプライアンスストア (常設チャットサーバーのバックエンドサーバーの役割) に推奨されるハードウェア

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
<td><p>64ビットデュアルプロセッサ、16ビットコア、2.26 ghz 以上。</p>
<p>Lync Server のサーバーの役割では、Intel Itanium プロセッサはサポートされていません。</p></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>32 gb</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 8 台以上</p>
<p>ディスクのうち 2 台で RAID 1 を使用し、6 台で RAID 10 を使用する必要があります。</p>
<p>- や</p></li>
<li><p>10,000 RPM の機械的ディスク ドライブ 8 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>1 Gbps 以上のデュアルポートネットワークアダプター1つ (2 つを推奨、1つの MAC アドレスと単一の IP アドレスのチーミングが必要)。</p>
<div>

> [!NOTE]  
> デュアルまたはマルチホーム構成は、フロントエンドサーバー、バックエンドサーバー、Standard Edition サーバー、および常設チャットサーバーではサポートされていません。<BR>オペレーティングシステムに公開されておらず、サーバーハードウェアの監視および管理に使用されていない ILO/DRAC/接続は、複数のホームサーバーを構成するものではないため、サポートされています。


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
<li><p>64ビットデュアルプロセッサ、クアッドコア、2.0 ghz またはそれ以上。</p>
<p>- や</p></li>
<li><p>64ビット4ウェイプロセッサ、デュアルコア、2.0 GHz またはそれ以上。</p></li>
</ul>
<p>Lync Server のサーバーの役割では、Intel Itanium プロセッサはサポートされていません。</p></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>16ギガバイト (GB)。</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>1万 RPM のハードディスクドライブのうち、少なくとも 72 GB の空きディスク領域があるものを4台以上。</p>
<p>ディスクは、RAID 1 の2倍の構成にする必要があります。</p>
<p>- や</p></li>
<li><p>10,000 RPM の機械的ディスク ドライブ 4 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>1 Gbps 以上のデュアルポートネットワークアダプター1つ (2 つを推奨、1つの MAC アドレスと単一の IP アドレスのチーミングが必要)。 エッジサーバーでは2つのネットワークインターフェイスが必要であり、スタンドアロンの仲介サーバーでサポートされています。</p></li>
</ul>
<div>

> [!NOTE]  
> ディレクターでは、デュアルまたはマルチホーム構成はサポートされていません。<BR>オペレーティングシステムに公開されておらず、サーバーハードウェアの監視および管理に使用されていない ILO/DRAC/接続は、複数のホームサーバーを構成するものではないため、サポートされています。


</div>
<p>エッジサーバーでは、2つのネットワークインターフェイス (または、1 Gbps 以上のデュアルポートネットワークアダプター、つまり合計4つのネットワークアダプターが1つの MAC アドレスと1つの IP アドレスでチーミングされ、合計2つのペア) が必要です。</p>
<p>その他のネットワークインターフェイスカード (Nic) をインストールすると、特定の PSTN IP アドレスの構成がスタンドアロンの仲介サーバーでサポートされます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

