---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 では、複数サイトと複数プールの展開がサポートされています。 複数のプールを Skype for Business Server 2019 に移行するプロセスには、以下の点を考慮する必要があります。
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752659"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="9efec-104">複数のサイトとプールの移行</span><span class="sxs-lookup"><span data-stu-id="9efec-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="9efec-105">Skype for Business Server 2019 では、複数サイトと複数プールの展開がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9efec-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="9efec-106">複数のプールを Skype for Business Server 2019 に移行するプロセスには、以下の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efec-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="9efec-107">Skype for business Server 2019 パイロットプールを展開した後、Skype for Business Server 2019 プールに移動するパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efec-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="9efec-108">たとえば、ユーザーをパイロットプールに移動した後、ユーザーの会議ポリシーが Skype for Business Server 2019 に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9efec-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="9efec-109">パイロットプールにエッジサーバーを展開した後、外部ユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efec-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="9efec-110">常設チャット、SQL ミラーリング、および XMPP の機能は、Skype for business Server 2019 では廃止され、Skype for Business Server 2019 の機能として使用できなくなりましたが、従来の環境で展開されていた場合は、共存環境で続行できます。</span><span class="sxs-lookup"><span data-stu-id="9efec-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="9efec-111">これらの機能を引き続き使用する場合は、特定のユーザーが従来のプールにとどまることがある共存環境で続行することを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efec-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="9efec-112">フェデレーションルートのエッジサーバーを、パイロットの Skype for Business Server 2019 エッジサーバーに移行した後、フェデレーションユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efec-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="9efec-113">すべてのユーザーおよびユーザー以外の連絡先オブジェクトを移動した後、従来のプールが空であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efec-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="9efec-114">従来のプールが空であることを確認した後、プールを非アクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="9efec-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="9efec-115">従来のプールおよびサーバーを非アクティブ化する方法の詳細については、「[フェーズ 8: 従来のプール](phase-8-decommission-legacy-pools.md)を使用停止にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9efec-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

