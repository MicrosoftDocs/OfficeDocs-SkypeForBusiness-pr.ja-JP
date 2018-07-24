---
title: エッジ サーバーの追加
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ設計にエッジ サーバーまたはエッジ サーバー プールを含めるには、エッジ サーバーまたはエッジ サーバー プールを展開するサーバーの完全修飾ドメイン名 (FQDN) を指定する必要があります。 エッジ サーバーまたはエッジ サーバー プールを含むトポロジを公開し、Skype をビジネスのサーバーのインストール、する前に作成した外部ユーザー アクセスを展開するためのすべての前提条件です。 これらの前提条件についての詳細は、展開に関するドキュメントの境界ネットワーク内のサーバーのインストールの準備を参照してください。
ms.openlocfilehash: 18f94e958c8a0e7b0859b598dd5b307dcb2d2411
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21068592"
---
# <a name="add-edge-server"></a><span data-ttu-id="28e1a-105">エッジ サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="28e1a-105">Add Edge Server</span></span>
 
<span data-ttu-id="28e1a-106">トポロジ設計にエッジ サーバーまたはエッジ サーバー プールを含めるには、エッジ サーバーまたはエッジ サーバー プールを展開するサーバーの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28e1a-106">To incorporate an Edge Server or an Edge Server pool into your topology design, you need to specify the fully qualified domain name (FQDN) of the server on which you want to deploy Edge Server or Edge Server pool.</span></span> <span data-ttu-id="28e1a-107">エッジ サーバーまたはエッジ サーバー プールを含むトポロジを公開し、Skype をビジネスのサーバーのインストール、する前に作成した外部ユーザー アクセスを展開するためのすべての前提条件です。</span><span class="sxs-lookup"><span data-stu-id="28e1a-107">Prior to publishing a topology that includes the Edge Server or Edge Server pool and installing Skype for Business Server, you should have completed all prerequisites for deploying external user access.</span></span> <span data-ttu-id="28e1a-108">これらの前提条件についての詳細は、展開に関するドキュメントの[境界ネットワーク内のサーバーのインストールの準備](http://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28e1a-108">For details about these prerequisites, see [Preparing for Installation of Servers in the Perimeter Network](http://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) in the Deployment documentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="28e1a-p103">指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。エッジ サーバーまたはエッジ サーバー プールとして展開するドメインに参加していないコンピューターの名前に、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28e1a-p103">The name you specify must be identical to the computer name configured on the server. By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN. Topology Builder uses FQDNs, not short names. You must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server or Edge Server pool that is not joined to a domain.</span></span> 
  
> [!TIP]
> <span data-ttu-id="28e1a-113">今後、エッジ サーバー プールを実装するように予定している場合は、[**複数のコンピューター プール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e1a-113">If you plan to implement an Edge Server pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="28e1a-114">プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="28e1a-114">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="28e1a-115">プールに後でより多くのコンピューターを追加する準備ができたら、トポロジ ビルダーはもう一度新しいプールのメンバーを定義、ビジネス サーバーの展開ウィザードは、Skype を使用して新しいエッジ サーバー プール メンバーを設定して、新しいトポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28e1a-115">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new Edge Server pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="28e1a-116">また、プールの該当するロード バランサー (DNS 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28e1a-116">You must also add the new pool member to the appropriate load balancers for the pool, DNS load balancing or hardware load balancers.</span></span> <span data-ttu-id="28e1a-117">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28e1a-117">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="28e1a-118">1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="28e1a-118">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="28e1a-119">適切なロード バランサーに新しいメンバー サーバーを必ず追加してください。</span><span class="sxs-lookup"><span data-stu-id="28e1a-119">Be sure that you are adding the new member server to the appropriate load balancer.</span></span> 
  
<span data-ttu-id="28e1a-120">初期トポロジの展開時や初期トポロジの展開後に、外部ユーザー アクセスのサポートを追加できます。</span><span class="sxs-lookup"><span data-stu-id="28e1a-120">You can add support for external user access when you deploy your initial topology, or after you deploy your initial topology.</span></span> <span data-ttu-id="28e1a-121">詳細については、エッジ サーバーを追加または既存のトポロジにエッジ サーバーのプールは、エッジ サーバーの展開に関するドキュメントで[エッジ トポロジの定義](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28e1a-121">For details about adding Edge Servers or Edge Server pool to an existing topology, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>
  

