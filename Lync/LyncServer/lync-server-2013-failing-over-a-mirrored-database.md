---
title: 'Lync Server 2013: ミラー化されたデータベースのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853dfdd6786b4e30513cb57be219edff8d8c1b9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530974"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="bd072-102">Lync Server 2013 でのミラー化されたデータベースのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="bd072-102">Failing over a mirrored database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd072-103">_**トピックの最終更新日:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="bd072-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="bd072-p101">ミラーリング監視を伴う同期されたミラーリングを使用するようにバックエンド データベースを構成している場合、フェールオーバーは自動で行われます。ミラーリング監視を伴わない同期されたミラーリングを構成している場合は、以下の手順を使用して、データベースのフェールオーバーとフェールバックを実行できます。また、これらの手順を使用すると、ミラーリング監視を構成している場合でも、データベースのフェールオーバーとフェールバックを手動で実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd072-p101">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic. If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database. You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="bd072-107">バックエンド データベースをフェールオーバーするには</span><span class="sxs-lookup"><span data-stu-id="bd072-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="bd072-108">フェールオーバーを行う前に、次のコマンドレットを入力して、どのバックエンド データベースがプリンシパルでどれがミラーであるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd072-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="bd072-109">中央管理ストアがこのプールにホストされている場合は、次のコマンドレットを入力して、どのがプリンシパルで、中央管理ストアのミラーであるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd072-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="bd072-110">ユーザー データベースのフェールオーバーを以下のように実行します。</span><span class="sxs-lookup"><span data-stu-id="bd072-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="bd072-111">プライマリに障害が発生してミラーにフェールオーバーする場合は、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd072-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="bd072-112">ミラーに障害が発生してプライマリにフェールオーバーする場合は、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd072-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="bd072-113">プールが中央管理サーバーをホストしている場合は、中央管理ストアのフェールオーバーを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd072-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="bd072-114">プライマリに障害が発生してミラーにフェールオーバーする場合は、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd072-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="bd072-115">ミラーに障害が発生してプライマリにフェールオーバーする場合は、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd072-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

