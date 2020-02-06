---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 は、複数サイトと複数プールの展開をサポートしています。 複数のプールを Skype for Business Server 2019 に移行するプロセスには、次の考慮事項があります。
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813445"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="32d73-104">複数のサイトとプールの移行</span><span class="sxs-lookup"><span data-stu-id="32d73-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="32d73-105">Skype for Business Server 2019 は、複数サイトと複数プールの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="32d73-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="32d73-106">複数のプールを Skype for Business Server 2019 に移行するプロセスには、次の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="32d73-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="32d73-107">Skype for Business Server 2019 パイロットプールを展開した後、Skype for Business Server 2019 プールに移動されるパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d73-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="32d73-108">たとえば、パイロットプールにユーザーを移動した後、ユーザーの会議ポリシーが Skype for Business Server 2019 に移行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="32d73-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="32d73-109">パイロットプールにエッジサーバーを展開した後、外部ユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d73-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="32d73-110">永続的なチャット、SQL ミラーリング、および XMPP 機能は、Skype for Business Server 2019 では廃止され、Skype for Business Server 2019 機能としては利用できなくなりましたが、以前に展開したことがある場合は、共存環境で続行できます。従来の環境。</span><span class="sxs-lookup"><span data-stu-id="32d73-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="32d73-111">これらの機能を引き続き使用する場合は、特定のユーザーが従来のプールにとどまることができる共存環境を継続することを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d73-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="32d73-112">フェデレーションルートのエッジサーバーをパイロット版の Skype for Business Server 2019 Edge サーバーに移行した後、フェデレーションされたユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d73-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="32d73-113">すべてのユーザーと非ユーザーの連絡先オブジェクトを移動した後、従来のプールが空であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d73-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="32d73-114">従来のプールが空であることを確認した後、プールを非アクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="32d73-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="32d73-115">従来のプールとサーバーを非アクティブ化する方法について詳しくは、「[フェーズ 8: レガシプールの廃止](phase-8-decommission-legacy-pools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32d73-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

