---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '概要: ビジネス サーバー 2015 の永続的なチャット サーバーの高可用性と Skype では障害回復を管理する方法を説明します。'
ms.openlocfilehash: 8e2b9cecef2a3598c318ab8a758c99eb2caf40e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910348"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="511aa-103">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の管理</span><span class="sxs-lookup"><span data-stu-id="511aa-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="511aa-104">**の概要:** ビジネス サーバー 2015 の永続的なチャット サーバーの高可用性と Skype では障害回復を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="511aa-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="511aa-105">このトピックでは、フェイル オーバーとフェイル バックに永続的なチャット サーバーにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="511aa-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="511aa-106">このトピックを読む前にするの Skype での永続的なチャット サーバーの[高可用性とビジネス サーバー 2015 の Skype での永続的なチャット サーバーの障害回復の計画](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)し[の構成の高可用性および災害復旧を参照してください。ビジネス サーバー 2015年](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="511aa-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="511aa-107">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="511aa-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="511aa-108">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="511aa-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="511aa-109">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="511aa-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="511aa-110">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="511aa-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="511aa-111">永続的なチャット サーバー上で失敗します。</span><span class="sxs-lookup"><span data-stu-id="511aa-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="511aa-112">永続的なチャット サーバーのフェイル オーバーは手動のプロセスでは主に設計されています。</span><span class="sxs-lookup"><span data-stu-id="511aa-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="511aa-113">フェイル オーバー手順をセカンダリ ・ データ ・ センターであることを前提に基づいており、実行中、ですが、プライマリの永続的なチャットのデータベースが格納されている永続的なチャット サーバー サービスは、完全に利用可能な次に示す。</span><span class="sxs-lookup"><span data-stu-id="511aa-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="511aa-114">永続的なチャット サーバーのプライマリ データベースとミラー データベースの永続的なチャット サーバー ダウンしています。</span><span class="sxs-lookup"><span data-stu-id="511aa-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="511aa-115">Skype のビジネス サーバーのフロント エンド サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="511aa-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="511aa-116">この操作は次の 2 つの基本手順に基づいています。</span><span class="sxs-lookup"><span data-stu-id="511aa-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="511aa-117">永続的なチャット プライマリ データベース (mgc) をリカバリします。</span><span class="sxs-lookup"><span data-stu-id="511aa-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="511aa-118">新しいプライマリ データベースのミラーリングを確立する。</span><span class="sxs-lookup"><span data-stu-id="511aa-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="511aa-119">永続的なチャット コンプライアンス データベース (mgccomp) はフェイル オーバーしません。</span><span class="sxs-lookup"><span data-stu-id="511aa-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="511aa-120">このデータベースの内容は一時的なものであり、コンプライアンス アダプターがデータを処理するときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="511aa-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="511aa-121">永続的なチャット管理者は、データの損失を避けるためにアダプターの出力を正しく管理するために、あなたの責任です。</span><span class="sxs-lookup"><span data-stu-id="511aa-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="511aa-122">常設チャット サーバーをフェールオーバーさせるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="511aa-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="511aa-123">永続的なチャット サーバーのバックアップ ログ配布のデータベースからログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="511aa-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="511aa-124">SQL Server Management Studio を使用すると、永続的なチャット サーバーのバックアップ mgc データベースが格納されているデータベース ・ インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="511aa-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="511aa-125">マスター データベースに対するクエリ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="511aa-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="511aa-126">次のコマンドを使用して、ログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="511aa-126">Use the following command to drop log shipping:</span></span>
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="511aa-127">バックアップ共有から、バックアップ サーバーのコピー先フォルダーへ、コピーしていないバックアップ ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="511aa-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="511aa-128">セカンダリ データベースに、適用していないトランザクション ログ バックアップを順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="511aa-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="511aa-129">詳細についてを参照してください[する方法: トランザクション ログのバックアップ (Transact SQL) を適用する](https://go.microsoft.com/fwlink/p/?linkid=247428)です。</span><span class="sxs-lookup"><span data-stu-id="511aa-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="511aa-p105">バックアップ mgc データベースをオンラインにします。手順 1b. で開いたクエリ ウィンドウを使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="511aa-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="511aa-132">mgc データベースへのすべての接続を終了します (接続がある場合)。</span><span class="sxs-lookup"><span data-stu-id="511aa-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="511aa-133">**exec sp_who2** を実行して、mgc データベースへの接続を識別します。</span><span class="sxs-lookup"><span data-stu-id="511aa-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="511aa-134">**kill \<spid\>** をこれらの接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="511aa-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="511aa-135">データベースをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="511aa-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="511aa-136">**restore database mgc with recovery** を実行します。</span><span class="sxs-lookup"><span data-stu-id="511aa-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="511aa-137">ビジネス サーバー管理シェルの Skype は、コマンドを使用して**セット CsPersistentChatState-アイデンティティ」サービス: atl の cs-001.litwareinc.com"- PoolState FailedOver** mgc バックアップ データベースにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="511aa-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="511aa-138">atl-cs-001.litwareinc.com の部分には、常設チャット プールの完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="511aa-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="511aa-139">mgc バックアップ データベースがプライマリ データベースとして動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="511aa-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="511aa-140">ビジネス サーバー管理シェルの Skype では、プライマリ データベースとして使用するデータベースのバックアップを高可用性のミラーを確立するために**インストール CsMirrorDatabase**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="511aa-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="511aa-141">バックアップ データベース インスタンスをプライマリ データベースとして使用し、バックアップ ミラー データベース インスタンスをミラー インスタンスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="511aa-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="511aa-142">これは、セットアップ時にプライマリ データベースに対して最初に構成したミラーと同じものではありません。</span><span class="sxs-lookup"><span data-stu-id="511aa-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="511aa-143">永続的なチャット サーバーのアクティブなサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="511aa-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="511aa-144">ビジネス サーバー管理シェルの Skype からには、アクティブなサーバーの一覧を設定するのには、**セット CsPersistentChatActiveServer**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="511aa-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="511aa-145">すべてのアクティブ サーバーは、新しいプライマリ データベースと同じデータ センター内、またはデータベースへの接続が低待機時間/高帯域幅であるデータ センター内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="511aa-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="511aa-146">この時点では、永続的なチャット サーバーのプライマリ データベースから永続的なチャット サーバーのバックアップ データベースへのフェールオーバーが正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="511aa-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="511aa-147">戻る永続的なチャット サーバーが失敗します。</span><span class="sxs-lookup"><span data-stu-id="511aa-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="511aa-148">この手順では、永続的なチャット サーバー障害から回復して、プライマリ ・ データ ・ センターから操作を再確立するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="511aa-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="511aa-149">永続的なチャット サーバーの障害発生時にプライマリ ・ データ ・ センターの低下、完全なシステム停止となり、プライマリおよびミラー データベースが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="511aa-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="511aa-150">プライマリ データ センターはバックアップ サーバーにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="511aa-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="511aa-151">以下の手順では、プライマリ データ センターがバックアップされ、サーバーが再構築された後、通常の動作を回復します。</span><span class="sxs-lookup"><span data-stu-id="511aa-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="511aa-152">プロシージャは、プライマリ ・ データ ・ センターが総停止から回復されたことと、mgc データベースと mgccomp データベースが再構築されトポロジ ビルダーを使用して再インストールを想定しています。</span><span class="sxs-lookup"><span data-stu-id="511aa-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="511aa-153">また、フェールオーバー期間に新たにミラー サーバーやバックアップ サーバーは展開されていないこと、および前述した「常設チャット サーバーのフェールオーバー」で定義されているように、展開されたサーバーはバックアップ サーバーとそのミラー サーバーだけであることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="511aa-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="511aa-154">この手順の意図は、プライマリ サーバーからバックアップ サーバーへのフェールオーバーの原因となった障害が発生する前の状態に構成を復旧することにあります。</span><span class="sxs-lookup"><span data-stu-id="511aa-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="511aa-155">ビジネス サーバー管理シェルには、Skype から**セット CsPersistentChatActiveServer**コマンドレットを使用して永続的なチャット アクティブ サーバー] ボックスの一覧からすべてのサーバーをオフにします。</span><span class="sxs-lookup"><span data-stu-id="511aa-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="511aa-156">これは、永続的なチャットからすべてのサーバーのフェイル バック中 mgc データベースと mgccomp データベースへの接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="511aa-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="511aa-157">セカンダリ上の SQL Server エージェント権限を持つアカウントで、永続的なチャット サーバー バック エンド サーバーを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="511aa-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="511aa-158">このアカウントには、次のアクセス許可が与えられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="511aa-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="511aa-159">バックアップが置かれるネットワーク共有に対する読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="511aa-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="511aa-160">バックアップのコピー先となるローカル ディレクトリに対する書き込みアクセス</span><span class="sxs-lookup"><span data-stu-id="511aa-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="511aa-161">バックアップ mgc データベースでのミラーリングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="511aa-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="511aa-162">SQL Server Management Studio を使用すると、バックアップの mgc のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="511aa-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="511aa-163">mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**ミラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="511aa-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="511aa-164">[**ミラーリングの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="511aa-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="511aa-165">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="511aa-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="511aa-166">mgccomp データベースに対しても同じ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="511aa-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="511aa-167">mgc データベースをバックアップして、新しいプライマリ データベースに復元できるようにします。</span><span class="sxs-lookup"><span data-stu-id="511aa-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="511aa-168">SQL Server Management Studio を使用すると、バックアップの mgc のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="511aa-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="511aa-p113">mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**バックアップ**] をクリックします。[**データベースのバックアップ**] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="511aa-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="511aa-171">[**バックアップの種類**] で、[**完全**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="511aa-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="511aa-172">[**バックアップ コンポーネント**] として、[**データベース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="511aa-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="511aa-173">[**名前**] に表示される既定のバックアップ セット名をそのまま使用するか、バックアップ セット名として別の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="511aa-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="511aa-174">*\<オプション\>* [**説明**] にバックアップ セットの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="511aa-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="511aa-175">バックアップ先の一覧から既定のバックアップ場所を削除します。</span><span class="sxs-lookup"><span data-stu-id="511aa-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="511aa-p114">ログ配布用に設定した共有の場所へのパスを使用して、この一覧にファイルを追加します。このパスはプライマリ データベースとバックアップ データベースの両方に使用できます。</span><span class="sxs-lookup"><span data-stu-id="511aa-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="511aa-178">[**OK**] をクリックします。ダイアログ ボックスが閉じられ、バックアップ プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="511aa-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="511aa-179">上記のステップで作成されたバックアップ データベースを使用して、プライマリ データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="511aa-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="511aa-180">SQL Server Management Studio を使用して、mgc のプライマリ ・ インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="511aa-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="511aa-p115">mgc データベースを右クリックし、[**タスク**]、[**復元**] の順にポイントしてから、[**データベース**] をクリックします。[**データベースの復元**] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="511aa-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="511aa-183">[**復元元デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="511aa-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="511aa-p116">[参照] ボタンをクリックします。[**バックアップの指定**] ダイアログ ボックスが表示されます。[**バックアップ メディア**] で、[**ファイル**] を選択します。[**追加**] をクリックし、ステップ 3 で作成したバックアップ ファイルを選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="511aa-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="511aa-187">[**復元するバックアップ セットの選択**] で、バックアップを選択します。</span><span class="sxs-lookup"><span data-stu-id="511aa-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="511aa-188">[**ページの選択**] ウィンドウで、[**オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="511aa-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="511aa-189">[**復元オプション**] で、[**既存のデータベースを上書きする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="511aa-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="511aa-190">[**復旧状態**] で、[**データベースを使用可能な状態にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="511aa-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="511aa-191">[**OK**] をクリックします。復元プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="511aa-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="511aa-192">プライマリ ・ データベースの SQL Server のログ配布を構成します。</span><span class="sxs-lookup"><span data-stu-id="511aa-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="511aa-193">[構成の高可用性と災害復旧業務サーバー 2015 の Skype での永続的なチャット サーバーの](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)mgc のプライマリ データベースのログ配布を設定する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="511aa-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="511aa-194">永続的なチャット サーバーのアクティブなサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="511aa-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="511aa-195">ビジネス サーバー管理シェルの Skype からには、アクティブなサーバーの一覧を設定するのには、**セット CsPersistentChatActiveServer**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="511aa-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="511aa-196">すべてのアクティブ サーバーは、新しいプライマリ データベースと同じデータ センター内、またはデータベースへの接続が低待機時間/高帯域幅であるデータ センター内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="511aa-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="511aa-197">プールを通常に戻すには、状態は、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="511aa-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="511aa-198">詳細については、[Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="511aa-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

