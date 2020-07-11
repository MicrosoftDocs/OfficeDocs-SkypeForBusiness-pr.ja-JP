---
title: Skype for Business Server でのフロントエンドサーバーの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: Skype for Business Server でフロントエンドサーバーを追加、削除、修正、または更新する方法について説明します。'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098415"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="14b90-103">Skype for Business Server でのフロントエンドサーバーの管理</span><span class="sxs-lookup"><span data-stu-id="14b90-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="14b90-104">この記事では、フロントエンドサーバーを追加または削除する方法と、フロントエンドサーバーにアップグレードまたはパッチを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14b90-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="14b90-105">Skype for Business Server 2019 は、2台のフロントエンドサーバーを持つ Enterprise Edition フロントエンドプールをサポートしていません。このシナリオでは、トポロジを公開することはできません。</span><span class="sxs-lookup"><span data-stu-id="14b90-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="14b90-106">フロントエンドサーバーの追加または削除</span><span class="sxs-lookup"><span data-stu-id="14b90-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="14b90-107">フロントエンド サーバーをプールに追加したり、フロントエンド サーバーをプールから削除した場合は、プールを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14b90-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="14b90-108">トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動されます。</span><span class="sxs-lookup"><span data-stu-id="14b90-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="14b90-109">サーバーが再起動している間はプールがオフラインになり、そのプールに接続しているユーザーのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="14b90-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="14b90-110">ユーザーにサービスが中断されないようにするには、営業時間外にプール内の新しいサーバーでトポロジを公開するように計画します。</span><span class="sxs-lookup"><span data-stu-id="14b90-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="14b90-111">フロントエンドサーバーを追加または削除する際には、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="14b90-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14b90-112">プールに新しいサーバーを追加している場合は、プール内の既存のサーバーと同じ累積更新レベルになるように、新しいプールサーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="14b90-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="14b90-113">フロントエンドサーバーを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="14b90-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="14b90-114">If you are removing any Front End Servers, first stop new connections to those servers.</span><span class="sxs-lookup"><span data-stu-id="14b90-114">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="14b90-115">To do so, you can use the following cmdlet:</span><span class="sxs-lookup"><span data-stu-id="14b90-115">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="14b90-116">トポロジ ビルダーを開き、必要なサーバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="14b90-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="14b90-117">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="14b90-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="14b90-118">トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動されます。</span><span class="sxs-lookup"><span data-stu-id="14b90-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="14b90-119">サーバーが再起動している間はプールがオフラインになり、そのプールに接続しているユーザーのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="14b90-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="14b90-120">ユーザーにサービスが中断されないようにするには、営業時間外にプール内の新しいサーバーでトポロジを公開するように計画します。</span><span class="sxs-lookup"><span data-stu-id="14b90-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="14b90-121">また、プールにサーバーを追加または削除する場合は、追加または削除した各コンピューターで Skype for business Server 展開ウィザードを実行する必要があります。詳細については、「 [Install skype For Business server on server on トポロジ」](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14b90-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="14b90-122">フロントエンドプール内のサーバーの数を次のいずれかの方法で変更した場合は、次のコマンドレットを入力して、プールをリセットします。 Reset-cspoolregistrarstate-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="14b90-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="14b90-123">2から任意</span><span class="sxs-lookup"><span data-stu-id="14b90-123">2 to any</span></span>
    
     - <span data-ttu-id="14b90-124">任意の2</span><span class="sxs-lookup"><span data-stu-id="14b90-124">Any to 2</span></span>
    
     - <span data-ttu-id="14b90-125">3から任意の</span><span class="sxs-lookup"><span data-stu-id="14b90-125">3 to any</span></span>
    
     - <span data-ttu-id="14b90-126">任意の3</span><span class="sxs-lookup"><span data-stu-id="14b90-126">Any to 3</span></span>
    
5. <span data-ttu-id="14b90-127">次のコマンドレットを入力して、プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="14b90-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="14b90-128">フロントエンドサーバーのパッチまたは更新</span><span class="sxs-lookup"><span data-stu-id="14b90-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="14b90-129">フロントエンドプール内のサーバーに修正プログラムを適用する場合は、一度に1台のサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="14b90-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="14b90-130">プール内のフロントエンドサーバーにアップグレードを適用するには</span><span class="sxs-lookup"><span data-stu-id="14b90-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="14b90-131">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="14b90-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="14b90-132">このコマンドレットで不足しているレプリカが表示された場合は、次のコマンドレットを実行して、更新プログラムを適用する前にプールを回復します。</span><span class="sxs-lookup"><span data-stu-id="14b90-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="14b90-133">最初に修正プログラムを適用するサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14b90-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="14b90-134">このコマンドレットは、すべてのサービスをプール内の他のフロントエンドサーバーに移動し、このサーバーをオフラインにします。</span><span class="sxs-lookup"><span data-stu-id="14b90-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="14b90-135">このサーバーにアップグレードまたはパッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="14b90-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="14b90-136">アップグレードされたサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14b90-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="14b90-137">サーバーがサービスに返されます。</span><span class="sxs-lookup"><span data-stu-id="14b90-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="14b90-138">アップグレードが必要な各サーバーについて、手順2-4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="14b90-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
