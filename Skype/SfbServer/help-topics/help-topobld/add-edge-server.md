---
title: エッジ サーバーを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: トポロジ設計にエッジ サーバーまたはエッジ サーバー プールを含めるには、エッジ サーバーまたはエッジ サーバー プールを展開するサーバーの完全修飾ドメイン名 (FQDN) を指定する必要があります。 エッジ サーバーまたはエッジ サーバー プールを含むトポロジを発行し、Skype for Business Server をインストールする前に、外部ユーザー アクセスを展開するためのすべての前提条件を完了している必要があります。 これらの前提条件の詳細については、「展開」のドキュメントの「Preparing for Installation of Servers in the Perimeter Network」を参照してください。
ms.openlocfilehash: 49e4a8a9dd6bd9fcd09332f062cb7646c47dac03
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114263"
---
# <a name="add-edge-server"></a><span data-ttu-id="61d02-105">エッジ サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="61d02-105">Add Edge Server</span></span>

<span data-ttu-id="61d02-106">トポロジ設計にエッジ サーバーまたはエッジ サーバー プールを含めるには、エッジ サーバーまたはエッジ サーバー プールを展開するサーバーの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d02-106">To incorporate an Edge Server or an Edge Server pool into your topology design, you need to specify the fully qualified domain name (FQDN) of the server on which you want to deploy Edge Server or Edge Server pool.</span></span> <span data-ttu-id="61d02-107">エッジ サーバーまたはエッジ サーバー プールを含むトポロジを発行し、Skype for Business Server をインストールする前に、外部ユーザー アクセスを展開するためのすべての前提条件を完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d02-107">Prior to publishing a topology that includes the Edge Server or Edge Server pool and installing Skype for Business Server, you should have completed all prerequisites for deploying external user access.</span></span> <span data-ttu-id="61d02-108">これらの前提条件の詳細については、「展開」のドキュメントの「[Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d02-108">For details about these prerequisites, see [Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61d02-p103">指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。エッジ サーバーまたはエッジ サーバー プールとして展開するドメインに参加していないコンピューターの名前に、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d02-p103">The name you specify must be identical to the computer name configured on the server. By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN. Topology Builder uses FQDNs, not short names. You must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server or Edge Server pool that is not joined to a domain.</span></span>

> [!TIP]
> <span data-ttu-id="61d02-113">今後、エッジ サーバー プールを実装するように予定している場合は、[**複数コンピューターのプール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61d02-113">If you plan to implement an Edge Server pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="61d02-114">プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューターのプールを作成して、単一コンピューターにプールの FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="61d02-114">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="61d02-115">後でプールにコンピューターを追加する準備ができたら、トポロジ ビルダーで新しいプール メンバーを定義し、新しいトポロジを発行し、Skype for Business Server 展開ウィザードを使用して新しいエッジ サーバー プール メンバーをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d02-115">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new Edge Server pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="61d02-116">また、プールの該当するロード バランサー (DNS 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d02-116">You must also add the new pool member to the appropriate load balancers for the pool, DNS load balancing or hardware load balancers.</span></span> <span data-ttu-id="61d02-117">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d02-117">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="61d02-118">1 つのいエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="61d02-118">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="61d02-119">適切なロード バランサーに新しいメンバー サーバーを必ず追加してください。</span><span class="sxs-lookup"><span data-stu-id="61d02-119">Be sure that you are adding the new member server to the appropriate load balancer.</span></span>

<span data-ttu-id="61d02-120">初期トポロジの展開時や初期トポロジの展開後に、外部ユーザー アクセスのサポートを追加できます。</span><span class="sxs-lookup"><span data-stu-id="61d02-120">You can add support for external user access when you deploy your initial topology, or after you deploy your initial topology.</span></span> <span data-ttu-id="61d02-121">既存のトポロジへのエッジ サーバーまたはエッジ サーバー プールの追加の詳細については、「エッジ サーバーの展開」のドキュメントの「[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d02-121">For details about adding Edge Servers or Edge Server pool to an existing topology, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Edge Server Deployment documentation.</span></span>