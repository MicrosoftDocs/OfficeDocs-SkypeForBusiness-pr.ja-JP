---
title: Skype Room System Exchange および Skype アカウントのプロビジョニング
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: 2da978d84ac763a27bba135e1899e83955b4fb53
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012555"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="f4542-103">Skype Room System Exchange および Skype アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="f4542-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="f4542-104">以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4542-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="f4542-105">マイクロソフト チームの会議室は、さまざまな依存関係および展開の手順で別の製品です。</span><span class="sxs-lookup"><span data-stu-id="f4542-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="f4542-106">マイクロソフト チームの会議室については、マイクロソフト チームの会議室[の配置の概要](room-systems-v2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4542-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4542-107">Skype ルームのシステム アカウントのプロビジョニングは、組織のトポロジの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f4542-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="f4542-108">Active Directory の詳細については、「[Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f4542-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="f4542-109">Skype ルーム システム交換の準備&amp;Skype のビジネス アカウント</span><span class="sxs-lookup"><span data-stu-id="f4542-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="f4542-110">次のトピックでは、以下の展開における、Skype Room System Exchange と Skype for Business アカウントのプロビジョニングおよび管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4542-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="f4542-111">単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="f4542-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="f4542-112">複数フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="f4542-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="f4542-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="f4542-113">Office 365</span></span>
    
- <span data-ttu-id="f4542-114">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="f4542-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="f4542-115">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="f4542-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="f4542-116">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="f4542-116">Manage Skype Room System accounts</span></span>
    

