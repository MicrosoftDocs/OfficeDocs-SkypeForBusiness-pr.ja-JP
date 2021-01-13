---
title: Skype for Business Server で場所ポリシースコープを割り当てる
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 展開環境での E9-1-1 展開の場所ポリシーのエンタープライズ VoIP。
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825527"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="56d0b-103">Skype for Business Server で場所ポリシースコープを割り当てる</span><span class="sxs-lookup"><span data-stu-id="56d0b-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="56d0b-104">Skype for Business Server 展開環境での E9-1-1 展開の場所ポリシーのエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="56d0b-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="56d0b-105">他の Skype for Business Server ポリシーと同様に、場所ポリシーは、グローバル、サイト、ユーザーの複数のスコープ レベルで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="56d0b-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="56d0b-106">ただし、ユーザー レベルの場所ポリシーのスコープの動作は、他の Skype for Business Server ポリシーとは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="56d0b-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="56d0b-107">ユーザー単位の場所ポリシーをエンドポイント オブジェクト (ユーザーや共通領域電話の連絡先オブジェクトなど) に適用できるだけでなく、Skype for Business Server ネットワーク サイトにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="56d0b-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="56d0b-108">ネットワーク サイトは、地理的場所に関連付けられたクライアント サブネットをグループ化したものです (ただし、必ずしも中央サイトまたはブランチ サイト全体の中のすべてのサブネットである必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="56d0b-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="56d0b-109">ネットワーク サイト内のサブネットに接続されるクライアントはすべて、そのネットワーク サイトに割り当てられた場所ポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="56d0b-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="56d0b-110">ユーザー レベルの場所ポリシーがユーザーとネットワーク サイトの両方に割り当てられる場合、ネットワーク サイト ベースの場所ポリシーがユーザーごとのポリシー設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="56d0b-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="56d0b-111">各ネットワーク サイトにはそれぞれに割り当てられた場所ポリシーがあり、各ポリシーには異なる PSTN 使用法、通知 URI、および電話会議 URI の値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="56d0b-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56d0b-112">このようにポリシー スコープが特殊な動作をするのは、ある支店のプールに所属するユーザーが別の支店を訪れていて、緊急電話を発信する場合、ユーザーに割り当てられたプールまたはサイトに関係なく、そのネットワーク サイトに適した E9-1-1 通話ルーティング設定が適用されるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="56d0b-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

