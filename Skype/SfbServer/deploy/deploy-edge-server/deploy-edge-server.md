---
title: Skype for Business Server でエッジサーバーを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: '概要: エッジサーバーまたはエッジプールを Skype for Business Server 環境に展開する方法について説明します。'
ms.openlocfilehash: bcb6f7fdd7b322411e793fe3466418db1dd00894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306952"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="c1fcc-103">Skype for Business Server でエッジサーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="c1fcc-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="c1fcc-104">**概要:** エッジサーバーまたはエッジプールを Skype for Business Server 環境に展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="c1fcc-105">エッジサーバーまたはエッジプールを Skype for Business Server 環境に展開する理由</span><span class="sxs-lookup"><span data-stu-id="c1fcc-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="c1fcc-106">組織の内部ネットワークにログインしていない外部ユーザーが内部ユーザーとやり取りできるようにする必要がある場合は、この方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="c1fcc-107">これらの外部ユーザーは、認証されたリモートユーザー、フェデレーションパートナー、またはその他のモバイルクライアントを認証することができます。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="c1fcc-108">エッジの展開チェックリスト (Skype for Business Server の場合)</span><span class="sxs-lookup"><span data-stu-id="c1fcc-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="c1fcc-109">上で説明したように、多くの場合、Skype for Business Server 向け Edge Server 展開に入ります。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="c1fcc-110">このチェックリストは、実行する必要があるタスクの概要と、より詳細な手順へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="c1fcc-111">「 [Skype For Business server で Edge server を展開するための計画](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)」を開始することを願っています。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="c1fcc-112">それ以外の場合は、ここで参照する多くの事項について、以下で詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="c1fcc-113">展開に関するセクションには手順のみが掲載されているため、それらの手順の背後にある理由を知りたいと考える場合は、計画から読み始めるのが適切です。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="c1fcc-114">このドキュメントは、Skype for Business Server の基本的な展開も完了していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="c1fcc-115">この展開を Edge と並行して実行することもありますが、これらの手順を最初に実行する必要があります。その後で、ここに記載されているエッジのトポロジを変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="c1fcc-116">これらは、実行する必要のある手順に関する概要の一覧であり、これらの手順に関する詳細は、参照先に掲載されています。</span><span class="sxs-lookup"><span data-stu-id="c1fcc-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="c1fcc-117">Skype for Business Server での Edge Server システム要件</span><span class="sxs-lookup"><span data-stu-id="c1fcc-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="c1fcc-118">Skype for Business Server での Edge Server の環境要件</span><span class="sxs-lookup"><span data-stu-id="c1fcc-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="c1fcc-119">Skype for Business Server の Edge トポロジを作成する</span><span class="sxs-lookup"><span data-stu-id="c1fcc-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="c1fcc-120">Skype for Business Server でエッジサーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="c1fcc-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="c1fcc-121">Skype for Business Server での Edge の展開を検証する</span><span class="sxs-lookup"><span data-stu-id="c1fcc-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

