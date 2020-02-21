---
title: 'Lync Server 2013: バックアップと復元の要件: ツールとアクセス許可'
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
ms.openlocfilehash: 900421ed081d5fb8e37fb6b23ddbb80dc85963eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="fd777-102">Lync Server 2013 のバックアップと復元の要件: ツールとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fd777-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd777-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="fd777-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="fd777-104">このトピックでは、Lync Server 2013 のバックアップおよび復元に使用できるツール、必要なアクセス許可、およびリモートまたはローカルでコマンドを実行できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fd777-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="fd777-105">具体的には、このトピックでは、バックアップと復元のために Lync Server に用意されているツールを中心に説明します。</span><span class="sxs-lookup"><span data-stu-id="fd777-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="fd777-106">バックアップ</span><span class="sxs-lookup"><span data-stu-id="fd777-106">Backups</span></span>

<span data-ttu-id="fd777-107">Lync Server をバックアップするには、次の表に示されているツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd777-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="fd777-108">Lync Server をバックアップするために必要なすべてのコマンドをスクリプト化して、リモートで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="fd777-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="fd777-109">Lync Server をバックアップするためのツール</span><span class="sxs-lookup"><span data-stu-id="fd777-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd777-110">バックアップ対象:</span><span class="sxs-lookup"><span data-stu-id="fd777-110">To back up this:</span></span></th>
<th><span data-ttu-id="fd777-111">使用するツールまたはコマンドレット:</span><span class="sxs-lookup"><span data-stu-id="fd777-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd777-112">トポロジ構成データ (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="fd777-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-113">エクスポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd777-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-114">Location Information Service (E9-1-1) データ (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="fd777-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-115">Export-cslisconfiguration</span><span class="sxs-lookup"><span data-stu-id="fd777-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd777-116">応答グループ構成データ (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="fd777-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd777-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-118">永続的なユーザーデータ (Rtcxds. .mdf データベース)</span><span class="sxs-lookup"><span data-stu-id="fd777-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="fd777-119">会議 ID</span><span class="sxs-lookup"><span data-stu-id="fd777-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="fd777-120">エクスポート-CsUserData</span><span class="sxs-lookup"><span data-stu-id="fd777-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="fd777-121">アーカイブ データベース (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="fd777-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fd777-122">監視通話詳細記録データベース (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="fd777-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fd777-123">監視 QoE データベース (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="fd777-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fd777-124">SQL Server Management Studio などの SQL Server データベース ツール</span><span class="sxs-lookup"><span data-stu-id="fd777-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-125">常設チャットデータベース (Mgc)</span><span class="sxs-lookup"><span data-stu-id="fd777-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-126">SQL Server のバックアップ手順または Export-cspersistentchatdata。</span><span class="sxs-lookup"><span data-stu-id="fd777-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="fd777-127">Export-cspersistentchatdata は、常設チャットデータをファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="fd777-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd777-128">すべてのファイルストア: Lync Server ファイルストア、アーカイブファイルストア</span><span class="sxs-lookup"><span data-stu-id="fd777-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fd777-129"><STRONG>Meeting.Active</STRONG> という名前のファイルはバックアップしないでください。</span><span class="sxs-lookup"><span data-stu-id="fd777-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="fd777-130">これらのファイルは、会議の開催中に使用されており、ロックされています。</span><span class="sxs-lookup"><span data-stu-id="fd777-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="fd777-131">標準のファイルシステム管理ツール (Robocopy など)。</span><span class="sxs-lookup"><span data-stu-id="fd777-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="fd777-132">復元</span><span class="sxs-lookup"><span data-stu-id="fd777-132">Restoration</span></span>

<span data-ttu-id="fd777-133">Lync Server を復元するには、次の表のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd777-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="fd777-134">Lync Server を復元するために必要なすべてのコマンドをスクリプト化できます。</span><span class="sxs-lookup"><span data-stu-id="fd777-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="fd777-135">一部はリモートで実行できますが、次の表で指定されているように、ローカルで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd777-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="fd777-136">Lync Server を復元するためのツール</span><span class="sxs-lookup"><span data-stu-id="fd777-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd777-137">操作内容:</span><span class="sxs-lookup"><span data-stu-id="fd777-137">To do this:</span></span></th>
<th><span data-ttu-id="fd777-138">使用するツールまたはコマンドレット:</span><span class="sxs-lookup"><span data-stu-id="fd777-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd777-139">新規またはクリーン コンピューターを構築する</span><span class="sxs-lookup"><span data-stu-id="fd777-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fd777-140">Windows オペレーティング システム インストール ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="fd777-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="fd777-141">SQL Server インストール ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="fd777-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="fd777-142">証明書とエクスポート可能な秘密キーを復元する場合は、Microsoft 管理コンソール (MMC) の証明書スナップイン</span><span class="sxs-lookup"><span data-stu-id="fd777-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-143">ファイル ストア データを復元する</span><span class="sxs-lookup"><span data-stu-id="fd777-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="fd777-144">標準のファイル システム管理ツール (Robocopy など)</span><span class="sxs-lookup"><span data-stu-id="fd777-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd777-145">空のデータベースを再作成し、次のアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="fd777-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd777-146">中央管理ストア</span><span class="sxs-lookup"><span data-stu-id="fd777-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="fd777-147">バック エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="fd777-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="fd777-148">監視データベース</span><span class="sxs-lookup"><span data-stu-id="fd777-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="fd777-149">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="fd777-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fd777-150">-CsDatabase をインストールする</span><span class="sxs-lookup"><span data-stu-id="fd777-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-151">Active Directory ドメインサービスのポインターを中央管理ストアに復元する</span><span class="sxs-lookup"><span data-stu-id="fd777-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fd777-152">サービス接続ポイントを失った場合は、このコマンドレットをいつでも再実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd777-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="fd777-153">Remove-csconfigurationstorelocation</span><span class="sxs-lookup"><span data-stu-id="fd777-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd777-154">トポロジ、ポリシー、および構成設定を中央管理ストア (Xds) にインポートします。</span><span class="sxs-lookup"><span data-stu-id="fd777-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-155">インポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd777-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-156">トポロジを公開して有効にする</span><span class="sxs-lookup"><span data-stu-id="fd777-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="fd777-157">トポロジ ビルダー</span><span class="sxs-lookup"><span data-stu-id="fd777-157">Topology Builder</span></span></p>
<p><span data-ttu-id="fd777-158">または</span><span class="sxs-lookup"><span data-stu-id="fd777-158">-or-</span></span></p>
<p><span data-ttu-id="fd777-159">発行-CsTopology た機能と Enable-CsTopology たテクノロジー</span><span class="sxs-lookup"><span data-stu-id="fd777-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd777-160">最後に公開したトポロジを有効にする</span><span class="sxs-lookup"><span data-stu-id="fd777-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="fd777-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="fd777-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-162">Lync Server コンポーネントを再インストールする</span><span class="sxs-lookup"><span data-stu-id="fd777-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="fd777-163">Lync Server のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fd777-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fd777-164">Lync Server のインストールフォルダーまたは¥にあるメディアにあります。</span><span class="sxs-lookup"><span data-stu-id="fd777-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd777-165">位置情報 (E9-1-1) データ (Lis.mdf) を復元する</span><span class="sxs-lookup"><span data-stu-id="fd777-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-166">Export-cslisconfiguration</span><span class="sxs-lookup"><span data-stu-id="fd777-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-167">永続的なユーザーデータ (Rtcxds) を復元する</span><span class="sxs-lookup"><span data-stu-id="fd777-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-168">インポート-CsUserData</span><span class="sxs-lookup"><span data-stu-id="fd777-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd777-169">応答グループ構成データ (RgsConfig.mdf) を復元する</span><span class="sxs-lookup"><span data-stu-id="fd777-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd777-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fd777-171">データベースに応答グループデータがない状態で、新たに展開されたプールで構成を復元する場合は、– OverwriteOwner オプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd777-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="fd777-172">復元されるデータが同じ完全修飾ドメイン名 (FQDN) を持つプールにある場合でも、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd777-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="fd777-173">それ以外の場合は、Active Directory 内に既に存在している応答グループに連絡先オブジェクトがあるため、インポートに失敗します。</span><span class="sxs-lookup"><span data-stu-id="fd777-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd777-174">次のデータベースを復元する</span><span class="sxs-lookup"><span data-stu-id="fd777-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd777-175">アーカイブ データベース (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="fd777-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fd777-176">監視データベース: 通話詳細記録データベース (LcsCDR.mdf) と QoE データベース (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="fd777-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fd777-177">SQL Server データベース管理ツール</span><span class="sxs-lookup"><span data-stu-id="fd777-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd777-178">常設チャットデータベース (Mgs)</span><span class="sxs-lookup"><span data-stu-id="fd777-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fd777-179">SQL Server の復元手順または Export-cspersistentchatdata。</span><span class="sxs-lookup"><span data-stu-id="fd777-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="fd777-180">Export-cspersistentchatdata を使用して、Export-cspersistentchatdata で作成されたファイルを使用して、データを常設チャットデータベースにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd777-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="fd777-181">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fd777-181">Required Permissions</span></span>

<span data-ttu-id="fd777-182">このトピックで説明されているすべてのコマンドを実行するには、ユーザーは**RTCUniversalServerAdmins**グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd777-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="fd777-183">ほとんどのバックアップおよび復元コマンドは、役割ベースのアクセス制御 (RBAC) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fd777-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="fd777-184">2つの例外として、常設チャットのコマンドレット Export-cspersistentchatdata および Export-cspersistentchatdata があります。これは、CsPersistentChatAdministrator グループのメンバーであるユーザーが実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd777-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="fd777-185">Lync Server 展開ウィザードを実行するには、ユーザーがローカルの administrators グループのメンバーでもある必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd777-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

