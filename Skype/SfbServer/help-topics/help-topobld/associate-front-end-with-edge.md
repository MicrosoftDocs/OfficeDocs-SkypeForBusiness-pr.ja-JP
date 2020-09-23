---
title: フロントエンドとエッジの関連付け
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: 各フロントエンドプールには、エッジサーバーまたはエッジプールを1つだけ関連付けることができます。 サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。 また、フェデレーションユーザーのサポートを有効にすることもできます。これには、特定のパブリックインスタントメッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポートや、匿名ユーザーのサポートを含めることができます。
ms.openlocfilehash: cc804ed9a21b81ce0315664bcb1b3530e8087584
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217758"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="205a1-105">フロントエンドとエッジの関連付け</span><span class="sxs-lookup"><span data-stu-id="205a1-105">Associate Front End With Edge</span></span>

<span data-ttu-id="205a1-106">各フロントエンドプールには、エッジサーバーまたはエッジプールを1つだけ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="205a1-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="205a1-107">サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="205a1-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="205a1-108">また、フェデレーションユーザーのサポートを有効にすることもできます。これには、特定のパブリックインスタントメッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポートや、匿名ユーザーのサポートを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="205a1-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="205a1-109">サイトのすべてのプールと複数のセントラルサイトのプールは、使用量がエッジサーバーの容量を超えていない場合は、同じエッジサーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="205a1-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="205a1-110">拡張を含む監視の詳細については、「計画」のドキュメントの「[Planning for External User Access (外部ユーザー アクセスの計画)](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="205a1-110">For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation.</span></span> <span data-ttu-id="205a1-111">外部ユーザー アクセスをサポートするトポロジ設計の詳細については、「展開」のドキュメントの「[Define Your Edge Topology (エッジ トポロジの設計)](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="205a1-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


