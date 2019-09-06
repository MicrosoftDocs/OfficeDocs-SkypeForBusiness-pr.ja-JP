---
title: Skype Room System Exchange および Skype アカウントのプロビジョニング
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: 5c713a417c35147fbcd3e49a1f841a01ab18fe4d
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774736"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="afa3f-103">Skype Room System Exchange および Skype アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="afa3f-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="afa3f-104">以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="afa3f-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="afa3f-105">Microsoft Teams のルームは、依存関係と展開手順が異なるさまざまな製品です。</span><span class="sxs-lookup"><span data-stu-id="afa3f-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="afa3f-106">Microsoft Teams のルームについては、「Microsoft Teams の会議室の[展開の概要](room-systems-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afa3f-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="afa3f-107">Skype Room System アカウントのプロビジョニングは、組織で使用しているトポロジの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="afa3f-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="afa3f-108">Active Directory の詳細については、「[Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="afa3f-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="afa3f-109">Skype Room System Exchange &amp; Skype For business アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="afa3f-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="afa3f-110">次のトピックでは、以下の展開における、Skype Room System Exchange と Skype for Business アカウントのプロビジョニングおよび管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="afa3f-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="afa3f-111">単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="afa3f-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="afa3f-112">複数フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="afa3f-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="afa3f-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="afa3f-113">Office 365</span></span>
    
- <span data-ttu-id="afa3f-114">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="afa3f-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="afa3f-115">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="afa3f-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="afa3f-116">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="afa3f-116">Manage Skype Room System accounts</span></span>
    

