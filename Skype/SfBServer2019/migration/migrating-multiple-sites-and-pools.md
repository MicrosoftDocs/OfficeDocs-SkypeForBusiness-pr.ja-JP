---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 の Skype では、複数のサイトおよび複数プール展開をサポートします。 ビジネス サーバー 2019 の Skype を複数のプールを移行するプロセスには、次の考慮事項が必要です。
ms.openlocfilehash: 5e369adb51bf95f4e3c3d12688d1e39611aa5692
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231638"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="fc112-104">複数のサイトとプールの移行</span><span class="sxs-lookup"><span data-stu-id="fc112-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="fc112-105">ビジネス サーバー 2019 の Skype では、複数のサイトおよび複数プール展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="fc112-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="fc112-106">ビジネス サーバー 2019 の Skype を複数のプールを移行するプロセスには、次の考慮事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="fc112-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="fc112-107">Skype のビジネス サーバー 2019 パイロット プールを配置すた後には、ビジネス サーバー 2019 プール、およびユーザーの機能を検証するための方法論、Skype を移動するパイロットのユーザーのサブセットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc112-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="fc112-108">たとえば、ユーザーをパイロット プールに移動した後のビジネス サーバー 2019 Skype に移動したユーザーの会議ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="fc112-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="fc112-109">パイロット プールにエッジ サーバーを展開するには後に、外部のユーザーがビジネス サーバー 2019 プールの Skype で通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc112-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="fc112-110">永続的なチャット、SQL のミラーリング、および XMPP の機能は、ビジネス サーバー 2019 の Skype では廃止され、ビジネス サーバー 2019 機能では、不要になった Skype としての利用可能なですが、以前に展開した場合の共存環境で続けることができます、従来の環境です。</span><span class="sxs-lookup"><span data-stu-id="fc112-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="fc112-111">これらの機能を使用して続行する場合は、引き続き共存環境では、特定のユーザーが、従来のプールに残ります。 計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc112-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="fc112-112">ビジネス サーバー 2019 エッジ サーバーのパイロットの Skype にエッジ サーバーのフェデレーション ルートの処理中後に、、フェデレーション ユーザーが、ビジネス サーバー 2019 プールの Skype で通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc112-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="fc112-113">すべてのユーザーおよびユーザー以外のユーザーの連絡先オブジェクトを移動するには後に、、レガシ プールが空であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc112-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="fc112-114">従来のプールが空であることを確認した後、プールを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="fc112-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="fc112-115">レガシ プールとサーバーを非アクティブ化する方法の詳細についてを参照してください[フェーズ 8: 従来のプールを非コミッションに](phase-8-decommission-legacy-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="fc112-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

