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

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="289b9-102">Lync Server 2013 のサーバー ハードウェア プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="289b9-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="289b9-103">_**最終更新日:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="289b9-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="289b9-104">Lync Server 2013 サーバーの役割と Lync Server 管理ツールを実行しているコンピューターには、64ビットのハードウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="289b9-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="289b9-105">Lync Server 2013 の展開に使用される特定のハードウェアは、サイズと使用状況の要件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="289b9-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="289b9-106">ここでは、推奨ハードウェアについて説明します。</span><span class="sxs-lookup"><span data-stu-id="289b9-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="289b9-107">これらは推奨値であり、要件ではありませんが、推奨値を満たさないハードウェアを使用すると、重大なパフォーマンスの問題やその他の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="289b9-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="289b9-108">推奨されるハードウェア プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="289b9-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="289b9-109">最高のパフォーマンスを得るには、次の表の要件を満たすハードウェアを備えたサーバーで Lync Server を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="289b9-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="289b9-110">性能の低いハードウェアを使用している場合は、機能の問題が発生するか、パフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="289b9-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="289b9-111">これらのハードウェア要件は、以前のバージョンの Lync Server よりも高いことに注意してください。主に、Lync Server 2013 では、すべてのフロントエンドサーバーが SQL Server を実行するためです。</span><span class="sxs-lookup"><span data-stu-id="289b9-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="289b9-112">NIC チーミングはサポートされているため、Lync Server には透過的である必要があります。</span><span class="sxs-lookup"><span data-stu-id="289b9-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="289b9-113">詳細について<A href="http://go.microsoft.com/fwlink/p/?linkid=389910">は、「通信サーバーまたは Lync server とネットワークアダプターチーミング</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289b9-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="289b9-114">フロント エンド サーバー、バック エンド サーバー、Standard Edition サーバー、常設チャット サーバー、常設チャット ストアと常設チャット コンプライアンス ストア (常設チャット サーバーのバック エンド サーバーの役割) の推奨ハードウェア</span><span class="sxs-lookup"><span data-stu-id="289b9-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="289b9-115">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="289b9-115">Hardware component</span></span></th>
<th><span data-ttu-id="289b9-116">推奨</span><span class="sxs-lookup"><span data-stu-id="289b9-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="289b9-117">CPU</span><span class="sxs-lookup"><span data-stu-id="289b9-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="289b9-118">64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上。</span><span class="sxs-lookup"><span data-stu-id="289b9-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="289b9-119">Lync Server server の役割では、Intel Itanium プロセッサはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="289b9-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="289b9-120">メモリ</span><span class="sxs-lookup"><span data-stu-id="289b9-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="289b9-121">32 ギガバイト (GB)</span><span class="sxs-lookup"><span data-stu-id="289b9-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="289b9-122">ディスク</span><span class="sxs-lookup"><span data-stu-id="289b9-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="289b9-123">10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 8 台以上。</span><span class="sxs-lookup"><span data-stu-id="289b9-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="289b9-124">ディスクのうち 2 台で RAID 1 を使用し、6 台で RAID 10 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="289b9-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="289b9-125">-/</span><span class="sxs-lookup"><span data-stu-id="289b9-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="289b9-126">10,000 RPM の機械的ディスク ドライブ 8 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)</span><span class="sxs-lookup"><span data-stu-id="289b9-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="289b9-127">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="289b9-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="289b9-128">1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</span><span class="sxs-lookup"><span data-stu-id="289b9-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="289b9-129">フロントエンドサーバー、バックエンドサーバー、標準エディションサーバー、常設チャットサーバーでは、デュアルホーム構成またはマルチホーム構成はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="289b9-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="289b9-130">ILO/DRAC/その他: オペレーティングシステムに公開されず、サーバーハードウェアを監視および管理するために使用される接続は、マルチホームサーバーではなく、サポートされます。</span><span class="sxs-lookup"><span data-stu-id="289b9-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="289b9-131">エッジ サーバー、スタンドアロン仲介サーバー、およびディレクターの推奨ハードウェア</span><span class="sxs-lookup"><span data-stu-id="289b9-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="289b9-132">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="289b9-132">Hardware component</span></span></th>
<th><span data-ttu-id="289b9-133">推奨</span><span class="sxs-lookup"><span data-stu-id="289b9-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="289b9-134">CPU</span><span class="sxs-lookup"><span data-stu-id="289b9-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="289b9-135">64ビットデュアルプロセッサ、クアッドコア、2.0 ghz (GHz) 以上。</span><span class="sxs-lookup"><span data-stu-id="289b9-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="289b9-136">-/</span><span class="sxs-lookup"><span data-stu-id="289b9-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="289b9-137">64ビット4方向プロセッサ、デュアルコア、2.0 GHz 以上。</span><span class="sxs-lookup"><span data-stu-id="289b9-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="289b9-138">Lync Server server の役割では、Intel Itanium プロセッサはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="289b9-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="289b9-139">メモリ</span><span class="sxs-lookup"><span data-stu-id="289b9-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="289b9-140">16ギガバイト (GB)。</span><span class="sxs-lookup"><span data-stu-id="289b9-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="289b9-141">ディスク</span><span class="sxs-lookup"><span data-stu-id="289b9-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="289b9-142">1万 RPM 以上のハードディスクドライブ (少なくとも 72 GB の空きディスク領域があります。</span><span class="sxs-lookup"><span data-stu-id="289b9-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="289b9-143">ディスクは 2 x RAID 1 構成である必要があります。</span><span class="sxs-lookup"><span data-stu-id="289b9-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="289b9-144">-/</span><span class="sxs-lookup"><span data-stu-id="289b9-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="289b9-145">10,000 RPM の機械的ディスク ドライブ 4 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。</span><span class="sxs-lookup"><span data-stu-id="289b9-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="289b9-146">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="289b9-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="289b9-147">1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</span><span class="sxs-lookup"><span data-stu-id="289b9-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="289b9-148">2ネットワークインターフェイスはエッジサーバーに必要であり、スタンドアロンの仲介サーバーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="289b9-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="289b9-149">2つまたは複数のホーム構成はディレクターに対してサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="289b9-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="289b9-150">ILO/DRAC/その他: オペレーティングシステムに公開されず、サーバーハードウェアを監視および管理するために使用される接続は、マルチホームサーバーではなく、サポートされます。</span><span class="sxs-lookup"><span data-stu-id="289b9-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="289b9-151">エッジサーバーには、2つのネットワークインターフェイス、1 Gbps 以上 (または2つのペアリングされたネットワークアダプター、1つの MAC アドレスと1つの IP アドレスを持つ各ペア) が必要であり、合計で2組の場合があります。</span><span class="sxs-lookup"><span data-stu-id="289b9-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="289b9-152">特定の PSTN IP アドレスの構成を可能にするための追加のネットワークインターフェイスカード (Nic) のインストールは、スタンドアロンの仲介サーバーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="289b9-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

