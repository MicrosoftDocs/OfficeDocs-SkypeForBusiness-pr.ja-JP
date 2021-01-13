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
description: Skype Room System 用に Exchange と Skype アカウントをプロビジョニングする方法については、以下のトピックを参照してください。
ms.openlocfilehash: fb0b511d8a99d6aa9901459e1ea06d2f05ae4a42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833917"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="18387-103">Skype Room System Exchange および Skype アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="18387-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="18387-104">以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18387-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="18387-105">Microsoft Teams Rooms は、依存関係と展開手順が異なる別の製品です。</span><span class="sxs-lookup"><span data-stu-id="18387-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="18387-106">Microsoft Teams Rooms の詳細については、Microsoft Teams Rooms の展開の概要を [参照してください](room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="18387-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="18387-107">Skype Room System アカウントのプロビジョニングは、組織が持つトポロジの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="18387-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="18387-108">Active Directory トポロジの詳細については [、「Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)の環境要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18387-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="18387-109">Skype Room System Exchange Skype for Business アカウント &amp; のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="18387-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="18387-110">次のトピックでは、Skype Room System Exchange および Skype for Business アカウントをプロビジョニングおよび管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18387-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="18387-111">単一フォレスト オンプレミスの展開</span><span class="sxs-lookup"><span data-stu-id="18387-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="18387-112">複数フォレスト オンプレミスの展開</span><span class="sxs-lookup"><span data-stu-id="18387-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="18387-113">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="18387-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="18387-114">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="18387-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="18387-115">Skype Room System と Skype for Business フェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="18387-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="18387-116">Skype Room System アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="18387-116">Manage Skype Room System accounts</span></span>
    

