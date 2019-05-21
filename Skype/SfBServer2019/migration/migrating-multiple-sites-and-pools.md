---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 は、複数サイトと複数プールの展開をサポートしています。 複数のプールを Skype for Business Server 2019 に移行するプロセスには、次の考慮事項があります。
ms.openlocfilehash: 05a94cb47568b9dfc3834f65f960353ad2933b03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298184"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="92f84-104">複数のサイトとプールの移行</span><span class="sxs-lookup"><span data-stu-id="92f84-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="92f84-105">Skype for Business Server 2019 は、複数サイトと複数プールの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="92f84-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="92f84-106">複数のプールを Skype for Business Server 2019 に移行するプロセスには、次の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="92f84-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="92f84-107">Skype for Business Server 2019 パイロットプールを展開した後、Skype for Business Server 2019 プールに移動されるパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f84-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="92f84-108">たとえば、パイロットプールにユーザーを移動した後、ユーザーの会議ポリシーが Skype for Business Server 2019 に移行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="92f84-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="92f84-109">パイロットプールにエッジサーバーを展開した後、外部ユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f84-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="92f84-110">永続的なチャット、SQL ミラーリング、および XMPP 機能は、Skype for Business Server 2019 では廃止され、Skype for Business Server 2019 機能としては利用できなくなりましたが、以前に展開したことがある場合は、共存環境で続行できます。従来の環境。</span><span class="sxs-lookup"><span data-stu-id="92f84-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="92f84-111">これらの機能を引き続き使用する場合は、特定のユーザーが従来のプールにとどまることができる共存環境を継続することを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f84-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="92f84-112">フェデレーションルートのエッジサーバーをパイロット版の Skype for Business Server 2019 Edge サーバーに移行した後、フェデレーションされたユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f84-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="92f84-113">すべてのユーザーと非ユーザーの連絡先オブジェクトを移動した後、従来のプールが空であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f84-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="92f84-114">従来のプールが空であることを確認した後、プールを非アクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="92f84-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="92f84-115">従来のプールとサーバーを非アクティブ化する方法について詳しくは、「[フェーズ 8: レガシプールの廃止](phase-8-decommission-legacy-pools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92f84-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

