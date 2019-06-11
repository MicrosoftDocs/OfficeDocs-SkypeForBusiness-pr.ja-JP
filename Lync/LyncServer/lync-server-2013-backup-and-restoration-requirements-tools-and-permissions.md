---
title: 'Lync Server 2013: バックアップと復元の要件: ツールと権限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="cf80f-102">Lync Server 2013 でのバックアップと復元の要件: ツールと権限</span><span class="sxs-lookup"><span data-stu-id="cf80f-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf80f-103">_**最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="cf80f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="cf80f-104">このトピックでは、Lync Server 2013 のバックアップと復元に使用できるツール、必要なアクセス許可、コマンドをリモートまたはローカルで実行できるかどうかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="cf80f-105">具体的には、このトピックでは、Lync Server にバックアップと復元のために提供されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="cf80f-106">バックアップ</span><span class="sxs-lookup"><span data-stu-id="cf80f-106">Backups</span></span>

<span data-ttu-id="cf80f-107">Lync Server をバックアップするには、次の表で示されているツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="cf80f-108">Lync Server のバックアップに必要なすべてのコマンドをスクリプト化して、リモートで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="cf80f-109">Lync Server のバックアップツール</span><span class="sxs-lookup"><span data-stu-id="cf80f-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf80f-110">バックアップするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cf80f-110">To back up this:</span></span></th>
<th><span data-ttu-id="cf80f-111">このツールまたはコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-112">トポロジ構成データ (Xds)</span><span class="sxs-lookup"><span data-stu-id="cf80f-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-113">エクスポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf80f-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-114">位置情報サービス (E9-1) データ (Lis)</span><span class="sxs-lookup"><span data-stu-id="cf80f-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-115">エクスポート-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf80f-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-116">応答グループの構成データ (RgsConfig)</span><span class="sxs-lookup"><span data-stu-id="cf80f-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf80f-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-118">常設ユーザーデータ (Rtcxds データベース)</span><span class="sxs-lookup"><span data-stu-id="cf80f-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="cf80f-119">会議 Id</span><span class="sxs-lookup"><span data-stu-id="cf80f-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="cf80f-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="cf80f-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="cf80f-121">アーカイブデータベース (LcsLog)</span><span class="sxs-lookup"><span data-stu-id="cf80f-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="cf80f-122">通話の詳細レコードデータベース (LcsCDR. mdf) を監視する</span><span class="sxs-lookup"><span data-stu-id="cf80f-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="cf80f-123">QoE データベース (QoEMetrics) の監視</span><span class="sxs-lookup"><span data-stu-id="cf80f-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf80f-124">Sql server Management Studio などの SQL Server データベースツール</span><span class="sxs-lookup"><span data-stu-id="cf80f-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-125">常設チャットデータベース (行う)</span><span class="sxs-lookup"><span data-stu-id="cf80f-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-126">SQL Server のバックアップ手順またはエクスポート-CsPersistentChatData。</span><span class="sxs-lookup"><span data-stu-id="cf80f-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="cf80f-127">エクスポート-CsPersistentChatData は、常設チャットデータをファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="cf80f-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-128">すべてのファイルストア: Lync Server ファイルストア、アーカイブファイルストア</span><span class="sxs-lookup"><span data-stu-id="cf80f-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cf80f-129">" <STRONG>Meeting. Active</STRONG> " という名前のファイルはバックアップしないでください。</span><span class="sxs-lookup"><span data-stu-id="cf80f-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="cf80f-130">これらのファイルは、会議の実行時に使用され、ロックされます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="cf80f-131">標準ファイルシステム管理ツール (Robocopy など)。</span><span class="sxs-lookup"><span data-stu-id="cf80f-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="cf80f-132">回復</span><span class="sxs-lookup"><span data-stu-id="cf80f-132">Restoration</span></span>

<span data-ttu-id="cf80f-133">Lync Server を復元するには、次の表のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="cf80f-134">Lync Server を復元するために必要なすべてのコマンドをスクリプト化することができます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="cf80f-135">一部はリモートで実行できますが、次の表に示すようにローカルで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf80f-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="cf80f-136">Lync Server を復元するためのツール</span><span class="sxs-lookup"><span data-stu-id="cf80f-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf80f-137">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cf80f-137">To do this:</span></span></th>
<th><span data-ttu-id="cf80f-138">このツールまたはコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-139">新しいコンピューターまたはクリーンコンピューターを作成する</span><span class="sxs-lookup"><span data-stu-id="cf80f-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cf80f-140">Windows オペレーティングシステムのインストールソフトウェア</span><span class="sxs-lookup"><span data-stu-id="cf80f-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="cf80f-141">SQL Server インストールソフトウェア</span><span class="sxs-lookup"><span data-stu-id="cf80f-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="cf80f-142">証明書 Microsoft 管理コンソール (MMC) スナップイン (エクスポート可能な秘密キーで証明書を復元する場合)</span><span class="sxs-lookup"><span data-stu-id="cf80f-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-143">ファイルストアデータを復元する</span><span class="sxs-lookup"><span data-stu-id="cf80f-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="cf80f-144">標準ファイルシステム管理ツール (Robocopy など)</span><span class="sxs-lookup"><span data-stu-id="cf80f-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-145">空のデータベースを再作成し、次の権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf80f-146">中央管理ストア</span><span class="sxs-lookup"><span data-stu-id="cf80f-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="cf80f-147">バック エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="cf80f-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="cf80f-148">監視データベース</span><span class="sxs-lookup"><span data-stu-id="cf80f-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="cf80f-149">アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="cf80f-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf80f-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="cf80f-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-151">Active Directory ドメインサービスのポインターを中央管理ストアに復元します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cf80f-152">サービス接続ポイントをいつでも紛失した場合は、このコマンドレットを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="cf80f-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="cf80f-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-154">トポロジ、ポリシー、構成の設定を中央管理ストア (Xds) にインポートする</span><span class="sxs-lookup"><span data-stu-id="cf80f-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-155">インポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf80f-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-156">トポロジを公開して有効にする</span><span class="sxs-lookup"><span data-stu-id="cf80f-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="cf80f-157">トポロジ ビルダー</span><span class="sxs-lookup"><span data-stu-id="cf80f-157">Topology Builder</span></span></p>
<p><span data-ttu-id="cf80f-158">/</span><span class="sxs-lookup"><span data-stu-id="cf80f-158">-or-</span></span></p>
<p><span data-ttu-id="cf80f-159">公開-CsTopology と有効化-CsTopology 機能</span><span class="sxs-lookup"><span data-stu-id="cf80f-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-160">最後に公開されたトポロジを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf80f-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="cf80f-161">有効にする-CsTopology テクノロジー</span><span class="sxs-lookup"><span data-stu-id="cf80f-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-162">Lync Server コンポーネントを再インストールする</span><span class="sxs-lookup"><span data-stu-id="cf80f-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="cf80f-163">Lync Server のセットアップ</span><span class="sxs-lookup"><span data-stu-id="cf80f-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cf80f-164">Lync Server のインストールフォルダーまたは¥の場合は、「¥の場合」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cf80f-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-165">位置情報 (E9-1) データ (Lis) を復元する</span><span class="sxs-lookup"><span data-stu-id="cf80f-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf80f-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-167">永続的なユーザーデータ (Rtcxds) を復元する</span><span class="sxs-lookup"><span data-stu-id="cf80f-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-168">インポート-CsUserData</span><span class="sxs-lookup"><span data-stu-id="cf80f-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-169">応答グループの構成データ (RgsConfig) を復元する</span><span class="sxs-lookup"><span data-stu-id="cf80f-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf80f-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cf80f-171">データベースに応答グループデータがない、新しく展開されたプールで構成を復元する場合は、– OverwriteOwner オプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf80f-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="cf80f-172">復元されるデータが、同じ完全修飾ドメイン名 (FQDN) を持つプールにある場合でも、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="cf80f-173">そうしないと、アクティブディレクトリに既に存在する返信グループに連絡先オブジェクトが存在するため、インポートは成功しません。</span><span class="sxs-lookup"><span data-stu-id="cf80f-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf80f-174">次のデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf80f-175">アーカイブデータベース (LcsLog)</span><span class="sxs-lookup"><span data-stu-id="cf80f-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="cf80f-176">監視データベース: call detail レコードデータベース (LcsCDR mdf) と QoE データベース (QoEMetrics)</span><span class="sxs-lookup"><span data-stu-id="cf80f-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf80f-177">SQL Server データベース管理ツール</span><span class="sxs-lookup"><span data-stu-id="cf80f-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf80f-178">常設チャットデータベース (Mgs)</span><span class="sxs-lookup"><span data-stu-id="cf80f-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="cf80f-179">SQL Server の復元手順またはインポート-CsPersistentChatData。</span><span class="sxs-lookup"><span data-stu-id="cf80f-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="cf80f-180">CsPersistentChatData で作成されたファイルと共に CsPersistentChatData を使用すると、データは永続的なチャットデータベースにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="cf80f-181">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="cf80f-181">Required Permissions</span></span>

<span data-ttu-id="cf80f-182">このトピックで説明されているすべてのコマンドを実行するには、ユーザーが**RTCUniversalServerAdmins** group のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf80f-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="cf80f-183">ほとんどのバックアップと復元コマンドは、役割ベースのアクセス制御 (RBAC) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cf80f-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="cf80f-184">2つの例外は、常設チャットコマンドレットのエクスポート-CsPersistentChatData と CsPersistentChatData を使用することです。これは、CsPersistentChatAdministrator グループのメンバーであるユーザーが実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf80f-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="cf80f-185">Lync Server 展開ウィザードを実行するには、ユーザーはローカルの [電話番号] グループのメンバーでもある必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf80f-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

