---
title: 'Lync Server 2013: バックアップと復元のワークシート'
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
ms.openlocfilehash: 3fcf163893a84e4b9244e43b12c702cf0076b1ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="21902-102">Lync Server 2013 のバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="21902-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21902-103">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="21902-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="21902-104">組織のバックアップと復元の計画には、データと設定をバックアップする方法と時期の詳細が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="21902-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="21902-105">ここに示されているワークシートを使用して、特定の展開および組織のバックアップと復元の要件に関する情報を文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="21902-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="21902-106">次のワークシートを使用して、Lync Server プールまたは Standard Edition サーバーのデータベース、ファイルストア、および設定に関する情報をバックアップおよび復元するために必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="21902-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="21902-107">Lync Server を復元する必要がある場合に容易にアクセスできるように、これらのワークシートの1つ以上のコピーを安全な場所に保管してください。</span><span class="sxs-lookup"><span data-stu-id="21902-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21902-108">このセクションのワークシートでは、Lync Server データベースおよびサーバーのデータと設定を復元するために必要な情報のみを説明します。</span><span class="sxs-lookup"><span data-stu-id="21902-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="21902-109">オペレーティングシステムおよびその他のソフトウェアを再インストールするための情報など、他の復元情報を文書化する必要がある場合は、組織の展開計画と、それらの要件に対応するためのバックアップと復元の計画を使用します。</span><span class="sxs-lookup"><span data-stu-id="21902-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="21902-110">データベースのバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="21902-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="21902-111">次の表を使用して、Lync Server データベースのバックアップと復元に必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="21902-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="21902-112">バックアップと復元のためのデータベース情報</span><span class="sxs-lookup"><span data-stu-id="21902-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="21902-113">データベース</span><span class="sxs-lookup"><span data-stu-id="21902-113">Database</span></span></th>
<th><span data-ttu-id="21902-114">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="21902-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="21902-115">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="21902-115">Backup schedule</span></span></th>
<th><span data-ttu-id="21902-116">データベースバックアップツール</span><span class="sxs-lookup"><span data-stu-id="21902-116">Database backup tool</span></span></th>
<th><span data-ttu-id="21902-117">バックアップセット</span><span class="sxs-lookup"><span data-stu-id="21902-117">Backup set</span></span></th>
<th><span data-ttu-id="21902-118">バックアップ先</span><span class="sxs-lookup"><span data-stu-id="21902-118">Backup destination</span></span></th>
<th><span data-ttu-id="21902-119">メモ</span><span class="sxs-lookup"><span data-stu-id="21902-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21902-120">バックエンドサーバー上のユーザーデータ用の Rtc データベース</span><span class="sxs-lookup"><span data-stu-id="21902-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="21902-121"><strong>Export-CsUserData</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="21902-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="21902-122">拡張子</span><span class="sxs-lookup"><span data-stu-id="21902-122">Name:</span></span></p>
<p><span data-ttu-id="21902-123">Nntp</span><span class="sxs-lookup"><span data-stu-id="21902-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21902-124">アーカイブデータベースサーバー上の LcsLog (既定の名前) データベース</span><span class="sxs-lookup"><span data-stu-id="21902-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21902-125">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="21902-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="21902-126">拡張子</span><span class="sxs-lookup"><span data-stu-id="21902-126">Name:</span></span></p>
<p><span data-ttu-id="21902-127">Nntp</span><span class="sxs-lookup"><span data-stu-id="21902-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21902-128">通話詳細レコードの監視データベースサーバー上の LcsCdr データベース (Cdr)</span><span class="sxs-lookup"><span data-stu-id="21902-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21902-129">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="21902-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="21902-130">拡張子</span><span class="sxs-lookup"><span data-stu-id="21902-130">Name:</span></span></p>
<p><span data-ttu-id="21902-131">Nntp</span><span class="sxs-lookup"><span data-stu-id="21902-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21902-132">QoEMetrics データベースサーバーの監視データベースサーバーでの、QoE (Quality of Experience) データ</span><span class="sxs-lookup"><span data-stu-id="21902-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21902-133">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="21902-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="21902-134">拡張子</span><span class="sxs-lookup"><span data-stu-id="21902-134">Name:</span></span></p>
<p><span data-ttu-id="21902-135">Nntp</span><span class="sxs-lookup"><span data-stu-id="21902-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21902-136">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="21902-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="21902-137">SQL Server 管理ツールまたは<strong>export-cspersistentchatdata</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="21902-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="21902-138">拡張子</span><span class="sxs-lookup"><span data-stu-id="21902-138">Name:</span></span></p>
<p><span data-ttu-id="21902-139">Nntp</span><span class="sxs-lookup"><span data-stu-id="21902-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="21902-140">次のデータベースのバックアップまたは復元は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="21902-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="21902-141">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="21902-141">Rtcdyn.</span></span> <span data-ttu-id="21902-142">このデータベースの一時ユーザーデータは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="21902-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="21902-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="21902-143">Rtcab.</span></span> <span data-ttu-id="21902-144">アドレス帳データベースは、Active Directory ドメインサービスのグローバルアドレス一覧 (GAL) から自動的に再作成されます。</span><span class="sxs-lookup"><span data-stu-id="21902-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="21902-145">Rgsdyn.mdf.</span><span class="sxs-lookup"><span data-stu-id="21902-145">Rgsdyn.</span></span> <span data-ttu-id="21902-146">このデータベース内の一時応答グループサービスデータは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="21902-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="21902-147">Cpsdyn.mdf.</span><span class="sxs-lookup"><span data-stu-id="21902-147">Cpsdyn.</span></span> <span data-ttu-id="21902-148">コールパークアプリケーションの動的情報は、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="21902-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="21902-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="21902-149">MgcComp.</span></span> <span data-ttu-id="21902-150">常設チャットのコンプライアンスデータベースは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="21902-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="21902-151">ファイルストアのバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="21902-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="21902-152">次の表を使用して、ファイルストアのバックアップと復元に必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="21902-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="21902-153">ファイルストアには、会議コンテンツのメタデータ、会議のコンプライアンスログ、デバイス更新のための更新ログ、応答グループ、コールパーク、アナウンスアプリケーションのオーディオファイルなどのデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21902-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="21902-154">バックアップと復元のためのファイルストア情報</span><span class="sxs-lookup"><span data-stu-id="21902-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="21902-155">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="21902-155">Content</span></span></th>
<th><span data-ttu-id="21902-156">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="21902-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="21902-157">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="21902-157">Backup schedule</span></span></th>
<th><span data-ttu-id="21902-158">ファイルシステムバックアップツール</span><span class="sxs-lookup"><span data-stu-id="21902-158">File system backup tool</span></span></th>
<th><span data-ttu-id="21902-159">バックアップするファイル共有 \*</span><span class="sxs-lookup"><span data-stu-id="21902-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="21902-160">バックアップ先</span><span class="sxs-lookup"><span data-stu-id="21902-160">Backup destination</span></span></th>
<th><span data-ttu-id="21902-161">メモ</span><span class="sxs-lookup"><span data-stu-id="21902-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21902-162">Lync Server ファイルストア</span><span class="sxs-lookup"><span data-stu-id="21902-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="21902-163">標準バックアップツール (Robocopy など)</span><span class="sxs-lookup"><span data-stu-id="21902-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="21902-164">Enterprise Edition のファイルサーバー。</span><span class="sxs-lookup"><span data-stu-id="21902-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="21902-165">Standard edition では、standard edition の展開に既定で適用されます。</span><span class="sxs-lookup"><span data-stu-id="21902-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="21902-166">通常は、サイトごとに1つ。</span><span class="sxs-lookup"><span data-stu-id="21902-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21902-167"><strong>Meeting.Active</strong> という名前のファイルはバックアップしないでください。</span><span class="sxs-lookup"><span data-stu-id="21902-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="21902-168">これらのファイルは使用中で、会議中にロックされます。</span><span class="sxs-lookup"><span data-stu-id="21902-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="21902-169">[設定のバックアップと復元] ワークシート</span><span class="sxs-lookup"><span data-stu-id="21902-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="21902-170">次の表を使用して、設定をバックアップおよび復元するために必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="21902-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="21902-171">バックアップと復元の設定情報</span><span class="sxs-lookup"><span data-stu-id="21902-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="21902-172">データベース</span><span class="sxs-lookup"><span data-stu-id="21902-172">Database</span></span></th>
<th><span data-ttu-id="21902-173">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="21902-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="21902-174">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="21902-174">Backup schedule</span></span></th>
<th><span data-ttu-id="21902-175">バックアップツール</span><span class="sxs-lookup"><span data-stu-id="21902-175">Backup tool</span></span></th>
<th><span data-ttu-id="21902-176">構成ファイル (.xml) 名</span><span class="sxs-lookup"><span data-stu-id="21902-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="21902-177">バックアップの場所</span><span class="sxs-lookup"><span data-stu-id="21902-177">Backup location</span></span></th>
<th><span data-ttu-id="21902-178">メモ</span><span class="sxs-lookup"><span data-stu-id="21902-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21902-179">トポロジ構成用の中央管理ストアの Xds データベース (グローバル)</span><span class="sxs-lookup"><span data-stu-id="21902-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="21902-180"><strong>Export-CsConfiguration</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="21902-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21902-181">E9-1-1 場所情報 (グローバル) の中央管理ストアの Lis データベース</span><span class="sxs-lookup"><span data-stu-id="21902-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21902-182"><strong>Export-cslisconfiguration</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="21902-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21902-183">応答グループ構成のバックエンドサーバー上の RgsConfig データベース (プール)</span><span class="sxs-lookup"><span data-stu-id="21902-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21902-184"><strong>Export-CsRgsConfiguration</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="21902-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

