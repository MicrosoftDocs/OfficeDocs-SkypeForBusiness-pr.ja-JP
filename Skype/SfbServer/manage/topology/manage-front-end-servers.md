---
title: Skype for Business Server でのフロントエンド サーバーの管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: Skype for Business Server でフロントエンド サーバーを追加、削除、パッチ、更新する方法について学習します。'
ms.openlocfilehash: 16af245b3c49b21309edd3ee2843f2585814ce9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826327"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="20a3e-103">Skype for Business Server でのフロントエンド サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="20a3e-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="20a3e-104">この記事では、フロントエンド サーバーを追加または削除する方法、およびアップグレードまたはパッチをフロントエンド サーバーに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="20a3e-105">Skype for Business Server 2019 は、2 台のフロントエンド サーバーを持つ Enterprise Edition フロントエンド プールをサポートしていないので、そのシナリオでトポロジを公開できません。</span><span class="sxs-lookup"><span data-stu-id="20a3e-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="20a3e-106">フロントエンド サーバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="20a3e-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="20a3e-107">フロントエンド サーバーをプールに追加したり、フロントエンド サーバーをプールから削除した場合は、プールを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20a3e-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="20a3e-108">トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="20a3e-109">サーバーがプールを再起動している間はオフラインで、そのプールに接続しているユーザーのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="20a3e-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="20a3e-110">ユーザーへのサービスが中断されるのを防ぐには、非営業時間内にプール内の新しいサーバーでトポロジを公開する計画を立てします。</span><span class="sxs-lookup"><span data-stu-id="20a3e-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="20a3e-111">フロントエンド サーバーを追加または削除する場合は、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="20a3e-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20a3e-112">プールに新しいサーバーを追加する場合は、プール内の既存のサーバーと同じ累積的な更新プログラム レベルに新しいプール サーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="20a3e-113">フロントエンド サーバーを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="20a3e-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="20a3e-p102">フロントエンド サーバーを削除する場合、最初にこれらのサーバーへの新しい接続を停止します。これを実行するには、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="20a3e-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="20a3e-116">トポロジ ビルダーを開き、必要なサーバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="20a3e-117">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="20a3e-118">トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="20a3e-119">サーバーがプールを再起動している間はオフラインで、そのプールに接続しているユーザーのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="20a3e-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="20a3e-120">ユーザーへのサービスが中断されるのを防ぐには、非営業時間内にプール内の新しいサーバーでトポロジを公開する計画を立てします。</span><span class="sxs-lookup"><span data-stu-id="20a3e-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="20a3e-121">また、プールにサーバーを追加または削除する場合は、追加または削除された各コンピューターで Skype for Business Server 展開ウィザードを実行する必要があります。詳細については、「トポロジ内のサーバーに[Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)をインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20a3e-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="20a3e-122">次の方法でフロントエンド プールのサーバー数を変更した場合は、次のコマンドレットを入力してプールをリセットします。Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="20a3e-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="20a3e-123">2 ~ 任意</span><span class="sxs-lookup"><span data-stu-id="20a3e-123">2 to any</span></span>
    
     - <span data-ttu-id="20a3e-124">Any to 2</span><span class="sxs-lookup"><span data-stu-id="20a3e-124">Any to 2</span></span>
    
     - <span data-ttu-id="20a3e-125">3 ~ 任意</span><span class="sxs-lookup"><span data-stu-id="20a3e-125">3 to any</span></span>
    
     - <span data-ttu-id="20a3e-126">Any to 3</span><span class="sxs-lookup"><span data-stu-id="20a3e-126">Any to 3</span></span>
    
5. <span data-ttu-id="20a3e-127">次のコマンドレットを入力してプールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="20a3e-128">フロントエンド サーバーのパッチまたは更新</span><span class="sxs-lookup"><span data-stu-id="20a3e-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="20a3e-129">フロントエンド プール内のサーバーにパッチを適用する場合は、一度に 1 つのサーバーを適用します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="20a3e-130">プール内のフロントエンド サーバーにアップグレードを適用するには</span><span class="sxs-lookup"><span data-stu-id="20a3e-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="20a3e-131">次の cmdlet を入力します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="20a3e-132">このコマンドレットで見つからないレプリカが表示される場合は、次のコマンドレットを実行してプールを回復してから、修正プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="20a3e-133">修正プログラムを適用する最初のサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="20a3e-134">このコマンドレットは、すべてのサービスをプール内の他のフロントエンド サーバーに移動し、このサーバーをオフラインにします。</span><span class="sxs-lookup"><span data-stu-id="20a3e-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="20a3e-135">このサーバーにアップグレードまたはパッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="20a3e-136">アップグレードしたサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="20a3e-137">サーバーはサービスに戻されます。</span><span class="sxs-lookup"><span data-stu-id="20a3e-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="20a3e-138">アップグレードする必要があるサーバーごとに、手順 2. ~ 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="20a3e-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
