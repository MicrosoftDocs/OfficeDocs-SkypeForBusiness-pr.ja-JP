---
title: Skype Room System Exchange および Skype アカウントのプロビジョニング
ms.author: v-lanac
author: lanachin
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
description: 以下のトピックでは、Skype Room System の Exchange および Skype アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: be43e732a97dc81fdd2e3a6bdb355afaff4db37d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220917"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="41c55-103">Skype Room System Exchange および Skype アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="41c55-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="41c55-104">以下のトピックでは、Skype Room System の Exchange および Skype アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41c55-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="41c55-105">Microsoft Teams ルームは、依存関係と展開手順が異なるさまざまな製品です。</span><span class="sxs-lookup"><span data-stu-id="41c55-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="41c55-106">Microsoft Teams ルームの詳細については、「Microsoft Teams ルームの[展開の概要](room-systems-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41c55-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="41c55-107">Skype Room System アカウントのプロビジョニングは、組織のトポロジの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="41c55-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="41c55-108">Active Directory トポロジの詳細については、「 [Skype For Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41c55-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="41c55-109">Skype Room System Exchange &amp; skype For Business アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="41c55-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="41c55-110">次のトピックでは、Skype Room System Exchange および Skype for Business アカウントをプロビジョニングおよび管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41c55-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="41c55-111">単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="41c55-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="41c55-112">複数フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="41c55-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="41c55-113">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="41c55-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="41c55-114">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="41c55-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="41c55-115">Skype Room System および Skype for Business フェデレーションパートナー</span><span class="sxs-lookup"><span data-stu-id="41c55-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="41c55-116">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="41c55-116">Manage Skype Room System accounts</span></span>
    

