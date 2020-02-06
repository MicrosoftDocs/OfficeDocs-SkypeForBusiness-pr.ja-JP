---
title: Skype for Business Server で位置情報ポリシーのスコープを割り当てる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Skype for Business Server Enterprise Voice での E9 展開のための位置情報ポリシーを計画しています。
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802757"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="5fba8-103">Skype for Business Server で位置情報ポリシーのスコープを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5fba8-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="5fba8-104">Skype for Business Server Enterprise Voice での E9 展開のための位置情報ポリシーを計画しています。</span><span class="sxs-lookup"><span data-stu-id="5fba8-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="5fba8-105">他の Skype for Business Server ポリシーと同じように、場所ポリシーは、グローバル、サイト、ユーザーという複数のスコープレベルで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5fba8-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="5fba8-106">ただし、ユーザーレベルの位置情報ポリシーの範囲は、他の Skype for Business Server のポリシーとは少し異なる動作をします。</span><span class="sxs-lookup"><span data-stu-id="5fba8-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="5fba8-107">ユーザーごとの場所ポリシーをエンドポイントオブジェクト (ユーザー、一般的なエリア電話の連絡先オブジェクトなど) に適用できるだけでなく、Skype for Business Server ネットワークサイトにも適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5fba8-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="5fba8-108">ネットワーク サイトは、地理的場所に関連付けられたクライアント サブネットをグループ化したものです (ただし、必ずしも中央サイトまたはブランチ サイト全体の中のすべてのサブネットである必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="5fba8-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="5fba8-109">ネットワーク サイト内のサブネットに接続されるクライアントはすべて、そのネットワーク サイトに割り当てられた場所ポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="5fba8-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="5fba8-110">ユーザー レベルの場所ポリシーがユーザーとネットワーク サイトの両方に割り当てられる場合、ネットワーク サイト ベースの場所ポリシーがユーザーごとのポリシー設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="5fba8-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="5fba8-111">各ネットワーク サイトにはそれぞれに割り当てられた場所ポリシーがあり、各ポリシーには異なる PSTN 使用法、通知 URI、および電話会議 URI の値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5fba8-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5fba8-112">このようにポリシー スコープが特殊な動作をするのは、ある支店のプールに所属するユーザーが別の支店を訪れていて、緊急電話を発信する場合、ユーザーに割り当てられたプールまたはサイトに関係なく、そのネットワーク サイトに適した E9-1-1 通話ルーティング設定が適用されるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="5fba8-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

