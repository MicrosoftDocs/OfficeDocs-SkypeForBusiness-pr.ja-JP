---
title: ビジネスのサーバーの場所ポリシーのスコープでは、Skype を割り当てる
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: ~ 9-1-1 展開のビジネス サーバーのエンタープライズ VoIP の Skype の場所のポリシーを計画します。
ms.openlocfilehash: 28759d88be1586149b0dd482d934c5bbc89a1853
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881887"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="b718e-103">ビジネスのサーバーの場所ポリシーのスコープでは、Skype を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b718e-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="b718e-104">~ 9-1-1 展開のビジネス サーバーのエンタープライズ VoIP の Skype の場所のポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="b718e-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b718e-105">ビジネス サーバー ポリシーの他の Skype で、複数のスコープ レベルでの場所のポリシーを割り当てることができるよう: グローバル、サイト、およびユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b718e-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="b718e-106">ただし、ユーザー レベルの場所のポリシーのスコープの動作とは異なるビジネス サーバー ポリシーの他の Skype でのビット。</span><span class="sxs-lookup"><span data-stu-id="b718e-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="b718e-107">だけでなく、ユーザーごとの場所のポリシー適用できます (ユーザー、共通領域電話の連絡先オブジェクトなど) は、エンドポイントのオブジェクトにも適用できます Skype をビジネス サーバー ネットワークのサイトです。</span><span class="sxs-lookup"><span data-stu-id="b718e-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="b718e-108">ネットワーク サイトは、地理的場所に関連付けられたクライアント サブネットをグループ化したものです (ただし、必ずしも中央サイトまたはブランチ サイト全体の中のすべてのサブネットである必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="b718e-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="b718e-109">ネットワーク サイト内のサブネットに接続されるクライアントはすべて、そのネットワーク サイトに割り当てられた場所ポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="b718e-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="b718e-110">ユーザー レベルの場所ポリシーがユーザーとネットワーク サイトの両方に割り当てられる場合、ネットワーク サイト ベースの場所ポリシーがユーザーごとのポリシー設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="b718e-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="b718e-111">各ネットワーク サイトにはそれぞれに割り当てられた場所ポリシーがあり、各ポリシーには異なる PSTN 使用法、通知 URI、および電話会議 URI の値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b718e-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b718e-112">このようにポリシー スコープが特殊な動作をするのは、ある支店のプールに所属するユーザーが別の支店を訪れていて、緊急電話を発信する場合、ユーザーに割り当てられたプールまたはサイトに関係なく、そのネットワーク サイトに適した E9-1-1 通話ルーティング設定が適用されるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="b718e-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

