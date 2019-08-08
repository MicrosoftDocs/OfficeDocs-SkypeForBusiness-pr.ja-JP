---
title: Skype Room System Exchange および Skype アカウントのプロビジョニング
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: a7a5a860d00cc88b068e9e415f27da37c0bfc814
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234717"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="2c8f0-103">Skype Room System Exchange および Skype アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="2c8f0-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="2c8f0-104">以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c8f0-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="2c8f0-105">Microsoft Teams のルームは、依存関係と展開手順が異なるさまざまな製品です。</span><span class="sxs-lookup"><span data-stu-id="2c8f0-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="2c8f0-106">Microsoft Teams のルームについては、「Microsoft Teams の会議室の[展開の概要](room-systems-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c8f0-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c8f0-107">Skype Room System アカウントのプロビジョニングは、組織で使用しているトポロジの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2c8f0-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="2c8f0-108">Active Directory の詳細については、「[Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c8f0-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="2c8f0-109">Skype Room System Exchange &amp; Skype For business アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="2c8f0-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="2c8f0-110">次のトピックでは、以下の展開における、Skype Room System Exchange と Skype for Business アカウントのプロビジョニングおよび管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c8f0-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="2c8f0-111">単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="2c8f0-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="2c8f0-112">複数フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="2c8f0-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="2c8f0-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="2c8f0-113">Office 365</span></span>
    
- <span data-ttu-id="2c8f0-114">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="2c8f0-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="2c8f0-115">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="2c8f0-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="2c8f0-116">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="2c8f0-116">Manage Skype Room System accounts</span></span>
    

