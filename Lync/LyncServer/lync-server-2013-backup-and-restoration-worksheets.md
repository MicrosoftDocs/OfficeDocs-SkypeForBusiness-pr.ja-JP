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
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="660ca-102">Lync Server 2013 のバックアップと復元ワークシート</span><span class="sxs-lookup"><span data-stu-id="660ca-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="660ca-103">_**最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="660ca-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="660ca-104">組織のバックアップと復元の計画には、データと設定をバックアップする方法とタイミングについての詳細が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="660ca-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="660ca-105">ここに記載されているワークシートを使用して、特定の展開や組織のバックアップと復元の要件について、この情報を文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="660ca-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="660ca-106">次のワークシートを使用して、Lync Server プールまたは Standard Edition サーバーのデータベース、ファイルストア、設定情報をバックアップおよび復元するために必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="660ca-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="660ca-107">Lync Server を復元する必要がある場合は、これらのワークシートのコピーを安全な場所に保管して、簡単にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="660ca-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="660ca-108">このセクションのワークシートには、Lync Server データベースおよびサーバーのデータと設定を復元するために必要な情報のみが記載されています。</span><span class="sxs-lookup"><span data-stu-id="660ca-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="660ca-109">オペレーティングシステムやその他のソフトウェアの再インストールに関する情報など、他の復元情報を文書化する必要がある場合は、組織の展開計画とバックアップおよび復元計画を使用して、これらの要件に対応します。</span><span class="sxs-lookup"><span data-stu-id="660ca-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="660ca-110">データベースのバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="660ca-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="660ca-111">次の表を使用して、Lync Server データベースのバックアップと復元に必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="660ca-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="660ca-112">バックアップと復元に関するデータベース情報</span><span class="sxs-lookup"><span data-stu-id="660ca-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="660ca-113">データベース</span><span class="sxs-lookup"><span data-stu-id="660ca-113">Database</span></span></th>
<th><span data-ttu-id="660ca-114">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="660ca-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="660ca-115">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="660ca-115">Backup schedule</span></span></th>
<th><span data-ttu-id="660ca-116">データベースバックアップツール</span><span class="sxs-lookup"><span data-stu-id="660ca-116">Database backup tool</span></span></th>
<th><span data-ttu-id="660ca-117">バックアップセット</span><span class="sxs-lookup"><span data-stu-id="660ca-117">Backup set</span></span></th>
<th><span data-ttu-id="660ca-118">バックアップ先</span><span class="sxs-lookup"><span data-stu-id="660ca-118">Backup destination</span></span></th>
<th><span data-ttu-id="660ca-119">メモ</span><span class="sxs-lookup"><span data-stu-id="660ca-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="660ca-120">バックエンドサーバー上の Rtc データベース (ユーザーデータの場合)</span><span class="sxs-lookup"><span data-stu-id="660ca-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="660ca-121"><strong>エクスポート-CsUserData</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="660ca-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="660ca-122">氏名</span><span class="sxs-lookup"><span data-stu-id="660ca-122">Name:</span></span></p>
<p><span data-ttu-id="660ca-123">無期限</span><span class="sxs-lookup"><span data-stu-id="660ca-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="660ca-124">アーカイブデータベースサーバーの LcsLog (既定の名前) データベース</span><span class="sxs-lookup"><span data-stu-id="660ca-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="660ca-125">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="660ca-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="660ca-126">氏名</span><span class="sxs-lookup"><span data-stu-id="660ca-126">Name:</span></span></p>
<p><span data-ttu-id="660ca-127">無期限</span><span class="sxs-lookup"><span data-stu-id="660ca-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="660ca-128">通話詳細レコードのモニタリングデータベースサーバー上の LcsCdr データベース (CDRs)</span><span class="sxs-lookup"><span data-stu-id="660ca-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="660ca-129">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="660ca-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="660ca-130">氏名</span><span class="sxs-lookup"><span data-stu-id="660ca-130">Name:</span></span></p>
<p><span data-ttu-id="660ca-131">無期限</span><span class="sxs-lookup"><span data-stu-id="660ca-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="660ca-132">Quality of Experience (QoE) データの監視データベースサーバー上の QoEMetrics データベース</span><span class="sxs-lookup"><span data-stu-id="660ca-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="660ca-133">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="660ca-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="660ca-134">氏名</span><span class="sxs-lookup"><span data-stu-id="660ca-134">Name:</span></span></p>
<p><span data-ttu-id="660ca-135">無期限</span><span class="sxs-lookup"><span data-stu-id="660ca-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="660ca-136">常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="660ca-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="660ca-137">SQL Server management tool または<strong>Export-CsPersistentChatData</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="660ca-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="660ca-138">氏名</span><span class="sxs-lookup"><span data-stu-id="660ca-138">Name:</span></span></p>
<p><span data-ttu-id="660ca-139">無期限</span><span class="sxs-lookup"><span data-stu-id="660ca-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="660ca-140">次のデータベースのバックアップまたは復元は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="660ca-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="660ca-141">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="660ca-141">Rtcdyn.</span></span> <span data-ttu-id="660ca-142">このデータベースの一時的なユーザーデータは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="660ca-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="660ca-143">Rtcab</span><span class="sxs-lookup"><span data-stu-id="660ca-143">Rtcab.</span></span> <span data-ttu-id="660ca-144">アドレス帳データベースは、Active Directory ドメインサービスのグローバルアドレス一覧 (GAL) から自動的に再作成されます。</span><span class="sxs-lookup"><span data-stu-id="660ca-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="660ca-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="660ca-145">Rgsdyn.</span></span> <span data-ttu-id="660ca-146">このデータベースの一時的な応答グループサービスデータは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="660ca-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="660ca-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="660ca-147">Cpsdyn.</span></span> <span data-ttu-id="660ca-148">コールパークアプリケーションの動的な情報は、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="660ca-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="660ca-149">・カンプ</span><span class="sxs-lookup"><span data-stu-id="660ca-149">MgcComp.</span></span> <span data-ttu-id="660ca-150">常設チャットのコンプライアンスデータベースは、サービスの復元には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="660ca-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="660ca-151">ファイルストアのバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="660ca-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="660ca-152">次の表を使用して、ファイルストアのバックアップと復元に必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="660ca-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="660ca-153">ファイルストアには、会議コンテンツメタデータ、会議のコンプライアンスログ、デバイス更新プログラムの更新ログ、応答グループ、コールパーク、アナウンスメントアプリケーションのオーディオファイルなどのデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="660ca-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="660ca-154">バックアップと復元に関するファイルストア情報</span><span class="sxs-lookup"><span data-stu-id="660ca-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="660ca-155">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="660ca-155">Content</span></span></th>
<th><span data-ttu-id="660ca-156">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="660ca-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="660ca-157">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="660ca-157">Backup schedule</span></span></th>
<th><span data-ttu-id="660ca-158">ファイルシステムバックアップツール</span><span class="sxs-lookup"><span data-stu-id="660ca-158">File system backup tool</span></span></th>
<th><span data-ttu-id="660ca-159">バックアップするファイル共有 \*</span><span class="sxs-lookup"><span data-stu-id="660ca-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="660ca-160">バックアップ先</span><span class="sxs-lookup"><span data-stu-id="660ca-160">Backup destination</span></span></th>
<th><span data-ttu-id="660ca-161">メモ</span><span class="sxs-lookup"><span data-stu-id="660ca-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="660ca-162">Lync Server ファイルストア</span><span class="sxs-lookup"><span data-stu-id="660ca-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="660ca-163">標準バックアップツール (Robocopy など)</span><span class="sxs-lookup"><span data-stu-id="660ca-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="660ca-164">Enterprise Edition のファイルサーバー。</span><span class="sxs-lookup"><span data-stu-id="660ca-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="660ca-165">Standard edition デプロイメントの場合は、標準エディションでは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="660ca-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="660ca-166">通常、サイトごとに1つ。</span><span class="sxs-lookup"><span data-stu-id="660ca-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="660ca-167">" <strong>Meeting. Active</strong> " という名前のファイルはバックアップしないでください。</span><span class="sxs-lookup"><span data-stu-id="660ca-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="660ca-168">これらのファイルは使用中であり、会議の実行中にロックされます。</span><span class="sxs-lookup"><span data-stu-id="660ca-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="660ca-169">設定のバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="660ca-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="660ca-170">次の表を使用して、設定のバックアップと復元に必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="660ca-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="660ca-171">バックアップと復元の設定情報</span><span class="sxs-lookup"><span data-stu-id="660ca-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="660ca-172">データベース</span><span class="sxs-lookup"><span data-stu-id="660ca-172">Database</span></span></th>
<th><span data-ttu-id="660ca-173">サーバー名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="660ca-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="660ca-174">バックアップスケジュール</span><span class="sxs-lookup"><span data-stu-id="660ca-174">Backup schedule</span></span></th>
<th><span data-ttu-id="660ca-175">バックアップツール</span><span class="sxs-lookup"><span data-stu-id="660ca-175">Backup tool</span></span></th>
<th><span data-ttu-id="660ca-176">構成ファイル (.xml) 名</span><span class="sxs-lookup"><span data-stu-id="660ca-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="660ca-177">バックアップの場所</span><span class="sxs-lookup"><span data-stu-id="660ca-177">Backup location</span></span></th>
<th><span data-ttu-id="660ca-178">メモ</span><span class="sxs-lookup"><span data-stu-id="660ca-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="660ca-179">トポロジ構成用の中央管理ストア内の Xds データベース (グローバル)</span><span class="sxs-lookup"><span data-stu-id="660ca-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="660ca-180"><strong>エクスポート-CsConfiguration</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="660ca-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="660ca-181">E9 の中央管理ストアの Lis データベース (グローバル) の場所情報 (グローバル)</span><span class="sxs-lookup"><span data-stu-id="660ca-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="660ca-182"><strong>CsLisConfiguration</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="660ca-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="660ca-183">応答グループ構成用のバックエンドサーバー上の RgsConfig データベース (プール)</span><span class="sxs-lookup"><span data-stu-id="660ca-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="660ca-184"><strong>Export-CsRgsConfiguration</strong>コマンドレット</span><span class="sxs-lookup"><span data-stu-id="660ca-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

