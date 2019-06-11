---
title: 'Lync Server 2013: ミラー化データベースのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a943705f13cff4f015285b1ef74feb11dc540091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="7f09b-102">Lync Server 2013 でのミラー化データベースのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="7f09b-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f09b-103">_**最終更新日:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="7f09b-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="7f09b-104">バックエンドデータベースが監視との同期ミラーリングを使用するように構成されている場合、フェールオーバーは自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7f09b-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="7f09b-105">ミラーリングを監視せずに同期ミラーリングを構成した場合は、次の手順を使用してデータベースのフェールオーバーとフェールバックを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7f09b-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="7f09b-106">また、監視を構成している場合でも、これらの手順を使用して手動でデータベースのフェールオーバーとフェールバックを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7f09b-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="7f09b-107">バックエンドデータベースをフェールオーバーするには</span><span class="sxs-lookup"><span data-stu-id="7f09b-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="7f09b-108">フェールオーバーする前に、次のコマンドレットを入力して、どのバックエンドデータベースがプリンシパルであり、ミラーであるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7f09b-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="7f09b-109">このプールで中央管理ストアがホストされている場合は、次のコマンドレットを入力して、どのプリンシパルが中央管理ストアのミラーであるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7f09b-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="7f09b-110">ユーザーデータベースのフェールオーバーを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f09b-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="7f09b-111">プライマリに障害が発生し、ミラーにフェイルオーバーする場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7f09b-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="7f09b-112">ミラーが失敗し、プライマリにフェイルオーバーする場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7f09b-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="7f09b-113">プールで中央管理サーバーがホストされている場合は、中央管理ストアのフェールオーバーを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f09b-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="7f09b-114">プライマリに障害が発生し、ミラーにフェイルオーバーする場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7f09b-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="7f09b-115">ミラーが失敗し、プライマリにフェイルオーバーする場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7f09b-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

