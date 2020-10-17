---
title: 'Lync Server 2013: バックアップと復元の要件: データ'
description: 'Lync Server 2013: バックアップと復元の要件: データ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e135f09706d31ff3f0efa54c8687546de9fab78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563183"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="e49c6-103">Lync Server 2013 のバックアップと復元の要件: データ</span><span class="sxs-lookup"><span data-stu-id="e49c6-103">Backup and restoration requirements in Lync Server 2013: data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e49c6-104">_**トピックの最終更新日:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="e49c6-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="e49c6-105">Lync Server は、データベースに格納されている設定と構成情報、およびデータベースおよびファイルストアに格納されているデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-105">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="e49c6-106">このトピックでは、組織で障害や停止が発生した場合にサービスを復元できるようにするためにバックアップする必要のあるデータについて説明します。また、個別にバックアップする必要がある Lync Server で使用されているデータとコンポーネントも識別します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-106">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="e49c6-107">設定と構成の要件</span><span class="sxs-lookup"><span data-stu-id="e49c6-107">Settings and Configuration Requirements</span></span>

<span data-ttu-id="e49c6-108">このトピックでは、Lync Server サービスの復旧に必要な設定と構成情報をバックアップおよび復元する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-108">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="e49c6-109">構成情報は、中央管理ストアまたは別のバックエンドデータベースまたは Standard Edition サーバーにあります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-109">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="e49c6-110">次の表に、バックアップと復元に必要な設定と構成情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-110">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="e49c6-111">設定と構成データ</span><span class="sxs-lookup"><span data-stu-id="e49c6-111">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e49c6-112">データの種類</span><span class="sxs-lookup"><span data-stu-id="e49c6-112">Type of data</span></span></th>
<th><span data-ttu-id="e49c6-113">保存場所</span><span class="sxs-lookup"><span data-stu-id="e49c6-113">Where stored</span></span></th>
<th><span data-ttu-id="e49c6-114">説明 / バックアップするタイミング</span><span class="sxs-lookup"><span data-stu-id="e49c6-114">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e49c6-115">トポロジ構成情報</span><span class="sxs-lookup"><span data-stu-id="e49c6-115">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="e49c6-116">中央管理ストア (データベース: Xds)</span><span class="sxs-lookup"><span data-stu-id="e49c6-116">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e49c6-117">トポロジ、ポリシー、および構成の設定。</span><span class="sxs-lookup"><span data-stu-id="e49c6-117">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="e49c6-118">通常のバックアップを使用してバックアップを行い、Lync Server コントロールパネルまたはコマンドレットを使用して構成またはポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-118">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e49c6-119">場所情報</span><span class="sxs-lookup"><span data-stu-id="e49c6-119">Location information</span></span></p></td>
<td><p><span data-ttu-id="e49c6-120">中央管理ストア (データベース: Lis)</span><span class="sxs-lookup"><span data-stu-id="e49c6-120">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e49c6-p103">エンタープライズ VoIP Enhanced 9-1-1 (E9-1-1) 構成情報。この情報は一般に静的です。</span><span class="sxs-lookup"><span data-stu-id="e49c6-p103">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information. This information is generally static.</span></span></p>
<p><span data-ttu-id="e49c6-123">定期的なバックアップによってバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e49c6-123">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e49c6-124">応答グループの構成情報</span><span class="sxs-lookup"><span data-stu-id="e49c6-124">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="e49c6-125">バックエンドサーバーまたは Standard Edition サーバー (データベース: RgsConfig)</span><span class="sxs-lookup"><span data-stu-id="e49c6-125">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e49c6-126">応答グループのエージェントグループ、キュー、およびワークフロー。</span><span class="sxs-lookup"><span data-stu-id="e49c6-126">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="e49c6-127">定期的なバックアップのとき、およびエージェント グループ、キュー、またはワークフローを追加または変更した後でバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e49c6-127">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="e49c6-128">データの要件</span><span class="sxs-lookup"><span data-stu-id="e49c6-128">Data Requirements</span></span>

<span data-ttu-id="e49c6-129">ここでは、障害が発生した場合に Lync Server サービスを復元できるように、バックアップする必要がある Lync Server データの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-129">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="e49c6-130">データの種類によっては、回復に必要でないものがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e49c6-130">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="e49c6-131">このトピックには、次のような種類のデータをバックアップする手順は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-131">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="e49c6-132">エンドポイントとサブスクリプション、アクティブな会議サーバー、一時的な会議状態など、一時的なユーザー データ (データベース: RtcDyn.mdf)</span><span class="sxs-lookup"><span data-stu-id="e49c6-132">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="e49c6-133">アドレス帳のデータ (データベース: Rtcab .mdf および Rtcab1.mdf)。</span><span class="sxs-lookup"><span data-stu-id="e49c6-133">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="e49c6-134">アドレス帳データベースは、Active Directory ドメインサービスから自動的に再生成されます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-134">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="e49c6-135">コールパークアプリケーションの動的情報 (データベース: Cpsdyn.mdf)</span><span class="sxs-lookup"><span data-stu-id="e49c6-135">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="e49c6-136">エージェントのサインイン状態や通話待機情報 (データベース: Rgsdyn.mdf) など、一時的な応答グループのデータ</span><span class="sxs-lookup"><span data-stu-id="e49c6-136">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="e49c6-137">常設チャット (データベース: お使いの場合) のコンプライアンスデータベース。</span><span class="sxs-lookup"><span data-stu-id="e49c6-137">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="e49c6-138">常設チャットコンプライアンスが有効になっている場合、データベースから情報を読み取って別の形式に変換するように構成されているアダプターを使用している限り、常設チャットコンプライアンスデータベースの情報は一時的なものになります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-138">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="e49c6-139">そのため、常設チャットのコンプライアンスデータベースは一時的なものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-139">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="e49c6-140">Lync Server 2013 常設チャットサーバーには、XML アダプターが付属しています。</span><span class="sxs-lookup"><span data-stu-id="e49c6-140">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="e49c6-141">また、このデータを受け取り、Exchange Hosted アーカイブなどの他のソースに移動するカスタムアダプターをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-141">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="e49c6-142">次の表に、バックアップと復元に必要なデータを示します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-142">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="e49c6-143">データベースに格納されているデータ</span><span class="sxs-lookup"><span data-stu-id="e49c6-143">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e49c6-144">データの種類</span><span class="sxs-lookup"><span data-stu-id="e49c6-144">Type of data</span></span></th>
<th><span data-ttu-id="e49c6-145">保存場所</span><span class="sxs-lookup"><span data-stu-id="e49c6-145">Where stored</span></span></th>
<th><span data-ttu-id="e49c6-146">説明 / バックアップするタイミング</span><span class="sxs-lookup"><span data-stu-id="e49c6-146">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e49c6-147">永続的なユーザー データ</span><span class="sxs-lookup"><span data-stu-id="e49c6-147">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="e49c6-148">バックエンドサーバーまたは Standard Edition サーバー (データベース: RTCXDS. .mdf)</span><span class="sxs-lookup"><span data-stu-id="e49c6-148">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e49c6-149">ユーザーの権限、ユーザーの連絡先リスト、サーバーまたはプール データ、予約された電話会議など。</span><span class="sxs-lookup"><span data-stu-id="e49c6-149">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="e49c6-150">このユーザー データには、会議にアップロードされたコンテンツは含まれません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-150">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="e49c6-151">定期的なバックアップによってバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e49c6-151">Back up with your regular backups.</span></span> <span data-ttu-id="e49c6-152">この情報は動的ですが、最新の正規バックアップに復元する必要がある場合は、更新の損失が Lync Server にとって重大ではありません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-152">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="e49c6-153">連絡先リストの重要性が高い組織では、このデータのバックアップの頻度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-153">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e49c6-154">アーカイブ データ</span><span class="sxs-lookup"><span data-stu-id="e49c6-154">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="e49c6-155">アーカイブ データベース (データベース: LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="e49c6-155">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="e49c6-156">このデータは、Microsoft Exchange 統合オプションが有効になっている場合、Exchange 2013 に保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-156">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="e49c6-157">それ以外の場合、このデータは Lync Server アーカイブデータベースに保持されます。これは、別の Lync Server データベースと併置されることもあれば、別のデータベースサーバー上にあるスタンドアロンでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-157">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="e49c6-158">インスタント メッセージング (IM) と会議のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="e49c6-158">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="e49c6-159">このデータは Lync Server にとって重要ではありませんが、規制を目的として組織にとって重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-159">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="e49c6-160">適切にバックアップのスケジュールを判断します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-160">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e49c6-161">監視データ</span><span class="sxs-lookup"><span data-stu-id="e49c6-161">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="e49c6-162">監視データベース (LcsCDR.mdf および QoeMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="e49c6-162">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="e49c6-163">これらのデータベースは、別の Lync Server データベースに併置されている場合もあれば、スタンドアロンの場合は別のデータベースサーバーに共存することもあります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-163">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="e49c6-164">通話詳細レコード (LcsCDR .mdf) および QoE (Quality of Experience) 指標 (QoeMetrics)。</span><span class="sxs-lookup"><span data-stu-id="e49c6-164">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="e49c6-p112">詳細通話記録は動的で、ビジネスにとって重大な場合があります。法令上の理由でこれらの記録が必要かどうかをふまえて、バックアップ スケジュールを判断します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-p112">Call detail records are dynamic and may be critical to your business. Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="e49c6-167">QoE 情報は動的です。</span><span class="sxs-lookup"><span data-stu-id="e49c6-167">Quality of experience information is dynamic.</span></span> <span data-ttu-id="e49c6-168">QoE データの損失は、Lync Server の操作にとって重要ではありませんが、ビジネスにとって重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-168">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="e49c6-169">この情報が組織にとってどの程度重大かに基づいて、バックアップ スケジュールを判断します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-169">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e49c6-170">常設チャットデータ</span><span class="sxs-lookup"><span data-stu-id="e49c6-170">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="e49c6-171">常設チャットデータベース (お持ちの場合)。</span><span class="sxs-lookup"><span data-stu-id="e49c6-171">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="e49c6-172">このデータベースは、別の Lync Server データベースと併置されている場合もあれば、独立したデータベースサーバーにスタンドアロンである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-172">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="e49c6-173">常設チャットデータは、チャットルームに投稿される実際のチャットコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="e49c6-173">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="e49c6-174">このデータは、多くの場合、ビジネス上非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="e49c6-174">This data is often business critical.</span></span></p>
<p><span data-ttu-id="e49c6-175">Lync Server に用意されている <strong>export-cspersistentchatdata</strong> コマンドレットを使用して、SQL Server バックアップを使用するか、データベースをエクスポートするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-175">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="e49c6-176">データを回復するには、最後の完全バックアップの時点までデータベースをインポートして復元することができます。これは、データベースを障害点まで復元できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-176">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="e49c6-177">ファイル ストア データの要件</span><span class="sxs-lookup"><span data-stu-id="e49c6-177">File Store Data Requirements</span></span>

<span data-ttu-id="e49c6-178">Enterprise Edition の展開では、Lync Server ファイルストアは通常、ファイルサーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-178">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="e49c6-179">Standard Edition の展開では、Lync Server ファイルストアは既定で Standard Edition サーバーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-179">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="e49c6-180">通常、サイトに対して共有される Lync Server ファイルストアは1つです。</span><span class="sxs-lookup"><span data-stu-id="e49c6-180">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="e49c6-181">常設チャットのファイルストアは、Lync Server ファイルストアと同じファイル共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-181">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="e49c6-182">ファイルストアの場所は、 \\ サーバー共有名として識別され \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-182">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="e49c6-183">ファイルストアの特定の場所を検索するには、トポロジビルダーを開き、[ **ファイルストア** ] ノードを探します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-183">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="e49c6-184">次の表に、バックアップおよび復元する必要があるファイル ストアを示します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-184">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="e49c6-185">ファイル ストア</span><span class="sxs-lookup"><span data-stu-id="e49c6-185">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e49c6-186">データの種類</span><span class="sxs-lookup"><span data-stu-id="e49c6-186">Type of data</span></span></th>
<th><span data-ttu-id="e49c6-187">保存場所</span><span class="sxs-lookup"><span data-stu-id="e49c6-187">Where stored</span></span></th>
<th><span data-ttu-id="e49c6-188">説明 / バックアップするタイミング</span><span class="sxs-lookup"><span data-stu-id="e49c6-188">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e49c6-189">Lync Server ファイル ストア</span><span class="sxs-lookup"><span data-stu-id="e49c6-189">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="e49c6-190">通常、ファイルサーバー、ファイルクラスター、または Standard Edition サーバー上で</span><span class="sxs-lookup"><span data-stu-id="e49c6-190">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="e49c6-191">会議コンテンツ、会議コンテンツのメタデータ、会議のコンプライアンスログ、アプリケーションデータファイル、デバイス更新のためのファイルの更新、応答グループのオーディオファイル、コールパーク、アナウンスアプリケーション、および常設チャットルームに投稿されたファイル。</span><span class="sxs-lookup"><span data-stu-id="e49c6-191">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="e49c6-192">定期的なバックアップによってバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e49c6-192">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="e49c6-193">追加のバックアップの要件</span><span class="sxs-lookup"><span data-stu-id="e49c6-193">Additional Backup Requirements</span></span>

<span data-ttu-id="e49c6-194">障害が発生した場合に Lync Server サービスを復元できるようにするには、Lync Server 自体に含まれていないいくつかの必要なコンポーネントをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-194">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="e49c6-195">次のコンポーネントは、このドキュメントで説明する Lync Server のバックアップと復元のプロセスの一環としてバックアップまたは復元されません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-195">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="e49c6-196">**Active Directory ドメインサービス**    Lync Server をバックアップするのと同時に、Active Directory ツールを使用して AD DS をバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-196">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="e49c6-197">Ad DS と Lync Server を同期させておくことが重要です。これは、Lync Server が AD DS 内の連絡先オブジェクトと一致しない場合に発生する問題を回避するためです。</span><span class="sxs-lookup"><span data-stu-id="e49c6-197">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="e49c6-198">AD DS は、Lync Server で使用される次の設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-198">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="e49c6-199">ユーザーの SIP URI と他のユーザー設定。</span><span class="sxs-lookup"><span data-stu-id="e49c6-199">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="e49c6-200">応答グループや会議アテンダントなどのアプリケーションの連絡先オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e49c6-200">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="e49c6-201">中央管理ストアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e49c6-201">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="e49c6-202">Kerberos 認証アカウント (オプションのコンピューターオブジェクト) と Lync Server セキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="e49c6-202">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="e49c6-203">Windows Server 2008 での AD DS のバックアップと復元の詳細については、「」の「AD DS のバックアップと復元のステップバイステップガイド」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) 。</span><span class="sxs-lookup"><span data-stu-id="e49c6-203">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="e49c6-204">**証明機関と証明書**    組織のポリシーを使用して、証明機関 (CA) と証明書をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e49c6-204">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="e49c6-205">エクスポート可能な秘密キーを使用している場合は、証明書と秘密キーをバックアップしてから、このドキュメントの手順を使用して Lync Server を復元する場合は、それらをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-205">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="e49c6-206">内部 CA を使用している場合は、Lync Server を復元する必要がある場合に再登録できます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-206">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="e49c6-207">秘密キーは、コンピューターで障害が発生した場合に使用できる安全な場所に保持しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="e49c6-207">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="e49c6-208">**System Center Operations Manager**    Microsoft System Center Operations Manager (旧称 Microsoft Operations Manager) を使用して Lync Server の展開を監視している場合は、Lync Server を監視している間に、必要に応じて、作成したデータをバックアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-208">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="e49c6-209">標準の SQL Server バックアッププロセスを使用して、System Center Operations Manager ファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e49c6-209">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="e49c6-210">これらのファイルは復旧の際に復元されません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-210">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="e49c6-211">**公衆交換電話網 (PSTN) ゲートウェイの構成**    エンタープライズ Voip または存続可能ブランチアプライアンスを使用する場合は、PSTN ゲートウェイ構成をバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-211">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="e49c6-212">PSTN ゲートウェイ構成のバックアップと復元の詳細については、ベンダーに確認してください。</span><span class="sxs-lookup"><span data-stu-id="e49c6-212">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="e49c6-213">**Lync server または Office Communications server**     の共存バージョンLync server 2013 の展開 coexists で Lync Server 2010 または以前のバージョンの Office Communications Server が使用されている場合は、このドキュメントの手順を使用して以前のバージョンのバックアップまたは復元を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-213">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="e49c6-214">代わりに、該当のバージョンのドキュメントにあるバックアップと復元の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-214">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="e49c6-215">Lync Server 2010 のバックアップと復元の詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) 。</span><span class="sxs-lookup"><span data-stu-id="e49c6-215">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="e49c6-216">Microsoft Office Communications Server 2007 R2 のバックアップと復元の詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) 。</span><span class="sxs-lookup"><span data-stu-id="e49c6-216">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="e49c6-217">**インフラストラクチャ情報**    インフラストラクチャの構成、負荷分散の構成、インターネットインフォメーションサービス (IIS) の構成、ドメインネームシステム (DNS) レコードおよび IP アドレス、動的ホスト構成プロトコル (DHCP) の構成など、インフラストラクチャに関する情報をバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-217">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="e49c6-218">これらのコンポーネントのバックアップの詳細については、それぞれのベンダーに確認してください。</span><span class="sxs-lookup"><span data-stu-id="e49c6-218">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="e49c6-219">**Microsoft exchange と Exchange ユニファイドメッセージング (UM)**    Microsoft exchange のドキュメントで説明されているように、Microsoft Exchange と Exchange UM をバックアップおよび復元します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-219">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="e49c6-220">Exchange Server 2013 のバックアップと復元の詳細については、「」を参照してください [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) 。</span><span class="sxs-lookup"><span data-stu-id="e49c6-220">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="e49c6-221">Exchange Server 2010 のバックアップと復元の詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) 。</span><span class="sxs-lookup"><span data-stu-id="e49c6-221">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="e49c6-222">Lync Server 2013 では、ユーザーの連絡先リスト、高精細定義のユーザー写真、および Exchange 2013 に格納されているアーカイブデータを持つことができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e49c6-222">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="e49c6-223">これらの種類のデータをバックアップする方法については、次のリストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e49c6-223">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="e49c6-224">**高品位写真** は、Exchange Server バックアップの一部としてバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-224">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="e49c6-225">**統合連絡先ストア** は、Lync Server 2013 で導入されています。</span><span class="sxs-lookup"><span data-stu-id="e49c6-225">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="e49c6-226">統合連絡先ストアによって、ユーザーは Exchange 2013 ですべての連絡先情報を保持できます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-226">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="e49c6-227">ユーザーの連絡先が統合連絡先ストアまたは Lync バックエンドサーバーに保存されているかどうかに関して、バックアップが最新の状態になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-227">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="e49c6-228">次のシナリオでは、ユーザーの連絡先を統合連絡先ストアに移行すると、バックアップと復元のプロセスで問題が発生する可能性があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="e49c6-228">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="e49c6-229">**シナリオ 1:** ユーザーの連絡先が統合連絡先ストアに移行され、ユーザーの連絡先を移行する前に行われた Lync Server バックアップから復元を実行します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-229">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="e49c6-230">このシナリオでは、Lync Server 移行タスクでユーザーの連絡先の Exchange への移行が開始されるまで、ユーザーは最大で1日前の状態になっています。</span><span class="sxs-lookup"><span data-stu-id="e49c6-230">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="e49c6-231">(ユーザーの連絡先は既に統合連絡先ストアに移行されているため、Exchange の連絡先情報が使用されることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="e49c6-231">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="e49c6-232">このシナリオでは、管理者の介入は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-232">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="e49c6-233">**シナリオ 2:** ユーザーの連絡先は、以前に統合連絡先ストアに保存されていて、ロールバックされています。</span><span class="sxs-lookup"><span data-stu-id="e49c6-233">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="e49c6-234">ユーザーの連絡先が統合連絡先ストアに格納されている場合に実行される Lync Server バックアップから復元を実行します。</span><span class="sxs-lookup"><span data-stu-id="e49c6-234">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="e49c6-235">このシナリオで `Error: Incorrect Exchange Version` は、クライアントまたはその他の ss サーバーログでエラーメッセージが表示され、これが問題として示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-235">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="e49c6-236">ユーザーは、Exchange から直接 Lync 2013 の連絡先リストにアクセスできますが、クライアントの状態は Lync Server の状態とは一致しません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-236">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="e49c6-237">この問題を解決するには、管理者は影響を受けるユーザーに対して **invoke-csucsrollback** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-237">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="e49c6-238">**アーカイブデータ** は、Exchange 2013 に保存できます。</span><span class="sxs-lookup"><span data-stu-id="e49c6-238">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="e49c6-239">このデータは Lync Server にとって重要ではありませんが、規制を目的として組織にとって重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e49c6-239">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="e49c6-240">アーカイブデータが Exchange に保存されており、組織にとって重要な場合は、Exchange のバックアップと復元の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e49c6-240">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="e49c6-241">Exchange に保存されているアーカイブデータを Lync Server に戻すことはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e49c6-241">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="e49c6-242">また、Lync アーカイブデータベースに既に格納されているデータを Exchange に移動する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="e49c6-242">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

