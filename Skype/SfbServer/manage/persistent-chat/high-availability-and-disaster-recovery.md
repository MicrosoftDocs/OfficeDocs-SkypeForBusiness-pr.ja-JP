---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '概要: Skype for Business Server 2015 で永続的なチャットサーバーの高可用性と障害回復を管理する方法について説明します。'
ms.openlocfilehash: 5cf0fc8ba175111a0e0760f4447bd309c34b759c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279306"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="ca525-103">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の管理</span><span class="sxs-lookup"><span data-stu-id="ca525-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ca525-104">**概要:** Skype for Business Server 2015 で永続的なチャットサーバーの高可用性と障害回復を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca525-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ca525-105">このトピックでは、常設チャットサーバをフェイルオーバーしてフェイルバックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca525-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="ca525-106">このトピックを読む前に、「 [skype For Business server 2015 の常設チャットサーバーの高可用性と障害回復の計画」](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)を参照して、 [Skype の常設チャットサーバーの高可用性と障害回復を構成することを確認してください。Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="ca525-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ca525-107">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ca525-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ca525-108">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca525-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="ca525-109">詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca525-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="ca525-110">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ca525-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="ca525-111">常設チャットサーバーのフェイルオーバー</span><span class="sxs-lookup"><span data-stu-id="ca525-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="ca525-112">常設チャットサーバーのフェールオーバーは、主に手動で行うように設計されています。</span><span class="sxs-lookup"><span data-stu-id="ca525-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="ca525-113">フェイルオーバー手順は、セカンダリデータセンターが稼働していることを前提としていますが、プライマリ常設チャットデータベースが配置されている常設チャットサーバーサービスは、次のように完全には使用できません。</span><span class="sxs-lookup"><span data-stu-id="ca525-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="ca525-114">常設チャットサーバーのプライマリデータベースと常設チャットサーバーのミラーデータベースがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="ca525-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="ca525-115">Skype for Business Server フロントエンドサーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="ca525-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="ca525-116">この操作は次の 2 つの基本手順に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ca525-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="ca525-117">プライマリ常設チャットデータベース (行う) を回復します。</span><span class="sxs-lookup"><span data-stu-id="ca525-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="ca525-118">新しいプライマリ データベースのミラーリングを確立する。</span><span class="sxs-lookup"><span data-stu-id="ca525-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="ca525-119">常設チャットのコンプライアンスデータベース (会社間) は、フェールオーバーされません。</span><span class="sxs-lookup"><span data-stu-id="ca525-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="ca525-120">このデータベースの内容は一時的なものであり、コンプライアンス アダプターがデータを処理するときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="ca525-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="ca525-121">データの損失を防ぐために、アダプターの出力を適切に管理することは、常設チャット管理者の責任となります。</span><span class="sxs-lookup"><span data-stu-id="ca525-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="ca525-122">常設チャット サーバーをフェールオーバーさせるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ca525-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="ca525-123">常設チャットサーバーバックアップログ配布データベースからログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="ca525-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="ca525-124">SQL Server Management Studio を使用して、常設チャットサーバーバックアップ行うデータベースが配置されているデータベースインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ca525-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="ca525-125">マスター データベースに対するクエリ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="ca525-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="ca525-126">次のコマンドを使用して、ログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="ca525-126">Use the following command to drop log shipping:</span></span>
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="ca525-127">バックアップ共有から、バックアップ サーバーのコピー先フォルダーへ、コピーしていないバックアップ ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ca525-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="ca525-128">セカンダリ データベースに、適用していないトランザクション ログ バックアップを順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="ca525-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="ca525-129">詳細については、「[トランザクションログバックアップ (transact-sql) を適用する方法](https://go.microsoft.com/fwlink/p/?linkid=247428)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca525-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="ca525-p105">バックアップ mgc データベースをオンラインにします。手順 1b. で開いたクエリ ウィンドウを使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca525-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="ca525-132">mgc データベースへのすべての接続を終了します (接続がある場合)。</span><span class="sxs-lookup"><span data-stu-id="ca525-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="ca525-133">**exec sp_who2** を実行して、mgc データベースへの接続を識別します。</span><span class="sxs-lookup"><span data-stu-id="ca525-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="ca525-134">spid を終了してこれらの接続を終了します。 \*\* \<\> \*\*</span><span class="sxs-lookup"><span data-stu-id="ca525-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="ca525-135">データベースをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="ca525-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="ca525-136">**restore database mgc with recovery** を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca525-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="ca525-137">Skype for Business Server 管理シェルで、コマンド**セット CsPersistentChatState-Identity "service: 001.litwareinc.com"-PoolState FailedOver**を使用して、行う backup データベースにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="ca525-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="ca525-138">atl-cs-001.litwareinc.com の部分には、常設チャット プールの完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca525-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="ca525-139">mgc バックアップ データベースがプライマリ データベースとして動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="ca525-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="ca525-140">Skype for Business Server 管理シェルで、 **CsMirrorDatabase**コマンドレットを使用して、プライマリデータベースとして機能するバックアップデータベースに対して高可用性ミラーを確立します。</span><span class="sxs-lookup"><span data-stu-id="ca525-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="ca525-141">バックアップ データベース インスタンスをプライマリ データベースとして使用し、バックアップ ミラー データベース インスタンスをミラー インスタンスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="ca525-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="ca525-142">これは、セットアップ時にプライマリ データベースに対して最初に構成したミラーと同じものではありません。</span><span class="sxs-lookup"><span data-stu-id="ca525-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="ca525-143">常設チャットサーバーのアクティブなサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ca525-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="ca525-144">Skype for Business Server 管理シェルで、 **CsPersistentChatActiveServer**コマンドレットを使用してアクティブなサーバーの一覧を設定します。</span><span class="sxs-lookup"><span data-stu-id="ca525-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ca525-145">すべてのアクティブ サーバーは、新しいプライマリ データベースと同じデータ センター内、またはデータベースへの接続が低待機時間/高帯域幅であるデータ センター内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca525-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="ca525-146">この時点で、常設チャットサーバーのプライマリデータベースから永続的なチャットサーバーバックアップデータベースへのフェールオーバーが正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="ca525-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="ca525-147">常設チャットサーバーのフェイルバック</span><span class="sxs-lookup"><span data-stu-id="ca525-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="ca525-148">この手順では、常設チャットサーバーの障害から回復するために必要な手順と、プライマリデータセンターからの操作を再確立するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca525-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="ca525-149">常設チャットサーバーの障害時に、プライマリデータセンターには完全な停止が発生し、プライマリデータベースとミラーデータベースは利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ca525-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="ca525-150">プライマリ データ センターはバックアップ サーバーにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="ca525-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="ca525-151">以下の手順では、プライマリ データ センターがバックアップされ、サーバーが再構築された後、通常の動作を回復します。</span><span class="sxs-lookup"><span data-stu-id="ca525-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="ca525-152">この手順では、プライマリデータセンターが全体の停止から回復され、トポロジビルダーを使用して行うデータベースと、使い方が再構築されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ca525-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="ca525-153">また、フェールオーバー期間に新たにミラー サーバーやバックアップ サーバーは展開されていないこと、および前述した「常設チャット サーバーのフェールオーバー」で定義されているように、展開されたサーバーはバックアップ サーバーとそのミラー サーバーだけであることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="ca525-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="ca525-154">この手順の意図は、プライマリ サーバーからバックアップ サーバーへのフェールオーバーの原因となった障害が発生する前の状態に構成を復旧することにあります。</span><span class="sxs-lookup"><span data-stu-id="ca525-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="ca525-155">Skype for Business Server 管理シェルから**CsPersistentChatActiveServer**コマンドレットを使用して、常設チャットサーバーの Active Server リストからすべてのサーバーをクリアします。</span><span class="sxs-lookup"><span data-stu-id="ca525-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ca525-156">これにより、すべての常設チャットサーバーが、フェイルバック中に行うデータベースとデータベースに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ca525-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ca525-157">セカンダリ常設チャットサーバーのバックエンドサーバー上の SQL Server エージェントは、特権を持つアカウントで実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca525-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="ca525-158">このアカウントには、次のアクセス許可が与えられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca525-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="ca525-159">バックアップが置かれるネットワーク共有に対する読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="ca525-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="ca525-160">バックアップのコピー先となるローカル ディレクトリに対する書き込みアクセス</span><span class="sxs-lookup"><span data-stu-id="ca525-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="ca525-161">バックアップ mgc データベースでのミラーリングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ca525-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="ca525-162">SQL Server Management Studio を使用して、backup 行うインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ca525-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="ca525-163">mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**ミラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca525-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="ca525-164">[**ミラーリングの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca525-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="ca525-165">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca525-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="ca525-166">mgccomp データベースに対しても同じ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca525-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="ca525-167">mgc データベースをバックアップして、新しいプライマリ データベースに復元できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ca525-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="ca525-168">SQL Server Management Studio を使用して、backup 行うインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ca525-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="ca525-p113">mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**バックアップ**] をクリックします。[**データベースのバックアップ**] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca525-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="ca525-171">[**バックアップの種類**] で、[**完全**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca525-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="ca525-172">[**バックアップ コンポーネント**] として、[**データベース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca525-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="ca525-173">[**名前**] に表示される既定のバックアップ セット名をそのまま使用するか、バックアップ セット名として別の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca525-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="ca525-174">\* \<オプション\> \* [**説明**] にバックアップセットの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca525-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="ca525-175">バックアップ先の一覧から既定のバックアップ場所を削除します。</span><span class="sxs-lookup"><span data-stu-id="ca525-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="ca525-p114">ログ配布用に設定した共有の場所へのパスを使用して、この一覧にファイルを追加します。このパスはプライマリ データベースとバックアップ データベースの両方に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca525-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="ca525-178">[**OK**] をクリックします。ダイアログ ボックスが閉じられ、バックアップ プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="ca525-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="ca525-179">上記のステップで作成されたバックアップ データベースを使用して、プライマリ データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="ca525-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="ca525-180">SQL Server Management Studio を使用して、プライマリ行うインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ca525-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="ca525-p115">mgc データベースを右クリックし、[**タスク**]、[**復元**] の順にポイントしてから、[**データベース**] をクリックします。[**データベースの復元**] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca525-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="ca525-183">[**復元元デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca525-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="ca525-p116">[参照] ボタンをクリックします。[**バックアップの指定**] ダイアログ ボックスが表示されます。[**バックアップ メディア**] で、[**ファイル**] を選択します。[**追加**] をクリックし、ステップ 3 で作成したバックアップ ファイルを選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca525-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ca525-187">[**復元するバックアップ セットの選択**] で、バックアップを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca525-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="ca525-188">[**ページの選択**] ウィンドウで、[**オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca525-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="ca525-189">[**復元オプション**] で、[**既存のデータベースを上書きする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca525-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="ca525-190">[**復旧状態**] で、[**データベースを使用可能な状態にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca525-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="ca525-191">[**OK**] をクリックします。復元プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="ca525-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="ca525-192">プライマリデータベースの SQL Server ログの配布を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca525-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="ca525-193">「 [Skype For Business server 2015 の常設チャットサーバー用に高可用性と障害回復を構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)する」の手順に従って、プライマリ行うデータベースのログの配布を確立します。</span><span class="sxs-lookup"><span data-stu-id="ca525-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="ca525-194">常設チャットサーバーのアクティブなサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ca525-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="ca525-195">Skype for Business Server 管理シェルで、 **CsPersistentChatActiveServer**コマンドレットを使用してアクティブなサーバーの一覧を設定します。</span><span class="sxs-lookup"><span data-stu-id="ca525-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ca525-196">すべてのアクティブ サーバーは、新しいプライマリ データベースと同じデータ センター内、またはデータベースへの接続が低待機時間/高帯域幅であるデータ センター内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca525-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="ca525-197">プールを通常の状態に復元するには、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca525-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="ca525-198">詳細については、[Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca525-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

