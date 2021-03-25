---
title: Skype Room System Exchange および Skype アカウントのプロビジョニング
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 以下のトピックを参照して、Exchange アカウントと Skype アカウントを Skype Room System 用にプロビジョニングする方法について説明します。
ms.openlocfilehash: 0e8c73bc83a62465dc711b4a6f2725f1d9c576f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113063"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="9046c-103">Skype Room System Exchange および Skype アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="9046c-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="9046c-104">以下のトピックを参照して、Exchange アカウントと Skype アカウントを Skype Room System 用にプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9046c-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="9046c-105">Microsoft Teams Rooms は、依存関係と展開手順が異なる別の製品です。</span><span class="sxs-lookup"><span data-stu-id="9046c-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="9046c-106">Microsoft Teams Rooms の詳細については、「Microsoft Teams Rooms の展開の概要」 [を参照してください](/MicrosoftTeams/rooms/rooms-deploy)。</span><span class="sxs-lookup"><span data-stu-id="9046c-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](/MicrosoftTeams/rooms/rooms-deploy).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9046c-107">Skype Room System アカウントのプロビジョニングは、組織が持つトポロジの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9046c-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="9046c-108">Active Directory トポロジの詳細については [、「Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)の環境要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9046c-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="9046c-109">Skype Room System Exchange &amp; Skype for Business アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="9046c-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="9046c-110">次のトピックでは、Skype Room System Exchange および Skype for Business アカウントをプロビジョニングおよび管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9046c-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="9046c-111">単一フォレスト オンプレミスの展開</span><span class="sxs-lookup"><span data-stu-id="9046c-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="9046c-112">複数フォレスト オンプレミスの展開</span><span class="sxs-lookup"><span data-stu-id="9046c-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="9046c-113">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="9046c-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="9046c-114">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="9046c-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="9046c-115">Skype Room System と Skype for Business フェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="9046c-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="9046c-116">Skype Room System アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="9046c-116">Manage Skype Room System accounts</span></span>
