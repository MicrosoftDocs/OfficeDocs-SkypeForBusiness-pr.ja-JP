---
title: Skype Room System Exchange および Skype アカウントのプロビジョニング
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: 1e6674c869e69611bbb405112d5a781eae502084
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893337"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="5046e-103">Skype Room System Exchange および Skype アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="5046e-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="5046e-104">以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5046e-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="5046e-105">マイクロソフト チームの会議室は、さまざまな依存関係および展開の手順で別の製品です。</span><span class="sxs-lookup"><span data-stu-id="5046e-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="5046e-106">マイクロソフト チームの会議室については、マイクロソフト チームの会議室[の配置の概要](room-systems-v2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5046e-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5046e-107">Skype ルームのシステム アカウントのプロビジョニングは、組織のトポロジの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5046e-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="5046e-108">Active Directory の詳細については、「[Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5046e-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="5046e-109">Skype ルーム システム交換の準備&amp;Skype のビジネス アカウント</span><span class="sxs-lookup"><span data-stu-id="5046e-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="5046e-110">次のトピックでは、以下の展開における、Skype Room System Exchange と Skype for Business アカウントのプロビジョニングおよび管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5046e-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="5046e-111">単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="5046e-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="5046e-112">複数フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="5046e-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="5046e-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="5046e-113">Office 365</span></span>
    
- <span data-ttu-id="5046e-114">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="5046e-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="5046e-115">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="5046e-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="5046e-116">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="5046e-116">Manage Skype Room System accounts</span></span>
    

