---
title: 'Lync Server 2013: 常設チャットサーバーのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d5ac758c1e4c87fd5559da1c2a9cf388dc8834
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="1ee44-102">Lync Server 2013 での常設チャットサーバーのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="1ee44-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee44-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="1ee44-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="1ee44-104">常設チャットサーバーのフェールオーバーは、主に手動プロセスとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="1ee44-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="1ee44-105">フェールオーバーの手順は、セカンダリデータセンターが稼働していることを前提としていますが、プライマリ常設チャットデータベースが配置されている常設チャットサーバーサービスは完全には使用できません (次のようなものがあります)。</span><span class="sxs-lookup"><span data-stu-id="1ee44-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="1ee44-106">常設チャットサーバーのプライマリデータベースと常設チャットサーバーのミラーデータベースがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="1ee44-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="1ee44-107">Lync Server フロントエンドサーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="1ee44-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="1ee44-108">操作は 2 つの基本手順に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="1ee44-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="1ee44-109">プライマリ常設チャットデータベース (mgc) を復元します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="1ee44-110">新しいプライマリ データベースのミラーリングを確立する。</span><span class="sxs-lookup"><span data-stu-id="1ee44-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="1ee44-111">常設チャットコンプライアンスデータベース (メンバー) がフェールオーバーしていません。</span><span class="sxs-lookup"><span data-stu-id="1ee44-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="1ee44-112">このデータベースの内容は一時的なものであり、コンプライアンス アダプターがデータを処理するときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="1ee44-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="1ee44-113">データ損失を防ぐためにアダプター出力を適切に管理するには、常設チャット管理者としての責任があります。</span><span class="sxs-lookup"><span data-stu-id="1ee44-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="1ee44-114">常設チャットサーバーをフェールオーバーするには</span><span class="sxs-lookup"><span data-stu-id="1ee44-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="1ee44-115">常設チャットサーバーのバックアップログ配布データベースからログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="1ee44-116">SQL Server Management Studio を使用して、常設チャットサーバーバックアップ mgc データベースが配置されているデータベースインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="1ee44-117">マスター データベースに対するクエリ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="1ee44-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="1ee44-118">次のコマンドを使用して、ログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="1ee44-119">バックアップ共有から、バックアップ サーバーのコピー先フォルダーへ、コピーしていないバックアップ ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1ee44-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="1ee44-120">セカンダリ データベースに、適用していないトランザクション ログ バックアップを順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="1ee44-121">詳細については、「方法: トランザクションログバックアップを適用する (Transact-sql)」をhttp://go.microsoft.com/fwlink/p/?linkid=247428参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ee44-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at http://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="1ee44-p103">バックアップ mgc データベースをオンラインにします。手順 1b. で開いたクエリ ウィンドウを使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="1ee44-124">mgc データベースへのすべての接続を終了します (接続がある場合)。</span><span class="sxs-lookup"><span data-stu-id="1ee44-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="1ee44-125">mgc データベースへの接続を識別するために、 **exec sp\_who2** 。</span><span class="sxs-lookup"><span data-stu-id="1ee44-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="1ee44-126">\*\* \<spid\>を切断\*\*してこれらの接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="1ee44-127">データベースをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="1ee44-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="1ee44-128">**restore database mgc with recovery**。</span><span class="sxs-lookup"><span data-stu-id="1ee44-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="1ee44-129">Lync Server 管理シェルで、コマンド**set-cspersistentchatstate-Identity "service: 001.litwareinc.com" – PoolState FailedOver**を使用して、mgc バックアップデータベースにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="1ee44-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="1ee44-130">Atl-cs-001.litwareinc.com の常設チャットプールの完全修飾ドメイン名に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="1ee44-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="1ee44-131">mgc バックアップ データベースがプライマリ データベースとして動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="1ee44-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="1ee44-132">Lync Server 管理シェルで、 **install-csmirrordatabase**コマンドレットを使用して、プライマリデータベースとして機能するバックアップデータベースの高可用性ミラーを確立します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="1ee44-133">バックアップ データベース インスタンスをプライマリ データベースとして使用し、バックアップ ミラー データベース インスタンスをミラー インスタンスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="1ee44-134">これは、セットアップ時にプライマリ データベースに対して最初に構成したミラーと同じものではありません。</span><span class="sxs-lookup"><span data-stu-id="1ee44-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="1ee44-135">詳細については、「 [Lync server 2013 でバックエンドサーバーの高可用性を実現するための SQL ミラーリングを展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)する」の「Lync Server 管理シェルコマンドレットを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ee44-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="1ee44-136">常設チャットサーバーのアクティブなサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="1ee44-137">Lync Server コマンドシェルから、 **set-cspersistentchatactiveserver**コマンドレットを使用してアクティブなサーバーの一覧を設定します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1ee44-138">すべてのアクティブ サーバーが新しいプライマリ データベースと同じデータ センター内に置かれているか、このデータベースへの接続が低待機時間/高帯域幅であるデータセンター内に置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ee44-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="1ee44-139">この時点で、常設チャットサーバーのプライマリデータベースから常設チャットサーバーのバックアップデータベースへのフェールオーバーは正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="1ee44-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

