---
title: 'Lync Server 2013: フロントエンドサーバーのアップグレードまたは更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530324"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="d9bb3-102">Lync Server 2013 でのフロントエンドサーバーのアップグレードまたは更新</span><span class="sxs-lookup"><span data-stu-id="d9bb3-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9bb3-103">_**トピックの最終更新日:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="d9bb3-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="d9bb3-104">Enterprise Edition プール内のフロントエンド サーバーは、アップグレード ドメイン\*\* にまとめられます。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="d9bb3-105">これらはプール内のフロントエンド サーバーのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="d9bb3-106">アップグレードドメインは、トポロジビルダーによって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="d9bb3-107">サーバーをアップグレードするときには、一度に1つのアップグレードドメインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="d9bb3-108">各サーバーを1つのアップグレードドメインから下に移動し、アップグレードしてから、別のアップグレードドメインに移行する前に再起動します。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="d9bb3-109">これまでにアップグレードしたアップグレードドメインとサーバーを常に追跡してください。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="d9bb3-110">各サーバーをアップグレードする場合は、次のフローチャート図を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-110">Use the following flowchart diagram when upgrading each server.</span></span>

![フロントエンド サーバーのアップグレードまたは更新](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="d9bb3-112">プール内のフロントエンドサーバーにアップグレードを適用するには</span><span class="sxs-lookup"><span data-stu-id="d9bb3-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="d9bb3-113">プール内のフロントエンド サーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="d9bb3-114">**Get-cspoolupgradereadinessstate 戻し**</span><span class="sxs-lookup"><span data-stu-id="d9bb3-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="d9bb3-115">*Poolupgradestate*の値が**ビジー**の場合は、10分間待ってからもう一度**get-cspoolupgradereadinessstate 戻し**を実行してください。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="d9bb3-116">少なくとも3回の連続する時間に [**ビジー** ] が表示される場合、各試行の間に10分待機した後、または**Poolupgradestate**の**InsufficientActiveFrontEnds**結果が表示された場合は、プールに問題があります。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="d9bb3-117">このプールが障害復旧トポロジの別のフロントエンド プールとペアになっている場合は、プールをバックアップ プールにフェールオーバーし、そのプール内のサーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="d9bb3-118">詳細については、「 [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="d9bb3-119">PoolUpgradeState\*\* の値が **Ready** の場合は、手順 2. に進みます。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="d9bb3-120">**Get-cspoolupgradereadinessstate 戻し**コマンドレットは、プール内の各アップグレードドメインに関する情報、および各アップグレードドメインにあるフロントエンドサーバーについても返します。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="d9bb3-121">アップグレードするサーバーが含まれているアップグレードドメインの **ReadyforUpgrade** 値が **True** の場合は、これらのサーバーをすぐにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="d9bb3-122">アップグレードを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="d9bb3-123">コマンドレットを使用して、アップグレードするフロントエンドサーバーへの新しい接続を停止し `Stop-CsWindowsService -Graceful -Verbose` ます。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d9bb3-124">スケジュールされたサーバーのダウンタイム中にこれらのサーバーのアップグレードを実行する場合は、次のように、このコマンドレットを '-<STRONG>正常</STRONG>' パラメーターなしで実行できます。 <STRONG>Stop-cswindowsservice</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="d9bb3-125">これにより、すべての既存のサービス要求がいっぱいになるのを待たずに、直ちにサービスがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="d9bb3-126">このアップグレードドメインに関連付けられているサーバーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="d9bb3-127">サーバーを再起動し、新しい接続を受け入れていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="d9bb3-128">すべてのフロントエンドサーバーがアップグレードされるまで、プール内の他のすべてのアップグレードドメインに対して手順1と2を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

