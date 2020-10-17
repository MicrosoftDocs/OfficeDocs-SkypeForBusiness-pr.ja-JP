---
title: 'Lync Server 2013: バックアップと復元のワークシート'
description: 'Lync Server 2013: バックアップと復元のワークシート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552323"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="f28a0-103">Lync Server 2013 のバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="f28a0-103">Backup and restoration worksheets for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f28a0-104">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="f28a0-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="f28a0-105">組織のバックアップと復元の計画には、データと設定をバックアップする方法と時期の詳細が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f28a0-105">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="f28a0-106">ここに示されているワークシートを使用して、特定の展開および組織のバックアップと復元の要件に関する情報を文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="f28a0-106">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="f28a0-107">次のワークシートを使用して、Lync Server プールまたは Standard Edition サーバーのデータベース、ファイルストア、および設定に関する情報をバックアップおよび復元するために必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="f28a0-107">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="f28a0-108">Lync Server を復元する必要がある場合に容易にアクセスできるように、これらのワークシートの1つ以上のコピーを安全な場所に保管してください。</span><span class="sxs-lookup"><span data-stu-id="f28a0-108">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f28a0-109">このセクションのワークシートでは、Lync Server データベースおよびサーバーのデータと設定を復元するために必要な情報のみを説明します。</span><span class="sxs-lookup"><span data-stu-id="f28a0-109">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="f28a0-110">オペレーティングシステムおよびその他のソフトウェアを再インストールするための情報など、他の復元情報を文書化する必要がある場合は、組織の展開計画と、それらの要件に対応するためのバックアップと復元の計画を使用します。</span><span class="sxs-lookup"><span data-stu-id="f28a0-110">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="f28a0-111">データベースのバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="f28a0-111">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="f28a0-112">次の表を使用して、Lync Server データベースのバックアップと復元に必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="f28a0-112">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="f28a0-113">バックアップと復元のためのデータベース情報</span><span class="sxs-lookup"><span data-stu-id="f28a0-113">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f28a0-114">Database</span><span class="sxs-lookup"><span data-stu-id="f28a0-114">Database</span></span></th>
<th><span data-ttu-id="f28a0-115">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f28a0-115">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="f28a0-116">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="f28a0-116">Backup schedule</span></span></th>
<th><span data-ttu-id="f28a0-117">データベースバックアップツール</span><span class="sxs-lookup"><span data-stu-id="f28a0-117">Database backup tool</span></span></th>
<th><span data-ttu-id="f28a0-118">バックアップセット</span><span class="sxs-lookup"><span data-stu-id="f28a0-118">Backup set</span></span></th>
<th><span data-ttu-id="f28a0-119">バックアップ先</span><span class="sxs-lookup"><span data-stu-id="f28a0-119">Backup destination</span></span></th>
<th><span data-ttu-id="f28a0-120">Notes</span><span class="sxs-lookup"><span data-stu-id="f28a0-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f28a0-121">バックエンドサーバー上のユーザーデータ用の Rtc データベース</span><span class="sxs-lookup"><span data-stu-id="f28a0-121">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="f28a0-122"><strong>Export-CsUserData</strong> コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f28a0-122"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="f28a0-123">拡張子</span><span class="sxs-lookup"><span data-stu-id="f28a0-123">Name:</span></span></p>
<p><span data-ttu-id="f28a0-124">Nntp</span><span class="sxs-lookup"><span data-stu-id="f28a0-124">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28a0-125">アーカイブデータベースサーバー上の LcsLog (既定の名前) データベース</span><span class="sxs-lookup"><span data-stu-id="f28a0-125">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f28a0-126">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="f28a0-126">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="f28a0-127">拡張子</span><span class="sxs-lookup"><span data-stu-id="f28a0-127">Name:</span></span></p>
<p><span data-ttu-id="f28a0-128">Nntp</span><span class="sxs-lookup"><span data-stu-id="f28a0-128">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f28a0-129">通話詳細レコードの監視データベースサーバー上の LcsCdr データベース (Cdr)</span><span class="sxs-lookup"><span data-stu-id="f28a0-129">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f28a0-130">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="f28a0-130">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="f28a0-131">拡張子</span><span class="sxs-lookup"><span data-stu-id="f28a0-131">Name:</span></span></p>
<p><span data-ttu-id="f28a0-132">Nntp</span><span class="sxs-lookup"><span data-stu-id="f28a0-132">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28a0-133">QoEMetrics データベースサーバーの監視データベースサーバーでの、QoE (Quality of Experience) データ</span><span class="sxs-lookup"><span data-stu-id="f28a0-133">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f28a0-134">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="f28a0-134">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="f28a0-135">拡張子</span><span class="sxs-lookup"><span data-stu-id="f28a0-135">Name:</span></span></p>
<p><span data-ttu-id="f28a0-136">Nntp</span><span class="sxs-lookup"><span data-stu-id="f28a0-136">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f28a0-137">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="f28a0-137">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="f28a0-138">SQL Server 管理ツールまたは <strong>export-cspersistentchatdata</strong> コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f28a0-138">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="f28a0-139">拡張子</span><span class="sxs-lookup"><span data-stu-id="f28a0-139">Name:</span></span></p>
<p><span data-ttu-id="f28a0-140">Nntp</span><span class="sxs-lookup"><span data-stu-id="f28a0-140">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f28a0-141">次のデータベースのバックアップまたは復元は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f28a0-141">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="f28a0-142">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="f28a0-142">Rtcdyn.</span></span> <span data-ttu-id="f28a0-143">このデータベースの一時ユーザーデータは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f28a0-143">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="f28a0-144">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="f28a0-144">Rtcab.</span></span> <span data-ttu-id="f28a0-145">アドレス帳データベースは、Active Directory ドメインサービスのグローバルアドレス一覧 (GAL) から自動的に再作成されます。</span><span class="sxs-lookup"><span data-stu-id="f28a0-145">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="f28a0-146">Rgsdyn.mdf.</span><span class="sxs-lookup"><span data-stu-id="f28a0-146">Rgsdyn.</span></span> <span data-ttu-id="f28a0-147">このデータベース内の一時応答グループサービスデータは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f28a0-147">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="f28a0-148">Cpsdyn.mdf.</span><span class="sxs-lookup"><span data-stu-id="f28a0-148">Cpsdyn.</span></span> <span data-ttu-id="f28a0-149">コールパークアプリケーションの動的情報は、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f28a0-149">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="f28a0-150">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="f28a0-150">MgcComp.</span></span> <span data-ttu-id="f28a0-151">常設チャットのコンプライアンスデータベースは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f28a0-151">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="f28a0-152">ファイルストアのバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="f28a0-152">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="f28a0-153">次の表を使用して、ファイルストアのバックアップと復元に必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="f28a0-153">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="f28a0-154">ファイルストアには、会議コンテンツのメタデータ、会議のコンプライアンスログ、デバイス更新のための更新ログ、応答グループ、コールパーク、アナウンスアプリケーションのオーディオファイルなどのデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f28a0-154">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="f28a0-155">バックアップと復元のためのファイルストア情報</span><span class="sxs-lookup"><span data-stu-id="f28a0-155">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f28a0-156">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="f28a0-156">Content</span></span></th>
<th><span data-ttu-id="f28a0-157">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f28a0-157">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="f28a0-158">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="f28a0-158">Backup schedule</span></span></th>
<th><span data-ttu-id="f28a0-159">ファイルシステムバックアップツール</span><span class="sxs-lookup"><span data-stu-id="f28a0-159">File system backup tool</span></span></th>
<th><span data-ttu-id="f28a0-160">バックアップするファイル共有 \*</span><span class="sxs-lookup"><span data-stu-id="f28a0-160">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="f28a0-161">バックアップ先</span><span class="sxs-lookup"><span data-stu-id="f28a0-161">Backup destination</span></span></th>
<th><span data-ttu-id="f28a0-162">Notes</span><span class="sxs-lookup"><span data-stu-id="f28a0-162">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f28a0-163">Lync Server ファイルストア</span><span class="sxs-lookup"><span data-stu-id="f28a0-163">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="f28a0-164">標準バックアップツール (Robocopy など)</span><span class="sxs-lookup"><span data-stu-id="f28a0-164">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="f28a0-165">Enterprise Edition のファイルサーバー。</span><span class="sxs-lookup"><span data-stu-id="f28a0-165">On file server for Enterprise Edition.</span></span> <span data-ttu-id="f28a0-166">Standard edition では、standard edition の展開に既定で適用されます。</span><span class="sxs-lookup"><span data-stu-id="f28a0-166">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="f28a0-167">通常は、サイトごとに1つ。</span><span class="sxs-lookup"><span data-stu-id="f28a0-167">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f28a0-168"><strong>Meeting.Active</strong> という名前のファイルはバックアップしないでください。</span><span class="sxs-lookup"><span data-stu-id="f28a0-168">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="f28a0-169">これらのファイルは使用中で、会議中にロックされます。</span><span class="sxs-lookup"><span data-stu-id="f28a0-169">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="f28a0-170">[設定のバックアップと復元] ワークシート</span><span class="sxs-lookup"><span data-stu-id="f28a0-170">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="f28a0-171">次の表を使用して、設定をバックアップおよび復元するために必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="f28a0-171">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="f28a0-172">バックアップと復元の設定情報</span><span class="sxs-lookup"><span data-stu-id="f28a0-172">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f28a0-173">Database</span><span class="sxs-lookup"><span data-stu-id="f28a0-173">Database</span></span></th>
<th><span data-ttu-id="f28a0-174">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f28a0-174">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="f28a0-175">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="f28a0-175">Backup schedule</span></span></th>
<th><span data-ttu-id="f28a0-176">バックアップツール</span><span class="sxs-lookup"><span data-stu-id="f28a0-176">Backup tool</span></span></th>
<th><span data-ttu-id="f28a0-177">構成ファイル (.xml) 名</span><span class="sxs-lookup"><span data-stu-id="f28a0-177">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="f28a0-178">バックアップの場所</span><span class="sxs-lookup"><span data-stu-id="f28a0-178">Backup location</span></span></th>
<th><span data-ttu-id="f28a0-179">Notes</span><span class="sxs-lookup"><span data-stu-id="f28a0-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f28a0-180">トポロジ構成用の中央管理ストアの Xds データベース (グローバル)</span><span class="sxs-lookup"><span data-stu-id="f28a0-180">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="f28a0-181"><strong>Export-CsConfiguration</strong> コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f28a0-181"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28a0-182">E9-1-1 場所情報 (グローバル) の中央管理ストアの Lis データベース</span><span class="sxs-lookup"><span data-stu-id="f28a0-182">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f28a0-183"><strong>Export-cslisconfiguration</strong> コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f28a0-183"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f28a0-184">応答グループ構成のバックエンドサーバー上の RgsConfig データベース (プール)</span><span class="sxs-lookup"><span data-stu-id="f28a0-184">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f28a0-185"><strong>Export-CsRgsConfiguration</strong> コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f28a0-185"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

