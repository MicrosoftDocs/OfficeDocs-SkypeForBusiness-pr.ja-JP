---
title: フロント エンドとエッジの関連付け
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: 各フロントエンド プールに関連付けられるエッジ サーバーまたはエッジ プールは 1 つのみです。 サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。 フェデレーション ユーザーのサポートを有効にし、特定のパブリック インスタント メッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポート、および匿名ユーザーのサポートを有効にできます。
ms.openlocfilehash: 57f8a7d2a62f1246ac74931491b9244f3aca0a0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811337"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="1adae-105">フロント エンドとエッジの関連付け</span><span class="sxs-lookup"><span data-stu-id="1adae-105">Associate Front End With Edge</span></span>

<span data-ttu-id="1adae-106">各フロントエンド プールに関連付けられるエッジ サーバーまたはエッジ プールは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="1adae-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="1adae-107">サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="1adae-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="1adae-108">フェデレーション ユーザーのサポートを有効にし、特定のパブリック インスタント メッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポート、および匿名ユーザーのサポートを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1adae-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="1adae-109">1 つのサイトのすべてのプール、および複数の中央サイトのプールは、使用量がエッジ サーバーの容量を超えない場合に、同じエッジ サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1adae-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="1adae-110">拡張を含む監視の詳細については、「計画」のドキュメントの「[Planning for External User Access (外部ユーザー アクセスの計画)](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1adae-110">For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation.</span></span> <span data-ttu-id="1adae-111">外部ユーザー アクセスをサポートするトポロジ設計の詳細については、「展開」のドキュメントの「[Define Your Edge Topology (エッジ トポロジの設計)](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1adae-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


