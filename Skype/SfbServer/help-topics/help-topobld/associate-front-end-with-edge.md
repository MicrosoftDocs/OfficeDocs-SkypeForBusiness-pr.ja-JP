---
title: フロントエンドとエッジの関連付け
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: 各フロントエンド プールには、エッジ サーバーまたはエッジ プールを 1 つだけ関連付けることができます。サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。また、フェデレーション ユーザーのサポートも有効にすることができますが、この場合は、特定のパブリック インスタント メッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポート、および匿名ユーザーのサポートを含めることができます。
ms.openlocfilehash: 719a9375cfab8c5e8b6f102315eaf12b4f30ff97
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879231"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="b415d-105">フロントエンドとエッジの関連付け</span><span class="sxs-lookup"><span data-stu-id="b415d-105">Associate Front End With Edge</span></span>

<span data-ttu-id="b415d-p102">各フロントエンド プールには、エッジ サーバーまたはエッジ プールを 1 つだけ関連付けることができます。サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。また、フェデレーション ユーザーのサポートも有効にすることができますが、この場合は、特定のパブリック インスタント メッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポート、および匿名ユーザーのサポートを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b415d-p102">Each Front End pool can have only one Edge Server or Edge pool associated with it. When you enable external user access for a site, you can provide support for remote users. You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="b415d-p103">1 つのサイトのすべてのプールと複数のセントラル サイトのプールでは、使用量がエッジ サーバーの処理能力を超えない限り、同じエッジ サーバーを使用できます。拡張を含む監視の詳細については、「計画」のドキュメントの「[Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)」を参照してください。外部ユーザー アクセスをサポートするトポロジ設計の詳細については、「展開」のドキュメントの「[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b415d-p103">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server. For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation. For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


