---
title: Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '概要: Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を管理する方法について学習します。'
ms.openlocfilehash: 4fb3a38fadf2a8a063715e389718859dcc7ddbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122411"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="69701-103">Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を管理する</span><span class="sxs-lookup"><span data-stu-id="69701-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="69701-104">**概要:** Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="69701-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="69701-105">このトピックでは、常設チャット サーバーをフェールオーバーしてフェールバックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="69701-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="69701-106">このトピックを読む前に [、「Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) での常設チャット サーバーの高可用性と障害復旧の計画」および [「Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)での常設チャット サーバーの高可用性と障害復旧の構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69701-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="69701-107">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="69701-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="69701-108">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="69701-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="69701-109">詳細については、「Microsoft Teams のアップグレードの [開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="69701-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="69701-110">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="69701-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="69701-111">常設チャット サーバーのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="69701-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="69701-112">常設チャット サーバーのフェールオーバーは、主に手動プロセスとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="69701-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="69701-113">フェールオーバー手順は、セカンダリ データ センターが稼働しているという前提に基づいて行いますが、プライマリ常設チャット データベースがある常設チャット サーバー サービスは、次のような完全に使用できません。</span><span class="sxs-lookup"><span data-stu-id="69701-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="69701-114">常設チャット サーバーのプライマリ データベースと常設チャット サーバー ミラー データベースがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="69701-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="69701-115">Skype for Business Server フロントエンド サーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="69701-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="69701-116">操作は 2 つの基本手順に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="69701-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="69701-117">プライマリ 常設チャット データベース (mgc) を回復します。</span><span class="sxs-lookup"><span data-stu-id="69701-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="69701-118">新しいプライマリ データベースのミラーリングを確立する。</span><span class="sxs-lookup"><span data-stu-id="69701-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="69701-119">常設チャット コンプライアンス データベース (mgccomp) はフェールオーバーされません。</span><span class="sxs-lookup"><span data-stu-id="69701-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="69701-120">このデータベースの内容は一時的なものであり、コンプライアンス アダプターがデータを処理するときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="69701-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="69701-121">データ損失を回避するためにアダプターの出力を正しく管理する責任は、常設チャット管理者です。</span><span class="sxs-lookup"><span data-stu-id="69701-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="69701-122">常設チャット サーバーをフェールオーバーするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="69701-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="69701-123">常設チャット サーバー のバックアップ ログ配布データベースからログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="69701-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="69701-124">このSQL Server Management Studioを使用して、常設チャット サーバー のバックアップ mgc データベースがあるデータベース インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="69701-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="69701-125">マスター データベースに対するクエリ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="69701-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="69701-126">次のコマンドを使用して、ログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="69701-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="69701-127">バックアップ共有から、バックアップ サーバーのコピー先フォルダーへ、コピーしていないバックアップ ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="69701-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="69701-128">セカンダリ データベースに、適用していないトランザクション ログ バックアップを順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="69701-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="69701-129">詳細については [、「How to: Apply a Transaction Log Backup (Transact-SQL)」を参照してください](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))。</span><span class="sxs-lookup"><span data-stu-id="69701-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105)).</span></span>
    
4. <span data-ttu-id="69701-p105">バックアップ mgc データベースをオンラインにします。手順 1b. で開いたクエリ ウィンドウを使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="69701-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="69701-132">mgc データベースへのすべての接続を終了します (接続がある場合)。</span><span class="sxs-lookup"><span data-stu-id="69701-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="69701-133">**exec sp_who2** mgc データベースへの接続を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69701-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="69701-134">**kill \<spid\>** をクリックして、これらの接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="69701-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="69701-135">データベースをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="69701-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="69701-136">**復元を使用してデータベース mgc を復元します**。</span><span class="sxs-lookup"><span data-stu-id="69701-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="69701-137">Skype for Business Server 管理シェルで、 **コマンド Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** を使用して、mgc バックアップ データベースにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="69701-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="69701-138">常設チャット プールの完全修飾ドメイン名を、必ずそのドメイン名に置き換 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="69701-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="69701-139">mgc バックアップ データベースがプライマリ データベースとして動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="69701-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="69701-140">Skype for Business Server 管理シェルで **、Install-CsMirrorDatabase** コマンドレットを使用して、プライマリ データベースとして機能するバックアップ データベースの高可用性ミラーを確立します。</span><span class="sxs-lookup"><span data-stu-id="69701-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="69701-141">バックアップ データベース インスタンスをプライマリ データベースとして使用し、バックアップ ミラー データベース インスタンスをミラー インスタンスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="69701-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="69701-142">これは、セットアップ時にプライマリ データベースに対して最初に構成したミラーと同じものではありません。</span><span class="sxs-lookup"><span data-stu-id="69701-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="69701-143">常設チャット サーバーのアクティブ サーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="69701-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="69701-144">Skype for Business Server 管理シェルから **、Set-CsPersistentChatActiveServer** コマンドレットを使用して、アクティブ なサーバーの一覧を設定します。</span><span class="sxs-lookup"><span data-stu-id="69701-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69701-145">すべてのアクティブ サーバーが新しいプライマリ データベースと同じデータ センター内に置かれているか、このデータベースへの接続が低待機時間/高帯域幅であるデータセンター内に置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69701-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="69701-146">この時点で、常設チャット サーバープライマリ データベースから常設チャット サーバー バックアップ データベースへのフェールオーバーが正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="69701-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="69701-147">常設チャット サーバーのフェールバック</span><span class="sxs-lookup"><span data-stu-id="69701-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="69701-148">この手順では、常設チャット サーバーの障害から回復し、プライマリ データ センターから操作を再確立するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="69701-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="69701-149">常設チャット サーバーの障害時にプライマリ データ センターが完全に停止し、プライマリ データベースとミラー データベースが使用できなくなる。</span><span class="sxs-lookup"><span data-stu-id="69701-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="69701-150">プライマリ データ センターはバックアップ サーバーにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="69701-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="69701-151">以下の手順では、プライマリ データ センターがバックアップされ、サーバーが再構築された後、通常の動作を回復します。</span><span class="sxs-lookup"><span data-stu-id="69701-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="69701-152">この手順では、プライマリ データ センターが完全な停止から回復され、トポロジ ビルダーを使用して mgc データベースと mgccomp データベースが再構築および再インストールされたと仮定します。</span><span class="sxs-lookup"><span data-stu-id="69701-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="69701-153">また、この手順では、フェールオーバー期間中に新しいミラー サーバーとバックアップ サーバーが展開されていないと仮定し、展開されたサーバーはバックアップ サーバーとミラー サーバーのみです。これは、前の「フェールオーバー常設チャット サーバー」で定義されています。</span><span class="sxs-lookup"><span data-stu-id="69701-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="69701-154">この手順の意図は、プライマリ サーバーからバックアップ サーバーへのフェールオーバーの原因となった障害が発生する前の状態に構成を復旧することにあります。</span><span class="sxs-lookup"><span data-stu-id="69701-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="69701-155">Skype for Business Server 管理シェルから **Set-CsPersistentChatActiveServer** コマンドレットを使用して、常設チャット サーバーの Active Server リストからすべてのサーバーをクリアします。</span><span class="sxs-lookup"><span data-stu-id="69701-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="69701-156">これにより、フェールバック中に、すべての常設チャット サーバーが mgc データベースと mgccomp データベースに接続しなくるのを停止します。</span><span class="sxs-lookup"><span data-stu-id="69701-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69701-157">セカンダリSQL Server常設チャット サーバーのバック エンド サーバー上の管理者エージェントが特権アカウントで実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69701-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="69701-158">このアカウントには、次のアクセス許可が与えられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69701-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="69701-159">バックアップが置かれるネットワーク共有に対する読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="69701-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="69701-160">バックアップのコピー先となるローカル ディレクトリに対する書き込みアクセス</span><span class="sxs-lookup"><span data-stu-id="69701-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="69701-161">バックアップ mgc データベースでのミラーリングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="69701-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="69701-162">このSQL Server Management Studioを使用して、バックアップ mgc インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="69701-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="69701-163">mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**ミラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69701-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="69701-164">[**ミラーリングの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69701-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="69701-165">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69701-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="69701-166">mgccomp データベースに対しても同じ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="69701-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="69701-167">mgc データベースをバックアップして、新しいプライマリ データベースに復元できるようにします。</span><span class="sxs-lookup"><span data-stu-id="69701-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="69701-168">このSQL Server Management Studioを使用して、バックアップ mgc インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="69701-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="69701-p113">mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**バックアップ**] をクリックします。[**データベースのバックアップ**] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69701-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="69701-171">[**バックアップの種類**] で、[**完全**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69701-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="69701-172">[**バックアップ コンポーネント**] として、[**データベース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69701-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="69701-173">[**名前**] に表示される既定のバックアップ セット名をそのまま使用するか、バックアップ セット名として別の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="69701-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="69701-174">*\<Optional\>*  [ **説明]** に、バックアップ セットの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="69701-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="69701-175">バックアップ先の一覧から既定のバックアップ場所を削除します。</span><span class="sxs-lookup"><span data-stu-id="69701-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="69701-p114">ログ配布用に設定した共有の場所へのパスを使用して、この一覧にファイルを追加します。このパスはプライマリ データベースとバックアップ データベースの両方に使用できます。</span><span class="sxs-lookup"><span data-stu-id="69701-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="69701-178">[**OK**] をクリックします。ダイアログ ボックスが閉じられ、バックアップ プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="69701-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="69701-179">上記のステップで作成されたバックアップ データベースを使用して、プライマリ データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="69701-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="69701-180">このSQL Server Management Studioを使用して、プライマリ mgc インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="69701-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="69701-p115">mgc データベースを右クリックし、[**タスク**]、[**復元**] の順にポイントしてから、[**データベース**] をクリックします。[**データベースの復元**] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69701-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="69701-183">[**復元元デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69701-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="69701-p116">[参照] ボタンをクリックします。[**バックアップの指定**] ダイアログ ボックスが表示されます。[**バックアップ メディア**] で、[**ファイル**] を選択します。[**追加**] をクリックし、ステップ 3. で作成したバックアップ ファイルを選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69701-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="69701-187">[**復元するバックアップ セットの選択**] で、バックアップを選択します。</span><span class="sxs-lookup"><span data-stu-id="69701-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="69701-188">[**ページの選択**] ペインで、[**オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69701-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="69701-189">[**復元オプション**] で、[**既存のデータベースを上書きする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69701-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="69701-190">[**復旧状態**] で、[**データベースを使用可能な状態にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69701-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="69701-191">[**OK**] をクリックします。復元プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="69701-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="69701-192">プライマリ SQL Serverログ配布を構成します。</span><span class="sxs-lookup"><span data-stu-id="69701-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="69701-193">「Configure high availability and disaster recovery for Persistent Chat [Server in Skype for Business Server 2015」](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) の手順に従って、プライマリ mgc データベースのログ配布を確立します。</span><span class="sxs-lookup"><span data-stu-id="69701-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="69701-194">常設チャット サーバーのアクティブ サーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="69701-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="69701-195">Skype for Business Server 管理シェルから **、Set-CsPersistentChatActiveServer** コマンドレットを使用して、アクティブ なサーバーの一覧を設定します。</span><span class="sxs-lookup"><span data-stu-id="69701-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69701-196">すべてのアクティブ サーバーが新しいプライマリ データベースと同じデータ センター内に置かれているか、このデータベースへの接続が低待機時間/高帯域幅であるデータセンター内に置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69701-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="69701-197">プールを通常の状態に復元するには、次のコマンドをWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="69701-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="69701-198">詳細については [、Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69701-198">For more information, see the help topic for the [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
