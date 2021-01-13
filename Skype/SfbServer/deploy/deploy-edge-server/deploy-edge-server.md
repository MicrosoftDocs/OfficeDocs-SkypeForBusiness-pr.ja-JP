---
title: Skype for Business Server でのエッジ サーバーの展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: '概要: Skype for Business Server 環境にエッジ サーバーまたはエッジ プールを展開する方法について学習します。'
ms.openlocfilehash: edd2ff501320c4252b8032d1528ede7b83b8fcd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804387"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="8282f-103">Skype for Business Server でのエッジ サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="8282f-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="8282f-104">**概要:** Skype for Business Server 環境にエッジ サーバーまたはエッジ プールを展開する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="8282f-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="8282f-105">Skype for Business Server 環境にエッジ サーバーまたはエッジ プールを展開する理由</span><span class="sxs-lookup"><span data-stu-id="8282f-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="8282f-106">組織の内部ネットワークにログインしていない外部ユーザーが内部ユーザーと対話できる必要がある場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="8282f-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="8282f-107">これらの外部ユーザーは、認証された匿名リモート ユーザー、フェデレーション パートナー、または他のモバイル クライアントである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8282f-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="8282f-108">Skype for Business Server 向けエッジの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="8282f-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="8282f-109">上で説明したように、多くの場合、Skype for Business Server のエッジ サーバーの展開に取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8282f-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="8282f-110">このチェックリストでは、実行する必要があるタスクの概要と、より詳細な手順へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="8282f-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="8282f-111">「Plan [for Edge Server deployments in Skype for Business Server」セクションで始まったらと思](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) います。</span><span class="sxs-lookup"><span data-stu-id="8282f-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="8282f-112">参照されていない場合は、参照する多くの情報について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8282f-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="8282f-113">展開セクションには手順だけが含まれているので、これらの手順の背後にある理由を知りたい場合は、計画を立て始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8282f-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="8282f-114">このドキュメントでは、Skype for Business Server の基本展開が既に完了している場合も仮定しています。</span><span class="sxs-lookup"><span data-stu-id="8282f-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="8282f-115">その展開をエッジと並べて実行している可能性がありますが、最初にこれらの手順を実行する必要があります。次に、ここに記載されているエッジのトポロジを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8282f-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="8282f-116">以下に、従う必要がある大きな手順と、それらの手順を見つける場所を示します。</span><span class="sxs-lookup"><span data-stu-id="8282f-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="8282f-117">Skype for Business Server のエッジ サーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="8282f-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="8282f-118">Skype for Business Server のエッジ サーバーの環境要件</span><span class="sxs-lookup"><span data-stu-id="8282f-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="8282f-119">Skype for Business Server のエッジ トポロジを作成する</span><span class="sxs-lookup"><span data-stu-id="8282f-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="8282f-120">Skype for Business Server でのエッジ サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="8282f-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="8282f-121">Skype for Business Server でのエッジ展開の検証</span><span class="sxs-lookup"><span data-stu-id="8282f-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

