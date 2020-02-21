---
title: 'Lync Server 2013: Lync Server の復元の準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd5875dc7e0dd999a1d94e6e7722eeba07c3a37e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="cd892-102">Lync Server 2013 の復元の準備</span><span class="sxs-lookup"><span data-stu-id="cd892-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd892-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cd892-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cd892-104">障害発生後にサーバーとデータベースの復元を開始する前に、次の点を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd892-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="cd892-105">何を復元する必要があるか。</span><span class="sxs-lookup"><span data-stu-id="cd892-105">What needs to be restored.</span></span>

  - <span data-ttu-id="cd892-106">復元に必要なハードウェア、ソフトウェア、データ、およびツール。</span><span class="sxs-lookup"><span data-stu-id="cd892-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="cd892-107">復元対象の決定</span><span class="sxs-lookup"><span data-stu-id="cd892-107">Determining What to Restore</span></span>

<span data-ttu-id="cd892-108">このトピックでは、サーバー、プール、または中央管理ストアのレベルで発生する Lync Server の停止を復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd892-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="cd892-109">中央管理ストアに障害が発生しても、Lync Server の展開は機能したままですが、構成を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd892-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="cd892-110">バックエンド サーバーまたは Standard Edition サーバーに障害が発生した場合は、ユーザー プールが機能を停止します。</span><span class="sxs-lookup"><span data-stu-id="cd892-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="cd892-111">それ以外のサーバーに障害が発生した場合、障害の程度は、そのサーバーが実行しているサーバーの役割と、サーバーが 1 つ以上のデータベースをホストしているかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="cd892-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="cd892-112">復元の対象</span><span class="sxs-lookup"><span data-stu-id="cd892-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd892-113">障害の発生箇所</span><span class="sxs-lookup"><span data-stu-id="cd892-113">If this failed</span></span></th>
<th><span data-ttu-id="cd892-114">参照先セクション</span><span class="sxs-lookup"><span data-stu-id="cd892-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd892-115">Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="cd892-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="cd892-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Lync Server 2013 での Standard Edition サーバーの復元</a></span><span class="sxs-lookup"><span data-stu-id="cd892-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd892-117">中央管理ストア</span><span class="sxs-lookup"><span data-stu-id="cd892-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="cd892-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Lync Server 2013 で中央管理ストアをホストしているサーバーを復元する</a></span><span class="sxs-lookup"><span data-stu-id="cd892-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd892-119">Enterprise Edition のバックエンド</span><span class="sxs-lookup"><span data-stu-id="cd892-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="cd892-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する</a></span><span class="sxs-lookup"><span data-stu-id="cd892-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd892-121">Enterprise Edition ミラーリングされたバックエンドプライマリサーバー</span><span class="sxs-lookup"><span data-stu-id="cd892-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="cd892-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Lync Server 2013 のミラー化された Enterprise Edition バックエンドサーバーの復元-プライマリ</a></span><span class="sxs-lookup"><span data-stu-id="cd892-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd892-123">Enterprise Edition ミラーリングされたバックエンドセカンダリサーバー</span><span class="sxs-lookup"><span data-stu-id="cd892-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="cd892-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013 のミラー化された Enterprise Edition バックエンドサーバーを復元する</a></span><span class="sxs-lookup"><span data-stu-id="cd892-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd892-125">フロントエンドサーバー、エッジサーバー、ディレクター、仲介サーバー、または常設チャットサーバーなどのサーバーの役割を実行している Enterprise Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="cd892-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="cd892-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync Server 2013 での Enterprise Edition メンバーサーバーの復元</a></span><span class="sxs-lookup"><span data-stu-id="cd892-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd892-127">Lync Server プール全体</span><span class="sxs-lookup"><span data-stu-id="cd892-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="cd892-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Lync server 2013 での Lync Server プールの復元</a></span><span class="sxs-lookup"><span data-stu-id="cd892-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd892-129">Enterprise Edition ファイルストア</span><span class="sxs-lookup"><span data-stu-id="cd892-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="cd892-130"><a href="lync-server-2013-restoring-a-file-store.md">Lync Server 2013 でのファイルストアの復元</a></span><span class="sxs-lookup"><span data-stu-id="cd892-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd892-131">スタンドアロンの監視データベースまたはアーカイブデータベース</span><span class="sxs-lookup"><span data-stu-id="cd892-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="cd892-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Lync Server 2013 での監視またはアーカイブデータの復元</a></span><span class="sxs-lookup"><span data-stu-id="cd892-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd892-133">スタンドアロンの常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="cd892-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="cd892-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Lync Server 2013 での常設チャットデータの復元</a></span><span class="sxs-lookup"><span data-stu-id="cd892-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="cd892-135">ハードウェア、ソフトウェア、およびツールの収集</span><span class="sxs-lookup"><span data-stu-id="cd892-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="cd892-136">サーバーを復元する際には、新しいコンピューターまたはクリーン コンピューターを使用して作業を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd892-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="cd892-137">さらに、次のハードウェアとソフトウェアを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd892-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="cd892-138">障害が発生したサーバーと同じ完全修飾ドメイン名 (FQDN) を持つクリーン サーバーまたは新しいサーバー。</span><span class="sxs-lookup"><span data-stu-id="cd892-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd892-139">オペレーティングシステムをインストールするときは、Active Directory ドメインサービスのコンピューターアカウントを削除しないようにし、アカウントのグループのアクセス許可が保持されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cd892-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="cd892-140">オペレーティング システムのインストール ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="cd892-140">Installation software for the operating system.</span></span> <span data-ttu-id="cd892-141">オペレーティング システムをインストールするには、組織で制定された、サーバーの展開手順と構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd892-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="cd892-142">サービスを復元するときには、これらの手順と構成要件を利用できます。</span><span class="sxs-lookup"><span data-stu-id="cd892-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="cd892-143">SQL Server 2012 または SQL Server 2008 R2 のインストールソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="cd892-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="cd892-144">データベース サーバーをインストールするには、組織で制定された、適切なバージョンの SQL Server およびデータベース サーバーの展開手順と構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd892-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="cd892-145">サービスを復元するときには、これらの手順と構成要件を利用できます。</span><span class="sxs-lookup"><span data-stu-id="cd892-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd892-146">SQL server 2012 または SQL Server 2008 R2 がインストールされていない場合、Lync Server Deployment ウィザードは、各 Standard Edition サーバーおよびその他の Lync Server サーバーに SQL Server 2012 Express を自動的にインストールします。サーバー。</span><span class="sxs-lookup"><span data-stu-id="cd892-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="cd892-147">システム イメージを作成するためのソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="cd892-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="cd892-148">オペレーティングシステムと SQL Server をインストールした後、復元を開始する前に、システムのイメージコピーを取得することをお勧めします。これにより、復元中に問題が発生した場合にこのイメージをロールバックポイントとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cd892-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="cd892-149">Lync Server 2013 インストールソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="cd892-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="cd892-150">Lync Server 展開ウィザードは、Lync Server のインストールフォルダーまたは\\セットアップ\\の amd64\\セットアップのメディアにあります。</span><span class="sxs-lookup"><span data-stu-id="cd892-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="cd892-151">復元時には、次のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd892-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="cd892-152">Lync Server 管理シェルのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="cd892-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="cd892-153">インポート-CsUserData</span><span class="sxs-lookup"><span data-stu-id="cd892-153">Import-CsUserData</span></span>

  - <span data-ttu-id="cd892-154">Windows フォルダーを復元するためのツール</span><span class="sxs-lookup"><span data-stu-id="cd892-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="cd892-155">トポロジ ビルダー</span><span class="sxs-lookup"><span data-stu-id="cd892-155">Topology Builder</span></span>

  - <span data-ttu-id="cd892-156">SQL Server データベース ユーティリティ (SQL Server Management Studio など)</span><span class="sxs-lookup"><span data-stu-id="cd892-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="cd892-157">サーバーを復元する準備</span><span class="sxs-lookup"><span data-stu-id="cd892-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="cd892-158">サーバーを復元する前に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd892-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="cd892-159">オペレーティング システムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cd892-159">Install the operating system.</span></span>

2.  <span data-ttu-id="cd892-160">サーバーがバックエンドサーバーの場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cd892-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="cd892-161">証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="cd892-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="cd892-162">証明書の詳細については、「 [Lync Server 2013: data」の「バックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)」の「追加のバックアップ要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd892-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="cd892-163">復元中に問題が発生した場合に備えて、復元を開始する前にシステムのイメージを取得して、ロールバックポイントとして使用します。</span><span class="sxs-lookup"><span data-stu-id="cd892-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd892-164">このトピックの手順で説明されている Lync Server 展開ウィザードとコマンドレット、および関連するトピックで、必要なアクセス制御リスト (Acl) をすべて設定します。</span><span class="sxs-lookup"><span data-stu-id="cd892-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="cd892-165">復元を開始する前に、復元するコンポーネントに必要なハードウェアとソフトウェアが利用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cd892-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="cd892-166">オペレーティング システムと SQL Server のインストール後は、以降の復元手順のほとんどのステップをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="cd892-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="cd892-167">その例外については、手順内で説明します。</span><span class="sxs-lookup"><span data-stu-id="cd892-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="cd892-168">また、復元を開始する前に、組織のバックアップと復元の計画と、最新のバックアップからの情報 (詳細については「 [Lync Server 2013 のバックアップと復元のワークシート](lync-server-2013-backup-and-restoration-worksheets.md)」を参照してください) を入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd892-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

