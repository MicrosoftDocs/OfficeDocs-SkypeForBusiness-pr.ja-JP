---
title: 修正プログラムを適用またはビジネスのサーバーの Skype でのフロント エンド サーバーを更新します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: '概要: は、Skype でのフロント エンド サーバーにビジネスのサーバーのアップグレードやパッチを適用する方法を説明します。'
ms.openlocfilehash: 29191192b1dab16b79cc594cc0a7b3b68aaa906f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972773"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="a5578-103">修正プログラムを適用またはビジネスのサーバーの Skype でのフロント エンド サーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="a5578-103">Patch or update Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="a5578-104">**の概要:** Skype でのフロント エンド サーバーにビジネスのサーバーのアップグレードやパッチを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5578-104">**Summary:** learn how to apply upgrades or patches to Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="a5578-105">フロント エンド プール内のサーバーにパッチを適用するときは、同時に、1 つのサーバーを行います。</span><span class="sxs-lookup"><span data-stu-id="a5578-105">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="a5578-106">プール内のフロントエンド サーバーにアップグレードを適用する</span><span class="sxs-lookup"><span data-stu-id="a5578-106">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="a5578-107">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="a5578-107">Type the following cmdlet:</span></span>
    
  ```
  Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
  ```

     <span data-ttu-id="a5578-108">このコマンドレットで不足しているレプリカが示された場合は、次のコマンドレットでプールを復元してから、パッチを適用してください。</span><span class="sxs-lookup"><span data-stu-id="a5578-108">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
  ```
  Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
  ```

2. <span data-ttu-id="a5578-109">パッチを適用する最初のサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5578-109">On the first server you want to patch, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="a5578-110">このコマンドレットでは、すべてのサービスを他のプール内のフロント エンド サーバーに移動し、このサーバーは、オフラインです。</span><span class="sxs-lookup"><span data-stu-id="a5578-110">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="a5578-111">このサーバーにアップグレードまたはパッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="a5578-111">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="a5578-112">アップグレードしたサーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5578-112">On the upgraded server, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="a5578-113">サーバーがサービスに復帰します。</span><span class="sxs-lookup"><span data-stu-id="a5578-113">The server is returned to service.</span></span>
    
5. <span data-ttu-id="a5578-114">アップグレードが必要なサーバーごとに、手順 2 ～ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a5578-114">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    

