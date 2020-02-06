---
title: Skype for Business Server でフロントエンドサーバーを管理する
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
description: '概要: Skype for Business Server でフロントエンドサーバーを追加、削除、更新、または更新する方法について説明します。'
ms.openlocfilehash: bc97faaf3ac36ff5cb74d6286aa7e75facbd98cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817263"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="0a015-103">Skype for Business Server でフロントエンドサーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="0a015-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="0a015-104">この記事では、フロントエンドサーバーを追加または削除する方法と、フロントエンドサーバーにアップグレードまたは更新プログラムを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a015-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="0a015-105">フロントエンドサーバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0a015-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="0a015-106">フロントエンドサーバーをプールに追加する場合、またはプールからフロントエンドサーバーを削除する場合は、プールを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a015-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0a015-p101">トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。</span><span class="sxs-lookup"><span data-stu-id="0a015-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="0a015-110">フロントエンドサーバーを追加または削除するときには、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0a015-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a015-111">プールに新しいサーバーを追加する場合、累積的な更新プログラムがプール内の既存のサーバーと同じレベルになるように、新しいプール サーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="0a015-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="0a015-112">フロントエンドサーバーを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="0a015-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="0a015-113">フロントエンドサーバーを削除する場合は、まず、それらのサーバーへの新しい接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="0a015-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="0a015-114">これを実行するには、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0a015-114">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="0a015-115">トポロジビルダーを開き、必要なサーバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="0a015-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="0a015-116">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="0a015-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0a015-p103">トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。</span><span class="sxs-lookup"><span data-stu-id="0a015-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="0a015-120">また、プールにサーバーを追加または削除する場合は、追加または削除された各コンピューターで Skype for Business Server 展開ウィザードを実行する必要があります。詳細については、「[トポロジのサーバーに skype for Business server をインストール](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a015-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="0a015-121">フロントエンドプール内のサーバーの数を次のいずれかの方法で変更した場合は、次のコマンドレットを入力してプールをリセットします。 CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="0a015-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="0a015-122">2 台から任意の数</span><span class="sxs-lookup"><span data-stu-id="0a015-122">2 to any</span></span>
    
     - <span data-ttu-id="0a015-123">任意の数から 2 台</span><span class="sxs-lookup"><span data-stu-id="0a015-123">Any to 2</span></span>
    
     - <span data-ttu-id="0a015-124">3 台から任意の数</span><span class="sxs-lookup"><span data-stu-id="0a015-124">3 to any</span></span>
    
     - <span data-ttu-id="0a015-125">任意の数から 3 台</span><span class="sxs-lookup"><span data-stu-id="0a015-125">Any to 3</span></span>
    
5. <span data-ttu-id="0a015-126">以下のコマンドレットを入力してプールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0a015-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="0a015-127">フロントエンド サーバーのパッチまたは更新</span><span class="sxs-lookup"><span data-stu-id="0a015-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="0a015-128">フロントエンドプールにサーバーを修正する場合は、一度に1つのサーバーを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a015-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="0a015-129">プール内のフロントエンド サーバーにアップグレードを適用する</span><span class="sxs-lookup"><span data-stu-id="0a015-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="0a015-130">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="0a015-130">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="0a015-131">このコマンドレットで不足しているレプリカが示された場合は、次のコマンドレットでプールを復元してから、パッチを適用してください。</span><span class="sxs-lookup"><span data-stu-id="0a015-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="0a015-132">パッチを適用する最初のサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a015-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="0a015-133">このコマンドレットは、すべてのサービスをプール内の他のフロントエンドサーバーに移動し、このサーバーをオフラインにします。</span><span class="sxs-lookup"><span data-stu-id="0a015-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="0a015-134">このサーバーにアップグレードまたはパッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="0a015-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="0a015-135">アップグレードしたサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a015-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="0a015-136">サーバーがサービスに復帰します。</span><span class="sxs-lookup"><span data-stu-id="0a015-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="0a015-137">アップグレードが必要なサーバーごとに、手順 2 ～ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0a015-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
