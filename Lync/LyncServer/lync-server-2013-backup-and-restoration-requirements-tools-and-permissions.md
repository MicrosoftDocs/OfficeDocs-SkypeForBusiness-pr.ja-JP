---
title: 'Lync Server 2013: バックアップと復元の要件: ツールとアクセス許可'
description: 'Lync Server 2013: バックアップと復元の要件: ツールとアクセス許可。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553471"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="77bd5-103">Lync Server 2013 のバックアップと復元の要件: ツールとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="77bd5-103">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77bd5-104">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="77bd5-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="77bd5-105">このトピックでは、Lync Server 2013 のバックアップおよび復元に使用できるツール、必要なアクセス許可、およびリモートまたはローカルでコマンドを実行できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="77bd5-105">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="77bd5-106">具体的には、このトピックでは、バックアップと復元のために Lync Server に用意されているツールを中心に説明します。</span><span class="sxs-lookup"><span data-stu-id="77bd5-106">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="77bd5-107">バックアップ</span><span class="sxs-lookup"><span data-stu-id="77bd5-107">Backups</span></span>

<span data-ttu-id="77bd5-108">Lync Server をバックアップするには、次の表に示されているツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="77bd5-108">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="77bd5-109">Lync Server をバックアップするために必要なすべてのコマンドをスクリプト化して、リモートで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="77bd5-109">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="77bd5-110">Lync Server をバックアップするためのツール</span><span class="sxs-lookup"><span data-stu-id="77bd5-110">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77bd5-111">バックアップ対象:</span><span class="sxs-lookup"><span data-stu-id="77bd5-111">To back up this:</span></span></th>
<th><span data-ttu-id="77bd5-112">使用するツールまたはコマンドレット:</span><span class="sxs-lookup"><span data-stu-id="77bd5-112">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-113">トポロジ構成データ (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="77bd5-113">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-114">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="77bd5-114">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-115">Location Information Service (E9-1-1) データ (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="77bd5-115">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-116">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="77bd5-116">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-117">応答グループ構成データ (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="77bd5-117">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-118">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="77bd5-118">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-119">永続的なユーザーデータ (Rtcxds. .mdf データベース)</span><span class="sxs-lookup"><span data-stu-id="77bd5-119">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="77bd5-120">会議 ID</span><span class="sxs-lookup"><span data-stu-id="77bd5-120">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="77bd5-121">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="77bd5-121">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="77bd5-122">アーカイブ データベース (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="77bd5-122">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="77bd5-123">監視通話詳細記録データベース (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="77bd5-123">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="77bd5-124">監視 QoE データベース (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="77bd5-124">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="77bd5-125">SQL Server Management Studio などの SQL Server データベース ツール</span><span class="sxs-lookup"><span data-stu-id="77bd5-125">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-126">常設チャットデータベース (Mgc)</span><span class="sxs-lookup"><span data-stu-id="77bd5-126">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-127">SQL Server のバックアップ手順または Export-cspersistentchatdata。</span><span class="sxs-lookup"><span data-stu-id="77bd5-127">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="77bd5-128">Export-CsPersistentChatData は、常設チャットデータをファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="77bd5-128">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-129">すべてのファイルストア: Lync Server ファイルストア、アーカイブファイルストア</span><span class="sxs-lookup"><span data-stu-id="77bd5-129">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="77bd5-130"><STRONG>Meeting.Active</STRONG> という名前のファイルはバックアップしないでください。</span><span class="sxs-lookup"><span data-stu-id="77bd5-130">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="77bd5-131">これらのファイルは、会議の開催中に使用されており、ロックされています。</span><span class="sxs-lookup"><span data-stu-id="77bd5-131">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="77bd5-132">標準のファイルシステム管理ツール (Robocopy など)。</span><span class="sxs-lookup"><span data-stu-id="77bd5-132">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="77bd5-133">復元</span><span class="sxs-lookup"><span data-stu-id="77bd5-133">Restoration</span></span>

<span data-ttu-id="77bd5-134">Lync Server を復元するには、次の表のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="77bd5-134">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="77bd5-135">Lync Server を復元するために必要なすべてのコマンドをスクリプト化できます。</span><span class="sxs-lookup"><span data-stu-id="77bd5-135">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="77bd5-136">一部はリモートで実行できますが、次の表で指定されているように、ローカルで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77bd5-136">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="77bd5-137">Lync Server を復元するためのツール</span><span class="sxs-lookup"><span data-stu-id="77bd5-137">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77bd5-138">操作内容:</span><span class="sxs-lookup"><span data-stu-id="77bd5-138">To do this:</span></span></th>
<th><span data-ttu-id="77bd5-139">使用するツールまたはコマンドレット:</span><span class="sxs-lookup"><span data-stu-id="77bd5-139">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-140">新規またはクリーン コンピューターを構築する</span><span class="sxs-lookup"><span data-stu-id="77bd5-140">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="77bd5-141">Windows オペレーティング システム インストール ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="77bd5-141">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="77bd5-142">SQL Server インストール ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="77bd5-142">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="77bd5-143">証明書とエクスポート可能な秘密キーを復元する場合は、Microsoft 管理コンソール (MMC) の証明書スナップイン</span><span class="sxs-lookup"><span data-stu-id="77bd5-143">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-144">ファイル ストア データを復元する</span><span class="sxs-lookup"><span data-stu-id="77bd5-144">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="77bd5-145">標準のファイル システム管理ツール (Robocopy など)</span><span class="sxs-lookup"><span data-stu-id="77bd5-145">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-146">空のデータベースを再作成し、次のアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="77bd5-146">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="77bd5-147">中央管理ストア</span><span class="sxs-lookup"><span data-stu-id="77bd5-147">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="77bd5-148">バック エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="77bd5-148">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="77bd5-149">監視データベース</span><span class="sxs-lookup"><span data-stu-id="77bd5-149">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="77bd5-150">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="77bd5-150">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="77bd5-151">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="77bd5-151">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-152">Active Directory ドメインサービスのポインターを中央管理ストアに復元する</span><span class="sxs-lookup"><span data-stu-id="77bd5-152">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="77bd5-153">サービス接続ポイントを失った場合は、このコマンドレットをいつでも再実行できます。</span><span class="sxs-lookup"><span data-stu-id="77bd5-153">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="77bd5-154">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="77bd5-154">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-155">トポロジ、ポリシー、および構成設定を中央管理ストア (Xds) にインポートします。</span><span class="sxs-lookup"><span data-stu-id="77bd5-155">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-156">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="77bd5-156">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-157">トポロジを公開して有効にする</span><span class="sxs-lookup"><span data-stu-id="77bd5-157">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="77bd5-158">トポロジ ビルダー</span><span class="sxs-lookup"><span data-stu-id="77bd5-158">Topology Builder</span></span></p>
<p><span data-ttu-id="77bd5-159">または</span><span class="sxs-lookup"><span data-stu-id="77bd5-159">-or-</span></span></p>
<p><span data-ttu-id="77bd5-160">Publish-CsTopology と Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="77bd5-160">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-161">最後に公開したトポロジを有効にする</span><span class="sxs-lookup"><span data-stu-id="77bd5-161">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="77bd5-162">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="77bd5-162">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-163">Lync Server コンポーネントを再インストールする</span><span class="sxs-lookup"><span data-stu-id="77bd5-163">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="77bd5-164">Lync Server のセットアップ</span><span class="sxs-lookup"><span data-stu-id="77bd5-164">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="77bd5-165">Lync Server インストールフォルダーまたは \setup\amd64\Setup.exe にあるメディアにあります。</span><span class="sxs-lookup"><span data-stu-id="77bd5-165">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-166">位置情報 (E9-1-1) データ (Lis.mdf) を復元する</span><span class="sxs-lookup"><span data-stu-id="77bd5-166">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-167">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="77bd5-167">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-168">永続的なユーザーデータ (Rtcxds) を復元する</span><span class="sxs-lookup"><span data-stu-id="77bd5-168">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-169">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="77bd5-169">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-170">応答グループ構成データ (RgsConfig.mdf) を復元する</span><span class="sxs-lookup"><span data-stu-id="77bd5-170">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-171">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="77bd5-171">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="77bd5-172">データベースに応答グループデータがない状態で、新たに展開されたプールで構成を復元する場合は、– OverwriteOwner オプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77bd5-172">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="77bd5-173">復元されるデータが同じ完全修飾ドメイン名 (FQDN) を持つプールにある場合でも、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="77bd5-173">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="77bd5-174">それ以外の場合は、Active Directory 内に既に存在している応答グループに連絡先オブジェクトがあるため、インポートに失敗します。</span><span class="sxs-lookup"><span data-stu-id="77bd5-174">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bd5-175">次のデータベースを復元する</span><span class="sxs-lookup"><span data-stu-id="77bd5-175">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="77bd5-176">アーカイブ データベース (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="77bd5-176">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="77bd5-177">監視データベース: 通話詳細記録データベース (LcsCDR.mdf) と QoE データベース (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="77bd5-177">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="77bd5-178">SQL Server データベース管理ツール</span><span class="sxs-lookup"><span data-stu-id="77bd5-178">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bd5-179">常設チャットデータベース (Mgs)</span><span class="sxs-lookup"><span data-stu-id="77bd5-179">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="77bd5-180">SQL Server の復元手順または Export-cspersistentchatdata。</span><span class="sxs-lookup"><span data-stu-id="77bd5-180">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="77bd5-181">Export-cspersistentchatdata によって作成されたファイルと共に Import-CsPersistentChatData を使用して、常設チャットデータベースにデータをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="77bd5-181">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="77bd5-182">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="77bd5-182">Required Permissions</span></span>

<span data-ttu-id="77bd5-183">このトピックで説明されているすべてのコマンドを実行するには、ユーザーは **RTCUniversalServerAdmins** グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="77bd5-183">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="77bd5-184">ほとんどのバックアップおよび復元コマンドは、役割ベースのアクセス制御 (RBAC) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="77bd5-184">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="77bd5-185">2つの例外として、常設チャットコマンドレット Export-CsPersistentChatData と Export-cspersistentchatdata、CsPersistentChatAdministrator グループのメンバーであるユーザーによって実行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="77bd5-185">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="77bd5-186">Lync Server 展開ウィザードを実行するには、ユーザーがローカルの administrators グループのメンバーでもある必要があります。</span><span class="sxs-lookup"><span data-stu-id="77bd5-186">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

