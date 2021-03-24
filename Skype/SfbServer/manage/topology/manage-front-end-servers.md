---
title: Skype for Business Server でフロントエンド サーバーを管理する
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
description: '概要: Skype for Business Server のフロント エンド サーバーを追加、削除、修正、または更新する方法について学習します。'
ms.openlocfilehash: 24527a5f973b21c35e386f0565ac6deb69e15070
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103193"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="e1dff-103">Skype for Business Server でフロントエンド サーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="e1dff-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="e1dff-104">この記事では、フロントエンド サーバーを追加または削除する方法、およびフロントエンド サーバーにアップグレードまたはパッチを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="e1dff-105">Skype for Business Server 2019 は、2 台のフロント エンド サーバーを持つ Enterprise Edition フロントエンド プールをサポートしていないので、そのシナリオではトポロジを公開できません。</span><span class="sxs-lookup"><span data-stu-id="e1dff-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="e1dff-106">フロントエンド サーバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="e1dff-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="e1dff-107">フロントエンド サーバーをプールに追加したり、フロントエンド サーバーをプールから削除した場合は、プールを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1dff-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e1dff-108">トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動されます。</span><span class="sxs-lookup"><span data-stu-id="e1dff-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="e1dff-109">サーバーがプールを再起動している間はオフラインで、そのプールに接続されているユーザーのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="e1dff-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="e1dff-110">ユーザーへのサービスの中断を防ぐには、非営業時間内にプール内の新しいサーバーでトポロジを公開する計画を立てします。</span><span class="sxs-lookup"><span data-stu-id="e1dff-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="e1dff-111">フロント エンド サーバーを追加または削除する場合は、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1dff-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1dff-112">プールに新しいサーバーを追加する場合は、新しいプール サーバーをプール内の既存のサーバーと同じ累積的な更新レベルに更新します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="e1dff-113">フロントエンド サーバーを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="e1dff-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="e1dff-p102">フロントエンド サーバーを削除する場合、最初にこれらのサーバーへの新しい接続を停止します。これを実行するには、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1dff-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="e1dff-116">トポロジ ビルダーを開き、必要なサーバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="e1dff-117">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e1dff-118">トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動されます。</span><span class="sxs-lookup"><span data-stu-id="e1dff-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="e1dff-119">サーバーがプールを再起動している間はオフラインで、そのプールに接続されているユーザーのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="e1dff-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="e1dff-120">ユーザーへのサービスの中断を防ぐには、非営業時間内にプール内の新しいサーバーでトポロジを公開する計画を立てします。</span><span class="sxs-lookup"><span data-stu-id="e1dff-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="e1dff-121">また、プールにサーバーを追加または削除する場合は、追加または削除された各コンピューターで Skype for Business Server 展開ウィザードを実行する必要があります。詳細については、「トポロジ内のサーバーに[Skype for Business Server](../../deploy/install/install-skype-for-business-server.md)をインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1dff-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](../../deploy/install/install-skype-for-business-server.md)</span></span>
  
4. <span data-ttu-id="e1dff-122">次の方法でフロントエンド プール内のサーバーの数を変更した場合は、次のコマンドレットを入力してプールをリセットします。Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="e1dff-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="e1dff-123">2 ~ any</span><span class="sxs-lookup"><span data-stu-id="e1dff-123">2 to any</span></span>
    
     - <span data-ttu-id="e1dff-124">Any ~ 2</span><span class="sxs-lookup"><span data-stu-id="e1dff-124">Any to 2</span></span>
    
     - <span data-ttu-id="e1dff-125">3 ~ any</span><span class="sxs-lookup"><span data-stu-id="e1dff-125">3 to any</span></span>
    
     - <span data-ttu-id="e1dff-126">Any ~ 3</span><span class="sxs-lookup"><span data-stu-id="e1dff-126">Any to 3</span></span>
    
5. <span data-ttu-id="e1dff-127">次のコマンドレットを入力してプールを再起動する</span><span class="sxs-lookup"><span data-stu-id="e1dff-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="e1dff-128">フロント エンド サーバーにパッチを適用または更新する</span><span class="sxs-lookup"><span data-stu-id="e1dff-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="e1dff-129">フロントエンド プール内のサーバーにパッチを適用する場合は、一度に 1 つのサーバーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="e1dff-130">プール内のフロントエンド サーバーにアップグレードを適用するには</span><span class="sxs-lookup"><span data-stu-id="e1dff-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="e1dff-131">次の cmdlet を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="e1dff-132">このコマンドレットに不足しているレプリカが表示される場合は、次のコマンドレットを実行してプールを回復してから、パッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="e1dff-133">パッチを適用する最初のサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="e1dff-134">このコマンドレットは、すべてのサービスをプール内の他のフロントエンド サーバーに移動し、このサーバーをオフラインにします。</span><span class="sxs-lookup"><span data-stu-id="e1dff-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="e1dff-135">このサーバーにアップグレードまたはパッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="e1dff-136">アップグレードされたサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="e1dff-137">サーバーはサービスに返されます。</span><span class="sxs-lookup"><span data-stu-id="e1dff-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="e1dff-138">アップグレードする必要があるサーバーごとに、手順 2 ~ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e1dff-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
