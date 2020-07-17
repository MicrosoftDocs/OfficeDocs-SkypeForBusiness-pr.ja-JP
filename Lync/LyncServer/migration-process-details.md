---
title: 移行プロセス-詳細
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
ms.openlocfilehash: 76624475b86427d8e3b1aa4f9efa75c127afcb85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="f1157-102">移行プロセス-詳細</span><span class="sxs-lookup"><span data-stu-id="f1157-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1157-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f1157-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f1157-104">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーのどちらかを移行するには、次の前提条件と詳細な手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1157-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="f1157-105">移行の前提条件</span><span class="sxs-lookup"><span data-stu-id="f1157-105">Prerequisites for Migration</span></span>

<span data-ttu-id="f1157-106">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーに移行する前に、以下の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1157-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="f1157-107">少なくとも1つの Lync Server 2013 プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="f1157-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="f1157-108">複数の Lync Server 2013 プールがある場合は、どの Lync server 2013 プールを新しい Lync Server 2013 常設チャットサーバープールのホームプールにするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f1157-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="f1157-109">Lync Server 2013、常設チャットサーバープールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f1157-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="f1157-110">空 (カテゴリ、ルーム、またはアドインはありません) になります。</span><span class="sxs-lookup"><span data-stu-id="f1157-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="f1157-111">従来のカテゴリ、ルーム、またはアドインを移行する前に、Lync Server 2013 の常設チャットサーバーの展開で、ルーム、カテゴリ、またはアドインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f1157-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f1157-112">新しく作成されたアイテムが、移行する従来のアイテムと競合する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f1157-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="f1157-113">名前付けの競合を回避します。そうしないと、従来のデータが移行されるときに上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f1157-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="f1157-114">移行のためのソースデータの準備</span><span class="sxs-lookup"><span data-stu-id="f1157-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="f1157-115">移行のためにソースデータを適切に準備するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1157-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="f1157-116">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットのソースデータベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="f1157-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="f1157-117">SQL Server のバックアップの詳細については、「」の「バックアップの概要 (SQL Server)」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=254851> 。</span><span class="sxs-lookup"><span data-stu-id="f1157-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f1157-118">Active Directory ドメインサービスは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="f1157-119">移行の条件として、異なる展開 (特に、別の Active Directory フォレスト) 内のプールに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="f1157-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="f1157-120">Lync Server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャットチャットルームおよびカテゴリ構成を調べます。</span><span class="sxs-lookup"><span data-stu-id="f1157-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="f1157-121">既存のレガシ展開で、カテゴリ、ルーム、またはアドインに加えた変更は、グループチャット管理ツールによって行われます。</span><span class="sxs-lookup"><span data-stu-id="f1157-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f1157-122">Lync Server 2013 のカテゴリ、ルーム、またはアドインに変更が加えられた場合、常設チャットサーバーの展開は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="f1157-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="f1157-123">従来のシステムを移行用に準備するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1157-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="f1157-124">常設チャットサーバーは、カテゴリの深い階層のセットとは異なり、1つのレベルのカテゴリをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f1157-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="f1157-125">移行後、サブカテゴリには完全な親カテゴリ名のプレフィックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="f1157-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="f1157-126">結果として得られる構造が要件を満たすように、既存のカテゴリ構造を単純化して統合する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="f1157-127">ルートカテゴリの**マネージャー**を確認します。</span><span class="sxs-lookup"><span data-stu-id="f1157-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="f1157-128">このレベルでマネージャーが存在する場合、これらのユーザーは移行後**にすべてのルームに管理者**として追加されます。</span><span class="sxs-lookup"><span data-stu-id="f1157-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="f1157-129">組織の要件ではない場合は、これらのマネージャーをルートカテゴリから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="f1157-130">ルーム名の長さを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1157-130">Verify the length of room names.</span></span> <span data-ttu-id="f1157-131">移行後、カテゴリ構造が簡略化されているため、ルームが子カテゴリの下に存在する場合は、完全な親カテゴリ名のプレフィックスが付いています。</span><span class="sxs-lookup"><span data-stu-id="f1157-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="f1157-132">名前付けの制限は、親カテゴリ名を含む256文字です。</span><span class="sxs-lookup"><span data-stu-id="f1157-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="f1157-133">ルーム名の長さを確認し、長すぎる場合は、長さを短くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="f1157-134">Lync Server 2013 で、カテゴリの**招待**の設定が true に設定されている場合は、そのカテゴリの下にあるルームへの招待に true または false を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f1157-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="f1157-135">ただし、カテゴリの招待の設定が false に設定されている場合は、そのカテゴリの下のルームの招待がオフになります。</span><span class="sxs-lookup"><span data-stu-id="f1157-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="f1157-136">移行の前に、特定のカテゴリの下に会議室が存在するようにするには、従来の Lync Server グループチャットサーバーバージョンの招待の設定をリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="f1157-137">それ以外の場合、移行時に Lync Server 2013 は警告を表示し、ルームを既定値の false に設定します。</span><span class="sxs-lookup"><span data-stu-id="f1157-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="f1157-138">チャットルームでファイルを使用した場合は、移行後に新しい常設チャットファイルストアに対してファイルを手動で XCOPY する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="f1157-139">このツールは、この操作を行いません。</span><span class="sxs-lookup"><span data-stu-id="f1157-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="f1157-140">フェデレーションユーザーとのフェデレーションユーザーおよびルームがある場合は、常設チャットサーバーがフェデレーションをサポートしていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f1157-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="f1157-141">フェデレーションユーザーがいるルームは移行されます。ただし、フェデレーションアクセスはサポートされていないため、ユーザー自体はコンテンツにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="f1157-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="f1157-142">移行しないルームを特定し、無効としてマークします。</span><span class="sxs-lookup"><span data-stu-id="f1157-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="f1157-143">チャットルームのコンテンツを移行する日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1157-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="f1157-144">たとえば、2010年1月1日より前のメッセージは移行しないようにする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="f1157-145">移行の実行</span><span class="sxs-lookup"><span data-stu-id="f1157-145">Performing the Migration</span></span>

<span data-ttu-id="f1157-146">従来のグループチャットサーバーを移行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1157-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="f1157-147">Lync Server 2010、グループチャット、Office Communications Server 2007 R2 グループチャット、または Lync Server 2013、常設チャットサーバーサービスをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="f1157-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="f1157-148">すべてのサービスを停止する必要があるので、ダウンタイムが十分に発生した場合に限り、この操作を計画してください。</span><span class="sxs-lookup"><span data-stu-id="f1157-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="f1157-149">前述のように、現在のグループチャットデータベースをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f1157-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="f1157-150">常設チャット管理者の RBAC 役割 (CsPersistentChatAdministrator) のメンバーとして、Windows PowerShell **export-cspersistentchatdata**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1157-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="f1157-151">エクスポート/インポートコマンドレットの詳細については、「 [Lync server 2013 で Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1157-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="f1157-152">エクスポートされたコンテンツを検査します。</span><span class="sxs-lookup"><span data-stu-id="f1157-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="f1157-153">インポートの準備ができたら、Lync Server 2013、常設チャットサーバーサービスをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="f1157-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="f1157-154">すべてのサービスを停止する必要があるので、ダウンタイムが十分に発生した場合には、そのための計画を立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="f1157-155">移行前に、Lync Server 2013 展開でカテゴリ、ルーム、またはアドインを作成した場合は、常設チャットデータベースのバックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1157-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="f1157-156">エクスポート/インポートプロセスでは、従来のデータを Lync Server 2013 の展開にマージできますが、コンテンツが誤って上書きされた場合 (たとえば、名前の競合がまだ存在している場合) は、データベースをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="f1157-157">Windows PowerShell Export-cspersistentchatdata コマンドレット (インポートツール) を実行し、 **WhatIf**コマンドを使用して、常設チャットサーバープールのバックエンドサーバーに移行**済み**データを設定します。</span><span class="sxs-lookup"><span data-stu-id="f1157-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="f1157-158">簡素化された管理モデルに対応するために、一部の変換がプロセスで行われます。</span><span class="sxs-lookup"><span data-stu-id="f1157-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="f1157-159">表示されるエラーまたは警告を修正します。</span><span class="sxs-lookup"><span data-stu-id="f1157-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="f1157-160">常設チャットサーバーの Windows PowerShell **export-cspersistentchatdata**コマンドレットを常設チャット管理者の RBAC 役割 (CsPersistentChatAdministrator) のメンバーとして実行します。</span><span class="sxs-lookup"><span data-stu-id="f1157-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="f1157-161">エクスポート/インポートコマンドレットの詳細については、「 [Lync server 2013 で Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1157-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="f1157-162">アップロードされたすべてのファイル (フォルダー全体) は、新しい Lync Server 2013、常設チャットファイルストアに対して XCOPY する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f1157-163">Lync 2013 (クライアント) は、チャットルームでのファイルのアップロードまたは表示をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f1157-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="f1157-164">従来のクライアントを使用して、ルーム内のファイルを投稿および表示することはできます。</span><span class="sxs-lookup"><span data-stu-id="f1157-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="f1157-165">Lync server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャット参照サーバー URI を Lync Server 2013、常設チャットサーバーの連絡先オブジェクトに移植します。</span><span class="sxs-lookup"><span data-stu-id="f1157-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="f1157-166">Lync 2010 グループチャットまたは Office Communicator 2007 R2 グループチャットクライアントが、クライアント側の構成を変更せずに、移行後に最新の Lync 2013、常設チャット (クライアント) に接続する必要がある場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1157-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="f1157-167">Ocschat@ \<domainName\> .Com 参照サーバーのユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="f1157-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="f1157-168">これは、Lync Server 2010 のグループチャットの参照サービスを指すために使用されました。</span><span class="sxs-lookup"><span data-stu-id="f1157-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="f1157-169">後で、そのプールをアンインストールして、信頼できるエントリを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f1157-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="f1157-170">従来のエンドポイント (常設チャットサーバーの連絡先オブジェクト) を作成するには、同じ SIP URI を使用して Windows PowerShell コマンドレット**new-cspersistentchatendpoint**を実行します。これにより、サービスの再起動時にレガシクライアントが効果的に動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="f1157-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="f1157-171">この時点で、必須の移行プロセスは完了しています。</span><span class="sxs-lookup"><span data-stu-id="f1157-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="f1157-172">Lync 2010 グループチャット (クライアント) または Office Communicator 2007 R2 グループチャット (クライアント) は、現在、透過的に新しい常設チャットサーバープールに接続できます。</span><span class="sxs-lookup"><span data-stu-id="f1157-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="f1157-173">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットの追加の使用停止手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f1157-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="f1157-174">新しい常設チャットサーバープール内のすべてのコンピューターをオンにして、常設チャットサーバーサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f1157-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="f1157-175">Lync Server コントロールパネルおよび Windows PowerShell コマンドレットを使用して、データが正常に移行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1157-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="f1157-176">グループチャットサーバープールのコンピューターから Lync 2010 グループチャットまたは Office Communicator 2007 R2 グループチャットをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f1157-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="f1157-177">Windows PowerShell コマンドレットを使用して、信頼されたアプリケーションと信頼されたアプリケーションプールを削除します。</span><span class="sxs-lookup"><span data-stu-id="f1157-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="f1157-178">これにより、これらのアイテムは中央管理ストアと、関連付けられている信頼済みサービスエントリ (TSEs) から Active Directory から削除されます。</span><span class="sxs-lookup"><span data-stu-id="f1157-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="f1157-179">別の方法として、この手順はトポロジビルダーを使用しても機能します (信頼されたアプリケーション/プールにも専用のノードがあります)。</span><span class="sxs-lookup"><span data-stu-id="f1157-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="f1157-180">これで、新しいクライアントを使用して常設チャットサーバーの機能を有効にすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="f1157-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="f1157-181">常設チャットサーバーの有効化の詳細については、「 [Lync server 2013 での常設チャットサーバーの展開](lync-server-2013-deploying-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1157-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f1157-182">Lync Server 2013 は、複数の常設チャットサーバープールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f1157-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="f1157-183">ただし、Lync 2010 グループチャットまたは Office Communications Server 2007 R2 &nbsp; グループチャットプールを1つの Lync server 2013、常設チャットサーバープールに移行することはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f1157-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="f1157-184">展開に新しい常設チャットサーバープールを追加して、規制要件を満たすようにすることができます (たとえば、特定の地域内のデータを保持する)。</span><span class="sxs-lookup"><span data-stu-id="f1157-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

