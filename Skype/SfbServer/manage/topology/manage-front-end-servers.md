---
title: ビジネス サーバーの Skype のフロント エンド サーバーを管理します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: は、追加、削除、修正プログラム、またはビジネス サーバーの Skype でのフロント エンド サーバーを更新する方法を説明します。'
ms.openlocfilehash: c7ccaee0ee70c10b855053fb63c39cfead148f4e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875223"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="e2f03-103">ビジネス サーバーの Skype のフロント エンド サーバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="e2f03-104">追加またはフロント エンド サーバーを削除する方法について説明しを適用する方法を更新または修正プログラムのフロント エンド サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="e2f03-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="e2f03-105">追加またはフロント エンド サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="e2f03-106">プールにフロント エンド サーバーを追加またはプールからフロント エンド サーバーを削除すると、ときに、プールを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2f03-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e2f03-p101">トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="e2f03-110">追加またはサーバーをフロント エンド サーバーを削除するときは、次の手順を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e2f03-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2f03-111">プールに新しいサーバーを追加する場合、累積的な更新プログラムがプール内の既存のサーバーと同じレベルになるように、新しいプール サーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="e2f03-112">追加またはフロント エンド サーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="e2f03-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="e2f03-113">任意のフロント エンド サーバーを削除する場合は、まず、これらのサーバーへの新しい接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="e2f03-114">これを実行するには、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2f03-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="e2f03-115">トポロジ ビルダーを開き、追加または必要なサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="e2f03-116">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e2f03-p103">トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
4. <span data-ttu-id="e2f03-120">次のコマンドレットを入力して、プールが、リセット、フロント エンド プール内の次の方法のいずれかのサーバーの数を変更した場合: リセット ・ CsPoolRegistrarState ・ ResetType ・ FullReset ・ PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="e2f03-120">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="e2f03-121">2 台から任意の数</span><span class="sxs-lookup"><span data-stu-id="e2f03-121">2 to any</span></span>
    
     - <span data-ttu-id="e2f03-122">任意の数から 2 台</span><span class="sxs-lookup"><span data-stu-id="e2f03-122">Any to 2</span></span>
    
     - <span data-ttu-id="e2f03-123">3 台から任意の数</span><span class="sxs-lookup"><span data-stu-id="e2f03-123">3 to any</span></span>
    
     - <span data-ttu-id="e2f03-124">任意の数から 3 台</span><span class="sxs-lookup"><span data-stu-id="e2f03-124">Any to 3</span></span>
    
5. <span data-ttu-id="e2f03-125">以下のコマンドレットを入力してプールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-125">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="e2f03-126">フロントエンド サーバーのパッチまたは更新</span><span class="sxs-lookup"><span data-stu-id="e2f03-126">Patch or update Front End Servers</span></span>

<span data-ttu-id="e2f03-127">フロント エンド プール内のサーバーにパッチを適用するときは、同時に、1 つのサーバーを行います。</span><span class="sxs-lookup"><span data-stu-id="e2f03-127">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="e2f03-128">プール内のフロントエンド サーバーにアップグレードを適用する</span><span class="sxs-lookup"><span data-stu-id="e2f03-128">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="e2f03-129">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-129">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="e2f03-130">このコマンドレットで不足しているレプリカが示された場合は、次のコマンドレットでプールを復元してから、パッチを適用してください。</span><span class="sxs-lookup"><span data-stu-id="e2f03-130">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="e2f03-131">パッチを適用する最初のサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-131">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="e2f03-132">このコマンドレットでは、すべてのサービスを他のプール内のフロント エンド サーバーに移動し、このサーバーは、オフラインです。</span><span class="sxs-lookup"><span data-stu-id="e2f03-132">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="e2f03-133">このサーバーにアップグレードまたはパッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-133">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="e2f03-134">アップグレードしたサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-134">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="e2f03-135">サーバーがサービスに復帰します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-135">The server is returned to service.</span></span>
    
5. <span data-ttu-id="e2f03-136">アップグレードが必要なサーバーごとに、手順 2 ～ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2f03-136">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
