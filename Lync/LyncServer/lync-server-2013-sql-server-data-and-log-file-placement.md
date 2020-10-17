---
title: 'Lync Server 2013: SQL Server データとログファイルの配置'
description: 'Lync Server 2013: SQL Server データとログファイルの配置。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a127254fec41a734136df9b63fc6cc8929745df7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558283"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="84361-103">Lync Server 2013 の SQL Server データとログファイルの配置</span><span class="sxs-lookup"><span data-stu-id="84361-103">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84361-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="84361-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="84361-105">Lync Server 2013 フロントエンドプールのための Microsoft SQL Server 2012 または Microsoft SQL Server 2008 R2 SP1 の計画と展開では、パフォーマンスを向上するために、データファイルとログファイルを物理ハードディスクに配置することが重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="84361-105">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="84361-106">推奨されるディスク構成は、6スピンドルを使用して 1 + 0 RAID セットを実装することです。</span><span class="sxs-lookup"><span data-stu-id="84361-106">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="84361-107">[Lync Server 展開ウィザード] を使用して、フロントエンドプールによって使用されるすべてのデータベースとログファイル、および関連するサーバーの役割とサービス (つまり、アーカイブおよび監視サーバー、Lync server Response Group service、Lync Server コールパークサービス) を RAID ドライブセットに配置すると、良好なパフォーマンスをテストした構成になります。</span><span class="sxs-lookup"><span data-stu-id="84361-107">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="84361-108">データベース ファイルとその役割の詳細を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="84361-108">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84361-109">ポリシーと SQL Server の構成でより特殊なインストールが必要な場合は、Lync Server 管理シェルを使用して、定義済みの任意の場所にデータベースとログファイルをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="84361-109">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="84361-110">詳細については、「 <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">lync Server 管理シェルを使用したデータベースのインストール 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84361-110">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="84361-111">中央管理ストアのデータ ファイルとログ ファイル</span><span class="sxs-lookup"><span data-stu-id="84361-111">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84361-112">中央管理ストアデータベースファイル</span><span class="sxs-lookup"><span data-stu-id="84361-112">Central Management store database files</span></span></th>
<th><span data-ttu-id="84361-113">データ ファイルまたはログ目的</span><span class="sxs-lookup"><span data-stu-id="84361-113">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84361-114">Xds</span><span class="sxs-lookup"><span data-stu-id="84361-114">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-115">中央管理ストアのトランザクションログファイル</span><span class="sxs-lookup"><span data-stu-id="84361-115">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-116">Xds</span><span class="sxs-lookup"><span data-stu-id="84361-116">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-117">トポロジビルダーによって定義および公開された、現在の Lync Server 2013 トポロジの構成を維持します。</span><span class="sxs-lookup"><span data-stu-id="84361-117">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-118">Lis</span><span class="sxs-lookup"><span data-stu-id="84361-118">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-119">場所情報サービスデータファイル</span><span class="sxs-lookup"><span data-stu-id="84361-119">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-120">Lis. .ldf</span><span class="sxs-lookup"><span data-stu-id="84361-120">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-121">場所情報サービスデータファイルのトランザクションログ</span><span class="sxs-lookup"><span data-stu-id="84361-121">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="84361-122">ユーザー、会議、およびアドレス帳のデータおよびログ ファイル</span><span class="sxs-lookup"><span data-stu-id="84361-122">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84361-123">主要な Lync Server 2013 データベースファイル</span><span class="sxs-lookup"><span data-stu-id="84361-123">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="84361-124">データ ファイルまたはログ目的</span><span class="sxs-lookup"><span data-stu-id="84361-124">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84361-125">Rtc</span><span class="sxs-lookup"><span data-stu-id="84361-125">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-126">永続的なユーザーデータ (たとえば、アクセス制御リスト (Acl)、連絡先、スケジュールされた会議)</span><span class="sxs-lookup"><span data-stu-id="84361-126">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-127">Rtc. .ldf</span><span class="sxs-lookup"><span data-stu-id="84361-127">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-128">Rtc データのトランザクションログ</span><span class="sxs-lookup"><span data-stu-id="84361-128">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-129">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="84361-129">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-130">一時ユーザーデータを保持する (プレゼンスランタイムデータ)</span><span class="sxs-lookup"><span data-stu-id="84361-130">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-131">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="84361-131">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-132">Rtcdyn データのトランザクションログ</span><span class="sxs-lookup"><span data-stu-id="84361-132">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-133">Rtcab</span><span class="sxs-lookup"><span data-stu-id="84361-133">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-134">リアルタイム通信 (RTC) アドレス帳データベースは、アドレス帳サービス情報が保存される SQL Server リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="84361-134">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-135">Rtcab. .ldf</span><span class="sxs-lookup"><span data-stu-id="84361-135">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-136">アドレス帳サービスのトランザクション ログ</span><span class="sxs-lookup"><span data-stu-id="84361-136">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-137">Rtclocal .mdb</span><span class="sxs-lookup"><span data-stu-id="84361-137">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="84361-138">会議ディレクトリをホストする</span><span class="sxs-lookup"><span data-stu-id="84361-138">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-139">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="84361-139">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-140">ユーザーデータのバックアップを維持する</span><span class="sxs-lookup"><span data-stu-id="84361-140">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-141">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="84361-141">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-142">Rtcxds データのトランザクションログ</span><span class="sxs-lookup"><span data-stu-id="84361-142">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="84361-143">通話保留および応答グループのデータとログ ファイル</span><span class="sxs-lookup"><span data-stu-id="84361-143">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84361-144">アプリケーション データベース</span><span class="sxs-lookup"><span data-stu-id="84361-144">Application database</span></span></th>
<th><span data-ttu-id="84361-145">データ ファイルまたはログ目的</span><span class="sxs-lookup"><span data-stu-id="84361-145">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84361-146">Cpsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="84361-146">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-147">コールパークアプリケーションの動的情報データベース</span><span class="sxs-lookup"><span data-stu-id="84361-147">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-148">Cpsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="84361-148">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-149">コールパークアプリケーションデータファイルのトランザクションログ</span><span class="sxs-lookup"><span data-stu-id="84361-149">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-150">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="84361-150">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-151">サービスの構成の Lync Server 応答グループ サービス データ ファイル</span><span class="sxs-lookup"><span data-stu-id="84361-151">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-152">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="84361-152">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-153">応答グループアプリケーションの構成のトランザクションログファイル</span><span class="sxs-lookup"><span data-stu-id="84361-153">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-154">Rgsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="84361-154">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-155">ランタイム操作の応答グループ サービス データ ファイル</span><span class="sxs-lookup"><span data-stu-id="84361-155">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-156">Rgsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="84361-156">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-157">応答グループ サービス ランタイム データ ファイルのトランザクション ログ</span><span class="sxs-lookup"><span data-stu-id="84361-157">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="84361-158">アーカイブ サーバーおよび監視サーバーのデータとログ ファイル</span><span class="sxs-lookup"><span data-stu-id="84361-158">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84361-159">アーカイブ データベースと監視データベースのファイル</span><span class="sxs-lookup"><span data-stu-id="84361-159">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="84361-160">データ ファイルまたはログ目的</span><span class="sxs-lookup"><span data-stu-id="84361-160">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84361-161">LcsCdr .mdf</span><span class="sxs-lookup"><span data-stu-id="84361-161">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-162">監視サーバーの通話詳細記録 (CDR) プロセスのデータストア</span><span class="sxs-lookup"><span data-stu-id="84361-162">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-163">LcsCdr .ldf</span><span class="sxs-lookup"><span data-stu-id="84361-163">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-164">通話詳細記録 (CDR) データのトランザクション ログ</span><span class="sxs-lookup"><span data-stu-id="84361-164">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-165">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="84361-165">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-166">監視サーバーから保存された qoe (Quality of Experience) データファイル</span><span class="sxs-lookup"><span data-stu-id="84361-166">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-167">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="84361-167">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-168">監視データのトランザクション ログ</span><span class="sxs-lookup"><span data-stu-id="84361-168">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84361-169">Lcslog .mdf</span><span class="sxs-lookup"><span data-stu-id="84361-169">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="84361-170">アーカイブサーバーでのインスタントメッセージングおよび電話会議データの保持期間のデータファイル</span><span class="sxs-lookup"><span data-stu-id="84361-170">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84361-171">Lcslog .ldf</span><span class="sxs-lookup"><span data-stu-id="84361-171">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="84361-172">アーカイブ データのトランザクション ログ</span><span class="sxs-lookup"><span data-stu-id="84361-172">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84361-p103">このトピックでは、ディスクおよび RAID セットについて説明します。SQL Server リソースの構成では、ディスクへの参照は単一のハードディスク デバイスへの参照を意味します。 2 つのパーティションがある 1 台のハード ディスク ドライブ (1 つはログ ファイルを保持し、もう 1 つのパーティションはデータ ファイルを保持) は、2 台のディスクそれぞれがログ ファイル専用またはデータ ファイル専用になっている状態とは異なります。</span><span class="sxs-lookup"><span data-stu-id="84361-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="84361-176">RAID セットの場合、さまざまなベンダーから出ている多様な RAID テクノロジが多数あります。</span><span class="sxs-lookup"><span data-stu-id="84361-176">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="84361-177">また、ストレージ エリア ネットワーク (SAN) が急増しているため、RAID セットが単一のシステム専用にされることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="84361-177">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="84361-178">Lync Server 2013 で SQL Server のパフォーマンスを構成する場合は、RAID または SAN ベンダーに問い合わせて、ディスクレイアウトに最適な構成を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84361-178">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="84361-179">また、すべてのディスクドライブが同じように作成されるわけではないことにも注意してください。一部の機能は他よりもパフォーマンスが優れています。</span><span class="sxs-lookup"><span data-stu-id="84361-179">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="84361-180">同じ製造元のドライブでも、回転速度、ハードウェアキャッシュサイズ、その他の要因によってパフォーマンスが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="84361-180">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

