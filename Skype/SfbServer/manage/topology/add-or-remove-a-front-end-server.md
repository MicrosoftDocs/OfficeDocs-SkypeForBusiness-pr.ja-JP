---
title: Skype for Business Server 2015 でのフロントエンド サーバーの追加または削除
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: は、追加または、Skype のビジネス サーバーのフロント エンド サーバーを削除する方法を説明します。'
ms.openlocfilehash: 80b0dab56d3adfb08856348b7ec749ef2e91079f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569007"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="b9c68-103">Skype for Business Server 2015 でのフロントエンド サーバーの追加または削除</span><span class="sxs-lookup"><span data-stu-id="b9c68-103">Add or remove a Front End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9c68-104">**の概要:** 追加または Skype のビジネス サーバーのフロント エンド サーバーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9c68-104">**Summary:** Learn how to add or remove Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="b9c68-105">プールにフロント エンド サーバーを追加またはプールからフロント エンド サーバーを削除すると、ときに、プールを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9c68-105">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b9c68-p101">トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。</span><span class="sxs-lookup"><span data-stu-id="b9c68-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="b9c68-109">追加またはサーバーをフロント エンド サーバーを削除するときは、次の手順を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b9c68-109">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9c68-110">プールに新しいサーバーを追加する場合、累積的な更新プログラムがプール内の既存のサーバーと同じレベルになるように、新しいプール サーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="b9c68-110">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="b9c68-111">追加またはフロント エンド サーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="b9c68-111">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="b9c68-112">任意のフロント エンド サーバーを削除する場合は、まず、これらのサーバーへの新しい接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="b9c68-112">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="b9c68-113">これを実行するには、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9c68-113">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="b9c68-114">トポロジ ビルダーを開き、追加または必要なサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b9c68-114">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="b9c68-115">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="b9c68-115">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b9c68-p103">トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。</span><span class="sxs-lookup"><span data-stu-id="b9c68-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
4. <span data-ttu-id="b9c68-119">次のコマンドレットを入力して、プールが、リセット、フロント エンド プール内の次の方法のいずれかのサーバーの数を変更した場合: リセット ・ CsPoolRegistrarState ・ ResetType ・ FullReset ・ PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="b9c68-119">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="b9c68-120">2 台から任意の数</span><span class="sxs-lookup"><span data-stu-id="b9c68-120">2 to any</span></span>
    
     - <span data-ttu-id="b9c68-121">任意の数から 2 台</span><span class="sxs-lookup"><span data-stu-id="b9c68-121">Any to 2</span></span>
    
     - <span data-ttu-id="b9c68-122">3 台から任意の数</span><span class="sxs-lookup"><span data-stu-id="b9c68-122">3 to any</span></span>
    
     - <span data-ttu-id="b9c68-123">任意の数から 3 台</span><span class="sxs-lookup"><span data-stu-id="b9c68-123">Any to 3</span></span>
    
5. <span data-ttu-id="b9c68-124">以下のコマンドレットを入力してプールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b9c68-124">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```