---
title: フロントエンドとエッジの関連付け
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: 各フロントエンド プールには、エッジ サーバーまたはエッジ プールを 1 つだけ関連付けることができます。サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。また、フェデレーション ユーザーのサポートも有効にすることができますが、この場合は、特定のパブリック インスタント メッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポート、および匿名ユーザーのサポートを含めることができます。
ms.openlocfilehash: 79c4a17f1d59a071470534915f5421e964f59d1b
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21063064"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="03019-105">フロントエンドとエッジの関連付け</span><span class="sxs-lookup"><span data-stu-id="03019-105">Associate Front End With Edge</span></span>
 
<span data-ttu-id="03019-p102">各フロントエンド プールには、エッジ サーバーまたはエッジ プールを 1 つだけ関連付けることができます。サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。また、フェデレーション ユーザーのサポートも有効にすることができますが、この場合は、特定のパブリック インスタント メッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポート、および匿名ユーザーのサポートを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="03019-p102">Each Front End pool can have only one Edge Server or Edge pool associated with it. When you enable external user access for a site, you can provide support for remote users. You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>
  
<span data-ttu-id="03019-109">1 つのサイトのすべてのプールと複数のセントラル サイトのプールでは、使用量がエッジ サーバーの処理能力を超えない限り、同じエッジ サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="03019-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="03019-110">監視の詳細については、拡大・縮小などを参照してください[外部ユーザー アクセスの計画](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)計画マニュアルを参照します。</span><span class="sxs-lookup"><span data-stu-id="03019-110">For details about monitoring, including scaling, see [Planning for External User Access](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation.</span></span> <span data-ttu-id="03019-111">外部ユーザー アクセスをサポートするトポロジの設計についての詳細は、展開に関するドキュメントで[エッジ トポロジの定義](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03019-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>
  

