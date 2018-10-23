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
description: 以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: ec812f569e096d31fb1085d196037677edf5da37
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699275"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="82cef-103">Skype Room System Exchange および Skype アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="82cef-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="82cef-104">以下のトピックでは、Skype Room System 用に Exchange および Skype アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="82cef-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="82cef-105">Skype ルーム システム v2 は、さまざまな依存関係および展開の手順で別の製品です。</span><span class="sxs-lookup"><span data-stu-id="82cef-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="82cef-106">Skype ルーム システム v2 については、Skype ルーム システムのバージョン 2 の[展開の概要](room-systems-v2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82cef-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="82cef-107">Skype ルームのシステム アカウントのプロビジョニングは、組織のトポロジの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="82cef-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="82cef-108">Active Directory の詳細については、「[Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82cef-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="82cef-109">Skype ルーム システム交換の準備&amp;Skype のビジネス アカウント</span><span class="sxs-lookup"><span data-stu-id="82cef-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="82cef-110">次のトピックでは、以下の展開における、Skype Room System Exchange と Skype for Business アカウントのプロビジョニングおよび管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="82cef-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="82cef-111">単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="82cef-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="82cef-112">複数フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="82cef-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="82cef-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="82cef-113">Office 365</span></span>
    
- <span data-ttu-id="82cef-114">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="82cef-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="82cef-115">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="82cef-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="82cef-116">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="82cef-116">Manage Skype Room System accounts</span></span>
    

