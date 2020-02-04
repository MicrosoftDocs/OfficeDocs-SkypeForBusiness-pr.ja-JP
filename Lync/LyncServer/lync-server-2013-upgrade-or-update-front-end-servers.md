---
title: 'Lync Server 2013: フロントエンドサーバーのアップグレードまたは更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1680da68299881fe94244969d44fce1900532b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="da172-102">Upgrade or update Front End Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da172-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da172-103">_**最終更新日:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="da172-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="da172-104">Enterprise Edition プールのフロントエンドサーバーは、*アップグレードドメイン*として編成されています。</span><span class="sxs-lookup"><span data-stu-id="da172-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="da172-105">これらは、プール内のフロントエンドサーバーのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="da172-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="da172-106">アップグレードドメインは、トポロジビルダーによって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="da172-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="da172-107">サーバーをアップグレードする場合は、一度に1つのアップグレードドメインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da172-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="da172-108">各サーバーを1つのアップグレードドメインに移動してアップグレードし、それを再起動してから別のアップグレードドメインに移行します。</span><span class="sxs-lookup"><span data-stu-id="da172-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="da172-109">これまでにアップグレードしたアップグレードドメインとサーバーを常に把握しておいてください。</span><span class="sxs-lookup"><span data-stu-id="da172-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="da172-110">各サーバーをアップグレードする場合は、次のフローチャート図を使用します。</span><span class="sxs-lookup"><span data-stu-id="da172-110">Use the following flowchart diagram when upgrading each server.</span></span>

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="フロントエンドサーバーのアップグレードまたは更新":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="da172-112">プール内のフロントエンド サーバーにアップグレードを適用する</span><span class="sxs-lookup"><span data-stu-id="da172-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="da172-113">プール内のフロントエンドサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="da172-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="da172-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="da172-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="da172-115">*Poolupgradestate*の値が**Busy**の場合は、10分間待ってから、もう一度**CsPoolUpgradeReadinessState**を試してください。</span><span class="sxs-lookup"><span data-stu-id="da172-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="da172-116">3回以上連続して [**取り込み中**] と表示されている場合、それぞれの試行の間に10分待ってから、または**InsufficientActiveFrontEnds**の**poolupgradestate**の結果が表示された場合は、プールに問題があります。</span><span class="sxs-lookup"><span data-stu-id="da172-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="da172-117">このプールが、障害回復トポロジの別のフロントエンドプールとペアリングされている場合は、プールをバックアッププールにフェールオーバーし、このプール内のサーバーを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da172-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="da172-118">詳細については、「 [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da172-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="da172-119">*Poolupgradestate*の値の準備が**でき**ている場合は、手順2に進みます。</span><span class="sxs-lookup"><span data-stu-id="da172-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="da172-120">**CsPoolUpgradeReadinessState**コマンドレットは、プール内の各アップグレードドメインについての情報と、各アップグレードドメインに含まれるフロントエンドサーバーについても返します。</span><span class="sxs-lookup"><span data-stu-id="da172-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="da172-121">アップグレードするサーバーが含まれているアップグレードドメインに対して**ReadyforUpgrade**値が**True**の場合は、これらのサーバーを現在安全にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="da172-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="da172-122">そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="da172-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="da172-123">アップグレードするフロントエンドサーバーへの新しい接続を停止するには、 `Stop-CsWindowsService -Graceful -Verbose`コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="da172-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="da172-124">スケジュールされたサーバーのダウンタイムにサーバーのアップグレードを実行している場合は、次のように、"-<STRONG>正常</STRONG>" パラメーターを指定せずにこのコマンドレットを実行でき<STRONG>ます。</STRONG></span><span class="sxs-lookup"><span data-stu-id="da172-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="da172-125">これにより、すべての既存のサービスリクエストがいっぱいになるのを待たずに、すぐにサービスが終了します。</span><span class="sxs-lookup"><span data-stu-id="da172-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="da172-126">このアップグレードドメインに関連付けられているサーバーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="da172-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="da172-127">サーバーを再起動して、新しい接続を受け入れていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da172-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="da172-128">すべてのフロントエンドサーバーがアップグレードされるまで、プール内の各アップグレードドメインについて、手順1と2を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="da172-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

