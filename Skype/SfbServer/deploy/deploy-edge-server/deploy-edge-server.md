---
title: ビジネス サーバーの Skype にエッジ サーバーを展開します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 概要では、エッジ サーバーまたはエッジ プールに、Skype をビジネスのサーバー環境に展開する方法について説明します。
ms.openlocfilehash: 8ac91d87e8ce7e7fb4b2f8ba0cb80331a3ad9cca
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883888"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="39efa-103">ビジネス サーバーの Skype にエッジ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="39efa-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="39efa-104">**の概要:** エッジ サーバーまたはエッジ プールに、Skype をビジネスのサーバー環境に展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39efa-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="39efa-105">導入する理由、エッジ サーバーまたはエッジ プールは、ビジネスのサーバー環境で、Skype にしますか。</span><span class="sxs-lookup"><span data-stu-id="39efa-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="39efa-106">内部ユーザーと対話することができるように、組織の内部ネットワークにログインしていない外部のユーザーが必要な場合、それは必要があります。</span><span class="sxs-lookup"><span data-stu-id="39efa-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="39efa-107">これらの外部ユーザーが認証ユーザーと匿名のリモート ユーザー、フェデレーション パートナー、またはその他のモバイル クライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="39efa-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="39efa-108">Skype ビジネス サーバーのため、エッジの展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="39efa-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="39efa-109">前述したように、多くが、Skype のエッジ サーバーの展開にビジネス サーバーの移動します。</span><span class="sxs-lookup"><span data-stu-id="39efa-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="39efa-110">このチェックリストを使用するより詳細な手順を実行するには、する必要がありますタスクとリンクの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="39efa-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="39efa-111">[Skype ビジネス サーバー用にエッジ サーバーの展開計画](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)に記載し始めていることを願っています。</span><span class="sxs-lookup"><span data-stu-id="39efa-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="39efa-112">それ以外の場合は、ここで参照する多くの事項について、以下で詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="39efa-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="39efa-113">展開に関するセクションには手順のみが掲載されているため、それらの手順の背後にある理由を知りたいと考える場合は、計画から読み始めるのが適切です。</span><span class="sxs-lookup"><span data-stu-id="39efa-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="39efa-114">このドキュメント、ビジネス サーバー用の Skype の基本的な展開を行ったことがあるもを練習します。</span><span class="sxs-lookup"><span data-stu-id="39efa-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="39efa-115">可能性があります行うその展開サイド バイ サイドのエッジを持つが、最初に、これらの手順を実行する必要は、ことができますここに記載されているエッジ トポロジを変更するには</span><span class="sxs-lookup"><span data-stu-id="39efa-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="39efa-116">これらは、実行する必要のある手順に関する概要の一覧であり、これらの手順に関する詳細は、参照先に掲載されています。</span><span class="sxs-lookup"><span data-stu-id="39efa-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="39efa-117">Skype のビジネス サーバーのサーバーのシステム要件をエッジします。</span><span class="sxs-lookup"><span data-stu-id="39efa-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="39efa-118">Skype のビジネス サーバーのサーバー環境の要件をエッジします。</span><span class="sxs-lookup"><span data-stu-id="39efa-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="39efa-119">Skype のビジネス サーバーのエッジ ・ トポロジーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39efa-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="39efa-120">ビジネス サーバーの Skype でエッジ トランスポート サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="39efa-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="39efa-121">ビジネス サーバーの Skype で、エッジ配置を検証します。</span><span class="sxs-lookup"><span data-stu-id="39efa-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

