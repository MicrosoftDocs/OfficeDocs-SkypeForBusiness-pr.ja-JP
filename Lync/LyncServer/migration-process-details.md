---
title: 移行プロセス-詳細
description: 移行プロセス-詳細。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569583"
---
# <a name="migration-process---details"></a><span data-ttu-id="e7bbb-103">移行プロセス-詳細</span><span class="sxs-lookup"><span data-stu-id="e7bbb-103">Migration process - details</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7bbb-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e7bbb-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e7bbb-105">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーのどちらかを移行するには、次の前提条件と詳細な手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-105">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="e7bbb-106">移行の前提条件</span><span class="sxs-lookup"><span data-stu-id="e7bbb-106">Prerequisites for Migration</span></span>

<span data-ttu-id="e7bbb-107">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーに移行する前に、以下の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-107">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="e7bbb-108">少なくとも1つの Lync Server 2013 プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-108">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="e7bbb-109">複数の Lync Server 2013 プールがある場合は、どの Lync server 2013 プールを新しい Lync Server 2013 常設チャットサーバープールのホームプールにするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-109">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="e7bbb-110">Lync Server 2013、常設チャットサーバープールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-110">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="e7bbb-111">空 (カテゴリ、ルーム、またはアドインはありません) になります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-111">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="e7bbb-112">従来のカテゴリ、ルーム、またはアドインを移行する前に、Lync Server 2013 の常設チャットサーバーの展開で、ルーム、カテゴリ、またはアドインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-112">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7bbb-113">新しく作成されたアイテムが、移行する従来のアイテムと競合する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-113">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="e7bbb-114">名前付けの競合を回避します。そうしないと、従来のデータが移行されるときに上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-114">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="e7bbb-115">移行のためのソースデータの準備</span><span class="sxs-lookup"><span data-stu-id="e7bbb-115">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="e7bbb-116">移行のためにソースデータを適切に準備するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-116">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="e7bbb-117">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットのソースデータベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-117">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="e7bbb-118">SQL Server のバックアップの詳細については、「」の「バックアップの概要 (SQL Server)」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=254851> 。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-118">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7bbb-119">Active Directory ドメインサービスは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-119">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="e7bbb-120">移行の条件として、異なる展開 (特に、別の Active Directory フォレスト) 内のプールに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-120">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="e7bbb-121">Lync Server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャットチャットルームおよびカテゴリ構成を調べます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-121">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="e7bbb-122">既存のレガシ展開で、カテゴリ、ルーム、またはアドインに加えた変更は、グループチャット管理ツールによって行われます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-122">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e7bbb-123">Lync Server 2013 のカテゴリ、ルーム、またはアドインに変更が加えられた場合、常設チャットサーバーの展開は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-123">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="e7bbb-124">従来のシステムを移行用に準備するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-124">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="e7bbb-125">常設チャットサーバーは、カテゴリの深い階層のセットとは異なり、1つのレベルのカテゴリをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-125">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="e7bbb-126">移行後、サブカテゴリには完全な親カテゴリ名のプレフィックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-126">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="e7bbb-127">結果として得られる構造が要件を満たすように、既存のカテゴリ構造を単純化して統合する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-127">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="e7bbb-128">ルートカテゴリの **マネージャー** を確認します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-128">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="e7bbb-129">このレベルでマネージャーが存在する場合、これらのユーザーは移行後 **にすべてのルームに管理者** として追加されます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-129">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="e7bbb-130">組織の要件ではない場合は、これらのマネージャーをルートカテゴリから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-130">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="e7bbb-131">ルーム名の長さを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-131">Verify the length of room names.</span></span> <span data-ttu-id="e7bbb-132">移行後、カテゴリ構造が簡略化されているため、ルームが子カテゴリの下に存在する場合は、完全な親カテゴリ名のプレフィックスが付いています。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-132">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="e7bbb-133">名前付けの制限は、親カテゴリ名を含む256文字です。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-133">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="e7bbb-134">ルーム名の長さを確認し、長すぎる場合は、長さを短くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-134">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="e7bbb-135">Lync Server 2013 で、カテゴリの **招待** の設定が true に設定されている場合は、そのカテゴリの下にあるルームへの招待に true または false を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-135">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="e7bbb-136">ただし、カテゴリの招待の設定が false に設定されている場合は、そのカテゴリの下のルームの招待がオフになります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-136">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="e7bbb-137">移行の前に、特定のカテゴリの下に会議室が存在するようにするには、従来の Lync Server グループチャットサーバーバージョンの招待の設定をリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-137">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="e7bbb-138">それ以外の場合、移行時に Lync Server 2013 は警告を表示し、ルームを既定値の false に設定します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-138">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="e7bbb-139">チャットルームでファイルを使用した場合は、移行後に新しい常設チャットファイルストアに対してファイルを手動で XCOPY する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-139">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="e7bbb-140">このツールは、この操作を行いません。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-140">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="e7bbb-141">フェデレーションユーザーとのフェデレーションユーザーおよびルームがある場合は、常設チャットサーバーがフェデレーションをサポートしていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-141">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="e7bbb-142">フェデレーションユーザーがいるルームは移行されます。ただし、フェデレーションアクセスはサポートされていないため、ユーザー自体はコンテンツにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-142">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="e7bbb-143">移行しないルームを特定し、無効としてマークします。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-143">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="e7bbb-144">チャットルームのコンテンツを移行する日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-144">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="e7bbb-145">たとえば、2010年1月1日より前のメッセージは移行しないようにする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-145">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="e7bbb-146">移行の実行</span><span class="sxs-lookup"><span data-stu-id="e7bbb-146">Performing the Migration</span></span>

<span data-ttu-id="e7bbb-147">従来のグループチャットサーバーを移行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-147">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="e7bbb-148">Lync Server 2010、グループチャット、Office Communications Server 2007 R2 グループチャット、または Lync Server 2013、常設チャットサーバーサービスをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-148">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="e7bbb-149">すべてのサービスを停止する必要があるので、ダウンタイムが十分に発生した場合に限り、この操作を計画してください。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-149">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="e7bbb-150">前述のように、現在のグループチャットデータベースをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-150">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="e7bbb-151">常設チャット管理者の RBAC 役割 (CsPersistentChatAdministrator) のメンバーとして、Windows PowerShell **export-cspersistentchatdata** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-151">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="e7bbb-152">エクスポート/インポートコマンドレットの詳細については、「 [Lync server 2013 で Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-152">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="e7bbb-153">エクスポートされたコンテンツを検査します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-153">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="e7bbb-154">インポートの準備ができたら、Lync Server 2013、常設チャットサーバーサービスをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-154">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="e7bbb-155">すべてのサービスを停止する必要があるので、ダウンタイムが十分に発生した場合には、そのための計画を立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-155">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="e7bbb-156">移行前に、Lync Server 2013 展開でカテゴリ、ルーム、またはアドインを作成した場合は、常設チャットデータベースのバックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-156">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="e7bbb-157">エクスポート/インポートプロセスでは、従来のデータを Lync Server 2013 の展開にマージできますが、コンテンツが誤って上書きされた場合 (たとえば、名前の競合がまだ存在している場合) は、データベースをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-157">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="e7bbb-158">Windows PowerShell Export-cspersistentchatdata コマンドレット (インポートツール) を実行し、 **WhatIf**コマンドを使用して、常設チャットサーバープールのバックエンドサーバーに移行**済み**データを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-158">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="e7bbb-159">簡素化された管理モデルに対応するために、一部の変換がプロセスで行われます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-159">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="e7bbb-160">表示されるエラーまたは警告を修正します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-160">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="e7bbb-161">常設チャットサーバーの Windows PowerShell **export-cspersistentchatdata** コマンドレットを常設チャット管理者の RBAC 役割 (CsPersistentChatAdministrator) のメンバーとして実行します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-161">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="e7bbb-162">エクスポート/インポートコマンドレットの詳細については、「 [Lync server 2013 で Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-162">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="e7bbb-163">アップロードされたすべてのファイル (フォルダー全体) は、新しい Lync Server 2013、常設チャットファイルストアに対して XCOPY する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-163">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7bbb-164">Lync 2013 (クライアント) は、チャットルームでのファイルのアップロードまたは表示をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-164">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="e7bbb-165">従来のクライアントを使用して、ルーム内のファイルを投稿および表示することはできます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-165">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="e7bbb-166">Lync server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャット参照サーバー URI を Lync Server 2013、常設チャットサーバーの連絡先オブジェクトに移植します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-166">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="e7bbb-167">Lync 2010 グループチャットまたは Office Communicator 2007 R2 グループチャットクライアントが、クライアント側の構成を変更せずに、移行後に最新の Lync 2013、常設チャット (クライアント) に接続する必要がある場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-167">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="e7bbb-168">Ocschat@ \<domainName\> .Com 参照サーバーのユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-168">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="e7bbb-169">これは、Lync Server 2010 のグループチャットの参照サービスを指すために使用されました。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-169">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="e7bbb-170">後で、そのプールをアンインストールして、信頼できるエントリを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-170">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="e7bbb-171">従来のエンドポイント (常設チャットサーバーの連絡先オブジェクト) を作成するには、同じ SIP URI を使用して Windows PowerShell コマンドレット **new-cspersistentchatendpoint**を実行します。これにより、サービスの再起動時にレガシクライアントが効果的に動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-171">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="e7bbb-172">この時点で、必須の移行プロセスは完了しています。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-172">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="e7bbb-173">Lync 2010 グループチャット (クライアント) または Office Communicator 2007 R2 グループチャット (クライアント) は、現在、透過的に新しい常設チャットサーバープールに接続できます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-173">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="e7bbb-174">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットの追加の使用停止手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-174">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="e7bbb-175">新しい常設チャットサーバープール内のすべてのコンピューターをオンにして、常設チャットサーバーサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-175">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="e7bbb-176">Lync Server コントロールパネルおよび Windows PowerShell コマンドレットを使用して、データが正常に移行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-176">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="e7bbb-177">グループチャットサーバープールのコンピューターから Lync 2010 グループチャットまたは Office Communicator 2007 R2 グループチャットをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-177">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="e7bbb-178">Windows PowerShell コマンドレットを使用して、信頼されたアプリケーションと信頼されたアプリケーションプールを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-178">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e7bbb-179">これにより、これらのアイテムは中央管理ストアと、関連付けられている信頼済みサービスエントリ (TSEs) から Active Directory から削除されます。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-179">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="e7bbb-180">別の方法として、この手順はトポロジビルダーを使用しても機能します (信頼されたアプリケーション/プールにも専用のノードがあります)。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-180">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="e7bbb-181">これで、新しいクライアントを使用して常設チャットサーバーの機能を有効にすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-181">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="e7bbb-182">常設チャットサーバーの有効化の詳細については、「 [Lync server 2013 での常設チャットサーバーの展開](lync-server-2013-deploying-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-182">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7bbb-183">Lync Server 2013 は、複数の常設チャットサーバープールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-183">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="e7bbb-184">ただし、Lync 2010 グループチャットまたは Office Communications Server 2007 R2 &nbsp; グループチャットプールを1つの Lync server 2013、常設チャットサーバープールに移行することはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-184">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="e7bbb-185">展開に新しい常設チャットサーバープールを追加して、規制要件を満たすようにすることができます (たとえば、特定の地域内のデータを保持する)。</span><span class="sxs-lookup"><span data-stu-id="e7bbb-185">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

