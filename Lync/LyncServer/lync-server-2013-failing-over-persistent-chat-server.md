---
title: 'Lync Server 2013: 常設チャット サーバーのフェールオーバー'
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
ms.openlocfilehash: dd62d4037ae1795a553d207cb698f88f9b3b8ab8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0537e-102">Lync Server 2013 での常設チャット サーバーのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="0537e-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0537e-103">_**最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="0537e-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="0537e-104">常設チャットサーバーのフェールオーバーは、主に手動で行うように設計されています。</span><span class="sxs-lookup"><span data-stu-id="0537e-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="0537e-105">フェイルオーバー手順は、セカンダリデータセンターが稼働していることを前提としていますが、プライマリ常設チャットデータベースが配置されている常設チャットサーバーサービスは、次のように完全には使用できません。</span><span class="sxs-lookup"><span data-stu-id="0537e-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="0537e-106">常設チャットサーバーのプライマリデータベースと常設チャットサーバーのミラーデータベースがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="0537e-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="0537e-107">Lync Server フロントエンドサーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="0537e-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="0537e-108">この操作は次の 2 つの基本手順に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0537e-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="0537e-109">プライマリ常設チャットデータベース (行う) を回復します。</span><span class="sxs-lookup"><span data-stu-id="0537e-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="0537e-110">新しいプライマリ データベースのミラーリングを確立する。</span><span class="sxs-lookup"><span data-stu-id="0537e-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="0537e-111">常設チャットのコンプライアンスデータベース (会社間) は、フェールオーバーされません。</span><span class="sxs-lookup"><span data-stu-id="0537e-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="0537e-112">このデータベースの内容は一時的なものであり、コンプライアンス アダプターがデータを処理するときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="0537e-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="0537e-113">データの損失を防ぐために、アダプターの出力を適切に管理することは、常設チャット管理者の責任となります。</span><span class="sxs-lookup"><span data-stu-id="0537e-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="0537e-114">常設チャットサーバーをフェイルオーバーするには</span><span class="sxs-lookup"><span data-stu-id="0537e-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="0537e-115">常設チャットサーバーバックアップログ配布データベースからログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="0537e-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="0537e-116">SQL Server Management Studio を使用して、常設チャットサーバーバックアップ行うデータベースが配置されているデータベースインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="0537e-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="0537e-117">マスター データベースに対するクエリ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="0537e-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="0537e-118">次のコマンドを使用して、ログ配布を削除します。</span><span class="sxs-lookup"><span data-stu-id="0537e-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="0537e-119">バックアップ共有から、バックアップ サーバーのコピー先フォルダーへ、コピーしていないバックアップ ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="0537e-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="0537e-120">セカンダリ データベースに、適用していないトランザクション ログ バックアップを順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="0537e-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="0537e-121">詳細については、「[方法: トランザクションログバックアップ (Transact-sql) を適用する方法http://go.microsoft.com/fwlink/p/?linkid=247428」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0537e-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at http://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="0537e-p103">バックアップ mgc データベースをオンラインにします。手順 1b. で開いたクエリ ウィンドウを使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0537e-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="0537e-124">mgc データベースへのすべての接続を終了します (接続がある場合)。</span><span class="sxs-lookup"><span data-stu-id="0537e-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="0537e-125">行うデータベースへの接続を確認するには、 **who2 sp\_** を実行します。</span><span class="sxs-lookup"><span data-stu-id="0537e-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="0537e-126">spid を終了してこれらの接続を終了します。 \*\* \<\> \*\*</span><span class="sxs-lookup"><span data-stu-id="0537e-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="0537e-127">データベースをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="0537e-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="0537e-128">**restore database mgc with recovery** を実行します。</span><span class="sxs-lookup"><span data-stu-id="0537e-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="0537e-129">Lync Server 管理シェルで、コマンド**セット CsPersistentChatState-Identity "service: 001.litwareinc.com" – PoolState FailedOver**を使用して、行う backup データベースにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="0537e-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="0537e-130">atl-cs-001.litwareinc.com の部分には、常設チャット プールの完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0537e-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="0537e-131">mgc バックアップ データベースがプライマリ データベースとして動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="0537e-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="0537e-132">Lync Server 管理シェルで、 **CsMirrorDatabase**コマンドレットを使用して、プライマリデータベースとして機能するバックアップデータベースに対して高可用性ミラーを確立します。</span><span class="sxs-lookup"><span data-stu-id="0537e-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="0537e-133">バックアップ データベース インスタンスをプライマリ データベースとして使用し、バックアップ ミラー データベース インスタンスをミラー インスタンスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="0537e-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="0537e-134">これは、セットアップ時にプライマリ データベースに対して最初に構成したミラーと同じものではありません。</span><span class="sxs-lookup"><span data-stu-id="0537e-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="0537e-135">詳細については、「 [lync server 2013 でのバックエンドサーバーの高可用性のための SQL ミラーリングの展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)」の「Lync Server 管理シェルコマンドレットの使用」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0537e-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="0537e-136">常設チャットサーバーのアクティブなサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="0537e-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="0537e-137">Lync Server コマンドシェルで、 **CsPersistentChatActiveServer**コマンドレットを使用してアクティブなサーバーの一覧を設定します。</span><span class="sxs-lookup"><span data-stu-id="0537e-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0537e-138">すべてのアクティブ サーバーは、新しいプライマリ データベースと同じデータ センター内、またはデータベースへの接続が低待機時間/高帯域幅であるデータ センター内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0537e-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="0537e-139">この時点で、常設チャットサーバーのプライマリデータベースから永続的なチャットサーバーバックアップデータベースへのフェールオーバーが正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="0537e-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

